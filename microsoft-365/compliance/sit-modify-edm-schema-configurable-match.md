---
title: Изменение схемы точного соответствия данных для использования настраиваемого совпадения
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
description: Узнайте, как изменить схему edm для использования настраиваемого совпадения.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7d470b986d4a94206935efb832deec7171f8e404
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114197"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a>Изменение схемы точного соответствия данных для использования настраиваемого совпадения

Классификация на основе Exact Data Match (EDM) позволяет создавать пользовательские типы конфиденциальной информации, ссылающиеся на точные значения в базе данных конфиденциальной информации. При необходимости разрешить варианты точной строки, можно использовать *настраиваемое совпадение*, чтобы Microsoft 365 игнорировал регистр и некоторые разделители. 

> [!IMPORTANT]
> Используйте эту процедуру для изменения существующей схемы EDM и файла данных.

1. Удалите **EdmUploadAgent.exe** с компьютера, который используется для подключения к Microsoft 365 для схемы EDM и загрузки файлов данных.

2. Загрузите соответствующий файл **EdmUploadAgent.exe** для вашей подписки по ссылкам ниже:
    - [Коммерческий + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) — для большинства коммерческих клиентов;
    - [GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) — специально для пользователей облачного хранилища для правительственных органов с высоким уровнем безопасности;
    - [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) — специально для пользователей облачного хранилища для Министерства обороны США.

3. Чтобы разрешить работу агента отправки EDM, откройте окно командной строки (в качестве администратора) и выполните следующую команду:

   `EdmUploadAgent.exe /Authorize`

4. При отсутствии текущей копии существующей схемы, необходимо загрузить копию существующей схемы, выполните следующую команду:

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. Настройте схему таким образом, чтобы каждая колонка использовала "caseInsensitive" и/или "ignoredDelimiters".  Значение по умолчанию для "caseInsensitive" — false, а для "ignoredDelimiters" — пустая строка. 

> [!NOTE]
> Базовый настраиваемый или встроенный тип конфиденциальной информации, используемый для обнаружения общего шаблона регулярного выражения, должен поддерживать обнаружение входных вариаций, перечисленных с ignoredDelimiters. Например, встроенный в номер социального страхования США (SSN) тип конфиденциальной информации может обнаружить вариации в данных, которые включают тире, пробелы или отсутствие пробелов между сгруппированными числами, составляющими SSN. В результате, единственными разделителями, которые необходимо включить в ignoredDelimiters EDM для данных SSN, являются тире и пробел.

Вот пример схемы, которая имитирует совпадение без учета регистра, создавая дополнительные столбцы, необходимые для распознавания вариаций регистра в конфиденциальных данных.

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
           <Field name="PolicyNumber" searchable="true" />
           <Field name="PolicyNumberLowerCase" searchable="true" />
           <Field name="PolicyNumberUpperCase" searchable="true" />
           <Field name="PolicyNumberCapitalLetters" searchable="true" />
  </DataStore>
</EdmSchema>
```

В приведенном выше примере варианты исходного столбца `PolicyNumber` больше не требуются, если добавлены оба: `caseInsensitive` и `ignoredDelimiters`.

Чтобы обновить эту схему таким образом, чтобы EDM использовал настраиваемое соответствие, используйте флаги `caseInsensitive` и `ignoredDelimiters`.  Вот как это выглядит:

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

Флаг `ignoredDelimiters` поддерживает любые не буквенно-цифровые символы. Вот несколько примеров:
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

6. Подключитесь к Центру безопасности и соответствия требованиям, используя процедуры, описанные в статье [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](/powershell/exchange/connect-to-scc-powershell).

> [!NOTE]
> Если ваша организация настроила [ключ клиента для Microsoft 365 на уровне клиента (общедоступная предварительная версия)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), точное соответствие данных будет автоматически использовать его функцию шифрования. Эта возможность доступна только лицензированным клиентам E5 в коммерческом облаке.

7. Обновите схему, запустив эти командлеты по очереди:

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. При необходимости обновите файл данных, чтобы он соответствовал новой версии схемы

> [!TIP]
> При желании можно запустить проверку CSV-файла перед загрузкой, запустив:
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
>Для получения дополнительной информации обо всех поддерживаемых параметрах EdmUploadAgent.exe> запустите
>
> `EdmUploadAgent.exe /?`

9. Откройте окно командной строки (в качестве администратора) и выполните следующую команду для хеширования и загрузки конфиденциальных данных:

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a>Статьи по теме

- [Создание пользовательского типа конфиденциальной информации с помощью классификации на основе точного совпадения данных](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).
- [Определения типа конфиденциальной информации](sensitive-information-type-entity-definitions.md)
- [Пользовательские типы конфиденциальной информации](./sensitive-information-type-learn-about.md)
- [Сведения о защите от потери данных](dlp-learn-about-dlp.md)
- [Microsoft Cloud App Security](/cloud-app-security)
- [New-DlpEdmSchema](/powershell/module/exchange/new-dlpedmschema)