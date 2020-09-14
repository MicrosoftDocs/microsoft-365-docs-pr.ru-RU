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
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Узнайте о создании пользовательских типов конфиденциальной информации с помощью классификации на основе точного совпадения данных.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1c47d682d7b3c52fa5ca5b71386a764f3b3da693
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546961"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a>Создание пользовательских типов конфиденциальной информации с помощью классификации на основе точного совпадения данных

[Пользовательские типы конфиденциальной информации](custom-sensitive-info-types.md) используются для определения конфиденциальных элементов, чтобы предотвратить непреднамеренное или неприемлемое предоставление к ним общего доступа. Вы определяете пользовательский тип конфиденциальной информации на основе следующего:

- шаблоны;
- ключевое слово, например  *сотрудник*,  *эмблема* или *идентификатор*;
- близкое расположение символов, свидетельствующее об определенном шаблоне;
- доверительные уровни.

 Такие пользовательские типы конфиденциальной информации соответствуют бизнес-требованиям большинства организаций.

Но что если вам нужен пользовательский тип конфиденциальной информации, использующий точные значения данных, а не ищущий сопоставления на основе универсальных шаблонов? С помощью классификации на основе точного совпадения данных (EDM) вы можете создать пользовательский тип конфиденциальной информации с такими характеристиками:

- динамичный и обновляемый;
- дополнительные возможности масштабирования;
- снижает число ошибочно положительных результатов;
- поддерживает структурированные конфиденциальные данные;
- более безопасная обработка конфиденциальной информации;
- использование с несколькими облачными службами Майкрософт.

![Классификация на основе EDM](../media/EDMClassification.png)

Классификация на основе EDM позволяет создавать пользовательские типы конфиденциальной информации, ссылающиеся на точные значения в базе данных конфиденциальной информации. Базу данных можно обновлять ежедневно, и она может содержать до 100 миллионов строк данных. Таким образом, ваши пользовательские типы конфиденциальной информации остаются актуальными и применимыми при смене сотрудников, пациентов или клиентов, а также при изменении записей. Вы также можете использовать классификацию на основе EDM с политиками, такими как [политики защиты от потери данных](data-loss-prevention-policies.md) (DLP) или [политики файлов Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).

> [!NOTE]
> Служба защиты информации Microsoft 365 теперь поддерживает в предварительный версии языки с  	набором двухбайтовых символов:
> - Китайский (упрощенное письмо)
> - Китайский (традиционное письмо)
> - Корейский
> - Японский
> 
>Эта предварительная версия доступна только в коммерческом облаке, а развертывание ограничено следующими странами:
> - Япония
> - Республика Корея
> - Китай
> - Гонконг
> - Макао
> - Тайвань
>
>Эта поддержка доступна для конфиденциальных типов информации. Дополнительные сведения см. в статье [Заметки о выпуске: поддержка защиты информации для наборов двухбайтовых символов (предварительная версия)](mip-dbcs-relnotes.md).

## <a name="required-licenses-and-permissions"></a>Обязательные лицензии и разрешения

Для выполнения задач, описанных в данной статье, вы должны быть глобальным администратором, администратором соответствия требованиям или администратором Exchange Online. Дополнительные сведения о разрешениях DLP см. в разделе [Разрешения](data-loss-prevention-policies.md#permissions).

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

1. [Сохранение конфиденциальных данных в формате CSV](#save-sensitive-data-in-csv-format)
2. [Определение схемы для базы данных конфиденциальной информации](#define-the-schema-for-your-database-of-sensitive-information)
3. [Создание пакета правил](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-format"></a>Сохранение конфиденциальных данных в формате CSV

1. Определите конфиденциальную информацию, которую нужно использовать. Экспортируйте данные в приложение, например Microsoft Excel, и сохраните файл в формате CSV. Файл данных может содержать:
      - до 100 миллионов строк конфиденциальных данных;
      - до 32 столбцов (полей) на источник данных;
      - до 5 столбцов (полей), отмеченных как доступные для поиска.

2. Структурируйте конфиденциальные данные в CSV-файле таким образом, чтобы первая строка включала имена полей, которые используются для классификации на основе EDM. В CSV-файле можно применять такие имена полей, как ssn, birthdate, firstname, lastname. В названиях заголовков столбцов не должно быть пробелов и символов подчеркивания. Например, используемый в этой статье пример CSV-файла называется  *PatientRecords.csv*, а его столбцы включают *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN* и другие.

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a>Определение схемы для базы данных конфиденциальной информации

3. Определите схему для базы данных конфиденциальной информации в формате XML (как в примере ниже). Назовите этот файл схемы  **edm.xml** и настройте его так, чтобы для каждого столбца в базе данных была строка, использующая синтаксис: 

      `\<Field name="" searchable=""/\>`.

      - Используйте имена столбцов для значений *Field name* .
      - Используйте параметр *searchable="true"* для 5 полей, которые должны поддерживать поиск. По крайней мере одно поле должно поддерживать поиск.

      Например, в следующем XML-файле определяется схема для базы данных записей пациентов с пятью полями, поддерживающими поиск: *PatientID*, *MRN*, *SSN*, *Phone* и *DOB*.

      (Вы можете скопировать, изменить и использовать наш пример.)

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" />
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

4. Подключитесь к Центру безопасности и соответствия требованиям, используя процедуры, описанные в статье [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

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
> Чтобы изменения вносились без запроса подтверждения, используйте вместо указанного в действии 5 командлета следующий: New-DlpEdmSchema -FileData $edmSchemaXml

> [!NOTE]
> Обновление EDMSchema с дополнениями может занять от 10 до 60 минут. Перед выполнением действий, в которых используется дополнение, необходимо выполнить обновление.

#### <a name="set-up-a-rule-package"></a>Настройка пакета правил

1. Создайте пакет правил в формате XML (в кодировке Юникод), как показано в примере ниже. (Вы можете скопировать, изменить и использовать наш пример.)

      Настраивая пакет правил, убедитесь, что в нем используются правильные ссылки на CSV-файл и файл **edm.xml**. Вы можете скопировать, изменить и использовать наш пример. В этом примере XML для создания типа конфиденциальной информации EDM должны быть настроены перечисленные ниже поля.

      - **Идентификаторы RulePack и ExactMatch**. Используйте командлет [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) для создания GUID.

      - **Datastore**. В этом поле указывается, какое хранилище данных подстановки EDM будет использоваться. Вы указываете имя источника данных для настроенной схемы EDM.

      - **idMatch**. Это поле указывает на основной элемент EDM.
        - Matches. Указывает поле, которое будет использоваться при точном поиске. Вы указываете имя поля для поиска в схеме EDM для DataStore.
        - Classification. В этом поле указывается соответствие типа конфиденциальной информации, которое активирует поиск EDM. Вы можете указать имя или идентификатор GUID имеющейся встроенной или настраиваемой классификации.

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

1. Отправьте пакет правил, выполнив по отдельности указанные ниже командлеты PowerShell.

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

На этом этапе вы настроили классификацию на основе EDM. На следующем этапе необходимо хешировать конфиденциальные данные, а затем отправить хеши на индексацию.

Помните, что схема PatientRecords определяет пять полей как доступные для поиска:  *PatientID*,  *MRN*,  *SSN*,  *Phone* и  *DOB*. В нашем примере пакет правил включает эти поля и ссылки на файл схемы базы данных (**edm.xml**), предусматривая один элемент *ExactMatch* для каждого доступного для поиска поля. Рассмотрим следующий элемент ExactMatch:

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

- Имя хранилища данных dataStore ссылается на ранее созданный файл CSV:  **dataStore = "PatientRecords"**.

- Значение idMatch ссылается на доступное для поиска поле, которое указано в файле схемы базы данных: **idMatch matches = "SSN"**.

- Значение классификации ссылается на существующий или пользовательский тип конфиденциальной информации:  **classification = "U.S. Social Security Number (SSN)"**. (В этом случае используется существующий тип конфиденциальной информации, содержащий номер социального страхования США.)

> [!NOTE]
> Обновление EDMSchema с дополнениями может занять от 10 до 60 минут. Перед выполнением действий, в которых используется дополнение, необходимо выполнить обновление.

#### <a name="editing-the-schema-for-edm-based-classification"></a>Редактирование схемы для классификации на основе EDM

Если нужно внести изменения в файл **edm.xml**, например изменить поля, используемые для классификации на основе EDM, выполните указанные ниже действия.

1. Измените файл **edm.xml** (файл, обсуждаемый в разделе [Определение схемы](#define-the-schema-for-your-database-of-sensitive-information)  этой статьи).

2. Подключитесь к Центру безопасности и соответствия требованиям, используя процедуры, описанные в статье [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

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
      > Чтобы изменения вносились без запроса подтверждения, используйте вместо указанного в действии 3 командлета следующий: Set-DlpEdmSchema -FileData $edmSchemaXml

      > [!NOTE]
      > Обновление EDMSchema с дополнениями может занять от 10 до 60 минут. Перед выполнением действий, в которых используется дополнение, необходимо выполнить обновление.

#### <a name="removing-the-schema-for-edm-based-classification"></a>Удаление схемы для классификации на основе EDM

(При необходимости.) Чтобы удалить схему, используемую для классификации на основе EDM, выполните указанные ниже действия.

1. Подключитесь к Центру безопасности и соответствия требованиям, используя процедуры, описанные в статье [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

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
      >  Чтобы изменения вносились без запроса подтверждения, используйте вместо указанного в действии 2 командлета следующий: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false


<!-- salt notes
need two salting procedures, one for onestep from the externally facing and another for two step, on an internal machine then the upload from the external machine

- create A  folder put the edmupload agent and, csv and salt file there, run all processes there
- 
- stuff you need to have first: DataStoreName, /DataFile name (csv file)  /Hashlocation

- salt can be randomly generated by Microsoft or can be provided by the customer. If provided by the customer it must follow  format of 64 character, and can contain only letters or 0-9 characters.  Use a website to generate a valid salt value.
 
- can run EDMuploadagent.exe from PS or Windows cmd window . tested on Windows Server 2016 or Windows 10 and dot net version 4.6.2

when defiuning the schema file the searchable fields must be either an out of box SIT or custom SIT, only 5 fields )column headings) can be searchable

1. From outbound access device from the cmd prompt run EdmUploadAgent.exe /Authorize -  
2. data store schema must have already been uploaded
3.  create hash first then do upload
4. EdmUploadAgent.exe /CreateHash /DataFile (where the data file is ) E:\emd\test\data\schema32_1000000,csv /HashLocation  (where to store it) E:\edm\tat\hash this makes the salt file and the hash file as output
5. next is upload EdmUploadAgent.exe /UploadHash /DataStoreName (found in the Schema file DataSore name="FOO" /HashFile (path to hash file locaztion and file name /HashLocation path to hash)  for example
1.EdmUploadAgent/exe /UploadHash /DataStoreName schema321 /HashFile E:\edm\test\hash\schema32_10000000.EdmHash /HashLocation E:\edm\test\hash  -this one  uses MSFT generated salt, so no need to provide

Salt is an optional parameter so if yo uwant to use a custom salt add /salt and the salt value if salt file not copied to the outbound machine 

OR copy both files hash and salt to the same directory and the commmand will get both


OR do it in single step hash, salt ulopad

!! once they download the updated upload agent they will always have SALT, there is no going back.


all in one step: EdmUploadAgent.exe /UploadData /DataStoreName schema321 /DataFile E:\edm\test\data\schema32_10000.csv /HashLocation E:\edm\test\hash

tshooting/check status cmd



Once it gets to completed the admin can start using it in the custom SIT

they have to get their own custom SALT

just copy SALT over in a secure fashion










1.
6.
7.
1.  


 -->

### <a name="part-2-hash-and-upload-the-sensitive-data"></a>Часть 2. Хеширование и отправка конфиденциальных данных

На этом этапе выполняется настройка пользовательской группы безопасности и учетной записи пользователя, а также настройка агента отправки EDM. Затем применяется средство для хеширования конфиденциальных данных с использованием значения соли и выполняется их отправка.

Хеширование и отправку можно выполнить на одном компьютере, или вы можете отделить этап хеширования от этапа отправки для дополнительной безопасности.

Если вы хотите выполнить хеширование и отправку с одного компьютера, нужно делать это на компьютере, который может напрямую подключаться к вашему клиенту Microsoft 365. Для этого требуется, чтобы ваши файлы с конфиденциальными данными в виде обычного текста находились на этом компьютере для хеширования.

Если вы не хотите предоставлять свой файл с конфиденциальными данными в виде обычного текста, вы можете хешировать его на компьютере в безопасном расположении, а затем скопировать хеш-файл и файл соли на компьютер, который может напрямую подключаться к клиенту Microsoft 365 для отправки. В этом сценарии вам потребуется EDMUploadAgent на обоих компьютерах. 

#### <a name="prerequisites"></a>Предварительные условия

- рабочая или учебная учетная запись для Microsoft 365, которая будет добавлена в группу безопасности **EDM\_DataUploaders**;
- компьютер с Windows 10 или Windows Server 2016 с .NET версии 4.6.2 для запуска EDMUploadAgent;
- каталог на компьютере отправки для следующего:
    -  EDMUploadAgent
    - файл конфиденциального элемента в формате CSV. **PatientRecords.csv** в наших примерах;
    -  выходной хеш-файл и файл соли;
    - имя хранилища данных из файла **edm.xml**. В этом примере: `PatientRecords`.

#### <a name="set-up-the-security-group-and-user-account"></a>Настройка группы безопасности и учетной записи пользователя

1. Как глобальный администратор перейдите в центр администрирования с помощью соответствующей [ссылки для вашей подписки](#portal-links-for-your-subscription) и [создайте группу безопасности](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) с именем **EDM\_DataUploaders**.

2. Добавьте одного или нескольких пользователей в группу безопасности **EDM\_DataUploaders** . (Эти пользователи будут управлять базой данных конфиденциальной информации.)

#### <a name="hash-and-upload-from-one-computer"></a>Хеширование и отправка с одного компьютера

Этот компьютер должен иметь прямой доступ к вашему клиенту Microsoft 365.

>[!NOTE]
> Перед началом этой процедуры убедитесь, что вы являетесь участником группы безопасности **EDM\_DataUploaders** .

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a>Ссылки на агента отправки EDM по типу подписки

- [Коммерческий + GCC](https://go.microsoft.com/fwlink/?linkid=2088639)
- [GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521)
- [DoD](https://go.microsoft.com/fwlink/?linkid=2137807)

1. Создайте рабочий каталог для EDMUploadAgent. Например, **C:\EDM\Data**. Поместите туда файл **PatientRecords.csv**.

2. Скачайте и установите соответствующий [агент отправки EDM](#links-to-edm-upload-agent-by-subscription-type) для своей подписки в каталог, созданный на шаге 1.

> [!NOTE]
> EDMUploadAgent по ссылкам выше обновлен, чтобы автоматически добавить значение соли в хешированные данные. Кроме того, вы можете указать собственное значение соли. После использования этой версии вы не сможете применить предыдущую версию EDMUploadAgent.
>
> Вы можете отправлять данные с помощью EDMUploadAgent в любое указанное хранилище данных только дважды в день.

> [!TIP]
> Чтобы получить список поддерживаемых параметров команды, запустите агент без аргументов. Например, EdmUploadAgent.exe.

2. Авторизуйте агент отправки EDM, откройте окно командной строки (как администратор), переключитесь на каталог **C:\EDM\Data** и выполните следующую команду:

   `EdmUploadAgent.exe /Authorize`

3. Войдите с помощью своей рабочей или учебной учетной записи Microsoft 365, добавленной в группу безопасности EDM_DataUploaders. Сведения о вашем клиенте извлекаются из учетной записи пользователя для выполнения подключения.

4. Чтобы хешировать и отправить конфиденциальные данные, выполните следующую команду в окне командной строки:

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

Пример: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**

Это автоматически добавит в хеш случайно созданное значение соли, чтобы повысить безопасность. Если вы хотите использовать собственное значение соли, добавьте **/Salt<saltvalue>** в команду. Это значение должно состоять из 64 символов и может содержать только символы a–z и 0–9.

5. Проверьте состояние отправки, выполнив следующую команду:

`EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

Пример: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**

Найдите состояние **ProcessingInProgress**. Повторяйте попытку каждые несколько минут, пока состояние не изменится на **Completed**. Когда отобразится завершенное состояние, ваши данные EDM готовы к использованию.

#### <a name="separate-hash-and-upload"></a>Раздельное хеширование и отправка

Выполняйте хеширование на компьютере в безопасной среде.

1. В окне командной строки выполните следующие команды:

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

Например:

> **EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**

Результатом будет хешированный файл и файл соли с этими расширениями, если вы не указали параметр **/Salt<saltvalue>**:
- .EdmHash
- .EdmSalt

2. Безопасно скопируйте эти файлы на компьютер, который вы используете для отправки CSV-файла с конфиденциальными элементами (PatientRecords) в свой клиент.

Чтобы отправить хешированные данные, выполните следующую команду в командной строке Windows:

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

Например:

> **EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**


Чтобы убедиться, что конфиденциальные данные были отправлены, выполните следующую команду в окне командной строки:


`EdmUploadAgent.exe /GetDataStore`

Появится список хранилищ данных и время их последнего обновления.

Если вы хотите просмотреть все отправки данных в определенное хранилище, выполните следующую команду в командной строке Windows:

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

Перейдите к настройке процесса и расписания для  [обновления базы данных конфиденциальной информации](#refreshing-your-sensitive-information-database).

На этом этапе вы готовы использовать классификацию на основе EDM с помощью облачных служб Майкрософт. Например, вы можете [настроить политику защиты от потери данных с помощью классификации на основе EDM](#to-create-a-dlp-policy-with-edm).

#### <a name="refreshing-your-sensitive-information-database"></a>Обновление базы данных конфиденциальной информации

Вы можете обновлять базу данных конфиденциальной информации ежедневно, а средство отправки EDM может повторно индексировать конфиденциальные данные и повторно отправлять индексированные данные.

1. Определите процесс и частоту (ежедневно или еженедельно) обновления базы данных конфиденциальной информации.

2. Повторно экспортируйте конфиденциальные данные в приложение, например Microsoft Excel, и сохраните файл в формате CSV. Не изменяйте имя и расположение файла, которые использовались при выполнении действий, описанных в разделе  [Хеширование и отправка конфиденциальных данных](#part-2-hash-and-upload-the-sensitive-data).

      > [!NOTE]
      > Если в структуру (имена полей) CSV-файла не вносится никаких изменений, то вам не нужно вносить изменения в файл схемы базы данных при обновлении данных. Но если нужно внести изменения, измените схему базы данных и пакет правил соответствующим образом.

3. Используйте  [планировщик заданий](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page)  для автоматизации действий 2 и 3 в процедуре  [хеширования и отправки конфиденциальных данных](#part-2-hash-and-upload-the-sensitive-data) . Вы можете планировать задачи с помощью нескольких методов:

      | Метод             | Действия |
      | ---------------------- | ---------------- |
      | Windows PowerShell     | См. документацию по [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps)  и [пример скрипта PowerShell](#example-powershell-script-for-task-scheduler) в этой статье |
      | API планировщика заданий     | Ознакомьтесь с документацией по [планировщику заданий](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler)                                                                                                                                                                                                                                                                                 |
      | Пользовательский интерфейс Windows | В Windows нажмите кнопку **Пуск** и введите "Планировщик заданий". Затем в списке результатов щелкните правой кнопкой мыши **Планировщик заданий** и выберите команду **Запуск от имени администратора**.                                                                                                                                                                                                                                                                           |

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
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation
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
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation
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

Типы конфиденциальной информации EDM для указанных ниже сценариев сейчас находятся в процессе разработки и пока недоступны.

- Автоматическая классификация меток конфиденциальности и хранения

#### <a name="to-create-a-dlp-policy-with-edm"></a>Создание политики защиты от потери данных с EDM

1. Перейдите в Центр безопасности и соответствия требованиям, воспользовавшись соответствующей [ссылкой для вашей подписки](#portal-links-for-your-subscription).

2. Выберите пункты **Защита от потери данных** \> **Политика**.

3. Нажмите **Создать политику** \> **Настраиваемая** \> **Далее**.

4. На вкладке **Назовите политику** укажите название и описание, а затем нажмите кнопку **Далее**.

5. На вкладке **Выберите расположения** щелкните **Позволить мне выбрать расположения** и нажмите кнопку **Далее**.

6. В столбце **Состояние** выберите **электронную почту Exchange, учетные записи OneDrive, чат и канал сообщений Teams** , а затем нажмите кнопку **Далее**.

7. На вкладке **Параметры политики** установите флажок **Использование дополнительных параметров** и нажмите кнопку  **Далее**.

8. Нажмите кнопку **+ Создать правило**.

9. В разделе **Название** укажите название и описание правила.

10. В разделе **Условия** в списке **+ Добавить условие** выберите вариант **Контент содержит типы конфиденциальной информации**.

      ![Контент содержит типы конфиденциальной информации](../media/edm-dlp-newrule-conditions.png)

11. Найдите тип конфиденциальной информации, созданный при настройке пакета правил, и нажмите кнопку **+ Добавить**.  
    Затем нажмите кнопку **Готово**.

12. Выберите остальные параметры для правила, например **Уведомления пользователей**, **Переопределения пользователя**, **Отчеты об инцидентах** и т. д., а затем нажмите кнопку **Сохранить**.

13. На вкладке **Параметры политики** проверьте свои правила и нажмите кнопку **Далее**.

14. Укажите, включить политику сразу, проверить ее или оставить выключенной. Затем нажмите кнопку **Далее**.

15. На вкладке **Проверьте параметры** просмотрите свою политику. Внесите все необходимые изменения. Когда все будет готово, нажмите кнопку **Создать**.

> [!NOTE]
> Потребуется примерно один час, чтобы новая политика защиты от потери данных распространилась по центру обработки данных.

## <a name="related-articles"></a>Статьи по теме

- [Определения типа конфиденциальной информации](sensitive-information-type-entity-definitions.md)
- [Пользовательские типы конфиденциальной информации](custom-sensitive-info-types.md)
- [Обзор политик защиты от потери данных](data-loss-prevention-policies.md)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)
- [New-DlpEdmSchema](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema)

