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
ms.openlocfilehash: 583419f6808d5b3d54d1f48d380e5b4110898ded
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908353"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="631ae-103">Создание пользовательских типов конфиденциальной информации с помощью классификации на основе точного совпадения данных</span><span class="sxs-lookup"><span data-stu-id="631ae-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="631ae-104">[Пользовательские типы конфиденциальной информации](sensitive-information-type-learn-about.md) используются для определения конфиденциальных элементов, чтобы предотвратить непреднамеренное или неприемлемое предоставление к ним общего доступа.</span><span class="sxs-lookup"><span data-stu-id="631ae-104">[Custom sensitive information types](sensitive-information-type-learn-about.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="631ae-105">Вы определяете пользовательский тип конфиденциальной информации на основе следующего:</span><span class="sxs-lookup"><span data-stu-id="631ae-105">You define a custom sensitive information type based on:</span></span>

- <span data-ttu-id="631ae-106">шаблоны;</span><span class="sxs-lookup"><span data-stu-id="631ae-106">patterns</span></span>
- <span data-ttu-id="631ae-107">ключевое слово, например *сотрудник*, *бейдж* или *идентификатор*;</span><span class="sxs-lookup"><span data-stu-id="631ae-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="631ae-108">близкое расположение символов, свидетельствующее об определенном шаблоне;</span><span class="sxs-lookup"><span data-stu-id="631ae-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="631ae-109">доверительные уровни.</span><span class="sxs-lookup"><span data-stu-id="631ae-109">confidence levels</span></span>

 <span data-ttu-id="631ae-110">Такие пользовательские типы конфиденциальной информации соответствуют бизнес-требованиям большинства организаций.</span><span class="sxs-lookup"><span data-stu-id="631ae-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="631ae-111">Но что если вам нужен пользовательский тип конфиденциальной информации, использующий точные значения данных, а не ищущий сопоставления на основе универсальных шаблонов?</span><span class="sxs-lookup"><span data-stu-id="631ae-111">But what if you wanted a custom sensitive information type that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="631ae-112">С помощью классификации на основе точного совпадения данных (EDM) вы можете создать пользовательский тип конфиденциальной информации с такими характеристиками:</span><span class="sxs-lookup"><span data-stu-id="631ae-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="631ae-113">динамика и простое обновление;</span><span class="sxs-lookup"><span data-stu-id="631ae-113">be dynamic and easily refreshed</span></span>
- <span data-ttu-id="631ae-114">дополнительные возможности масштабирования;</span><span class="sxs-lookup"><span data-stu-id="631ae-114">be more scalable</span></span>
- <span data-ttu-id="631ae-115">снижает число ошибочно положительных результатов;</span><span class="sxs-lookup"><span data-stu-id="631ae-115">result in fewer false-positives</span></span>
- <span data-ttu-id="631ae-116">поддерживает структурированные конфиденциальные данные;</span><span class="sxs-lookup"><span data-stu-id="631ae-116">work with structured sensitive data</span></span>
- <span data-ttu-id="631ae-117">более безопасная обработка конфиденциальной информации;</span><span class="sxs-lookup"><span data-stu-id="631ae-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="631ae-118">использование с несколькими облачными службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="631ae-118">be used with several Microsoft cloud services</span></span>

![Классификация на основе EDM](../media/EDMClassification.png)

<span data-ttu-id="631ae-120">Классификация на основе EDM позволяет создавать пользовательские типы конфиденциальной информации, ссылающиеся на точные значения в базе данных конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="631ae-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="631ae-121">Базу данных можно обновлять ежедневно, и она может содержать до 100 миллионов строк данных.</span><span class="sxs-lookup"><span data-stu-id="631ae-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="631ae-122">Таким образом, ваши пользовательские типы конфиденциальной информации остаются актуальными и применимыми при смене сотрудников, пациентов или клиентов, а также при изменении записей.</span><span class="sxs-lookup"><span data-stu-id="631ae-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="631ae-123">Вы также можете использовать классификацию на основе EDM с политиками, такими как [политики защиты от потери данных](data-loss-prevention-policies.md) (DLP) или [политики файлов Microsoft Cloud App Security](/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="631ae-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="631ae-124">Служба защиты информации Microsoft 365 поддерживает в предварительной версии языки с двухбайтовой кодировкой:</span><span class="sxs-lookup"><span data-stu-id="631ae-124">Microsoft 365 Information Protection supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="631ae-125">Китайский (упрощенное письмо)</span><span class="sxs-lookup"><span data-stu-id="631ae-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="631ae-126">Китайский (традиционное письмо)</span><span class="sxs-lookup"><span data-stu-id="631ae-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="631ae-127">Корейский</span><span class="sxs-lookup"><span data-stu-id="631ae-127">Korean</span></span>
> - <span data-ttu-id="631ae-128">Японский</span><span class="sxs-lookup"><span data-stu-id="631ae-128">Japanese</span></span>
> 
> <span data-ttu-id="631ae-129">Эта поддержка доступна для конфиденциальных типов информации.</span><span class="sxs-lookup"><span data-stu-id="631ae-129">This support is available for sensitive information types.</span></span> <span data-ttu-id="631ae-130">Дополнительные сведения см. в статье [Заметки о выпуске: поддержка защиты информации для наборов двухбайтовых символов (предварительная версия)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="631ae-130">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="631ae-131">Обязательные лицензии и разрешения</span><span class="sxs-lookup"><span data-stu-id="631ae-131">Required licenses and permissions</span></span>

<span data-ttu-id="631ae-132">Для выполнения задач, описанных в данной статье, вы должны быть глобальным администратором, администратором соответствия требованиям или администратором Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="631ae-132">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="631ae-133">Дополнительные сведения о разрешениях DLP см. в разделе [Разрешения](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="631ae-133">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="631ae-134">Классификация на основе EDM включена в следующие подписки:</span><span class="sxs-lookup"><span data-stu-id="631ae-134">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="631ae-135">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="631ae-135">Office 365 E5</span></span>
- <span data-ttu-id="631ae-136">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="631ae-136">Microsoft 365 E5</span></span>
- <span data-ttu-id="631ae-137">Соответствие требованиям Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="631ae-137">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="631ae-138">Защита информации и управление данными в Microsoft E5/A5</span><span class="sxs-lookup"><span data-stu-id="631ae-138">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="631ae-139">Ссылки на портал для вашей подписки</span><span class="sxs-lookup"><span data-stu-id="631ae-139">Portal links for your subscription</span></span>


|<span data-ttu-id="631ae-140">Портал</span><span class="sxs-lookup"><span data-stu-id="631ae-140">Portal</span></span>  |<span data-ttu-id="631ae-141">Интернет/GCC</span><span class="sxs-lookup"><span data-stu-id="631ae-141">World Wide/GCC</span></span>  |<span data-ttu-id="631ae-142">GCC High</span><span class="sxs-lookup"><span data-stu-id="631ae-142">GCC-High</span></span>  |<span data-ttu-id="631ae-143">DOD</span><span class="sxs-lookup"><span data-stu-id="631ae-143">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="631ae-144">Office SCC</span><span class="sxs-lookup"><span data-stu-id="631ae-144">Office SCC</span></span>     |  <span data-ttu-id="631ae-145">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="631ae-145">protection.office.com</span></span>       |<span data-ttu-id="631ae-146">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="631ae-146">scc.office365.us</span></span>         |<span data-ttu-id="631ae-147">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="631ae-147">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="631ae-148">Центр безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="631ae-148">Microsoft 365 Security center</span></span>     |<span data-ttu-id="631ae-149">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="631ae-149">security.microsoft.com</span></span>         |<span data-ttu-id="631ae-150">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="631ae-150">security.microsoft.us</span></span>         |<span data-ttu-id="631ae-151">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="631ae-151">security.apps.mil</span></span>|
|<span data-ttu-id="631ae-152">Центр соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="631ae-152">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="631ae-153">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="631ae-153">compliance.microsoft.com</span></span>         |<span data-ttu-id="631ae-154">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="631ae-154">compliance.microsoft.us</span></span>         |<span data-ttu-id="631ae-155">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="631ae-155">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="631ae-156">Обзор рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="631ae-156">The work flow at a glance</span></span>

|<span data-ttu-id="631ae-157">Этап</span><span class="sxs-lookup"><span data-stu-id="631ae-157">Phase</span></span>  |<span data-ttu-id="631ae-158">Требуемые параметры</span><span class="sxs-lookup"><span data-stu-id="631ae-158">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="631ae-159">Часть 1. Настройка классификации на основе EDM</span><span class="sxs-lookup"><span data-stu-id="631ae-159">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="631ae-160">(При необходимости)</span><span class="sxs-lookup"><span data-stu-id="631ae-160">(As needed)</span></span><br/><span data-ttu-id="631ae-161">- [Изменение схемы базы данных](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="631ae-161">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="631ae-162">- [Удаление схемы](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="631ae-162">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="631ae-163">– Доступ для чтения конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="631ae-163">- Read access to the sensitive data</span></span><br/><span data-ttu-id="631ae-164">– Схема базы данных в формате XML (доступен пример)</span><span class="sxs-lookup"><span data-stu-id="631ae-164">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="631ae-165">– Пакет правил в формате XML (доступен пример)</span><span class="sxs-lookup"><span data-stu-id="631ae-165">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="631ae-166">– Разрешения администратора на доступ к Центру безопасности и соответствия требованиям (с помощью PowerShell)</span><span class="sxs-lookup"><span data-stu-id="631ae-166">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="631ae-167">Часть 2. Хеширование и отправка конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="631ae-167">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="631ae-168">(При необходимости)</span><span class="sxs-lookup"><span data-stu-id="631ae-168">(As needed)</span></span><br/>[<span data-ttu-id="631ae-169">Обновление данных</span><span class="sxs-lookup"><span data-stu-id="631ae-169">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="631ae-170">– Настраиваемая группа безопасности и учетная запись пользователя</span><span class="sxs-lookup"><span data-stu-id="631ae-170">- Custom security group and user account</span></span><br/><span data-ttu-id="631ae-171">– Доступ локального администратора к компьютеру с агентом отправки EDM</span><span class="sxs-lookup"><span data-stu-id="631ae-171">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="631ae-172">– Доступ для чтения конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="631ae-172">- Read access to the sensitive data</span></span><br/><span data-ttu-id="631ae-173">– Процесс и расписание для обновления данных</span><span class="sxs-lookup"><span data-stu-id="631ae-173">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="631ae-174">Часть 3. Использование классификации на основе EDM с помощью облачных служб Майкрософт</span><span class="sxs-lookup"><span data-stu-id="631ae-174">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="631ae-175">– Подписка на Microsoft 365 с DLP</span><span class="sxs-lookup"><span data-stu-id="631ae-175">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="631ae-176">– Включенная функция классификации на основе EDM</span><span class="sxs-lookup"><span data-stu-id="631ae-176">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="631ae-177">Часть 1. Настройка классификации на основе EDM</span><span class="sxs-lookup"><span data-stu-id="631ae-177">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="631ae-178">Установка и настройка классификации на основе EDM включает:</span><span class="sxs-lookup"><span data-stu-id="631ae-178">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="631ae-179">Сохранение конфиденциальных данных в формате CSV</span><span class="sxs-lookup"><span data-stu-id="631ae-179">Saving sensitive data in .csv format</span></span>](#save-sensitive-data-in-csv-format)
2. [<span data-ttu-id="631ae-180">Определение схемы для базы данных конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="631ae-180">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="631ae-181">Создание пакета правил</span><span class="sxs-lookup"><span data-stu-id="631ae-181">Create a rule package</span></span>](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-format"></a><span data-ttu-id="631ae-182">Сохранение конфиденциальных данных в формате CSV</span><span class="sxs-lookup"><span data-stu-id="631ae-182">Save sensitive data in .csv format</span></span>

1. <span data-ttu-id="631ae-183">Определите конфиденциальную информацию, которую нужно использовать.</span><span class="sxs-lookup"><span data-stu-id="631ae-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="631ae-184">Экспортируйте данные в приложение, например Microsoft Excel, и сохраните файл в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="631ae-184">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="631ae-185">Файл данных может содержать:</span><span class="sxs-lookup"><span data-stu-id="631ae-185">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="631ae-186">до 100 миллионов строк конфиденциальных данных;</span><span class="sxs-lookup"><span data-stu-id="631ae-186">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="631ae-187">до 32 столбцов (полей) на источник данных;</span><span class="sxs-lookup"><span data-stu-id="631ae-187">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="631ae-188">до 5 столбцов (полей), отмеченных как доступные для поиска.</span><span class="sxs-lookup"><span data-stu-id="631ae-188">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="631ae-189">Структурируйте конфиденциальные данные в CSV-файле таким образом, чтобы первая строка включала имена полей, которые используются для классификации на основе EDM.</span><span class="sxs-lookup"><span data-stu-id="631ae-189">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="631ae-190">В CSV-файле можно применять такие имена полей, как ssn, birthdate, firstname, lastname.</span><span class="sxs-lookup"><span data-stu-id="631ae-190">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="631ae-191">В названиях заголовков столбцов не должно быть пробелов и символов подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="631ae-191">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="631ae-192">Например, используемый в этой статье пример CSV-файла называется *PatientRecords.csv*, а его столбцы включают *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN* и другие.</span><span class="sxs-lookup"><span data-stu-id="631ae-192">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="631ae-193">Обратите внимание на формат полей конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="631ae-193">Pay attention to the format of the sensitive data fields.</span></span> <span data-ttu-id="631ae-194">В частности, поля, в содержимом которых могут использоваться запятые (например, почтовый адрес, содержащий значение "Сиэтл, Вашингтон"), будут рассматриваться как два отдельных поля при анализе инструментом EDM.</span><span class="sxs-lookup"><span data-stu-id="631ae-194">In particular, fields that may contain commas in their content (e.g. a street address that contains the value "Seattle,WA") would be parsed as two separate fields when parsed by the EDM tool.</span></span> <span data-ttu-id="631ae-195">Чтобы этого избежать, необходимо убедиться в том, что такие поля заключены в одинарные или двойные кавычки в таблице конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="631ae-195">In order to avoid this, you need to ensure such fields are surrounded by single or double quotes in the sensitive data table.</span></span> <span data-ttu-id="631ae-196">Если поля с запятыми могут содержать также пробелы, следует создать пользовательский тип конфиденциальных данных соответствующего формата (например, строка из нескольких слов с запятыми и пробелами), чтобы обеспечить правильное сопоставление строки при сканировании документа.</span><span class="sxs-lookup"><span data-stu-id="631ae-196">If fields with commas in them may also contain spaces, you would need to create a custom Sensitive Information Type that matches the corresponding format (e.g. a multi-word string with commas and spaces in it) to ensure the string is correctly matched when the document is scanned.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="631ae-197">Определение схемы для базы данных конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="631ae-197">Define the schema for your database of sensitive information</span></span>

<span data-ttu-id="631ae-198">Если по деловым или техническим причинам вы не используете PowerShell или командную строку для создания схемы и шаблона типа конфиденциальной информации EDM (пакет правил), используйте для их создания [схему точного соответствия данных и мастер типов конфиденциальной информации](sit-edm-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="631ae-198">If for business or technical reasons, you prefer not to use PowerShell or command line to create your schema and EDM sensitive info type pattern (rule package), you can use the [Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) to create them.</span></span> <span data-ttu-id="631ae-199">После создания схемы и шаблона типа конфиденциальной информации EDM, вернитесь, чтобы выполнить все шаги, необходимые для того, чтобы сделать ваш тип конфиденциальной информации на основе EDM доступным для использования.</span><span class="sxs-lookup"><span data-stu-id="631ae-199">When you are done creating the schema and EDM sensitive info type pattern, return to complete all the steps necessary to make your EDM based sensitive information type available for use.</span></span>

> [!NOTE]
> <span data-ttu-id="631ae-200">Мастер схемы точного соответствия данных и типа конфиденциальной информации доступен только для облаков World Wide и GCC.</span><span class="sxs-lookup"><span data-stu-id="631ae-200">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

1. <span data-ttu-id="631ae-201">Определите схему для базы данных конфиденциальной информации в формате XML (как в примере ниже).</span><span class="sxs-lookup"><span data-stu-id="631ae-201">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="631ae-202">Назовите этот файл схемы **edm.xml** и настройте его так, чтобы для каждого столбца в базе данных была строка, использующая синтаксис:</span><span class="sxs-lookup"><span data-stu-id="631ae-202">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="631ae-203">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="631ae-203">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="631ae-204">Используйте имена столбцов для значений *Field name*.</span><span class="sxs-lookup"><span data-stu-id="631ae-204">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="631ae-205">Используйте параметр *searchable="true"* для 5 полей, которые должны поддерживать поиск.</span><span class="sxs-lookup"><span data-stu-id="631ae-205">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="631ae-206">По крайней мере одно поле должно поддерживать поиск.</span><span class="sxs-lookup"><span data-stu-id="631ae-206">At least one field must be searchable.</span></span>

      <span data-ttu-id="631ae-207">Например, следующий XML-файл определяет схему для базы данных записей пациентов с пятью полями, для которых указывается возможность поиска: *PatientID*, *MRN*, *SSN*, *Phone* и *DOB*.</span><span class="sxs-lookup"><span data-stu-id="631ae-207">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="631ae-208">(Вы можете скопировать, изменить и использовать наш пример.)</span><span class="sxs-lookup"><span data-stu-id="631ae-208">(You can copy, modify, and use our example.)</span></span>

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

##### <a name="configurable-match-using-the-caseinsensitive-and-ignoreddelimiters-fields"></a><span data-ttu-id="631ae-209">Настраиваемое совпадение с использованием полей caseInsensitive и ignoredDelimiters </span><span class="sxs-lookup"><span data-stu-id="631ae-209">Configurable match using the caseInsensitive and ignoredDelimiters fields</span></span>

<span data-ttu-id="631ae-210">В приведенном выше примере XML используются поля `caseInsensitive` и `ignoredDelimiters`.</span><span class="sxs-lookup"><span data-stu-id="631ae-210">The above XML sample makes use of the `caseInsensitive` and the `ignoredDelimiters` fields.</span></span> 

<span data-ttu-id="631ae-211">При включении поля \***caseInsensitive** _, для которого задано значение `true` в определении схемы, EDM не будет исключать элемент на основе различий для поля `PatientID`.</span><span class="sxs-lookup"><span data-stu-id="631ae-211">When you include the \***caseInsensitive** _ field set to the value of `true` in your schema definition, EDM will not exclude an item based on case differences for `PatientID` field.</span></span> <span data-ttu-id="631ae-212">Так, EDM будет рассматривать `PatientID` _ *FOO-1234*\* и **fOo-1234** как идентичные.</span><span class="sxs-lookup"><span data-stu-id="631ae-212">So EDM will see, `PatientID` _ *FOO-1234*\* and **fOo-1234** as being identical.</span></span>

<span data-ttu-id="631ae-213">При включении поля **ignoredDelimiters** _ с поддерживаемыми символами EDM игнорирует эти символы в `PatientID`.</span><span class="sxs-lookup"><span data-stu-id="631ae-213">When you include the \***ignoredDelimiters** _ field with supported characters,  EDM will ignore those characters in the `PatientID`.</span></span> <span data-ttu-id="631ae-214">Так, EDM будет рассматривать `PatientID` _ *FOO-1234*\* и `PatientID` **FOO#1234** как идентичные.</span><span class="sxs-lookup"><span data-stu-id="631ae-214">So EDM will see, `PatientID` _ *FOO-1234*\* and `PatientID` **FOO#1234** as being identical.</span></span> <span data-ttu-id="631ae-215">Флаг `ignoredDelimiters` поддерживает любые не буквенно-цифровые символы. Вот несколько примеров:</span><span class="sxs-lookup"><span data-stu-id="631ae-215">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="631ae-216">\.</span><span class="sxs-lookup"><span data-stu-id="631ae-216">\.</span></span>
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

- <span data-ttu-id="631ae-217">Флаг `ignoredDelimiters` не поддерживает:</span><span class="sxs-lookup"><span data-stu-id="631ae-217">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="631ae-218">символы от 0 до 9</span><span class="sxs-lookup"><span data-stu-id="631ae-218">characters 0-9</span></span>
- <span data-ttu-id="631ae-219">От А до Я</span><span class="sxs-lookup"><span data-stu-id="631ae-219">A-Z</span></span>
- <span data-ttu-id="631ae-220">от a до z</span><span class="sxs-lookup"><span data-stu-id="631ae-220">a-z</span></span>
- \"
- \,

<span data-ttu-id="631ae-221">В этом примере, где используются оба `caseInsensitive` и `ignoredDelimiters`, EDM будет рассматривать **FOO-1234** и **fOo#1234** как идентичные и классифицировать элемент как тип конфиденциальной информации из карты пациента.</span><span class="sxs-lookup"><span data-stu-id="631ae-221">In this example, where both `caseInsensitive` and `ignoredDelimiters` are used, EDM would see **FOO-1234** and **fOo#1234** as  identical and classify the item as a patient record sensitive information type.</span></span> 

4. <span data-ttu-id="631ae-222">Подключитесь к Центру безопасности и соответствия требованиям, используя процедуры, описанные в статье [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="631ae-222">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

5. <span data-ttu-id="631ae-223">Чтобы добавить схему базы данных, выполните по отдельности указанные ниже командлеты.</span><span class="sxs-lookup"><span data-stu-id="631ae-223">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="631ae-224">Появится запрос на подтверждение, показанный ниже.</span><span class="sxs-lookup"><span data-stu-id="631ae-224">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="631ae-225">Подтверждение</span><span class="sxs-lookup"><span data-stu-id="631ae-225">Confirm</span></span>
      >
      > <span data-ttu-id="631ae-226">Вы действительно хотите выполнить это действие?</span><span class="sxs-lookup"><span data-stu-id="631ae-226">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="631ae-227">Будет импортирована новая схема модели EDM для хранилища данных "patientrecords".</span><span class="sxs-lookup"><span data-stu-id="631ae-227">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="631ae-228">\[Y\] Да \[A\] Да для всех \[N\] Нет \[L\] Нет для всех \[?\] Справка (значение по умолчанию "Y"):</span><span class="sxs-lookup"><span data-stu-id="631ae-228">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="631ae-229">Чтобы изменения вносились без запроса подтверждения, используйте вместо командлета, указанного в действии 5, следующий: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="631ae-229">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="631ae-230">Обновление EDMSchema с дополнениями может занять от 10 до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="631ae-230">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="631ae-231">Перед выполнением действий, в которых используется дополнение, необходимо выполнить обновление.</span><span class="sxs-lookup"><span data-stu-id="631ae-231">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="631ae-232">Настройка пакета правил</span><span class="sxs-lookup"><span data-stu-id="631ae-232">Set up a rule package</span></span>

1. <span data-ttu-id="631ae-233">Создайте пакет правил в формате XML (в кодировке Юникод), как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="631ae-233">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="631ae-234">(Вы можете скопировать, изменить и использовать наш пример.)</span><span class="sxs-lookup"><span data-stu-id="631ae-234">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="631ae-235">Настраивая пакет правил, убедитесь, что в нем используются правильные ссылки на CSV-файл и файл **edm.xml**.</span><span class="sxs-lookup"><span data-stu-id="631ae-235">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="631ae-236">Вы можете скопировать, изменить и использовать наш пример.</span><span class="sxs-lookup"><span data-stu-id="631ae-236">You can copy, modify, and use our example.</span></span> <span data-ttu-id="631ae-237">В этом примере XML для создания типа конфиденциальной информации EDM должны быть настроены перечисленные ниже поля.</span><span class="sxs-lookup"><span data-stu-id="631ae-237">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="631ae-238">**Идентификаторы RulePack и ExactMatch**. Используйте командлет [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) для создания GUID.</span><span class="sxs-lookup"><span data-stu-id="631ae-238">**RulePack id & ExactMatch id**: Use [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="631ae-239">**Datastore**. В этом поле указывается, какое хранилище данных подстановки EDM будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="631ae-239">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="631ae-240">Вы указываете имя источника данных для настроенной схемы EDM.</span><span class="sxs-lookup"><span data-stu-id="631ae-240">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="631ae-241">**idMatch**. Это поле указывает на основной элемент EDM.</span><span class="sxs-lookup"><span data-stu-id="631ae-241">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="631ae-242">Matches. Указывает поле, которое будет использоваться при точном поиске.</span><span class="sxs-lookup"><span data-stu-id="631ae-242">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="631ae-243">Вы указываете имя поля для поиска в схеме EDM для DataStore.</span><span class="sxs-lookup"><span data-stu-id="631ae-243">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="631ae-244">Classification. В этом поле указывается соответствие типа конфиденциальной информации, которое активирует поиск EDM.</span><span class="sxs-lookup"><span data-stu-id="631ae-244">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="631ae-245">Вы можете указать имя или идентификатор GUID имеющегося встроенного или настраиваемого типа конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="631ae-245">You can provide the Name or GUID of an existing built-in or custom sensitive information type.</span></span> <span data-ttu-id="631ae-246">Следует учитывать, что любая строка, соответствующая указанному типу конфиденциальной информации, будет хэшироваться и сравниваться с каждым элементом таблицы конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="631ae-246">Be aware that any string that matches the sensitive information type provided will be hashed and compared to every entry in the sensitive information table.</span></span> <span data-ttu-id="631ae-247">Чтобы избежать проблем с производительностью, при использовании настраиваемого типа конфиденциальной информации в качестве элемента классификации в EDM избегайте использования типов, которым будет соответствовать значительная часть содержимого (например, "любая цифра" или "любое слово из пяти букв"), добавляя вспомогательные ключевые слова или включая элементы форматирования в определение настраиваемого типа конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="631ae-247">In order to avoid causing performance issues, if you use a custom sensitive information type as the Classification element in EDM, avoid using one that will match a large percentage of content (such as "any number" or "any five-letter word") by adding supporting keywords or including formatting in the definition of the custom classification sensitive information type.</span></span> 

      - <span data-ttu-id="631ae-248">**Match**. В этом поле указываются дополнительные свидетельства, находящиеся близко к idMatch.</span><span class="sxs-lookup"><span data-stu-id="631ae-248">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="631ae-249">Matches. Вы указываете имя поля для поиска в схеме EDM для DataStore.</span><span class="sxs-lookup"><span data-stu-id="631ae-249">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="631ae-250">**Resource**. В этом разделе указываются имя и описание типа конфиденциальной информации в нескольких языковых средах.</span><span class="sxs-lookup"><span data-stu-id="631ae-250">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="631ae-251">idRef. Укажите GUID для идентификатора ExactMatch.</span><span class="sxs-lookup"><span data-stu-id="631ae-251">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="631ae-252">Имена & описания: настройте в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="631ae-252">Name & descriptions: customize as required.</span></span>

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

2. <span data-ttu-id="631ae-253">Отправьте пакет правил, выполнив по отдельности указанные ниже командлеты PowerShell.</span><span class="sxs-lookup"><span data-stu-id="631ae-253">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="631ae-254">На этом этапе вы настроили классификацию на основе EDM.</span><span class="sxs-lookup"><span data-stu-id="631ae-254">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="631ae-255">На следующем этапе необходимо хешировать конфиденциальные данные, а затем отправить хеши на индексацию.</span><span class="sxs-lookup"><span data-stu-id="631ae-255">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="631ae-256">Хотим еще раз напомнить, что схема PatientRecords определяет как доступные для поиска пять полей: *PatientID*, *MRN*, *SSN*, *Phone* и *DOB*.</span><span class="sxs-lookup"><span data-stu-id="631ae-256">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="631ae-257">Наш пакет правил, созданный для примера, включает эти пять полей и ссылается на файл схемы базы данных (**edm.xml**), предусматривая один элемент *ExactMatch* для каждого доступного для поиска поля.</span><span class="sxs-lookup"><span data-stu-id="631ae-257">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="631ae-258">Рассмотрим следующий элемент ExactMatch:</span><span class="sxs-lookup"><span data-stu-id="631ae-258">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="631ae-259">В этом примере обратите внимание, что:</span><span class="sxs-lookup"><span data-stu-id="631ae-259">In this example, note that:</span></span>

- <span data-ttu-id="631ae-260">Имя хранилища данных dataStore ссылается на ранее созданный файл CSV: **dataStore = "PatientRecords"**.</span><span class="sxs-lookup"><span data-stu-id="631ae-260">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="631ae-261">Значение idMatch ссылается на доступное для поиска поле, которое указано в файле схемы базы данных: **idMatch matches = "SSN"**.</span><span class="sxs-lookup"><span data-stu-id="631ae-261">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="631ae-262">Значение классификации ссылается на существующий или пользовательский тип конфиденциальной информации: **classification = "U.S. Social Security Number (SSN)"**.</span><span class="sxs-lookup"><span data-stu-id="631ae-262">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="631ae-263">(В этом случае используется существующий тип конфиденциальной информации, содержащий номер социального страхования США.)</span><span class="sxs-lookup"><span data-stu-id="631ae-263">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="631ae-264">Обновление EDMSchema с дополнениями может занять от 10 до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="631ae-264">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="631ae-265">Перед выполнением действий, в которых используется дополнение, необходимо выполнить обновление.</span><span class="sxs-lookup"><span data-stu-id="631ae-265">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="631ae-266">Редактирование схемы для классификации на основе EDM</span><span class="sxs-lookup"><span data-stu-id="631ae-266">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="631ae-267">Если нужно внести изменения в файл **edm.xml**, например изменить поля, используемые для классификации на основе EDM, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="631ae-267">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

> [!TIP]
> <span data-ttu-id="631ae-268">Схему EDM и файл данных можно изменить, чтобы воспользоваться **настраиваемым совпадением**.</span><span class="sxs-lookup"><span data-stu-id="631ae-268">You can change your EDM schema and data file to take advantage of **configurable match**.</span></span> <span data-ttu-id="631ae-269">При настройке EDM будет игнорировать различия в регистре и некоторые разделители при оценке элемента.</span><span class="sxs-lookup"><span data-stu-id="631ae-269">When configured, EDM will ignore case differences and some delimiters when it evaluates an item.</span></span> <span data-ttu-id="631ae-270">Это упрощает определение схемы XML и файлов конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="631ae-270">This makes defining your xml schema and your sensitive data files easier.</span></span> <span data-ttu-id="631ae-271">Дополнительные сведения см. в статье [Изменение схемы точного соответствия данных для использования настраиваемого совпадения](sit-modify-edm-schema-configurable-match.md).</span><span class="sxs-lookup"><span data-stu-id="631ae-271">To learn more see, [Modify Exact Data Match schema to use configurable match](sit-modify-edm-schema-configurable-match.md).</span></span>

1. <span data-ttu-id="631ae-272">Внесите изменения в файл **edm.xml** (он рассматривается в разделе [Определение схемы](#define-the-schema-for-your-database-of-sensitive-information) в этой статье).</span><span class="sxs-lookup"><span data-stu-id="631ae-272">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="631ae-273">Подключитесь к Центру безопасности и соответствия требованиям, используя процедуры, описанные в статье [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="631ae-273">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="631ae-274">Чтобы обновить схему базы данных, выполните по отдельности указанные ниже командлеты.</span><span class="sxs-lookup"><span data-stu-id="631ae-274">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="631ae-275">Появится запрос на подтверждение, показанный ниже.</span><span class="sxs-lookup"><span data-stu-id="631ae-275">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="631ae-276">Подтверждение</span><span class="sxs-lookup"><span data-stu-id="631ae-276">Confirm</span></span>
      >
      > <span data-ttu-id="631ae-277">Вы действительно хотите выполнить это действие?</span><span class="sxs-lookup"><span data-stu-id="631ae-277">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="631ae-278">Схема модели EDM для хранилища данных "patientrecords" будет обновлена.</span><span class="sxs-lookup"><span data-stu-id="631ae-278">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="631ae-279">\[Y\] Да \[A\] Да для всех \[N\] Нет \[L\] Нет для всех \[?\] Справка (значение по умолчанию "Y"):</span><span class="sxs-lookup"><span data-stu-id="631ae-279">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="631ae-280">Чтобы изменения вносились без запроса подтверждения, используйте вместо командлета, указанного в действии 3, следующий: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="631ae-280">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="631ae-281">Обновление EDMSchema с дополнениями может занять от 10 до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="631ae-281">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="631ae-282">Перед выполнением действий, в которых используется дополнение, необходимо выполнить обновление.</span><span class="sxs-lookup"><span data-stu-id="631ae-282">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="631ae-283">Удаление схемы для классификации на основе EDM</span><span class="sxs-lookup"><span data-stu-id="631ae-283">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="631ae-284">(При необходимости.) Чтобы удалить схему, используемую для классификации на основе EDM, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="631ae-284">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="631ae-285">Подключитесь к Центру безопасности и соответствия требованиям, используя процедуры, описанные в статье [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="631ae-285">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="631ae-286">Выполните следующие командлеты PowerShell, заменив имя хранилища данных "patient records" на имя удаляемого хранилища.</span><span class="sxs-lookup"><span data-stu-id="631ae-286">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="631ae-287">Появится запрос на подтверждение:</span><span class="sxs-lookup"><span data-stu-id="631ae-287">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="631ae-288">Подтверждение</span><span class="sxs-lookup"><span data-stu-id="631ae-288">Confirm</span></span>
      >
      > <span data-ttu-id="631ae-289">Вы действительно хотите выполнить это действие?</span><span class="sxs-lookup"><span data-stu-id="631ae-289">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="631ae-290">Схема модели EDM для хранилища данных "patientrecords" будет удалена.</span><span class="sxs-lookup"><span data-stu-id="631ae-290">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="631ae-291">\[Y\] Да \[A\] Да для всех \[N\] Нет \[L\] Нет для всех \[?\] Справка (значение по умолчанию "Y"):</span><span class="sxs-lookup"><span data-stu-id="631ae-291">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="631ae-292">Чтобы изменения вносились без запроса подтверждения, используйте вместо командлета, указанного в действии 2, следующий: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="631ae-292">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="631ae-293">Часть 2. Хеширование и отправка конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="631ae-293">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="631ae-294">На этом этапе выполняется настройка пользовательской группы безопасности и учетной записи пользователя, а также настройка агента отправки EDM.</span><span class="sxs-lookup"><span data-stu-id="631ae-294">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="631ae-295">Затем применяется средство для хеширования конфиденциальных данных с использованием значения соли и выполняется их отправка.</span><span class="sxs-lookup"><span data-stu-id="631ae-295">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="631ae-296">Хеширование и отправку можно выполнить на одном компьютере, или вы можете отделить этап хеширования от этапа отправки для дополнительной безопасности.</span><span class="sxs-lookup"><span data-stu-id="631ae-296">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="631ae-297">Если вы хотите выполнить хеширование и отправку с одного компьютера, нужно делать это на компьютере, который может напрямую подключаться к вашему клиенту Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="631ae-297">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="631ae-298">Для этого требуется, чтобы ваши файлы с конфиденциальными данными в виде обычного текста находились на этом компьютере для хеширования.</span><span class="sxs-lookup"><span data-stu-id="631ae-298">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="631ae-299">Если вы не хотите предоставлять свой файл с конфиденциальными данными в виде обычного текста, вы можете хешировать его на компьютере в безопасном расположении, а затем скопировать хеш-файл и файл соли на компьютер, который может напрямую подключаться к клиенту Microsoft 365 для отправки.</span><span class="sxs-lookup"><span data-stu-id="631ae-299">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload.</span></span> <span data-ttu-id="631ae-300">В этом сценарии вам потребуется EDMUploadAgent на обоих компьютерах.</span><span class="sxs-lookup"><span data-stu-id="631ae-300">In this scenario, you will need the EDMUploadAgent on both computers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="631ae-301">Если вы использовали мастер схемы точного соответствия данных и типов конфиденциальной информации для создания схемы и файлов шаблонов, вам \***необходимо** загрузить схему для этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="631ae-301">If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, you \***must** download the schema for this procedure.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="631ae-302">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="631ae-302">Prerequisites</span></span>

- <span data-ttu-id="631ae-303">рабочая или учебная учетная запись для Microsoft 365, которая будет добавлена в группу безопасности **EDM\_DataUploaders**;</span><span class="sxs-lookup"><span data-stu-id="631ae-303">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="631ae-304">компьютер с Windows 10 или Windows Server 2016 с .NET версии 4.6.2 для запуска EDMUploadAgent;</span><span class="sxs-lookup"><span data-stu-id="631ae-304">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="631ae-305">каталог на компьютере отправки для следующего:</span><span class="sxs-lookup"><span data-stu-id="631ae-305">a directory on your upload machine for the:</span></span>
    -  <span data-ttu-id="631ae-306">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="631ae-306">EDMUploadAgent</span></span>
    - <span data-ttu-id="631ae-307">файл конфиденциального элемента в формате CSV. **PatientRecords.csv** в наших примерах;</span><span class="sxs-lookup"><span data-stu-id="631ae-307">your sensitive item file in csv format **PatientRecords.csv** in our examples</span></span>
    -  <span data-ttu-id="631ae-308">выходной хеш-файл и файл соли;</span><span class="sxs-lookup"><span data-stu-id="631ae-308">and the output hash and salt files</span></span>
    - <span data-ttu-id="631ae-309">имя хранилища данных из файла **edm.xml**. В этом примере: `PatientRecords`.</span><span class="sxs-lookup"><span data-stu-id="631ae-309">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>
- <span data-ttu-id="631ae-310">Если вы использовали [мастер схемы точного соответствия данных и типа конфиденциальной информации](sit-edm-wizard.md), вам ***необходимо*** загрузить его</span><span class="sxs-lookup"><span data-stu-id="631ae-310">If you used the [Exact Data Match schema and sensitive information type wizard](sit-edm-wizard.md) you ***must*** download it</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="631ae-311">Настройка группы безопасности и учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="631ae-311">Set up the security group and user account</span></span>

1. <span data-ttu-id="631ae-312">Как глобальный администратор перейдите в центр администрирования с помощью соответствующей [ссылки для вашей подписки](#portal-links-for-your-subscription) и [создайте группу безопасности](/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) с именем **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="631ae-312">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="631ae-313">Добавьте одного или нескольких пользователей в группу безопасности **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="631ae-313">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="631ae-314">(Эти пользователи будут управлять базой данных конфиденциальной информации.)</span><span class="sxs-lookup"><span data-stu-id="631ae-314">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="631ae-315">Хеширование и отправка с одного компьютера</span><span class="sxs-lookup"><span data-stu-id="631ae-315">Hash and upload from one computer</span></span>

<span data-ttu-id="631ae-316">Этот компьютер должен иметь прямой доступ к вашему клиенту Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="631ae-316">This computer must have direct access to your Microsoft 365 tenant.</span></span>

>[!NOTE]
> <span data-ttu-id="631ae-317">Перед началом этой процедуры убедитесь, что вы являетесь участником группы безопасности **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="631ae-317">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>

> [!TIP]
> <span data-ttu-id="631ae-318">При желании можно запустить проверку CSV-файла перед загрузкой, запустив:</span><span class="sxs-lookup"><span data-stu-id="631ae-318">Optionally, you can run a validation against your csv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
><span data-ttu-id="631ae-319">Для получения дополнительной информации обо всех поддерживаемых параметрах EdmUploadAgent.exe> запустите</span><span class="sxs-lookup"><span data-stu-id="631ae-319">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`


#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="631ae-320">Ссылки на агента отправки EDM по типу подписки</span><span class="sxs-lookup"><span data-stu-id="631ae-320">Links to EDM upload agent by subscription type</span></span>

- <span data-ttu-id="631ae-321">[Коммерческий + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) — для большинства коммерческих клиентов;</span><span class="sxs-lookup"><span data-stu-id="631ae-321">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
- <span data-ttu-id="631ae-322">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) — специально для пользователей облачного хранилища для правительственных органов с высоким уровнем безопасности;</span><span class="sxs-lookup"><span data-stu-id="631ae-322">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
- <span data-ttu-id="631ae-323">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) — специально для пользователей облачного хранилища для Министерства обороны США.</span><span class="sxs-lookup"><span data-stu-id="631ae-323">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

1. <span data-ttu-id="631ae-324">Создайте рабочий каталог для EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="631ae-324">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="631ae-325">Например, **C:\EDM\Data**.</span><span class="sxs-lookup"><span data-stu-id="631ae-325">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="631ae-326">Поместите туда файл **PatientRecords.csv**.</span><span class="sxs-lookup"><span data-stu-id="631ae-326">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="631ae-327">Скачайте и установите соответствующий [агент отправки EDM](#links-to-edm-upload-agent-by-subscription-type) для своей подписки в каталог, созданный на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="631ae-327">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

   > [!NOTE]
   > <span data-ttu-id="631ae-328">EDMUploadAgent по ссылкам выше обновлен, чтобы автоматически добавить значение соли в хешированные данные.</span><span class="sxs-lookup"><span data-stu-id="631ae-328">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="631ae-329">Кроме того, вы можете указать собственное значение соли.</span><span class="sxs-lookup"><span data-stu-id="631ae-329">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="631ae-330">После использования этой версии вы не сможете применить предыдущую версию EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="631ae-330">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
   >
   > <span data-ttu-id="631ae-331">Вы можете отправлять данные с помощью EDMUploadAgent в любое указанное хранилище данных только дважды в день.</span><span class="sxs-lookup"><span data-stu-id="631ae-331">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

   > [!TIP]
   > <span data-ttu-id="631ae-332">Чтобы получить список поддерживаемых параметров команды, запустите агент без аргументов.</span><span class="sxs-lookup"><span data-stu-id="631ae-332">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="631ae-333">Например, EdmUploadAgent.exe.</span><span class="sxs-lookup"><span data-stu-id="631ae-333">For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="631ae-334">Авторизуйте агент отправки EDM, откройте окно командной строки (как администратор), переключитесь на каталог **C:\EDM\Data** и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="631ae-334">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="631ae-335">Войдите с помощью своей рабочей или учебной учетной записи Microsoft 365, добавленной в группу безопасности EDM_DataUploaders.</span><span class="sxs-lookup"><span data-stu-id="631ae-335">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="631ae-336">Сведения о вашем клиенте извлекаются из учетной записи пользователя для выполнения подключения.</span><span class="sxs-lookup"><span data-stu-id="631ae-336">Your tenant information is extracted from the user account to make the connection.</span></span>

   <span data-ttu-id="631ae-337">НЕОБЯЗАТЕЛЬНО. Если вы использовали мастер схемы точного соответствия данных и типов конфиденциальной информации для создания схемы и файлов шаблонов, запустите следующую команду в окне командной строки:</span><span class="sxs-lookup"><span data-stu-id="631ae-337">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

   `EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>`

4. <span data-ttu-id="631ae-338">Чтобы хешировать и отправить конфиденциальные данные, выполните следующую команду в окне командной строки:</span><span class="sxs-lookup"><span data-stu-id="631ae-338">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

   `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file]`

   <span data-ttu-id="631ae-339">Пример: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span><span class="sxs-lookup"><span data-stu-id="631ae-339">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span></span>

   <span data-ttu-id="631ae-340">Это автоматически добавит в хеш случайно созданное значение соли, чтобы повысить безопасность.</span><span class="sxs-lookup"><span data-stu-id="631ae-340">This will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="631ae-341">Если вы хотите использовать собственное значение соли, добавьте **/Salt<saltvalue>** в команду.</span><span class="sxs-lookup"><span data-stu-id="631ae-341">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="631ae-342">Это значение должно состоять из 64 символов и может содержать только символы a–z и 0–9.</span><span class="sxs-lookup"><span data-stu-id="631ae-342">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

5. <span data-ttu-id="631ae-343">Проверьте состояние отправки, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="631ae-343">Check the upload status by running this command:</span></span>

   `EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

   <span data-ttu-id="631ae-344">Пример: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="631ae-344">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

   <span data-ttu-id="631ae-345">Найдите состояние **ProcessingInProgress**.</span><span class="sxs-lookup"><span data-stu-id="631ae-345">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="631ae-346">Повторяйте попытку каждые несколько минут, пока состояние не изменится на **Completed**.</span><span class="sxs-lookup"><span data-stu-id="631ae-346">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="631ae-347">Когда отобразится завершенное состояние, ваши данные EDM готовы к использованию.</span><span class="sxs-lookup"><span data-stu-id="631ae-347">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="631ae-348">Раздельное хеширование и отправка</span><span class="sxs-lookup"><span data-stu-id="631ae-348">Separate Hash and upload</span></span>

<span data-ttu-id="631ae-349">Выполняйте хеширование на компьютере в безопасной среде.</span><span class="sxs-lookup"><span data-stu-id="631ae-349">Perform the hash on a computer in a secure environment.</span></span>

<span data-ttu-id="631ae-350">НЕОБЯЗАТЕЛЬНО. Если вы использовали мастер схемы точного соответствия данных и типов конфиденциальной информации для создания схемы и файлов шаблонов, запустите следующую команду в окне командной строки:</span><span class="sxs-lookup"><span data-stu-id="631ae-350">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

`EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>`

1. <span data-ttu-id="631ae-351">В окне командной строки выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="631ae-351">Run the following command in Command Prompt windows:</span></span>

   `EdmUploadAgent.exe /CreateHash /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] >`

   <span data-ttu-id="631ae-352">Например:</span><span class="sxs-lookup"><span data-stu-id="631ae-352">For example:</span></span>

   > <span data-ttu-id="631ae-353">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span><span class="sxs-lookup"><span data-stu-id="631ae-353">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span></span>

   <span data-ttu-id="631ae-354">Результатом будет хешированный файл и файл соли с этими расширениями, если вы не указали параметр **/Salt<saltvalue>**:</span><span class="sxs-lookup"><span data-stu-id="631ae-354">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>
   - <span data-ttu-id="631ae-355">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="631ae-355">.EdmHash</span></span>
   - <span data-ttu-id="631ae-356">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="631ae-356">.EdmSalt</span></span>

2. <span data-ttu-id="631ae-357">Безопасно скопируйте эти файлы на компьютер, который вы используете для отправки CSV-файла с конфиденциальными элементами (PatientRecords) в свой клиент.</span><span class="sxs-lookup"><span data-stu-id="631ae-357">Copy these files in a secure fashion to the computer you will use to upload your sensitive items csv file (PatientRecords) to your tenant.</span></span>

   <span data-ttu-id="631ae-358">Чтобы отправить хешированные данные, выполните следующую команду в командной строке Windows:</span><span class="sxs-lookup"><span data-stu-id="631ae-358">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

   `EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

   <span data-ttu-id="631ae-359">Например:</span><span class="sxs-lookup"><span data-stu-id="631ae-359">For example:</span></span>

   > <span data-ttu-id="631ae-360">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="631ae-360">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


   <span data-ttu-id="631ae-361">Чтобы убедиться, что конфиденциальные данные были отправлены, выполните следующую команду в окне командной строки:</span><span class="sxs-lookup"><span data-stu-id="631ae-361">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>

   `EdmUploadAgent.exe /GetDataStore`

   <span data-ttu-id="631ae-362">Появится список хранилищ данных и время их последнего обновления.</span><span class="sxs-lookup"><span data-stu-id="631ae-362">You'll see a list of data stores and when they were last updated.</span></span>

   <span data-ttu-id="631ae-363">Если вы хотите просмотреть все отправки данных в определенное хранилище, выполните следующую команду в командной строке Windows:</span><span class="sxs-lookup"><span data-stu-id="631ae-363">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

   `EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

   <span data-ttu-id="631ae-364">Перейдите к настройке процесса и расписания для [обновления базы данных конфиденциальной информации](#refreshing-your-sensitive-information-database).</span><span class="sxs-lookup"><span data-stu-id="631ae-364">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="631ae-365">На этом этапе вы готовы использовать классификацию на основе EDM с помощью облачных служб Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="631ae-365">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="631ae-366">Например, вы можете [настроить политику защиты от потери данных с помощью классификации на основе EDM](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="631ae-366">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="631ae-367">Обновление базы данных конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="631ae-367">Refreshing your sensitive information database</span></span>

<span data-ttu-id="631ae-368">Вы можете обновлять базу данных конфиденциальной информации ежедневно, а средство отправки EDM может повторно индексировать конфиденциальные данные и повторно отправлять индексированные данные.</span><span class="sxs-lookup"><span data-stu-id="631ae-368">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="631ae-369">Определите процесс и частоту (ежедневно или еженедельно) обновления базы данных конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="631ae-369">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="631ae-370">Повторно экспортируйте конфиденциальные данные в приложение, например Microsoft Excel, и сохраните файл в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="631ae-370">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="631ae-371">Не изменяйте имя и расположение файла, которые использовались при выполнении действий, описанных в разделе [Хеширование и отправка конфиденциальных данных](#part-2-hash-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="631ae-371">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="631ae-372">Если в структуру (имена полей) CSV-файла не вносится никаких изменений, то вам не нужно вносить изменения в файл схемы базы данных при обновлении данных.</span><span class="sxs-lookup"><span data-stu-id="631ae-372">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="631ae-373">Но если нужно внести изменения, измените схему базы данных и пакет правил соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="631ae-373">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="631ae-374">Используйте [планировщик заданий](/windows/desktop/TaskSchd/task-scheduler-start-page) для автоматизации действий 2 и 3 в процедуре [хеширования и отправки конфиденциальных данных](#part-2-hash-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="631ae-374">Use [Task Scheduler](/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="631ae-375">Вы можете планировать задачи с помощью нескольких методов:</span><span class="sxs-lookup"><span data-stu-id="631ae-375">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="631ae-376">Метод</span><span class="sxs-lookup"><span data-stu-id="631ae-376">Method</span></span>             | <span data-ttu-id="631ae-377">Действия</span><span class="sxs-lookup"><span data-stu-id="631ae-377">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="631ae-378">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="631ae-378">Windows PowerShell</span></span>     | <span data-ttu-id="631ae-379">См. документацию по [ScheduledTasks](/powershell/module/scheduledtasks/?view=win10-ps) и [пример скрипта PowerShell](#example-powershell-script-for-task-scheduler) в этой статье</span><span class="sxs-lookup"><span data-stu-id="631ae-379">See the [ScheduledTasks](/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="631ae-380">API планировщика заданий</span><span class="sxs-lookup"><span data-stu-id="631ae-380">Task Scheduler API</span></span>     | <span data-ttu-id="631ae-381">См. документацию по [планировщику заданий](/windows/desktop/TaskSchd/using-the-task-scheduler)</span><span class="sxs-lookup"><span data-stu-id="631ae-381">See the [Task Scheduler](/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="631ae-382">Пользовательский интерфейс Windows</span><span class="sxs-lookup"><span data-stu-id="631ae-382">Windows user interface</span></span> | <span data-ttu-id="631ae-383">В Windows нажмите **Пуск** и введите "Планировщик заданий".</span><span class="sxs-lookup"><span data-stu-id="631ae-383">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="631ae-384">Затем в списке результатов щелкните правой кнопкой мыши **Планировщик заданий** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="631ae-384">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="631ae-385">Пример скрипта PowerShell для планировщика заданий</span><span class="sxs-lookup"><span data-stu-id="631ae-385">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="631ae-386">Этот раздел содержит пример скрипта PowerShell, который можно использовать для планирования задач по хешированию данных и отправке хешированных данных:</span><span class="sxs-lookup"><span data-stu-id="631ae-386">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="631ae-387">Планирование хеширования и отправки одним действием</span><span class="sxs-lookup"><span data-stu-id="631ae-387">To schedule hashing and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$schemaext = '.xml'
\# Assuming CSV file name is same as data store name
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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="631ae-388">Планирование хеширования и отправки отдельными действиями</span><span class="sxs-lookup"><span data-stu-id="631ae-388">To schedule hashing and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
$schemaext = '.xml'
\# Assuming CSV file name is same as data store name
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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="631ae-389">Часть 3. Использование классификации на основе EDM с помощью облачных служб Майкрософт</span><span class="sxs-lookup"><span data-stu-id="631ae-389">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="631ae-390">Типы конфиденциальной информации EDM поддерживаются для следующих расположений::</span><span class="sxs-lookup"><span data-stu-id="631ae-390">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="631ae-391">DLP для Exchange Online (электронная почта)</span><span class="sxs-lookup"><span data-stu-id="631ae-391">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="631ae-392">OneDrive для бизнеса (файлы)</span><span class="sxs-lookup"><span data-stu-id="631ae-392">OneDrive for Business (files)</span></span>
- <span data-ttu-id="631ae-393">Microsoft Teams (беседы)</span><span class="sxs-lookup"><span data-stu-id="631ae-393">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="631ae-394">DLP для SharePoint (файлы)</span><span class="sxs-lookup"><span data-stu-id="631ae-394">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="631ae-395">Политики DLP Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="631ae-395">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="631ae-396">Типы конфиденциальной информации EDM для указанных ниже сценариев сейчас находятся в процессе разработки и пока недоступны.</span><span class="sxs-lookup"><span data-stu-id="631ae-396">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="631ae-397">Автоматическая классификация меток конфиденциальности и хранения</span><span class="sxs-lookup"><span data-stu-id="631ae-397">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="631ae-398">Создание политики защиты от потери данных с EDM</span><span class="sxs-lookup"><span data-stu-id="631ae-398">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="631ae-399">Перейдите в Центр безопасности и соответствия требованиям, воспользовавшись соответствующей [ссылкой для вашей подписки](#portal-links-for-your-subscription).</span><span class="sxs-lookup"><span data-stu-id="631ae-399">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="631ae-400">Выберите **Защита от потери данных** \> **Политика**.</span><span class="sxs-lookup"><span data-stu-id="631ae-400">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="631ae-401">Нажмите **Создание политики** \> **Custom** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="631ae-401">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="631ae-402">На вкладке **Назовите политику** укажите название и описание, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="631ae-402">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="631ae-403">На вкладке **Выберите расположения** щелкните **Позволить мне выбрать расположения** и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="631ae-403">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="631ae-404">В столбце **Состояние** выберите **электронную почту Exchange, учетные записи OneDrive, сообщение из чатов и каналов Teams**, а затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="631ae-404">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message**, and then choose **Next**.</span></span>

7. <span data-ttu-id="631ae-405">На вкладке **Параметры политики** установите флажок **Использование дополнительных параметров** и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="631ae-405">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="631ae-406">Нажмите кнопку **+ Создать правило**.</span><span class="sxs-lookup"><span data-stu-id="631ae-406">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="631ae-407">В разделе **Название** укажите название и описание для правила.</span><span class="sxs-lookup"><span data-stu-id="631ae-407">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="631ae-408">В разделе **Условия** в списке **+ Добавить условие** выберите вариант **Содержит типы конфиденциальной информации**.</span><span class="sxs-lookup"><span data-stu-id="631ae-408">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![Контент содержит типы конфиденциальной информации](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="631ae-410">Найдите тип конфиденциальной информации, созданный при настройке пакета правил, и нажмите кнопку **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="631ae-410">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="631ae-411">Затем нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="631ae-411">Then choose **Done**.</span></span>

12. <span data-ttu-id="631ae-412">Завершите выбор параметров для правила, таких как **Уведомления пользователей**, **Переопределения пользователя**, **Отчеты об инцидентах** и т. д., и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="631ae-412">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="631ae-413">На вкладке **Параметры политики** проверьте свои правила и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="631ae-413">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="631ae-414">Укажите, включить ли политику сразу, проверить ее или оставить выключенной.</span><span class="sxs-lookup"><span data-stu-id="631ae-414">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="631ae-415">Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="631ae-415">Then choose **Next**.</span></span>

15. <span data-ttu-id="631ae-416">На вкладке **Проверьте параметры** просмотрите свою политику.</span><span class="sxs-lookup"><span data-stu-id="631ae-416">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="631ae-417">Внесите любые необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="631ae-417">Make any needed changes.</span></span> <span data-ttu-id="631ae-418">После завершения нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="631ae-418">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="631ae-419">Потребуется примерно один час, чтобы новая политика защиты от потери данных распространилась по центру обработки данных.</span><span class="sxs-lookup"><span data-stu-id="631ae-419">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="631ae-420">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="631ae-420">Related articles</span></span>

- [<span data-ttu-id="631ae-421">Определения типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="631ae-421">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="631ae-422">Сведения о типах конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="631ae-422">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="631ae-423">Обзор политик защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="631ae-423">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="631ae-424">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="631ae-424">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="631ae-425">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="631ae-425">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)
- <span data-ttu-id="631ae-426">[Изменение схемы точного соответствия данных для использования настраиваемого совпадения](sit-modify-edm-schema-configurable-match.md).</span><span class="sxs-lookup"><span data-stu-id="631ae-426">[Modify Exact Data Match schema to use configurable match](sit-modify-edm-schema-configurable-match.md)</span></span>