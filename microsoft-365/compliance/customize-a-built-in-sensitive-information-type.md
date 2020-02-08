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
description: При поиске конфиденциальных данных в содержимом необходимо описать эти данные в правиле. Коллекция для защиты от потери данных (DLP) содержит правила для самых распространенных типов конфиденциальных данных, которые вы можете сразу использовать, включив их в политику. Иногда эти встроенные правила требуется скорректировать в соответствии с потребностями организации. Чтобы сделать это, нужно создать специальный тип конфиденциальных данных. В этой статье показано, как изменить XML-файл, содержащий существующую коллекцию правил, для обнаружения более широкого круга данных кредитных карт.
ms.openlocfilehash: 4c61ab1a60b6259509d2928e22d31e447a996ec9
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595496"
---
# <a name="customize-a-built-in-sensitive-information-type"></a><span data-ttu-id="a6c0d-107">Настройка встроенных типов конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="a6c0d-107">Customize a built-in sensitive information type</span></span>

<span data-ttu-id="a6c0d-p102">При поиске конфиденциальных данных в содержимом необходимо описать эти данные в *правиле*. Коллекция для защиты от потери данных (DLP) содержит правила для самых распространенных типов конфиденциальных данных, которые вы можете сразу использовать, включив их в политику. Иногда эти встроенные правила требуется скорректировать в соответствии с потребностями организации. Чтобы сделать это, нужно создать специальный тип конфиденциальных данных. В этой статье показано, как изменить XML-файл, содержащий существующую коллекцию правил, для обнаружения более широкого круга данных кредитных карт.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p102">When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  . Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away. To use these rules, you have to include them in a policy. You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type. This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information.</span></span> 
  
<span data-ttu-id="a6c0d-p103">Вы можете использовать этот пример для изменения других встроенных типов конфиденциальных данных. Список типов конфиденциальных данных по умолчанию и определений XML см. в статье [Что позволяют искать типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p103">You can take this example and apply it to other built-in sensitive information types. For a list of default sensitive information types and XML definitions, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span> 
  
## <a name="export-the-xml-file-of-the-current-rules"></a><span data-ttu-id="a6c0d-115">Экспорт XML-файла с текущими правилами</span><span class="sxs-lookup"><span data-stu-id="a6c0d-115">Export the XML file of the current rules</span></span>

<span data-ttu-id="a6c0d-116">Чтобы экспортировать XML-файл, нужно [подключиться к Центру безопасности и соответствия требованиям через удаленный сеанс PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="a6c0d-116">To export the XML, you need to [connect to the Security and Compliance Center via Remote PowerShell.](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="a6c0d-p104">В PowerShell введите указанную ниже команду, чтобы отобразить правила организации на экране. Если вы не создавали собственные правила, вы увидите только стандартные, встроенные правила, отмеченные как "Пакет правил Майкрософт".</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p104">In the PowerShell, type the following to display your organization's rules on screen. If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."</span></span>

```powershell
Get-DlpSensitiveInformationTypeRulePackage
```    
2. <span data-ttu-id="a6c0d-p105">Сохраните правила организации в переменной, введя указанную ниже команду. Переменные можно затем легко использовать в том формате, который подходит для команд удаленного сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p105">Store your organization's rules in a variable by typing the following. Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.</span></span>

```powershell    
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
```
    
3. <span data-ttu-id="a6c0d-p106">Создайте форматированный XML-файл со всеми этими данными, введя указанную ниже команду. (`Set-content` — часть командлета, которая записывает код XML в файл.)</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p106">Make a formatted XML file with all that data by typing the following. ( `Set-content` is the part of the cmdlet that writes the XML to the file.)</span></span> 
    
```powershell
Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
```

> [!IMPORTANT]
> <span data-ttu-id="a6c0d-p107">Укажите расположение, где фактически хранится пакет правил. `C:\custompath\` — это просто замещающий текст.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p107">Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder.</span></span> 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a><span data-ttu-id="a6c0d-125">Найдите правило, которое требуется изменить, в XML.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-125">Find the rule that you want to modify in the XML</span></span>

<span data-ttu-id="a6c0d-p108">Указанные выше командлеты экспортировали всю *коллекцию правил*, состоящую из стандартных правил. После этого вам необходимо найти именно то правило для номера кредитной карты, которое нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p108">The cmdlets above exported the entire *rule collection*, which includes the default rules we provide. Next you'll need to look specifically for the Credit Card Number rule that you want to modify.</span></span> 
  
1. <span data-ttu-id="a6c0d-128">Откройте в текстовом редакторе XML-файл, экспорт которого показан в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-128">Use a text editor to open the XML file that you exported in the previous section.</span></span>
    
2. <span data-ttu-id="a6c0d-p109">Прокрутите вниз до тега `<Rules>`, представляющего начало раздела с правилами DLP. Этот XML-файл содержит сведения для всей коллекции правил, поэтому необходимо пропустить другие данные в начале файла, чтобы добраться до правил.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p109">Scroll down to the  `<Rules>` tag, which is the start of the section that contains the DLP rules. Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.</span></span>
    
3. <span data-ttu-id="a6c0d-p110">Найдите *Func_credit_card* с определением правила для номера кредитной карты. В XML имена правил не могут содержать пробелы, поэтому они обычно заменяются подчеркиваниями. Кроме того, имена правил иногда сокращаются. Например, имя правила для номера социального страхования США — "SSN". XML для правила номера кредитной карты будет выглядеть, как в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p110">Look for *Func_credit_card* to find the Credit Card Number rule definition. In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated. An example of this is the U.S. Social Security number rule, which is abbreviated "SSN." The Credit Card Number rule XML should look like the following code sample.</span></span>
    
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

<span data-ttu-id="a6c0d-p111">После того как вы нашли определение правила для номера кредитной карты, вы можете изменить код XML правила в соответствии с вашими потребностями. Сведения об определениях XML см. в разделе [Глоссарий с терминами](#term-glossary) в конце этой статьи.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p111">Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs. For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.</span></span>
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a><span data-ttu-id="a6c0d-137">Изменение XML и создание типа конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="a6c0d-137">Modify the XML and create a new sensitive information type</span></span>

<span data-ttu-id="a6c0d-p112">Во-первых, вам потребуется создать тип конфиденциальных данных, так как напрямую правила по умолчанию не могут быть изменены. Над специальными типами конфиденциальных данных можно выполнять различные действия, описанные в статье [Создание специальных типов конфиденциальных данных в PowerShell Центра безопасности и соответствия требованиям](create-a-custom-sensitive-information-type-in-scc-powershell.md). Для простоты в этом примере мы удалим подкрепляющее доказательство и добавим ключевые слова в правило номера кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p112">First, you need to create a new sensitive information type because you can't directly modify the default rules. You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md). For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.</span></span>
  
<span data-ttu-id="a6c0d-p113">Все XML-определения правил основаны на следующем шаблоне. Вам потребуется скопировать и вставить XML-определение правила номера кредитной карты в шаблон, изменить некоторые значения (обратите внимание на заполнители ". . ." в следующем примере) и загрузить измененный XML как новое правило, которое можно использовать в политиках.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p113">All XML rule definitions are built on the following general template. You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ". . ." placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.</span></span>
  
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

<span data-ttu-id="a6c0d-p114">Вы получили код, который похож на следующий XML-фрагмент. Так как пакеты правил и правила идентифицируются по уникальным GUID, необходимо создать два GUID: один для пакета правил и один для замены GUID правила номера кредитной карты. GUID для кода объекта в следующем примере кода — это идентификатор для определения встроенного правила, который необходимо заменить на новый. GUID можно создать несколькими способами, например ввести в PowerShell команду **[guid]::NewGuid()**.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p114">Now, you have something that looks similar to the following XML. Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule. The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one. There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span> 
  
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

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a><span data-ttu-id="a6c0d-150">Отмена поиска подкрепляющего доказательства для типа конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="a6c0d-150">Remove the corroborative evidence requirement from a sensitive information type</span></span>

<span data-ttu-id="a6c0d-151">После создания типа конфиденциальных данных, который можно загрузить в Центр безопасности и соответствия требованиям, необходимо настроить правило.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-151">Now that you have a new sensitive information type that you're able to upload to the Security &amp; Compliance Center, the next step is to make the rule more specific.</span></span> <span data-ttu-id="a6c0d-152">Измените его так, чтобы оно искало 16-значное число, передающее контрольную сумму, но не требовало дополнительных (подкрепляющих) свидетельств, например ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-152">Modify the rule so that it only looks for a 16-digit number that passes the checksum but doesn't require additional (corroborative) evidence, like keywords.</span></span> <span data-ttu-id="a6c0d-153">Для этого потребуется удалить часть XML, которая ищет подкрепляющее свидетельство.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-153">To do this, you need to remove the part of the XML that looks for corroborative evidence.</span></span> <span data-ttu-id="a6c0d-154">Подкрепляющие свидетельства помогают сократить число ложных срабатываний.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-154">Corroborative evidence is very helpful in reducing false positives.</span></span> <span data-ttu-id="a6c0d-155">В этом случае они обычно представляют собой определенные ключевые слова или дату истечения срока действия рядом с номером кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-155">In this case there are usually certain keywords or an expiration date near the credit card number.</span></span> <span data-ttu-id="a6c0d-156">Если удалить такое свидетельство, также следует снизить уровень вероятности нахождения номера кредитной карты, уменьшив значение `confidenceLevel`, которое в этом примере равно 85.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-156">If you remove that evidence, you should also adjust how confident you are that you found a credit card number by lowering the  `confidenceLevel`, which is 85 in the example.</span></span>
  
```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a><span data-ttu-id="a6c0d-157">Поиск ключевых слов, связанных с вашей организацией</span><span class="sxs-lookup"><span data-stu-id="a6c0d-157">Look for keywords that are specific to your organization</span></span>

<span data-ttu-id="a6c0d-p116">Вам может потребоваться подкрепляющее доказательство, но с другими или дополнительными ключевыми словами. Кроме того, вы можете изменить область поиска этого доказательства. Можно так скорректировать `patternsProximity`, чтобы расширить или сузить окно поиска доказательства для числа из 16 цифр. Чтобы добавить собственные ключевые слова, необходимо задать список ключевых слов и указать его в правиле. Следующий XML-фрагмент добавляет ключевые слова "company card" (карта компании) и "Contoso card" (карта Contoso), чтобы любое сообщение с этими фразами в пределах 150 символов от номера кредитной карты определялось как номер кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p116">You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence. You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number. To add your own keywords, you need to define a keyword list and reference it within your rule. The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.</span></span>
  
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

## <a name="upload-your-rule"></a><span data-ttu-id="a6c0d-162">Отправка правила</span><span class="sxs-lookup"><span data-stu-id="a6c0d-162">Upload your rule</span></span>

<span data-ttu-id="a6c0d-163">Чтобы отправить правило, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-163">To upload your rule, you need to do the following.</span></span>
  
1. <span data-ttu-id="a6c0d-p117">Сохраните правило как XML-файл с кодировкой Юникод. Это важно, так как правило в другой кодировке работать не будет.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p117">Save it as an .xml file with Unicode encoding. This is important because the rule won't work if the file is saved with a different encoding.</span></span>
    
2. [<span data-ttu-id="a6c0d-166">Подключение к Центру безопасности и соответствия требованиям через удаленный сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-166">Connect to the Security and Compliance Center via Remote PowerShell.</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
3. <span data-ttu-id="a6c0d-167">В PowerShell введите указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-167">In the PowerShell, type the following.</span></span>

```powershell    
New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte).
```
> [!IMPORTANT]
> <span data-ttu-id="a6c0d-p118">Укажите расположение, где фактически хранится пакет правил. `C:\custompath\` — это просто замещающий текст.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p118">Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder.</span></span> 
  
4. <span data-ttu-id="a6c0d-170">Для подтверждения введите Y и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-170">To confirm, type Y, and then press **Enter**.</span></span>
5. <span data-ttu-id="a6c0d-171">Убедитесь, что новое правило добавлено, и проверьте его отображаемое имя, введя следующее:</span><span class="sxs-lookup"><span data-stu-id="a6c0d-171">Verify that your new rule was uploaded and it's display name by typing:</span></span>

```powershell
Get-DlpSensitiveInformationType
```

<span data-ttu-id="a6c0d-p119">Чтобы начать использовать новое правило для обнаружения конфиденциальных данных, необходимо добавить правило в политику DLP. Сведения о добавлении правила в политику см. в статье [Создание политики защиты от потери данных на основе шаблона](create-a-dlp-policy-from-a-template.md).</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p119">To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy. To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).</span></span>
  
## <a name="term-glossary"></a><span data-ttu-id="a6c0d-174">Глоссарий с терминами</span><span class="sxs-lookup"><span data-stu-id="a6c0d-174">Term glossary</span></span>

<span data-ttu-id="a6c0d-175">Это определения терминов, которые используются в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-175">These are the definitions for the terms you encountered during this procedure.</span></span>
  
|<span data-ttu-id="a6c0d-176">**Термин**</span><span class="sxs-lookup"><span data-stu-id="a6c0d-176">**Term**</span></span>|<span data-ttu-id="a6c0d-177">**Определение**</span><span class="sxs-lookup"><span data-stu-id="a6c0d-177">**Definition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a6c0d-178">Объект</span><span class="sxs-lookup"><span data-stu-id="a6c0d-178">Entity</span></span>|<span data-ttu-id="a6c0d-p120">Сущности  это то, что мы называем типами конфиденциальных данных, например номера кредитных карт. У каждой сущности есть уникальный идентификатор GUID. Если скопировать GUID и выполнить его поиск, вы найдете XML-определение правила и его локализованный перевод. Это определение также можно найти, выполнив поиск GUID для перевода, а затем выполнив поиск этого GUID.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p120">Entities are what we call sensitive information types, such as credit card numbers. Each entity has a unique GUID as its ID. If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule. You can also find this definition by locating the GUID for the translation and then searching for that GUID.</span></span>|
|<span data-ttu-id="a6c0d-183">Функции</span><span class="sxs-lookup"><span data-stu-id="a6c0d-183">Functions</span></span>|<span data-ttu-id="a6c0d-p121">В XML-файле указана ссылка на `Func_credit_card` — функцию в скомпилированном коде. Функции используются для выполнения сложных регулярных выражений и проверки соответствия контрольных сумм для встроенных правил. Так как все происходит в коде, некоторые переменные в XML-файле не отображаются.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p121">The XML file references  `Func_credit_card`, which is a function in compiled code. Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.</span></span>|
|<span data-ttu-id="a6c0d-186">IdMatch</span><span class="sxs-lookup"><span data-stu-id="a6c0d-186">IdMatch</span></span>|<span data-ttu-id="a6c0d-187">Это идентификатор, с которым должен совпасть шаблон, например, номер кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-187">This is the identifier that the pattern is to trying to match—for example, a credit card number.</span></span>|
|<span data-ttu-id="a6c0d-188">Списки ключевых слов</span><span class="sxs-lookup"><span data-stu-id="a6c0d-188">Keyword lists</span></span>|<span data-ttu-id="a6c0d-p122">XML-файл также ссылается на `keyword_cc_verification` и `keyword_cc_name`. Это списки ключевых слов, с которыми мы ищем совпадения в элементе `patternsProximity` сущности. Они в XML не отображаются.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p122">The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity. These aren't currently displayed in the XML.</span></span>|
|<span data-ttu-id="a6c0d-191">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a6c0d-191">Pattern</span></span>|<span data-ttu-id="a6c0d-192">Шаблон содержит список искомых типом конфиденциальных данных сведений.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-192">The pattern contains the list of what the sensitive type is looking for.</span></span> <span data-ttu-id="a6c0d-193">К ним относятся ключевые слова, регулярные выражения и внутренние функции, выполняющие различные задачи, такие как проверка контрольных сумм.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-193">This includes keywords, regexes, and internal functions, which perform tasks like verifying checksums.</span></span> <span data-ttu-id="a6c0d-194">Типы конфиденциальных данных могут использовать несколько шаблонов с уникальными уровнями вероятности.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-194">Sensitive information types can have multiple patterns with unique confidences.</span></span> <span data-ttu-id="a6c0d-195">Это полезно при создании типа конфиденциальных данных, который возвращает высокую вероятность, если найдено подкрепляющее свидетельство, и низкий уровень вероятности, если свидетельств мало или они не найдены.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-195">This is useful when creating a sensitive information type that returns a high confidence if corroborative evidence is found and a lower confidence if little or no corroborative evidence is found.</span></span>|
|<span data-ttu-id="a6c0d-196">Параметр confidenceLevel шаблона</span><span class="sxs-lookup"><span data-stu-id="a6c0d-196">Pattern confidenceLevel</span></span>|<span data-ttu-id="a6c0d-p124">Это уровень вероятности совпадения, определенный модулем DLP. Он связан с совпадением с шаблоном, если заданы соответствующие требования. Это значение следует учитывать при использовании правил потока обработки почты (также называемых правилами транспорта) Exchange.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p124">This is the level of confidence that the DLP engine found a match. This level of confidence is associated with a match for the pattern if the pattern's requirements are met. This is the confidence measure you should consider when using Exchange mail flow rules (also known as transport rules).</span></span>|
|<span data-ttu-id="a6c0d-200">patternsProximity</span><span class="sxs-lookup"><span data-stu-id="a6c0d-200">patternsProximity</span></span>|<span data-ttu-id="a6c0d-201">Если мы нашли что-то похожее на шаблон номера кредитной карты, в `patternsProximity` — области возле этого номера — мы будем искать подкрепляющее доказательство.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-201">When we find what looks like a credit card number pattern,  `patternsProximity` is the proximity around that number where we'll look for corroborative evidence.</span></span>|
|<span data-ttu-id="a6c0d-202">recommendedConfidence</span><span class="sxs-lookup"><span data-stu-id="a6c0d-202">recommendedConfidence</span></span>|<span data-ttu-id="a6c0d-p125">Это рекомендуемый для правила уровень вероятности. Он применяется к сущностям и соответствиям. В случае сущностей этот номер никогда не сравнивается со значением `confidenceLevel` для шаблона. Это просто дополнительный фактор, помогающий выбрать уровень вероятности. В случае соответствий значение `confidenceLevel` шаблона должно быть больше значения `recommendedConfidence`, чтобы можно было инициировать действие правила потока обработки почты. `recommendedConfidence` — это уровень вероятности по умолчанию, используемый в правилах потока обработки почты, при котором вызывается действие. При необходимости можно вручную изменить правило потока обработки почты так, чтобы вызывать в зависимости от уровня вероятности шаблона.</span><span class="sxs-lookup"><span data-stu-id="a6c0d-p125">This is the confidence level we recommend for this rule. The recommended confidence applies to entities and affinities. For entities, this number is never evaluated against the  `confidenceLevel` for the pattern. It's merely a suggestion to help you choose a confidence level if you want to apply one. For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for a mail flow rule action to be invoked. The  `recommendedConfidence` is the default confidence level used in mail flow rules that invokes an action. If you want, you can manually change the mail flow rule to be invoked based off the pattern's confidence level, instead.</span></span>|
   
## <a name="for-more-information"></a><span data-ttu-id="a6c0d-210">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a6c0d-210">For more information</span></span>

- [<span data-ttu-id="a6c0d-211">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="a6c0d-211">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    
- [<span data-ttu-id="a6c0d-212">Создание специальных типов конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="a6c0d-212">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    
- [<span data-ttu-id="a6c0d-213">Обзор политик защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="a6c0d-213">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
