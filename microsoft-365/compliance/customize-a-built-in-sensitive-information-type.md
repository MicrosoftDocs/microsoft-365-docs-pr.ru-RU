---
title: Настройка встроенных типов конфиденциальных данных
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Получите сведения о том, как создать настраиваемый тип конфиденциальной информации, который позволит пользоваться правилами, соответствующими потребностям вашей организации.
ms.openlocfilehash: 6e9fb0295f8958584878921c1fac362dc511be8f
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086616"
---
# <a name="customize-a-built-in-sensitive-information-type"></a>Настройка встроенных типов конфиденциальных данных

При поиске конфиденциальных данных в содержимом необходимо описать эти данные в *правиле*. Коллекция для защиты от потери данных (DLP) содержит правила для самых распространенных типов конфиденциальных данных, которые вы можете сразу использовать, включив их в политику. Иногда эти встроенные правила требуется скорректировать в соответствии с потребностями организации. Чтобы сделать это, нужно создать специальный тип конфиденциальных данных. В этой статье показано, как изменить XML-файл, содержащий существующую коллекцию правил, для обнаружения более широкого круга данных кредитных карт. 
  
Вы можете взять этот пример и применить его к другим встроенным типам конфиденциальной информации. Список типов конфиденциальной информации по умолчанию и определений XML см. в разделе [Определения объектов типа конфиденциальной информации](sensitive-information-type-entity-definitions.md). 
  
## <a name="export-the-xml-file-of-the-current-rules"></a>Экспорт XML-файла с текущими правилами

Чтобы экспортировать XML-файл, нужно [подключиться к Центру безопасности и соответствия требованиям через удаленный сеанс PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).
  
1. В PowerShell введите указанную ниже команду, чтобы отобразить правила организации на экране. Если вы не создавали собственные правила, вы увидите только стандартные, встроенные правила, отмеченные как "Пакет правил Майкрософт".

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

2. Сохраните правила организации в переменной, введя указанную ниже команду. Переменные можно затем легко использовать в том формате, который подходит для команд удаленного сеанса PowerShell.

   ```powershell    
   $ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
   ```
    
3. Создайте форматированный XML-файл со всеми этими данными, введя указанную ниже команду. (`Set-content` — часть командлета, которая записывает код XML в файл.) 

   ```powershell
   Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
   ```

   > [!IMPORTANT]
   > Укажите расположение, где фактически хранится пакет правил. `C:\custompath\` — это просто замещающий текст. 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a>Найдите правило, которое требуется изменить, в XML.

Указанные выше командлеты экспортировали всю *коллекцию правил*, состоящую из стандартных правил. После этого вам необходимо найти именно то правило для номера кредитной карты, которое нужно изменить. 
  
1. Откройте в текстовом редакторе XML-файл, экспорт которого показан в предыдущем разделе.
    
2. Прокрутите вниз до тега `<Rules>`, представляющего начало раздела с правилами DLP. Этот XML-файл содержит сведения для всей коллекции правил, поэтому необходимо пропустить другие данные в начале файла, чтобы добраться до правил.
    
3. Найдите *Func_credit_card* с определением правила для номера кредитной карты. В XML имена правил не могут содержать пробелы, поэтому они обычно заменяются подчеркиваниями. Кроме того, имена правил иногда сокращаются. Например, имя правила для номера социального страхования США — _SSN_. XML для правила номера кредитной карты будет выглядеть, как в следующем примере кода.
    
   ```xml
   <Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085"
          patternsProximity="300" recommendedConfidence="85">
         <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_credit_card" />
           <Any minMatches="1">
             <Match idRef="Keyword_cc_verification" />
             <Match idRef="Keyword_cc_name" />
             <Match idRef="Func_expiration_date" />
           </Any>
         </Pattern>
       </Entity>
   ```

После того как вы нашли определение правила для номера кредитной карты, вы можете изменить код XML правила в соответствии с вашими потребностями. Сведения об определениях XML см. в разделе [Глоссарий с терминами](#term-glossary) в конце этой статьи.
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a>Изменение XML и создание типа конфиденциальных данных

Во-первых, вам потребуется создать тип конфиденциальных данных, так как напрямую правила по умолчанию не могут быть изменены. Над специальными типами конфиденциальных данных можно выполнять различные действия, описанные в статье [Создание специальных типов конфиденциальных данных в PowerShell Центра безопасности и соответствия требованиям](create-a-custom-sensitive-information-type-in-scc-powershell.md). Для простоты в этом примере мы удалим подкрепляющее доказательство и добавим ключевые слова в правило номера кредитной карты.
  
Все XML-определения правил основаны на следующем шаблоне. Вам потребуется скопировать и вставить XML-определение правила номера кредитной карты в шаблон, изменить некоторые значения (обратите внимание на заполнители ". . ." в следующем примере) и загрузить измененный XML как новое правило, которое можно использовать в политиках.
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." /> 
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
   <!-- Paste the Credit Card Number rule definition here.--> 
      <LocalizedStrings>
         <Resource idRef=". . .">
           <Name default="true" langcode=" . . . ">. . .</Name>
           <Description default="true" langcode=". . ."> . . .</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

Вы получили код, который похож на следующий XML-фрагмент. Так как пакеты правил и правила идентифицируются по уникальным GUID, необходимо создать два GUID: один для пакета правил и один для замены GUID правила номера кредитной карты. GUID для кода объекта в следующем примере кода — это идентификатор для определения встроенного правила, который необходимо заменить на новый. GUID можно создать несколькими способами, например ввести в PowerShell команду **[guid]::NewGuid()**. 
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id="8aac8390-e99f-4487-8d16-7f0cdee8defc">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="8d34806e-cd65-4178-ba0e-5d7d712e5b66" />
    <Details defaultLangCode="en">
      <LocalizedDetails langcode="en">
        <PublisherName>Contoso Ltd.</PublisherName>
        <Name>Financial Information</Name>
        <Description>Modified versions of the Microsoft rule package</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f"
       patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
      <LocalizedStrings>
         <Resource idRef="db80b3da-0056-436e-b0ca-1f4cf7080d1f"> 
<!-- This is the GUID for the preceding Credit Card Number entity because the following text is for that Entity. -->
           <Name default="true" langcode="en-us">Modified Credit Card Number</Name>
           <Description default="true" langcode="en-us">Credit Card Number that looks for additional keywords, and another version of Credit Card Number that doesn't require keywords (but has a lower confidence level)</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a>Отмена поиска подкрепляющего доказательства для типа конфиденциальных данных

После создания типа конфиденциальных данных, который можно загрузить в Центр безопасности и соответствия требованиям, необходимо настроить правило. Измените его так, чтобы оно искало 16-значное число, передающее контрольную сумму, но не требовало дополнительных (подкрепляющих) свидетельств, например ключевых слов. Для этого потребуется удалить часть XML, которая ищет подкрепляющее свидетельство. Подкрепляющие свидетельства помогают сократить число ложных срабатываний. В этом случае они обычно представляют собой определенные ключевые слова или дату истечения срока действия рядом с номером кредитной карты. Если удалить такое свидетельство, также следует снизить уровень вероятности нахождения номера кредитной карты, уменьшив значение `confidenceLevel`, которое в этом примере равно 85.
  
```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a>Поиск ключевых слов, связанных с вашей организацией

Вам может потребоваться подкрепляющее доказательство, но с другими или дополнительными ключевыми словами. Кроме того, вы можете изменить область поиска этого доказательства. Можно так скорректировать `patternsProximity`, чтобы расширить или сузить окно поиска доказательства для числа из 16 цифр. Чтобы добавить собственные ключевые слова, необходимо задать список ключевых слов и указать его в правиле. Следующий XML-фрагмент добавляет ключевые слова "company card" (карта компании) и "Contoso card" (карта Contoso), чтобы любое сообщение с этими фразами в пределах 150 символов от номера кредитной карты определялось как номер кредитной карты.
  
```xml
<Rules>
<! -- Modify the patternsProximity to be "150" rather than "300." -->
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="150" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
<!-- Add the following XML, which references the keywords at the end of the XML sample. -->
          <Match idRef="My_Additional_Keywords" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
<!-- Add the following XML, and update the information inside the <Term> tags with the keywords that you want to detect. -->
    <Keyword id="My_Additional_Keywords">
      <Group matchStyle="word">
        <Term caseSensitive="false">company card</Term>
        <Term caseSensitive="false">Contoso card</Term>
      </Group>
    </Keyword>
```

## <a name="upload-your-rule"></a>Отправка правила

Чтобы отправить правило, выполните следующие действия.
  
1. Сохраните правило как XML-файл с кодировкой Юникод. Это важно, так как правило в другой кодировке работать не будет.
    
2. [Подключение к Центру безопасности и соответствия требованиям через удаленный сеанс PowerShell.](https://go.microsoft.com/fwlink/?linkid=799771)
    
3. В PowerShell введите указанную ниже команду.

   ```powershell    
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)
   ```
   
   > [!IMPORTANT]
   > Укажите расположение, где фактически хранится пакет правил. `C:\custompath\` — это просто замещающий текст. 
  
4. Для подтверждения введите Y и нажмите клавишу **ВВОД**.

5. Убедитесь, что новое правило добавлено, и проверьте его отображаемое имя, введя следующее:

   ```powershell
   Get-DlpSensitiveInformationType
   ```

Чтобы начать использовать новое правило для обнаружения конфиденциальных данных, необходимо добавить правило в политику DLP. Сведения о добавлении правила в политику см. в статье [Создание политики защиты от потери данных на основе шаблона](create-a-dlp-policy-from-a-template.md).
  
## <a name="term-glossary"></a>Глоссарий с терминами

Это определения терминов, которые используются в этой процедуре.
  
|**Термин**|**Определение**|
|:-----|:-----|
|Объект|Сущности  это то, что мы называем типами конфиденциальных данных, например номера кредитных карт. У каждой сущности есть уникальный идентификатор GUID. Если скопировать GUID и выполнить его поиск, вы найдете XML-определение правила и его локализованный перевод. Это определение также можно найти, выполнив поиск GUID для перевода, а затем выполнив поиск этого GUID.|
|Функции|В XML-файле указана ссылка на `Func_credit_card` — функцию в скомпилированном коде. Функции используются для выполнения сложных регулярных выражений и проверки соответствия контрольных сумм для встроенных правил. Так как все происходит в коде, некоторые переменные в XML-файле не отображаются.|
|IdMatch|Это идентификатор, с которым должен совпасть шаблон, например, номер кредитной карты.|
|Списки ключевых слов|XML-файл также ссылается на `keyword_cc_verification` и `keyword_cc_name`. Это списки ключевых слов, с которыми мы ищем совпадения в элементе `patternsProximity` сущности. Они в XML не отображаются.|
|Шаблон|Шаблон содержит список искомых типом конфиденциальных данных сведений. К ним относятся ключевые слова, регулярные выражения и внутренние функции, выполняющие различные задачи, такие как проверка контрольных сумм. Типы конфиденциальных данных могут использовать несколько шаблонов с уникальными уровнями вероятности. Это полезно при создании типа конфиденциальных данных, который возвращает высокую вероятность, если найдено подкрепляющее свидетельство, и низкий уровень вероятности, если свидетельств мало или они не найдены.|
|Параметр confidenceLevel шаблона|Это уровень вероятности совпадения, определенный модулем DLP. Он связан с совпадением с шаблоном, если заданы соответствующие требования. Это значение следует учитывать при использовании правил потока обработки почты (также называемых правилами транспорта) Exchange.|
|patternsProximity|Если мы нашли что-то похожее на шаблон номера кредитной карты, в `patternsProximity` — области возле этого номера — мы будем искать подкрепляющее доказательство.|
|recommendedConfidence|Это рекомендуемый для правила уровень вероятности. Он применяется к сущностям и соответствиям. В случае сущностей этот номер никогда не сравнивается со значением `confidenceLevel` для шаблона. Это просто дополнительный фактор, помогающий выбрать уровень вероятности. В случае соответствий значение `confidenceLevel` шаблона должно быть больше значения `recommendedConfidence`, чтобы можно было инициировать действие правила потока обработки почты. `recommendedConfidence` — это уровень вероятности по умолчанию, используемый в правилах потока обработки почты, при котором вызывается действие. При необходимости можно вручную изменить правило потока обработки почты так, чтобы вызывать в зависимости от уровня вероятности шаблона.|
   
## <a name="for-more-information"></a>Дополнительные сведения

- [Определения объектов типа конфиденциальной информации](sensitive-information-type-entity-definitions.md)
    
- [Создание пользовательского типа конфиденциальных данных](create-a-custom-sensitive-information-type.md)
    
- [Обзор политик защиты от потери данных](data-loss-prevention-policies.md)
