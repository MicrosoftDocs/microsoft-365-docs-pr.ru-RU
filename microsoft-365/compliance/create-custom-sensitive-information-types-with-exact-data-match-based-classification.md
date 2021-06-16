---
title: Создание пользовательских типов конфиденциальной информации с помощью точного совпадения данных
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Узнайте о создании пользовательских типов конфиденциальной информации с помощью классификации на основе точного совпадения данных.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 05d5889ba690bdf61fd51044b3c059f1476342af
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964660"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a>Создание пользовательских типов конфиденциальной информации с помощью классификации на основе точного совпадения данных



[Пользовательские типы конфиденциальной информации](sensitive-information-type-learn-about.md) используются для определения конфиденциальных элементов, чтобы предотвратить непреднамеренное или неприемлемое предоставление к ним общего доступа. Настраиваемый тип конфиденциальной информации (SIT) определяется на основе:

- шаблоны;
- ключевое слово, например *сотрудник*, *бейдж* или *идентификатор*;
- близкое расположение символов, свидетельствующее об определенном шаблоне;
- доверительные уровни.

 Такие пользовательские типы конфиденциальной информации соответствуют бизнес-требованиям большинства организаций.

Но что если вам нужен пользовательский тип конфиденциальной информации (SIT), использующий точные значения данных, а не ищущий сопоставления на основе универсальных шаблонов? С помощью классификации на основе точного совпадения данных (EDM) вы можете создать пользовательский тип конфиденциальной информации с такими характеристиками:

- динамика и простое обновление;
- дополнительные возможности масштабирования;
- снижает число ошибочно положительных результатов;
- поддерживает структурированные конфиденциальные данные;
- более безопасная обработка конфиденциальной информации;
- использование с несколькими облачными службами Майкрософт.

![Классификация на основе EDM](../media/EDMClassification.png)

Классификация на основе EDM позволяет создавать пользовательские типы конфиденциальной информации, ссылающиеся на точные значения в базе данных конфиденциальной информации. Базу данных можно обновлять ежедневно, и она может содержать до 100 миллионов строк данных. Таким образом, ваши пользовательские типы конфиденциальной информации остаются актуальными и применимыми при смене сотрудников, пациентов или клиентов, а также при изменении записей. Вы также можете использовать классификацию на основе EDM для политик, таких как [политики защиты от потери данных](dlp-learn-about-dlp.md) или [политики файлов Microsoft Cloud App Security](/cloud-app-security/data-protection-policies).

> [!NOTE]
> Служба защиты информации Microsoft 365 поддерживает в предварительной версии языки с двухбайтовой кодировкой:
> - Китайский (упрощенное письмо)
> - Китайский (традиционное письмо)
> - Корейский
> - Японский
> 
> Эта поддержка доступна для конфиденциальных типов информации. Дополнительные сведения см. в статье [Заметки о выпуске: поддержка защиты информации для наборов двухбайтовых символов (предварительная версия)](mip-dbcs-relnotes.md).
 

## <a name="required-licenses-and-permissions"></a>Обязательные лицензии и разрешения

Для выполнения задач, описанных в данной статье, вы должны быть глобальным администратором, администратором соответствия требованиям или администратором Exchange Online. Дополнительные сведения о разрешениях DLP см. в разделе [Разрешения](data-loss-prevention-policies.md#permissions).

Классификация на основе EDM включена в следующие подписки:

- Office 365 E5
- Microsoft 365 E5
- Соответствие требованиям Microsoft 365 E5
- Защита информации и управление данными в Microsoft E5/A5

## <a name="portal-links-for-your-subscription"></a>Ссылки на портал для вашей подписки


|Портал  |Интернет/GCC  |GCC High  |DOD  |
|---------|---------|---------|---------|
|Office SCC     |  protection.office.com       |scc.office365.us         |scc.protection.apps.mil |
|Центр безопасности Microsoft 365     |security.microsoft.com         |security.microsoft.us         |security.apps.mil|
|Центр соответствия требованиям Microsoft 365     |compliance.microsoft.com         |compliance.microsoft.us         |compliance.apps.mil|


## <a name="the-work-flow-at-a-glance"></a>Обзор рабочего процесса

|Этап  |Требуемые параметры  |
|---------|---------|
|[Часть 1. Настройка классификации на основе EDM](#part-1-set-up-edm-based-classification)<br/><br/>(При необходимости)<br/>- [Изменение схемы базы данных](#editing-the-schema-for-edm-based-classification) <br/>- [Удаление схемы](#removing-the-schema-for-edm-based-classification) |– Доступ для чтения конфиденциальных данных<br/>– Схема базы данных в формате XML (доступен пример)<br/>– Пакет правил в формате XML (доступен пример)<br/>– Разрешения администратора на доступ к Центру безопасности и соответствия требованиям (с помощью PowerShell) |
|[Часть 2. Хеширование и отправка конфиденциальных данных](#part-2-hash-and-upload-the-sensitive-data)<br/><br/>(При необходимости)<br/>[Обновление данных](#refreshing-your-sensitive-information-database) |– Настраиваемая группа безопасности и учетная запись пользователя<br/>– Доступ локального администратора к компьютеру с агентом отправки EDM<br/>– Доступ для чтения конфиденциальных данных<br/>– Процесс и расписание для обновления данных|
|[Часть 3. Использование классификации на основе EDM с помощью облачных служб Майкрософт](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |– Подписка на Microsoft 365 с DLP<br/>– Включенная функция классификации на основе EDM |

### <a name="part-1-set-up-edm-based-classification"></a>Часть 1. Настройка классификации на основе EDM

Установка и настройка классификации на основе EDM включает:

1. [Сохранение конфиденциальных данных в формате .csv или tsv](#save-sensitive-data-in-csv-or-tsv-format)
2. [Определение схемы для базы данных конфиденциальной информации](#define-the-schema-for-your-database-of-sensitive-information)
3. [Создание пакета правил](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-or-tsv-format"></a>Сохранение конфиденциальных данных в формате .csv или tsv

1. Определите конфиденциальную информацию, которую нужно использовать. Экспорт данных в приложение, например Microsoft Excel, и сохранение файла в текстовом файле. Файл можно сохранить в формате .csv (разделенные запятой), tsv (значения, разделенные вкладками) или в формате |. Формат .tsv рекомендуется в тех случаях, когда значения данных могут включать запятые, например уличные адреса.
Файл данных может содержать:
      - до 100 миллионов строк конфиденциальных данных;
      - до 32 столбцов (полей) на источник данных;
      - до 5 столбцов (полей), отмеченных как доступные для поиска.

2. Структурировать конфиденциальные данные в .csv или tsv-файле таким образом, чтобы первая строка включала имена полей, используемых для классификации на основе EDM. В файле могут быть имена полей, такие как "ssn", "birthdate", "firstname", "lastname". В названиях заголовков столбцов не должно быть пробелов и символов подчеркивания. Например, используемый в этой статье пример CSV-файла называется *PatientRecords.csv*, а его столбцы включают *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN* и другие.

3. Обратите внимание на формат полей конфиденциальных данных. В частности, поля, которые могут содержать запятые в их контенте, например, уличный адрес, содержащий значение "Seattle,WA", при размыве при выборе формата .csv будут рассматриваться как два отдельных поля. Чтобы избежать этого, используйте формат .tsv или окружили запятую, содержащую значения двойными кавычками в таблице конфиденциальных данных. Если запятая, содержащая значения, также содержит пробелы, необходимо создать настраиваемый sit, соответствующий соответствующему формату. Например, sit, который обнаруживает много словую строку с запятой и пробелами в ней.

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a>Определение схемы для базы данных конфиденциальной информации

Если по деловым или техническим причинам вы не используете PowerShell или командную строку для создания схемы и шаблона типа конфиденциальной информации EDM (пакет правил), используйте для их создания [схему точного соответствия данных и мастер типов конфиденциальной информации](sit-edm-wizard.md). После создания схемы и шаблона типа конфиденциальной информации EDM, вернитесь, чтобы выполнить все шаги, необходимые для того, чтобы сделать ваш тип конфиденциальной информации на основе EDM доступным для использования.

> [!NOTE]
> Мастер схемы точного соответствия данных и типа конфиденциальной информации доступен только для облаков World Wide и GCC.

1. Определите схему для базы данных конфиденциальной информации в формате XML (как в примере ниже). Назовите этот файл схемы **edm.xml** и настройте его так, чтобы для каждого столбца в базе данных была строка, использующая синтаксис: 

      `\<Field name="" searchable=""/\>`.

      - Используйте имена столбцов для значений *Field name*.
      - Используйте параметр *searchable="true"* для 5 полей, которые должны поддерживать поиск. По крайней мере одно поле должно поддерживать поиск.

      Например, следующий XML-файл определяет схему для базы данных записей пациентов с пятью полями, для которых указывается возможность поиска: *PatientID*, *MRN*, *SSN*, *Phone* и *DOB*.

      (Вы можете скопировать, изменить и использовать наш пример.)

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
                  <Field name="MRN" searchable="true" />
                  <Field name="FirstName" />
                  <Field name="LastName" />
                  <Field name="SSN" searchable="true" />
                  <Field name="Phone" searchable="true" />
                  <Field name="DOB" searchable="true" />
                  <Field name="Gender" />
                  <Field name="Address" />
            </DataStore>
      </EdmSchema>
      ```

##### <a name="configurable-match-using-the-caseinsensitive-and-ignoreddelimiters-fields"></a>Настраиваемое совпадение с использованием полей caseInsensitive и ignoredDelimiters 

В приведенном выше примере XML используются поля `caseInsensitive` и `ignoredDelimiters`. 

При включении поля ***caseInsensitive** _, для которого задано значение `true` в определении схемы, EDM не будет исключать элемент на основе различий для поля `PatientID`. Так, EDM будет рассматривать `PatientID` _ *FOO-1234** и **fOo-1234** как идентичные.

При включении поля **ignoredDelimiters** _ с поддерживаемыми символами EDM игнорирует эти символы в `PatientID`. Так, EDM будет рассматривать `PatientID` _ *FOO-1234** и `PatientID` **FOO#1234** как идентичные. Флаг `ignoredDelimiters` поддерживает любые не буквенно-цифровые символы. Вот несколько примеров:
- \.
- \-
- \/
- \_
- \*
- \^
- \#
- \!
- \?
- \[
- \]
- \{
- \}
- \\
- \~
- \; 

Флаг `ignoredDelimiters` не поддерживает:
- символы от 0 до 9
- От А до Я
- от a до z
- \"
- \,

В этом примере, где используются оба `caseInsensitive` и `ignoredDelimiters`, EDM будет рассматривать **FOO-1234** и **fOo#1234** как идентичные и классифицировать элемент как тип конфиденциальной информации из карты пациента. 

4. Подключитесь к Центру безопасности и соответствия требованиям, используя процедуры, описанные в статье [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](/powershell/exchange/connect-to-scc-powershell).

5. Чтобы добавить схему базы данных, выполните по отдельности указанные ниже командлеты.

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      Появится запрос на подтверждение, показанный ниже.

      > Подтверждение
      >
      > Вы действительно хотите выполнить это действие?
      >
      > Будет импортирована новая схема модели EDM для хранилища данных "patientrecords".
      >
      > \[Y\] Да \[A\] Да для всех \[N\] Нет \[L\] Нет для всех \[?\] Справка (значение по умолчанию "Y"):

> [!TIP]
> Чтобы изменения вносились без запроса подтверждения, используйте вместо командлета, указанного в действии 5, следующий: New-DlpEdmSchema -FileData $edmSchemaXml

> [!NOTE]
> Обновление EDMSchema с дополнениями может занять от 10 до 60 минут. Перед выполнением действий, в которых используется дополнение, необходимо выполнить обновление.

#### <a name="set-up-a-rule-package"></a>Настройка пакета правил

1. Создайте пакет правил в формате XML (в кодировке Юникод), как показано в примере ниже. (Вы можете скопировать, изменить и использовать наш пример.)

      При настройках пакета правил убедитесь, что вы правильно ссылались на .csv или файл tsv **иedm.xml** файл. Вы можете скопировать, изменить и использовать наш пример. В этом примере XML для создания типа конфиденциальной информации EDM должны быть настроены перечисленные ниже поля.

      - **Идентификаторы RulePack и ExactMatch**. Используйте командлет [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) для создания GUID.

      - **Datastore**. В этом поле указывается, какое хранилище данных подстановки EDM будет использоваться. Вы указываете имя источника данных для настроенной схемы EDM.

      - **idMatch**. Это поле указывает на основной элемент EDM.
        - Matches. Указывает поле, которое будет использоваться при точном поиске. Вы указываете имя поля для поиска в схеме EDM для DataStore.
        - Classification. В этом поле указывается соответствие типа конфиденциальной информации, которое активирует поиск EDM. Вы можете указать имя или идентификатор GUID имеющегося встроенного или настраиваемого типа конфиденциальной информации. Следует учитывать, что любая строка, соответствующая указанному типу конфиденциальной информации, будет хэшироваться и сравниваться с каждым элементом таблицы конфиденциальной информации. Чтобы избежать проблем с производительностью, при использовании настраиваемого типа конфиденциальной информации в качестве элемента классификации в EDM избегайте использования типов, которым будет соответствовать значительная часть содержимого (например, "любая цифра" или "любое слово из пяти букв"), добавляя вспомогательные ключевые слова или включая элементы форматирования в определение настраиваемого типа конфиденциальной информации. 

      - **Match**. В этом поле указываются дополнительные свидетельства, находящиеся близко к idMatch.
        - Matches. Вы указываете имя поля для поиска в схеме EDM для DataStore.
      - **Resource**. В этом разделе указываются имя и описание типа конфиденциальной информации в нескольких языковых средах.
        - idRef. Укажите GUID для идентификатора ExactMatch.
        - Имена & описания: настройте в соответствии с требованиями.

      ```xml
      <RulePackage xmlns="http://schemas.microsoft.com/office/2018/edm">
        <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
          <Version build="0" major="2" minor="0" revision="0" />
          <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
          <Details defaultLangCode="en-us">
            <LocalizedDetails langcode="en-us">
              <PublisherName>IP DLP</PublisherName>
              <Name>Health Care EDM Rulepack</Name>
              <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
            </LocalizedDetails>
          </Details>
        </RulePack>
        <Rules>
          <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
            <Pattern confidenceLevel="65">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
            </Pattern>
            <Pattern confidenceLevel="75">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
              <Any minMatches ="3" maxMatches ="6">
                <match matches="PatientID" />
                <match matches="MRN"/>
                <match matches="FirstName"/>
                <match matches="LastName"/>
                <match matches="Phone"/>
                <match matches="DOB"/>
              </Any>
            </Pattern>
          </ExactMatch>
          <LocalizedStrings>
            <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
              <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
              <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
            </Resource>
          </LocalizedStrings>
        </Rules>
      </RulePackage>
      ```

2. Отправьте пакет правил, выполнив по отдельности указанные ниже командлеты PowerShell.

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

На этом этапе вы настроили классификацию на основе EDM. На следующем этапе необходимо хешировать конфиденциальные данные, а затем отправить хеши на индексацию.

Хотим еще раз напомнить, что схема PatientRecords определяет как доступные для поиска пять полей: *PatientID*, *MRN*, *SSN*, *Phone* и *DOB*. Наш пакет правил, созданный для примера, включает эти пять полей и ссылается на файл схемы базы данных (**edm.xml**), предусматривая один элемент *ExactMatch* для каждого доступного для поиска поля. Рассмотрим следующий элемент ExactMatch:

```xml
<ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="100">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </ExactMatch>
```

В этом примере обратите внимание, что:

- Имя хранилища данных dataStore ссылается на ранее созданный файл CSV: **dataStore = "PatientRecords"**.

- Значение idMatch ссылается на доступное для поиска поле, которое указано в файле схемы базы данных: **idMatch matches = "SSN"**.

- Значение классификации ссылается на существующий или пользовательский тип конфиденциальной информации: **classification = "U.S. Social Security Number (SSN)"**. (В этом случае используется существующий тип конфиденциальной информации, содержащий номер социального страхования США.)

> [!NOTE]
> Обновление EDMSchema с дополнениями может занять от 10 до 60 минут. Перед выполнением действий, в которых используется дополнение, необходимо выполнить обновление.
 
После того, как вы импортировали пакет правил с типом конфиденциальной информации EDM и импортировали таблицу конфиденциальных данных, вы можете протестировать созданный тип с помощью функции **Test** в мастере EDM в Центре соответствия требованиям. Инструкции по использованию этой функции см. в статье [Использование мастера для схемы точного соответствия данных и типа конфиденциальной информации](sit-edm-wizard.md).

#### <a name="editing-the-schema-for-edm-based-classification"></a>Редактирование схемы для классификации на основе EDM

Если нужно внести изменения в файл **edm.xml**, например изменить поля, используемые для классификации на основе EDM, выполните указанные ниже действия.

> [!TIP]
> Схему EDM и файл данных можно изменить, чтобы воспользоваться **настраиваемым совпадением**. При настройке EDM будет игнорировать различия в регистре и некоторые разделители при оценке элемента. Это упрощает определение схемы XML и файлов конфиденциальных данных. Дополнительные сведения см. в статье [Изменение схемы точного соответствия данных для использования настраиваемого совпадения](sit-modify-edm-schema-configurable-match.md).

1. Внесите изменения в файл **edm.xml** (он рассматривается в разделе [Определение схемы](#define-the-schema-for-your-database-of-sensitive-information) в этой статье).

2. Подключитесь к Центру безопасности и соответствия требованиям, используя процедуры, описанные в статье [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](/powershell/exchange/connect-to-scc-powershell).

3. Чтобы обновить схему базы данных, выполните по отдельности указанные ниже командлеты.

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      Появится запрос на подтверждение, показанный ниже.

      > Подтверждение
      >
      > Вы действительно хотите выполнить это действие?
      >
      > Схема модели EDM для хранилища данных "patientrecords" будет обновлена.
      >
      > \[Y\] Да \[A\] Да для всех \[N\] Нет \[L\] Нет для всех \[?\] Справка (значение по умолчанию "Y"):

      > [!TIP]
      > Чтобы изменения вносились без запроса подтверждения, используйте вместо командлета, указанного в действии 3, следующий: Set-DlpEdmSchema -FileData $edmSchemaXml

      > [!NOTE]
      > Обновление EDMSchema с дополнениями может занять от 10 до 60 минут. Перед выполнением действий, в которых используется дополнение, необходимо выполнить обновление.

#### <a name="removing-the-schema-for-edm-based-classification"></a>Удаление схемы для классификации на основе EDM

(При необходимости.) Чтобы удалить схему, используемую для классификации на основе EDM, выполните указанные ниже действия.

1. Подключитесь к Центру безопасности и соответствия требованиям, используя процедуры, описанные в статье [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](/powershell/exchange/connect-to-scc-powershell).

2. Выполните следующие командлеты PowerShell, заменив имя хранилища данных "patient records" на имя удаляемого хранилища.

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      Появится запрос на подтверждение:

      > Подтверждение
      >
      > Вы действительно хотите выполнить это действие?
      >
      > Схема модели EDM для хранилища данных "patientrecords" будет удалена.
      >
      > \[Y\] Да \[A\] Да для всех \[N\] Нет \[L\] Нет для всех \[?\] Справка (значение по умолчанию "Y"):

      > [!TIP]
      >  Чтобы изменения вносились без запроса подтверждения, используйте вместо командлета, указанного в действии 2, следующий: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false

### <a name="part-2-hash-and-upload-the-sensitive-data"></a>Часть 2. Хеширование и отправка конфиденциальных данных

На этом этапе выполняется настройка пользовательской группы безопасности и учетной записи пользователя, а также настройка агента отправки EDM. Затем применяется средство для хеширования конфиденциальных данных с использованием значения соли и выполняется их отправка.

Хеширование и отправку можно выполнить на одном компьютере, или вы можете отделить этап хеширования от этапа отправки для дополнительной безопасности.

Если вы хотите выполнить хеширование и отправку с одного компьютера, нужно делать это на компьютере, который может напрямую подключаться к вашему клиенту Microsoft 365. Для этого требуется, чтобы ваши файлы с конфиденциальными данными в виде обычного текста находились на этом компьютере для хеширования.

Если вы не хотите предоставлять свой файл с конфиденциальными данными в виде обычного текста, вы можете хешировать его на компьютере в безопасном расположении, а затем скопировать хеш-файл и файл соли на компьютер, который может напрямую подключаться к клиенту Microsoft 365 для отправки. В этом случае вам потребуется установить EDMUploadAgent на обоих компьютерах.

> [!IMPORTANT]
> Если вы использовали мастер схемы точного соответствия данных и типов конфиденциальной информации для создания схемы и файлов шаблонов, вам ***требуется*** скачать схему для этой процедуры.

> [!NOTE]
> Если ваша организация настроит ключ клиента Microsoft 365 на уровне [клиента,](customer-key-overview.md)точные данные будут автоматически использовать его функции шифрования. Эта возможность доступна только лицензированным клиентам E5 в коммерческом облаке.

#### <a name="prerequisites"></a>Предварительные условия

- рабочая или учебная учетная запись для Microsoft 365, которая будет добавлена в группу безопасности **EDM\_DataUploaders**;
- компьютер с Windows 10 или Windows Server 2016 с .NET версии 4.6.2 для запуска EDMUploadAgent;
- каталог на компьютере отправки для следующего:
    -  EDMUploadAgent
    - конфиденциальный файл элемента в .csv или формате tsv, **PatientRecords.csv** в наших примерах
    -  выходной хеш-файл и файл соли;
    - имя хранилища данных из файла **edm.xml**. В этом примере: `PatientRecords`.
- Если вы использовали [мастер схемы точного соответствия данных и типа конфиденциальной информации](sit-edm-wizard.md), вам ***необходимо*** загрузить его

#### <a name="set-up-the-security-group-and-user-account"></a>Настройка группы безопасности и учетной записи пользователя

1. Как глобальный администратор перейдите в центр администрирования с помощью соответствующей [ссылки для вашей подписки](#portal-links-for-your-subscription) и [создайте группу безопасности](/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) с именем **EDM\_DataUploaders**.

2. Добавьте одного или нескольких пользователей в группу безопасности **EDM\_DataUploaders**. (Эти пользователи будут управлять базой данных конфиденциальной информации.)

#### <a name="hash-and-upload-from-one-computer"></a>Хеширование и отправка с одного компьютера

Этот компьютер должен иметь прямой доступ к вашему клиенту Microsoft 365.

>[!NOTE]
> Перед началом этой процедуры убедитесь, что вы являетесь участником группы безопасности **EDM\_DataUploaders**.

> [!TIP]
> Необязательно, вы можете выполнить проверку в отношении .csv или TSV-файла перед отправкой при запуске:
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
>Для получения дополнительной информации обо всех поддерживаемых параметрах EdmUploadAgent.exe> запустите
>
> `EdmUploadAgent.exe /?`


#### <a name="links-to-edm-upload-agent-by-subscription-type"></a>Ссылки на агента отправки EDM по типу подписки

- [Коммерческий + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) — для большинства коммерческих клиентов;
- [GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) — специально для пользователей облачного хранилища для правительственных органов с высоким уровнем безопасности;
- [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) — специально для пользователей облачного хранилища для Министерства обороны США.

1. Создайте рабочий каталог для EDMUploadAgent. Например, **C:\EDM\Data**. Поместите туда файл **PatientRecords.csv**.

2. Скачайте и установите соответствующий [агент отправки EDM](#links-to-edm-upload-agent-by-subscription-type) для своей подписки в каталог, созданный на шаге 1.

   > [!NOTE]
   > EDMUploadAgent по ссылкам выше обновлен, чтобы автоматически добавить значение соли в хешированные данные. Кроме того, вы можете указать собственное значение соли. После использования этой версии вы не сможете применить предыдущую версию EDMUploadAgent.
   >
   > Вы можете отправлять данные с помощью EDMUploadAgent в любое указанное хранилище данных только дважды в день.

   > [!TIP]
   > Чтобы получить список поддерживаемых параметров команды, запустите агент без аргументов, например: “EdmUploadAgent.exe”.

2. Авторизуйте агент отправки EDM, откройте окно командной строки (как администратор), переключитесь на каталог **C:\EDM\Data** и выполните следующую команду:

   `EdmUploadAgent.exe /Authorize`

3. Войдите с помощью своей рабочей или учебной учетной записи Microsoft 365, добавленной в группу безопасности EDM_DataUploaders. Сведения о вашем клиенте извлекаются из учетной записи пользователя для выполнения подключения.

   НЕОБЯЗАТЕЛЬНО. Если вы использовали мастер схемы точного соответствия данных и типов конфиденциальной информации для создания схемы и файлов шаблонов, запустите следующую команду в окне командной строки:

   `EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>`

4. Чтобы хешировать и отправить конфиденциальные данные, выполните следующую команду в окне командной строки:

   `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /ColumnSeparator ["{Tab}"|"|"]`

   Пример: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**

   Формат конфиденциальных данных по умолчанию — разделенные запятыми значения. Можно указать файл, разделенный вкладками, указав параметр "{Tab}" с параметром /ColumnSeparator, или указать файл, разделенный на трубу, указав параметр "|".  
   Эта команда автоматически добавляет в hash случайно генерируемую солевое значение для большей безопасности. Если вы хотите использовать собственное значение соли, добавьте **/Salt<saltvalue>** в команду. Это значение должно состоять из 64 символов и может содержать только символы a–z и 0–9.

5. Проверьте состояние отправки, выполнив следующую команду:

   `EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

   Пример: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**

   Найдите состояние **ProcessingInProgress**. Повторяйте попытку каждые несколько минут, пока состояние не изменится на **Completed**. Когда отобразится завершенное состояние, ваши данные EDM готовы к использованию.

#### <a name="separate-hash-and-upload"></a>Раздельное хеширование и отправка

Выполняйте хеширование на компьютере в безопасной среде.

НЕОБЯЗАТЕЛЬНО. Если вы использовали мастер схемы точного соответствия данных и типов конфиденциальной информации для создания схемы и файлов шаблонов, запустите следующую команду в окне командной строки:

`EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>`

1. В окне командной строки выполните следующие команды:

   `EdmUploadAgent.exe /CreateHash /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] >`

   Например:

   > **EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**

   Результатом будет хешированный файл и файл соли с этими расширениями, если вы не указали параметр **/Salt<saltvalue>**:
   - .EdmHash
   - .EdmSalt

2. Скопируйте эти файлы безопасным способом на компьютер, который будет использовать для отправки конфиденциальных элементов .csv или файл tsv (PatientRecords) в клиент.

   Чтобы отправить хешированные данные, выполните следующую команду в командной строке Windows:

   `EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

   Например:

   > **EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**


   Чтобы убедиться, что конфиденциальные данные были отправлены, выполните следующую команду в окне командной строки:

   `EdmUploadAgent.exe /GetDataStore`

   Появится список хранилищ данных и время их последнего обновления.

   Если вы хотите просмотреть все отправки данных в определенное хранилище, выполните следующую команду в командной строке Windows:

   `EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

   Перейдите к настройке процесса и расписания для [обновления базы данных конфиденциальной информации](#refreshing-your-sensitive-information-database).

На этом этапе вы готовы использовать классификацию на основе EDM с помощью облачных служб Майкрософт. Например, вы можете [настроить политику защиты от потери данных с помощью классификации на основе EDM](#to-create-a-dlp-policy-with-edm).

#### <a name="refreshing-your-sensitive-information-database"></a>Обновление базы данных конфиденциальной информации

Вы можете обновлять базу данных конфиденциальной информации ежедневно, а средство отправки EDM может повторно индексировать конфиденциальные данные и повторно отправлять индексированные данные.

1. Определите процесс и частоту (ежедневно или еженедельно) обновления базы данных конфиденциальной информации.

2. Повторно экспортировать конфиденциальные данные в приложение, например Microsoft Excel, и сохранить файл в формате .csv tsv. Не изменяйте имя и расположение файла, которые использовались при выполнении действий, описанных в разделе [Хеширование и отправка конфиденциальных данных](#part-2-hash-and-upload-the-sensitive-data).

      > [!NOTE]
      > Если нет изменений в структуре (имена полей) файла .csv tsv, при обновлении данных не потребуется вносить изменения в файл схемы базы данных. Но если нужно внести изменения, измените схему базы данных и пакет правил соответствующим образом.

3. Используйте [планировщик заданий](/windows/desktop/TaskSchd/task-scheduler-start-page) для автоматизации действий 2 и 3 в процедуре [хеширования и отправки конфиденциальных данных](#part-2-hash-and-upload-the-sensitive-data). Вы можете планировать задачи с помощью нескольких методов:

      | Метод             | Действия |
      | ---------------------- | ---------------- |
      | Windows PowerShell     | См. документацию по [ScheduledTasks](/powershell/module/scheduledtasks/?view=win10-ps) и [пример скрипта PowerShell](#example-powershell-script-for-task-scheduler) в этой статье |
      | API планировщика заданий     | См. документацию по [планировщику заданий](/windows/desktop/TaskSchd/using-the-task-scheduler)                                                                                                                                                                                                                                                                                |
      | Пользовательский интерфейс Windows | В Windows нажмите **Пуск** и введите "Планировщик заданий". Затем в списке результатов щелкните правой кнопкой мыши **Планировщик заданий** и выберите команду **Запуск от имени администратора**.                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a>Пример скрипта PowerShell для планировщика заданий

Этот раздел содержит пример скрипта PowerShell, который можно использовать для планирования задач по хешированию данных и отправке хешированных данных:

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a>Планирование хеширования и отправки одним действием

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext"
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation + ' /Schema ' + $schemaFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadDataArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a>Планирование хеширования и отправки отдельными действиями

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext "

\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation + ' /Schema ' + $schemaFile
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password

```

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a>Часть 3. Использование классификации на основе EDM с помощью облачных служб Майкрософт

Типы конфиденциальной информации EDM поддерживаются для следующих расположений::

- DLP для Exchange Online (электронная почта)
- OneDrive для бизнеса (файлы)
- Microsoft Teams (беседы)
- DLP для SharePoint (файлы)
- Политики DLP Microsoft Cloud App Security
- Политики автоматической маркировки на стороне сервера, доступные для коммерческих клиентов облачных и государственных облачных клиентов

#### <a name="to-create-a-dlp-policy-with-edm"></a>Создание политики защиты от потери данных с EDM

1. Перейдите в Центр безопасности и соответствия требованиям, воспользовавшись соответствующей [ссылкой для вашей подписки](#portal-links-for-your-subscription).

2. Выберите **Защита от потери данных** \> **Политика**.

3. Нажмите **Создание политики** \> **Custom** \> **Далее**.

4. На вкладке **Назовите политику** укажите название и описание, а затем нажмите кнопку **Далее**.

5. На вкладке **Выберите расположения** щелкните **Позволить мне выбрать расположения** и нажмите **Далее**.

6. В столбце **Состояние** выберите **электронную почту Exchange, учетные записи OneDrive, сообщение из чатов и каналов Teams**, а затем нажмите **Далее**.

7. На вкладке **Параметры политики** установите флажок **Использование дополнительных параметров** и нажмите **Далее**.

8. Нажмите кнопку **+ Создать правило**.

9. В разделе **Название** укажите название и описание для правила.

10. В разделе **Условия** в списке **+ Добавить условие** выберите вариант **Содержит типы конфиденциальной информации**.

      ![Контент содержит типы конфиденциальной информации](../media/edm-dlp-newrule-conditions.png)

11. Найдите тип конфиденциальной информации, созданный при настройке пакета правил, и нажмите кнопку **+ Добавить**.  
    Затем нажмите **Готово**.

12. Завершите выбор параметров для правила, таких как **Уведомления пользователей**, **Переопределения пользователя**, **Отчеты об инцидентах** и т. д., и нажмите кнопку **Сохранить**.

13. На вкладке **Параметры политики** проверьте свои правила и нажмите кнопку **Далее**.

14. Укажите, включить ли политику сразу, проверить ее или оставить выключенной. Затем нажмите кнопку **Далее**.

15. На вкладке **Проверьте параметры** просмотрите свою политику. Внесите любые необходимые изменения. После завершения нажмите кнопку **Создать**.

> [!NOTE]
> Потребуется примерно один час, чтобы новая политика защиты от потери данных распространилась по центру обработки данных.

## <a name="related-articles"></a>Статьи по теме

- [Определения типа конфиденциальной информации](sensitive-information-type-entity-definitions.md)
- [Сведения о типах конфиденциальной информации](sensitive-information-type-learn-about.md)
- [Сведения о защите от потери данных](dlp-learn-about-dlp.md)
- [Microsoft Cloud App Security](/cloud-app-security)
- [New-DlpEdmSchema](/powershell/module/exchange/new-dlpedmschema)
- [Изменение схемы точного соответствия данных для использования настраиваемого совпадения](sit-modify-edm-schema-configurable-match.md).
