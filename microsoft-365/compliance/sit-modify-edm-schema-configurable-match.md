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
ms.openlocfilehash: dea641072983163c6fbbcc5888d5ee6ea91f6990
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408318"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a><span data-ttu-id="79451-103">Изменение схемы точного соответствия данных для использования настраиваемого совпадения</span><span class="sxs-lookup"><span data-stu-id="79451-103">Modify Exact Data Match schema to use configurable match</span></span>

<span data-ttu-id="79451-104">Классификация на основе Exact Data Match (EDM) позволяет создавать пользовательские типы конфиденциальной информации, ссылающиеся на точные значения в базе данных конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="79451-104">Exact Data Match (EDM) based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="79451-105">При необходимости разрешить варианты точной строки, можно использовать *настраиваемое совпадение*, чтобы Microsoft 365 игнорировал регистр и некоторые разделители.</span><span class="sxs-lookup"><span data-stu-id="79451-105">When you need to allow for variants of a exact string, you can use *configurable match* to tell Microsoft 365 to ignore case and some delimiters.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="79451-106">Используйте эту процедуру для изменения существующей схемы EDM и файла данных.</span><span class="sxs-lookup"><span data-stu-id="79451-106">Use this procedure to modify an existing EDM schema and data file.</span></span>

1. <span data-ttu-id="79451-107">Удалите **EdmUploadAgent.exe** с компьютера, который используется для подключения к Microsoft 365 для схемы EDM и загрузки файлов данных.</span><span class="sxs-lookup"><span data-stu-id="79451-107">Uninstall the **EdmUploadAgent.exe** from the computer that you use to connect to Microsoft 365 for EDM schema and data file upload purposes.</span></span>

2. <span data-ttu-id="79451-108">Загрузите соответствующий файл **EdmUploadAgent.exe** для вашей подписки по ссылкам ниже:</span><span class="sxs-lookup"><span data-stu-id="79451-108">Download the appropriate **EdmUploadAgent.exe** file for your subscription using the links below:</span></span>
    - <span data-ttu-id="79451-109">[Коммерческий + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) — для большинства коммерческих клиентов;</span><span class="sxs-lookup"><span data-stu-id="79451-109">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
    - <span data-ttu-id="79451-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) — специально для пользователей облачного хранилища для правительственных органов с высоким уровнем безопасности;</span><span class="sxs-lookup"><span data-stu-id="79451-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
    - <span data-ttu-id="79451-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) — специально для пользователей облачного хранилища для Министерства обороны США.</span><span class="sxs-lookup"><span data-stu-id="79451-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

3. <span data-ttu-id="79451-112">Чтобы разрешить работу агента отправки EDM, откройте окно командной строки (в качестве администратора) и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="79451-112">Authorize the EDM Upload Agent, open Command Prompt window (as an administrator) and run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

4. <span data-ttu-id="79451-113">При отсутствии текущей копии существующей схемы, необходимо загрузить копию существующей схемы, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="79451-113">If you don't have a current copy of the existing schema, you'll need to download a copy of the existing schema, run this command:</span></span>

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. <span data-ttu-id="79451-114">Настройте схему таким образом, чтобы каждая колонка использовала "caseInsensitive" и/или "ignoredDelimiters".</span><span class="sxs-lookup"><span data-stu-id="79451-114">Customize the schema so each column utilizes “caseInsensitive” and / or “ignoredDelimiters”.</span></span>  <span data-ttu-id="79451-115">Значение по умолчанию для "caseInsensitive" — false, а для "ignoredDelimiters" — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="79451-115">The default value for “caseInsensitive” is “false” and for “ignoredDelimiters”, it is an empty string.</span></span> 

> [!NOTE]
> <span data-ttu-id="79451-116">Базовый настраиваемый или встроенный тип конфиденциальной информации, используемый для обнаружения общего шаблона регулярного выражения, должен поддерживать обнаружение входных вариаций, перечисленных с ignoredDelimiters.</span><span class="sxs-lookup"><span data-stu-id="79451-116">The underlying custom sensitive information type or built in sensitive information type used to detect the general regex pattern must support detection of the variations inputs listed with ignoredDelimiters.</span></span> <span data-ttu-id="79451-117">Например, встроенный в номер социального страхования США (SSN) тип конфиденциальной информации может обнаружить вариации в данных, которые включают тире, пробелы или отсутствие пробелов между сгруппированными числами, составляющими SSN.</span><span class="sxs-lookup"><span data-stu-id="79451-117">For example, the built in U.S. social security number (SSN) sensitive information type can detect variations in the data that include dashes, spaces, or lack of spaces between the grouped numbers that make up the SSN.</span></span> <span data-ttu-id="79451-118">В результате, единственными разделителями, которые необходимо включить в ignoredDelimiters EDM для данных SSN, являются тире и пробел.</span><span class="sxs-lookup"><span data-stu-id="79451-118">As a result, the only delimiters that are relevant to include in EDM’s ignoredDelimiters for SSN data are: dash and space.</span></span>

<span data-ttu-id="79451-119">Вот пример схемы, которая имитирует совпадение без учета регистра, создавая дополнительные столбцы, необходимые для распознавания вариаций регистра в конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="79451-119">Here is a sample schema that simulates case insensitive match by creating the extra columns needed to recognize case variations in the sensitive data.</span></span>

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

<span data-ttu-id="79451-120">В приведенном выше примере варианты исходного столбца `PolicyNumber` больше не требуются, если добавлены оба: `caseInsensitive` и `ignoredDelimiters`.</span><span class="sxs-lookup"><span data-stu-id="79451-120">In the above example, the variations of the original `PolicyNumber` column will no longer be needed if both `caseInsensitive` and `ignoredDelimiters` are added.</span></span>

<span data-ttu-id="79451-121">Чтобы обновить эту схему таким образом, чтобы EDM использовал настраиваемое соответствие, используйте флаги `caseInsensitive` и `ignoredDelimiters`.</span><span class="sxs-lookup"><span data-stu-id="79451-121">To update this schema so that EDM uses configurable match use the `caseInsensitive` and `ignoredDelimiters` flags.</span></span>  <span data-ttu-id="79451-122">Вот как это выглядит:</span><span class="sxs-lookup"><span data-stu-id="79451-122">Here's how that looks:</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="79451-123">Флаг `ignoredDelimiters` поддерживает любые не буквенно-цифровые символы. Вот несколько примеров:</span><span class="sxs-lookup"><span data-stu-id="79451-123">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="79451-124">\.</span><span class="sxs-lookup"><span data-stu-id="79451-124">\.</span></span>
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

<span data-ttu-id="79451-125">Флаг `ignoredDelimiters` не поддерживает:</span><span class="sxs-lookup"><span data-stu-id="79451-125">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="79451-126">символы от 0 до 9</span><span class="sxs-lookup"><span data-stu-id="79451-126">characters 0-9</span></span>
- <span data-ttu-id="79451-127">От А до Я</span><span class="sxs-lookup"><span data-stu-id="79451-127">A-Z</span></span>
- <span data-ttu-id="79451-128">от a до z</span><span class="sxs-lookup"><span data-stu-id="79451-128">a-z</span></span>
- \"
- \,

6. <span data-ttu-id="79451-129">Подключитесь к Центру безопасности и соответствия требованиям, используя процедуры, описанные в статье [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="79451-129">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="79451-130">Если ваша организация настроила [ключ клиента для Microsoft 365 на уровне клиента (общедоступная предварительная версия)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), точное соответствие данных будет автоматически использовать его функцию шифрования.</span><span class="sxs-lookup"><span data-stu-id="79451-130">If your organization has set up [Customer Key for Microsoft 365 at the tenant level (public preview)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), Exact data match will make use of its encryption functionality automatically.</span></span> <span data-ttu-id="79451-131">Эта возможность доступна только лицензированным клиентам E5 в коммерческом облаке.</span><span class="sxs-lookup"><span data-stu-id="79451-131">This is available only to E5 licensed tenants in the Commercial cloud.</span></span>

7. <span data-ttu-id="79451-132">Обновите схему, запустив эти командлеты по очереди:</span><span class="sxs-lookup"><span data-stu-id="79451-132">Update your schema by running these cmdlets one at a time:</span></span>

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. <span data-ttu-id="79451-133">При необходимости обновите файл данных, чтобы он соответствовал новой версии схемы</span><span class="sxs-lookup"><span data-stu-id="79451-133">If necessary, update the data file to match the new schema version</span></span>

> [!TIP]
> <span data-ttu-id="79451-134">При желании можно запустить проверку CSV-файла перед загрузкой, запустив:</span><span class="sxs-lookup"><span data-stu-id="79451-134">Optionally, you can run a validation against your csv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
><span data-ttu-id="79451-135">Для получения дополнительной информации обо всех поддерживаемых параметрах EdmUploadAgent.exe> запустите</span><span class="sxs-lookup"><span data-stu-id="79451-135">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`

9. <span data-ttu-id="79451-136">Откройте окно командной строки (в качестве администратора) и выполните следующую команду для хеширования и загрузки конфиденциальных данных:</span><span class="sxs-lookup"><span data-stu-id="79451-136">Open Command Prompt window (as an administrator) and run the following command to hash and upload your sensitive data:</span></span>

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a><span data-ttu-id="79451-137">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="79451-137">Related articles</span></span>

- <span data-ttu-id="79451-138">[Создание пользовательского типа конфиденциальной информации с помощью классификации на основе точного совпадения данных](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="79451-138">[Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span></span>
- [<span data-ttu-id="79451-139">Определения типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="79451-139">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="79451-140">Пользовательские типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="79451-140">Custom sensitive information types</span></span>](./sensitive-information-type-learn-about.md)
- [<span data-ttu-id="79451-141">Обзор политик защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="79451-141">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="79451-142">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="79451-142">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="79451-143">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="79451-143">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)