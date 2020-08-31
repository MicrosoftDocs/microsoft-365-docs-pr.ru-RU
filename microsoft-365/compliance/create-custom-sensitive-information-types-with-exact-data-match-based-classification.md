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
ms.openlocfilehash: f4bbbe8726370297e9ef6317cd468789bb3b3bfe
ms.sourcegitcommit: 97ef8f846939c3d31bb0638edf07bb89463ace0b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300437"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="4e490-103">Создание пользовательских типов конфиденциальной информации с помощью классификации на основе точного совпадения данных</span><span class="sxs-lookup"><span data-stu-id="4e490-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="4e490-104">[Пользовательские типы конфиденциальной информации](custom-sensitive-info-types.md) используются для определения конфиденциальных элементов, чтобы предотвратить непреднамеренное или неприемлемое предоставление к ним общего доступа.</span><span class="sxs-lookup"><span data-stu-id="4e490-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="4e490-105">Вы определяете пользовательский тип конфиденциальной информации на основе следующего:</span><span class="sxs-lookup"><span data-stu-id="4e490-105">You define a custom sensitive information type based on:</span></span>

- <span data-ttu-id="4e490-106">шаблоны;</span><span class="sxs-lookup"><span data-stu-id="4e490-106">patterns</span></span>
- <span data-ttu-id="4e490-107">ключевое слово, например  *сотрудник*,  *эмблема* или *идентификатор*;</span><span class="sxs-lookup"><span data-stu-id="4e490-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="4e490-108">близкое расположение символов, свидетельствующее об определенном шаблоне;</span><span class="sxs-lookup"><span data-stu-id="4e490-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="4e490-109">доверительные уровни.</span><span class="sxs-lookup"><span data-stu-id="4e490-109">confidence levels</span></span>

 <span data-ttu-id="4e490-110">Такие пользовательские типы конфиденциальной информации соответствуют бизнес-требованиям большинства организаций.</span><span class="sxs-lookup"><span data-stu-id="4e490-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="4e490-111">Но что если вам нужен пользовательский тип конфиденциальной информации, использующий точные значения данных, а не ищущий сопоставления на основе универсальных шаблонов?</span><span class="sxs-lookup"><span data-stu-id="4e490-111">But what if you wanted a custom sensitive information type that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="4e490-112">С помощью классификации на основе точного совпадения данных (EDM) вы можете создать пользовательский тип конфиденциальной информации с такими характеристиками:</span><span class="sxs-lookup"><span data-stu-id="4e490-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="4e490-113">динамичный и обновляемый;</span><span class="sxs-lookup"><span data-stu-id="4e490-113">be dynamic and refreshable</span></span>
- <span data-ttu-id="4e490-114">дополнительные возможности масштабирования;</span><span class="sxs-lookup"><span data-stu-id="4e490-114">be more scalable</span></span>
- <span data-ttu-id="4e490-115">снижает число ошибочно положительных результатов;</span><span class="sxs-lookup"><span data-stu-id="4e490-115">result in fewer false-positives</span></span>
- <span data-ttu-id="4e490-116">поддерживает структурированные конфиденциальные данные;</span><span class="sxs-lookup"><span data-stu-id="4e490-116">work with structured sensitive data</span></span>
- <span data-ttu-id="4e490-117">более безопасная обработка конфиденциальной информации;</span><span class="sxs-lookup"><span data-stu-id="4e490-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="4e490-118">использование с несколькими облачными службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4e490-118">be used with several Microsoft cloud services</span></span>

![Классификация на основе EDM](../media/EDMClassification.png)

<span data-ttu-id="4e490-120">Классификация на основе EDM позволяет создавать пользовательские типы конфиденциальной информации, ссылающиеся на точные значения в базе данных конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="4e490-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="4e490-121">Базу данных можно обновлять ежедневно, и она может содержать до 100 миллионов строк данных.</span><span class="sxs-lookup"><span data-stu-id="4e490-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="4e490-122">Таким образом, ваши пользовательские типы конфиденциальной информации остаются актуальными и применимыми при смене сотрудников, пациентов или клиентов, а также при изменении записей.</span><span class="sxs-lookup"><span data-stu-id="4e490-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="4e490-123">Вы также можете использовать классификацию на основе EDM с политиками, такими как [политики защиты от потери данных](data-loss-prevention-policies.md) (DLP) или [политики файлов Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="4e490-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="4e490-124">Служба защиты информации Microsoft 365 теперь поддерживает в предварительный версии языки с  	набором двухбайтовых символов:</span><span class="sxs-lookup"><span data-stu-id="4e490-124">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="4e490-125">Китайский (упрощенное письмо)</span><span class="sxs-lookup"><span data-stu-id="4e490-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="4e490-126">Китайский (традиционное письмо)</span><span class="sxs-lookup"><span data-stu-id="4e490-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="4e490-127">Корейский</span><span class="sxs-lookup"><span data-stu-id="4e490-127">Korean</span></span>
> - <span data-ttu-id="4e490-128">Японский</span><span class="sxs-lookup"><span data-stu-id="4e490-128">Japanese</span></span>
> 
><span data-ttu-id="4e490-129">Эта предварительная версия доступна только в коммерческом облаке, а развертывание ограничено следующими странами:</span><span class="sxs-lookup"><span data-stu-id="4e490-129">This preview is only in the commercial cloud and the rollout is limited to:</span></span>
> - <span data-ttu-id="4e490-130">Япония</span><span class="sxs-lookup"><span data-stu-id="4e490-130">Japan</span></span>
> - <span data-ttu-id="4e490-131">Республика Корея</span><span class="sxs-lookup"><span data-stu-id="4e490-131">Korea</span></span>
> - <span data-ttu-id="4e490-132">Китай</span><span class="sxs-lookup"><span data-stu-id="4e490-132">China</span></span>
> - <span data-ttu-id="4e490-133">Гонконг</span><span class="sxs-lookup"><span data-stu-id="4e490-133">Hong Kong</span></span>
> - <span data-ttu-id="4e490-134">Макао</span><span class="sxs-lookup"><span data-stu-id="4e490-134">Macau</span></span>
> - <span data-ttu-id="4e490-135">Тайвань</span><span class="sxs-lookup"><span data-stu-id="4e490-135">Taiwan</span></span>
>
><span data-ttu-id="4e490-136">Эта поддержка доступна для конфиденциальных типов информации.</span><span class="sxs-lookup"><span data-stu-id="4e490-136">This support is available for sensitive information types.</span></span> <span data-ttu-id="4e490-137">Дополнительные сведения см. в статье [Заметки о выпуске: поддержка защиты информации для наборов двухбайтовых символов (предварительная версия)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="4e490-137">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="4e490-138">Обязательные лицензии и разрешения</span><span class="sxs-lookup"><span data-stu-id="4e490-138">Required licenses and permissions</span></span>

<span data-ttu-id="4e490-139">Для выполнения задач, описанных в данной статье, вы должны быть глобальным администратором, администратором соответствия требованиям или администратором Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4e490-139">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="4e490-140">Дополнительные сведения о разрешениях DLP см. в разделе [Разрешения](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="4e490-140">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="4e490-141">Классификация на основе EDM включена в следующие подписки:</span><span class="sxs-lookup"><span data-stu-id="4e490-141">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="4e490-142">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="4e490-142">Office 365 E5</span></span>
- <span data-ttu-id="4e490-143">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4e490-143">Microsoft 365 E5</span></span>
- <span data-ttu-id="4e490-144">Соответствие требованиям Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4e490-144">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="4e490-145">Защита информации и управление данными в Microsoft E5/A5</span><span class="sxs-lookup"><span data-stu-id="4e490-145">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="4e490-146">Ссылки на портал для вашей подписки</span><span class="sxs-lookup"><span data-stu-id="4e490-146">Portal links for your subscription</span></span>


|<span data-ttu-id="4e490-147">Портал</span><span class="sxs-lookup"><span data-stu-id="4e490-147">Portal</span></span>  |<span data-ttu-id="4e490-148">Интернет/GCC</span><span class="sxs-lookup"><span data-stu-id="4e490-148">World Wide/GCC</span></span>  |<span data-ttu-id="4e490-149">GCC High</span><span class="sxs-lookup"><span data-stu-id="4e490-149">GCC-High</span></span>  |<span data-ttu-id="4e490-150">DOD</span><span class="sxs-lookup"><span data-stu-id="4e490-150">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="4e490-151">Office SCC</span><span class="sxs-lookup"><span data-stu-id="4e490-151">Office SCC</span></span>     |  <span data-ttu-id="4e490-152">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="4e490-152">protection.office.com</span></span>       |<span data-ttu-id="4e490-153">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="4e490-153">scc.office365.us</span></span>         |<span data-ttu-id="4e490-154">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="4e490-154">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="4e490-155">Центр безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e490-155">Microsoft 365 Security center</span></span>     |<span data-ttu-id="4e490-156">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4e490-156">security.microsoft.com</span></span>         |<span data-ttu-id="4e490-157">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="4e490-157">security.microsoft.us</span></span>         |<span data-ttu-id="4e490-158">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="4e490-158">security.apps.mil</span></span>|
|<span data-ttu-id="4e490-159">Центр соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e490-159">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="4e490-160">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4e490-160">compliance.microsoft.com</span></span>         |<span data-ttu-id="4e490-161">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="4e490-161">compliance.microsoft.us</span></span>         |<span data-ttu-id="4e490-162">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="4e490-162">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="4e490-163">Обзор рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="4e490-163">The work flow at a glance</span></span>

|<span data-ttu-id="4e490-164">Этап</span><span class="sxs-lookup"><span data-stu-id="4e490-164">Phase</span></span>  |<span data-ttu-id="4e490-165">Требуемые параметры</span><span class="sxs-lookup"><span data-stu-id="4e490-165">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="4e490-166">Часть 1. Настройка классификации на основе EDM</span><span class="sxs-lookup"><span data-stu-id="4e490-166">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="4e490-167">(При необходимости)</span><span class="sxs-lookup"><span data-stu-id="4e490-167">(As needed)</span></span><br/><span data-ttu-id="4e490-168">- [Изменение схемы базы данных](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="4e490-168">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="4e490-169">- [Удаление схемы](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="4e490-169">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="4e490-170">– Доступ для чтения конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="4e490-170">- Read access to the sensitive data</span></span><br/><span data-ttu-id="4e490-171">– Схема базы данных в формате XML (доступен пример)</span><span class="sxs-lookup"><span data-stu-id="4e490-171">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="4e490-172">– Пакет правил в формате XML (доступен пример)</span><span class="sxs-lookup"><span data-stu-id="4e490-172">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="4e490-173">– Разрешения администратора на доступ к Центру безопасности и соответствия требованиям (с помощью PowerShell)</span><span class="sxs-lookup"><span data-stu-id="4e490-173">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="4e490-174">Часть 2. Хеширование и отправка конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="4e490-174">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="4e490-175">(При необходимости)</span><span class="sxs-lookup"><span data-stu-id="4e490-175">(As needed)</span></span><br/>[<span data-ttu-id="4e490-176">Обновление данных</span><span class="sxs-lookup"><span data-stu-id="4e490-176">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="4e490-177">– Настраиваемая группа безопасности и учетная запись пользователя</span><span class="sxs-lookup"><span data-stu-id="4e490-177">- Custom security group and user account</span></span><br/><span data-ttu-id="4e490-178">– Доступ локального администратора к компьютеру с агентом отправки EDM</span><span class="sxs-lookup"><span data-stu-id="4e490-178">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="4e490-179">– Доступ для чтения конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="4e490-179">- Read access to the sensitive data</span></span><br/><span data-ttu-id="4e490-180">– Процесс и расписание для обновления данных</span><span class="sxs-lookup"><span data-stu-id="4e490-180">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="4e490-181">Часть 3. Использование классификации на основе EDM с помощью облачных служб Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4e490-181">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="4e490-182">– Подписка на Microsoft 365 с DLP</span><span class="sxs-lookup"><span data-stu-id="4e490-182">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="4e490-183">– Включенная функция классификации на основе EDM</span><span class="sxs-lookup"><span data-stu-id="4e490-183">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="4e490-184">Часть 1. Настройка классификации на основе EDM</span><span class="sxs-lookup"><span data-stu-id="4e490-184">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="4e490-185">Установка и настройка классификации на основе EDM включает:</span><span class="sxs-lookup"><span data-stu-id="4e490-185">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="4e490-186">Сохранение конфиденциальных данных в формате CSV</span><span class="sxs-lookup"><span data-stu-id="4e490-186">Saving sensitive data in .csv format</span></span>](#save-sensitive-data-in-csv-format)
2. [<span data-ttu-id="4e490-187">Определение схемы для базы данных конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="4e490-187">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="4e490-188">Создание пакета правил</span><span class="sxs-lookup"><span data-stu-id="4e490-188">Create a rule package</span></span>](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-format"></a><span data-ttu-id="4e490-189">Сохранение конфиденциальных данных в формате CSV</span><span class="sxs-lookup"><span data-stu-id="4e490-189">Save sensitive data in .csv format</span></span>

1. <span data-ttu-id="4e490-190">Определите конфиденциальную информацию, которую нужно использовать.</span><span class="sxs-lookup"><span data-stu-id="4e490-190">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="4e490-191">Экспортируйте данные в приложение, например Microsoft Excel, и сохраните файл в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="4e490-191">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="4e490-192">Файл данных может содержать:</span><span class="sxs-lookup"><span data-stu-id="4e490-192">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="4e490-193">до 100 миллионов строк конфиденциальных данных;</span><span class="sxs-lookup"><span data-stu-id="4e490-193">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="4e490-194">до 32 столбцов (полей) на источник данных;</span><span class="sxs-lookup"><span data-stu-id="4e490-194">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="4e490-195">до 5 столбцов (полей), отмеченных как доступные для поиска.</span><span class="sxs-lookup"><span data-stu-id="4e490-195">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="4e490-196">Структурируйте конфиденциальные данные в CSV-файле таким образом, чтобы первая строка включала имена полей, которые используются для классификации на основе EDM.</span><span class="sxs-lookup"><span data-stu-id="4e490-196">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="4e490-197">В CSV-файле можно применять такие имена полей, как ssn, birthdate, firstname, lastname.</span><span class="sxs-lookup"><span data-stu-id="4e490-197">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="4e490-198">В названиях заголовков столбцов не должно быть пробелов и символов подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="4e490-198">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="4e490-199">Например, используемый в этой статье пример CSV-файла называется  *PatientRecords.csv*, а его столбцы включают *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN* и другие.</span><span class="sxs-lookup"><span data-stu-id="4e490-199">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="4e490-200">Определение схемы для базы данных конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="4e490-200">Define the schema for your database of sensitive information</span></span>

3. <span data-ttu-id="4e490-201">Определите схему для базы данных конфиденциальной информации в формате XML (как в примере ниже).</span><span class="sxs-lookup"><span data-stu-id="4e490-201">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="4e490-202">Назовите этот файл схемы  **edm.xml** и настройте его так, чтобы для каждого столбца в базе данных была строка, использующая синтаксис:</span><span class="sxs-lookup"><span data-stu-id="4e490-202">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="4e490-203">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="4e490-203">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="4e490-204">Используйте имена столбцов для значений *Field name* .</span><span class="sxs-lookup"><span data-stu-id="4e490-204">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="4e490-205">Используйте параметр *searchable="true"* для 5 полей, которые должны поддерживать поиск.</span><span class="sxs-lookup"><span data-stu-id="4e490-205">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="4e490-206">По крайней мере одно поле должно поддерживать поиск.</span><span class="sxs-lookup"><span data-stu-id="4e490-206">At least one field must be searchable.</span></span>

      <span data-ttu-id="4e490-207">Например, в следующем XML-файле определяется схема для базы данных записей пациентов с пятью полями, поддерживающими поиск: *PatientID*, *MRN*, *SSN*, *Phone* и *DOB*.</span><span class="sxs-lookup"><span data-stu-id="4e490-207">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="4e490-208">(Вы можете скопировать, изменить и использовать наш пример.)</span><span class="sxs-lookup"><span data-stu-id="4e490-208">(You can copy, modify, and use our example.)</span></span>

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

4. <span data-ttu-id="4e490-209">Подключитесь к Центру безопасности и соответствия требованиям, используя процедуры, описанные в статье [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="4e490-209">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

5. <span data-ttu-id="4e490-210">Чтобы добавить схему базы данных, выполните по отдельности указанные ниже командлеты.</span><span class="sxs-lookup"><span data-stu-id="4e490-210">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="4e490-211">Появится запрос на подтверждение, показанный ниже.</span><span class="sxs-lookup"><span data-stu-id="4e490-211">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="4e490-212">Подтверждение</span><span class="sxs-lookup"><span data-stu-id="4e490-212">Confirm</span></span>
      >
      > <span data-ttu-id="4e490-213">Вы действительно хотите выполнить это действие?</span><span class="sxs-lookup"><span data-stu-id="4e490-213">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="4e490-214">Будет импортирована новая схема модели EDM для хранилища данных "patientrecords".</span><span class="sxs-lookup"><span data-stu-id="4e490-214">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="4e490-215">\[Y\] Да \[A\] Да для всех \[N\] Нет \[L\] Нет для всех \[?\] Справка (значение по умолчанию "Y"):</span><span class="sxs-lookup"><span data-stu-id="4e490-215">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="4e490-216">Чтобы изменения вносились без запроса подтверждения, используйте вместо указанного в действии 5 командлета следующий: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="4e490-216">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="4e490-217">Обновление EDMSchema с дополнениями может занять от 10 до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="4e490-217">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="4e490-218">Перед выполнением действий, в которых используется дополнение, необходимо выполнить обновление.</span><span class="sxs-lookup"><span data-stu-id="4e490-218">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="4e490-219">Настройка пакета правил</span><span class="sxs-lookup"><span data-stu-id="4e490-219">Set up a rule package</span></span>

1. <span data-ttu-id="4e490-220">Создайте пакет правил в формате XML (в кодировке Юникод), как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="4e490-220">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="4e490-221">(Вы можете скопировать, изменить и использовать наш пример.)</span><span class="sxs-lookup"><span data-stu-id="4e490-221">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="4e490-222">Настраивая пакет правил, убедитесь, что в нем используются правильные ссылки на CSV-файл и файл **edm.xml**.</span><span class="sxs-lookup"><span data-stu-id="4e490-222">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="4e490-223">Вы можете скопировать, изменить и использовать наш пример.</span><span class="sxs-lookup"><span data-stu-id="4e490-223">You can copy, modify, and use our example.</span></span> <span data-ttu-id="4e490-224">В этом примере XML для создания типа конфиденциальной информации EDM должны быть настроены перечисленные ниже поля.</span><span class="sxs-lookup"><span data-stu-id="4e490-224">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="4e490-225">**Идентификаторы RulePack и ExactMatch**. Используйте командлет [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) для создания GUID.</span><span class="sxs-lookup"><span data-stu-id="4e490-225">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="4e490-226">**Datastore**. В этом поле указывается, какое хранилище данных подстановки EDM будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="4e490-226">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="4e490-227">Вы указываете имя источника данных для настроенной схемы EDM.</span><span class="sxs-lookup"><span data-stu-id="4e490-227">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="4e490-228">**idMatch**. Это поле указывает на основной элемент EDM.</span><span class="sxs-lookup"><span data-stu-id="4e490-228">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="4e490-229">Matches. Указывает поле, которое будет использоваться при точном поиске.</span><span class="sxs-lookup"><span data-stu-id="4e490-229">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="4e490-230">Вы указываете имя поля для поиска в схеме EDM для DataStore.</span><span class="sxs-lookup"><span data-stu-id="4e490-230">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="4e490-231">Classification. В этом поле указывается соответствие типа конфиденциальной информации, которое активирует поиск EDM.</span><span class="sxs-lookup"><span data-stu-id="4e490-231">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="4e490-232">Вы можете указать имя или идентификатор GUID имеющейся встроенной или настраиваемой классификации.</span><span class="sxs-lookup"><span data-stu-id="4e490-232">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="4e490-233">**Match**. В этом поле указываются дополнительные свидетельства, находящиеся близко к idMatch.</span><span class="sxs-lookup"><span data-stu-id="4e490-233">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="4e490-234">Matches. Вы указываете имя поля для поиска в схеме EDM для DataStore.</span><span class="sxs-lookup"><span data-stu-id="4e490-234">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="4e490-235">**Resource**. В этом разделе указываются имя и описание типа конфиденциальной информации в нескольких языковых средах.</span><span class="sxs-lookup"><span data-stu-id="4e490-235">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="4e490-236">idRef. Укажите GUID для идентификатора ExactMatch.</span><span class="sxs-lookup"><span data-stu-id="4e490-236">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="4e490-237">Имена & описания: настройте в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="4e490-237">Name & descriptions: customize as required.</span></span>

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

1. <span data-ttu-id="4e490-238">Отправьте пакет правил, выполнив по отдельности указанные ниже командлеты PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e490-238">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="4e490-239">На этом этапе вы настроили классификацию на основе EDM.</span><span class="sxs-lookup"><span data-stu-id="4e490-239">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="4e490-240">На следующем этапе необходимо хешировать конфиденциальные данные, а затем отправить хеши на индексацию.</span><span class="sxs-lookup"><span data-stu-id="4e490-240">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="4e490-241">Помните, что схема PatientRecords определяет пять полей как доступные для поиска:  *PatientID*,  *MRN*,  *SSN*,  *Phone* и  *DOB*.</span><span class="sxs-lookup"><span data-stu-id="4e490-241">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="4e490-242">В нашем примере пакет правил включает эти поля и ссылки на файл схемы базы данных (**edm.xml**), предусматривая один элемент *ExactMatch* для каждого доступного для поиска поля.</span><span class="sxs-lookup"><span data-stu-id="4e490-242">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="4e490-243">Рассмотрим следующий элемент ExactMatch:</span><span class="sxs-lookup"><span data-stu-id="4e490-243">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="4e490-244">В этом примере обратите внимание, что:</span><span class="sxs-lookup"><span data-stu-id="4e490-244">In this example, note that:</span></span>

- <span data-ttu-id="4e490-245">Имя хранилища данных dataStore ссылается на ранее созданный файл CSV:  **dataStore = "PatientRecords"**.</span><span class="sxs-lookup"><span data-stu-id="4e490-245">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="4e490-246">Значение idMatch ссылается на доступное для поиска поле, которое указано в файле схемы базы данных: **idMatch matches = "SSN"**.</span><span class="sxs-lookup"><span data-stu-id="4e490-246">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="4e490-247">Значение классификации ссылается на существующий или пользовательский тип конфиденциальной информации:  **classification = "U.S. Social Security Number (SSN)"**.</span><span class="sxs-lookup"><span data-stu-id="4e490-247">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="4e490-248">(В этом случае используется существующий тип конфиденциальной информации, содержащий номер социального страхования США.)</span><span class="sxs-lookup"><span data-stu-id="4e490-248">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="4e490-249">Обновление EDMSchema с дополнениями может занять от 10 до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="4e490-249">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="4e490-250">Перед выполнением действий, в которых используется дополнение, необходимо выполнить обновление.</span><span class="sxs-lookup"><span data-stu-id="4e490-250">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="4e490-251">Редактирование схемы для классификации на основе EDM</span><span class="sxs-lookup"><span data-stu-id="4e490-251">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="4e490-252">Если нужно внести изменения в файл **edm.xml**, например изменить поля, используемые для классификации на основе EDM, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4e490-252">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="4e490-253">Измените файл **edm.xml** (файл, обсуждаемый в разделе [Определение схемы](#define-the-schema-for-your-database-of-sensitive-information)  этой статьи).</span><span class="sxs-lookup"><span data-stu-id="4e490-253">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="4e490-254">Подключитесь к Центру безопасности и соответствия требованиям, используя процедуры, описанные в статье [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="4e490-254">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="4e490-255">Чтобы обновить схему базы данных, выполните по отдельности указанные ниже командлеты.</span><span class="sxs-lookup"><span data-stu-id="4e490-255">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="4e490-256">Появится запрос на подтверждение, показанный ниже.</span><span class="sxs-lookup"><span data-stu-id="4e490-256">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="4e490-257">Подтверждение</span><span class="sxs-lookup"><span data-stu-id="4e490-257">Confirm</span></span>
      >
      > <span data-ttu-id="4e490-258">Вы действительно хотите выполнить это действие?</span><span class="sxs-lookup"><span data-stu-id="4e490-258">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="4e490-259">Схема модели EDM для хранилища данных "patientrecords" будет обновлена.</span><span class="sxs-lookup"><span data-stu-id="4e490-259">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="4e490-260">\[Y\] Да \[A\] Да для всех \[N\] Нет \[L\] Нет для всех \[?\] Справка (значение по умолчанию "Y"):</span><span class="sxs-lookup"><span data-stu-id="4e490-260">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="4e490-261">Чтобы изменения вносились без запроса подтверждения, используйте вместо указанного в действии 3 командлета следующий: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="4e490-261">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="4e490-262">Обновление EDMSchema с дополнениями может занять от 10 до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="4e490-262">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="4e490-263">Перед выполнением действий, в которых используется дополнение, необходимо выполнить обновление.</span><span class="sxs-lookup"><span data-stu-id="4e490-263">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="4e490-264">Удаление схемы для классификации на основе EDM</span><span class="sxs-lookup"><span data-stu-id="4e490-264">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="4e490-265">(При необходимости.) Чтобы удалить схему, используемую для классификации на основе EDM, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4e490-265">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="4e490-266">Подключитесь к Центру безопасности и соответствия требованиям, используя процедуры, описанные в статье [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="4e490-266">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="4e490-267">Выполните следующие командлеты PowerShell, заменив имя хранилища данных "patient records" на имя удаляемого хранилища.</span><span class="sxs-lookup"><span data-stu-id="4e490-267">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="4e490-268">Появится запрос на подтверждение:</span><span class="sxs-lookup"><span data-stu-id="4e490-268">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="4e490-269">Подтверждение</span><span class="sxs-lookup"><span data-stu-id="4e490-269">Confirm</span></span>
      >
      > <span data-ttu-id="4e490-270">Вы действительно хотите выполнить это действие?</span><span class="sxs-lookup"><span data-stu-id="4e490-270">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="4e490-271">Схема модели EDM для хранилища данных "patientrecords" будет удалена.</span><span class="sxs-lookup"><span data-stu-id="4e490-271">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="4e490-272">\[Y\] Да \[A\] Да для всех \[N\] Нет \[L\] Нет для всех \[?\] Справка (значение по умолчанию "Y"):</span><span class="sxs-lookup"><span data-stu-id="4e490-272">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="4e490-273">Чтобы изменения вносились без запроса подтверждения, используйте вместо указанного в действии 2 командлета следующий: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="4e490-273">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>


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

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="4e490-274">Часть 2. Хеширование и отправка конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="4e490-274">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="4e490-275">На этом этапе выполняется настройка пользовательской группы безопасности и учетной записи пользователя, а также настройка агента отправки EDM.</span><span class="sxs-lookup"><span data-stu-id="4e490-275">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="4e490-276">Затем применяется средство для хеширования конфиденциальных данных с использованием значения соли и выполняется их отправка.</span><span class="sxs-lookup"><span data-stu-id="4e490-276">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="4e490-277">Хеширование и отправку можно выполнить на одном компьютере, или вы можете отделить этап хеширования от этапа отправки для дополнительной безопасности.</span><span class="sxs-lookup"><span data-stu-id="4e490-277">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="4e490-278">Если вы хотите выполнить хеширование и отправку с одного компьютера, нужно делать это на компьютере, который может напрямую подключаться к вашему клиенту Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e490-278">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="4e490-279">Для этого требуется, чтобы ваши файлы с конфиденциальными данными в виде обычного текста находились на этом компьютере для хеширования.</span><span class="sxs-lookup"><span data-stu-id="4e490-279">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="4e490-280">Если вы не хотите предоставлять свой файл с конфиденциальными данными в виде обычного текста, вы можете хешировать его на компьютере в безопасном расположении, а затем скопировать хеш-файл и файл соли на компьютер, который может напрямую подключаться к клиенту Microsoft 365 для отправки.</span><span class="sxs-lookup"><span data-stu-id="4e490-280">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload.</span></span> <span data-ttu-id="4e490-281">В этом сценарии вам потребуется EDMUploadAgent на обоих компьютерах.</span><span class="sxs-lookup"><span data-stu-id="4e490-281">In this scenario, you will need the EDMUploadAgent on both computers.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="4e490-282">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="4e490-282">Prerequisites</span></span>

- <span data-ttu-id="4e490-283">рабочая или учебная учетная запись для Microsoft 365, которая будет добавлена в группу безопасности **EDM\_DataUploaders**;</span><span class="sxs-lookup"><span data-stu-id="4e490-283">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="4e490-284">компьютер с Windows 10 или Windows Server 2016 с .NET версии 4.6.2 для запуска EDMUploadAgent;</span><span class="sxs-lookup"><span data-stu-id="4e490-284">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="4e490-285">каталог на компьютере отправки для следующего:</span><span class="sxs-lookup"><span data-stu-id="4e490-285">a directory on your upload machine for the:</span></span>
    -  <span data-ttu-id="4e490-286">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="4e490-286">EDMUploadAgent</span></span>
    - <span data-ttu-id="4e490-287">файл конфиденциального элемента в формате CSV. **PatientRecords.csv** в наших примерах;</span><span class="sxs-lookup"><span data-stu-id="4e490-287">your sensitive item file in csv format **PatientRecords.csv** in our examples</span></span>
    -  <span data-ttu-id="4e490-288">выходной хеш-файл и файл соли;</span><span class="sxs-lookup"><span data-stu-id="4e490-288">and the output hash and salt files</span></span>
    - <span data-ttu-id="4e490-289">имя хранилища данных из файла **edm.xml**. В этом примере: `PatientRecords`.</span><span class="sxs-lookup"><span data-stu-id="4e490-289">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="4e490-290">Настройка группы безопасности и учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="4e490-290">Set up the security group and user account</span></span>

1. <span data-ttu-id="4e490-291">Как глобальный администратор перейдите в центр администрирования с помощью соответствующей [ссылки для вашей подписки](#portal-links-for-your-subscription) и [создайте группу безопасности](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) с именем **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="4e490-291">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="4e490-292">Добавьте одного или нескольких пользователей в группу безопасности **EDM\_DataUploaders** .</span><span class="sxs-lookup"><span data-stu-id="4e490-292">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="4e490-293">(Эти пользователи будут управлять базой данных конфиденциальной информации.)</span><span class="sxs-lookup"><span data-stu-id="4e490-293">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="4e490-294">Хеширование и отправка с одного компьютера</span><span class="sxs-lookup"><span data-stu-id="4e490-294">Hash and upload from one computer</span></span>

<span data-ttu-id="4e490-295">Этот компьютер должен иметь прямой доступ к вашему клиенту Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e490-295">This computer must have direct access to your Microsoft 365 tenant.</span></span>

>[!NOTE]
> <span data-ttu-id="4e490-296">Перед началом этой процедуры убедитесь, что вы являетесь участником группы безопасности **EDM\_DataUploaders** .</span><span class="sxs-lookup"><span data-stu-id="4e490-296">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="4e490-297">Ссылки на агента отправки EDM по типу подписки</span><span class="sxs-lookup"><span data-stu-id="4e490-297">Links to EDM upload agent by subscription type</span></span>

- [<span data-ttu-id="4e490-298">Коммерческий + GCC</span><span class="sxs-lookup"><span data-stu-id="4e490-298">Commercial + GCC</span></span>](https://go.microsoft.com/fwlink/?linkid=2088639)
- [<span data-ttu-id="4e490-299">GCC-High</span><span class="sxs-lookup"><span data-stu-id="4e490-299">GCC-High</span></span>](https://go.microsoft.com/fwlink/?linkid=2137521)
- [<span data-ttu-id="4e490-300">DoD</span><span class="sxs-lookup"><span data-stu-id="4e490-300">DoD</span></span>](https://go.microsoft.com/fwlink/?linkid=2137807)

1. <span data-ttu-id="4e490-301">Создайте рабочий каталог для EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="4e490-301">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="4e490-302">Например, **C:\EDM\Data**.</span><span class="sxs-lookup"><span data-stu-id="4e490-302">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="4e490-303">Поместите туда файл **PatientRecords.csv**.</span><span class="sxs-lookup"><span data-stu-id="4e490-303">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="4e490-304">Скачайте и установите соответствующий [агент отправки EDM](#links-to-edm-upload-agent-by-subscription-type) для своей подписки в каталог, созданный на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="4e490-304">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

> [!NOTE]
> <span data-ttu-id="4e490-305">EDMUploadAgent по ссылкам выше обновлен, чтобы автоматически добавить значение соли в хешированные данные.</span><span class="sxs-lookup"><span data-stu-id="4e490-305">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="4e490-306">Кроме того, вы можете указать собственное значение соли.</span><span class="sxs-lookup"><span data-stu-id="4e490-306">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="4e490-307">После использования этой версии вы не сможете применить предыдущую версию EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="4e490-307">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
>
> <span data-ttu-id="4e490-308">Вы можете отправлять данные с помощью EDMUploadAgent в любое указанное хранилище данных только дважды в день.</span><span class="sxs-lookup"><span data-stu-id="4e490-308">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

> [!TIP]
> <span data-ttu-id="4e490-309">Чтобы получить список поддерживаемых параметров команды, запустите агент без аргументов.</span><span class="sxs-lookup"><span data-stu-id="4e490-309">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="4e490-310">Например, EdmUploadAgent.exe.</span><span class="sxs-lookup"><span data-stu-id="4e490-310">For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="4e490-311">Авторизуйте агент отправки EDM, откройте окно командной строки (как администратор), переключитесь на каталог **C:\EDM\Data** и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4e490-311">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="4e490-312">Войдите с помощью своей рабочей или учебной учетной записи Microsoft 365, добавленной в группу безопасности EDM_DataUploaders.</span><span class="sxs-lookup"><span data-stu-id="4e490-312">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="4e490-313">Сведения о вашем клиенте извлекаются из учетной записи пользователя для выполнения подключения.</span><span class="sxs-lookup"><span data-stu-id="4e490-313">Your tenant information is extracted from the user account to make the connection.</span></span>

4. <span data-ttu-id="4e490-314">Чтобы хешировать и отправить конфиденциальные данные, выполните следующую команду в окне командной строки:</span><span class="sxs-lookup"><span data-stu-id="4e490-314">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="4e490-315">Пример: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="4e490-315">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="4e490-316">Это автоматически добавит в хеш случайно созданное значение соли, чтобы повысить безопасность.</span><span class="sxs-lookup"><span data-stu-id="4e490-316">This will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="4e490-317">Если вы хотите использовать собственное значение соли, добавьте **/Salt<saltvalue>** в команду.</span><span class="sxs-lookup"><span data-stu-id="4e490-317">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="4e490-318">Это значение должно состоять из 64 символов и может содержать только символы a–z и 0–9.</span><span class="sxs-lookup"><span data-stu-id="4e490-318">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

5. <span data-ttu-id="4e490-319">Проверьте состояние отправки, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4e490-319">Check the upload status by running this command:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

<span data-ttu-id="4e490-320">Пример: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="4e490-320">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

<span data-ttu-id="4e490-321">Найдите состояние **ProcessingInProgress**.</span><span class="sxs-lookup"><span data-stu-id="4e490-321">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="4e490-322">Повторяйте попытку каждые несколько минут, пока состояние не изменится на **Completed**.</span><span class="sxs-lookup"><span data-stu-id="4e490-322">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="4e490-323">Когда отобразится завершенное состояние, ваши данные EDM готовы к использованию.</span><span class="sxs-lookup"><span data-stu-id="4e490-323">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="4e490-324">Раздельное хеширование и отправка</span><span class="sxs-lookup"><span data-stu-id="4e490-324">Separate Hash and upload</span></span>

<span data-ttu-id="4e490-325">Выполняйте хеширование на компьютере в безопасной среде.</span><span class="sxs-lookup"><span data-stu-id="4e490-325">Perform the hash on a computer in a secure environment.</span></span>

1. <span data-ttu-id="4e490-326">В окне командной строки выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="4e490-326">Run the following command in Command Prompt windows:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="4e490-327">Например:</span><span class="sxs-lookup"><span data-stu-id="4e490-327">For example:</span></span>

> <span data-ttu-id="4e490-328">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="4e490-328">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="4e490-329">Результатом будет хешированный файл и файл соли с этими расширениями, если вы не указали параметр **/Salt<saltvalue>**:</span><span class="sxs-lookup"><span data-stu-id="4e490-329">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>
- <span data-ttu-id="4e490-330">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="4e490-330">.EdmHash</span></span>
- <span data-ttu-id="4e490-331">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="4e490-331">.EdmSalt</span></span>

2. <span data-ttu-id="4e490-332">Безопасно скопируйте эти файлы на компьютер, который вы используете для отправки CSV-файла с конфиденциальными элементами (PatientRecords) в свой клиент.</span><span class="sxs-lookup"><span data-stu-id="4e490-332">Copy these files in a secure fashion to the computer you will use to upload your sensitive items csv file (PatientRecords) to your tenant.</span></span>

<span data-ttu-id="4e490-333">Чтобы отправить хешированные данные, выполните следующую команду в командной строке Windows:</span><span class="sxs-lookup"><span data-stu-id="4e490-333">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="4e490-334">Например:</span><span class="sxs-lookup"><span data-stu-id="4e490-334">For example:</span></span>

> <span data-ttu-id="4e490-335">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="4e490-335">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


<span data-ttu-id="4e490-336">Чтобы убедиться, что конфиденциальные данные были отправлены, выполните следующую команду в окне командной строки:</span><span class="sxs-lookup"><span data-stu-id="4e490-336">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>


`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="4e490-337">Появится список хранилищ данных и время их последнего обновления.</span><span class="sxs-lookup"><span data-stu-id="4e490-337">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="4e490-338">Если вы хотите просмотреть все отправки данных в определенное хранилище, выполните следующую команду в командной строке Windows:</span><span class="sxs-lookup"><span data-stu-id="4e490-338">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="4e490-339">Перейдите к настройке процесса и расписания для  [обновления базы данных конфиденциальной информации](#refreshing-your-sensitive-information-database).</span><span class="sxs-lookup"><span data-stu-id="4e490-339">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="4e490-340">На этом этапе вы готовы использовать классификацию на основе EDM с помощью облачных служб Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4e490-340">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="4e490-341">Например, вы можете [настроить политику защиты от потери данных с помощью классификации на основе EDM](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="4e490-341">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="4e490-342">Обновление базы данных конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="4e490-342">Refreshing your sensitive information database</span></span>

<span data-ttu-id="4e490-343">Вы можете обновлять базу данных конфиденциальной информации ежедневно, а средство отправки EDM может повторно индексировать конфиденциальные данные и повторно отправлять индексированные данные.</span><span class="sxs-lookup"><span data-stu-id="4e490-343">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="4e490-344">Определите процесс и частоту (ежедневно или еженедельно) обновления базы данных конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="4e490-344">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="4e490-345">Повторно экспортируйте конфиденциальные данные в приложение, например Microsoft Excel, и сохраните файл в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="4e490-345">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="4e490-346">Не изменяйте имя и расположение файла, которые использовались при выполнении действий, описанных в разделе  [Хеширование и отправка конфиденциальных данных](#part-2-hash-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="4e490-346">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="4e490-347">Если в структуру (имена полей) CSV-файла не вносится никаких изменений, то вам не нужно вносить изменения в файл схемы базы данных при обновлении данных.</span><span class="sxs-lookup"><span data-stu-id="4e490-347">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="4e490-348">Но если нужно внести изменения, измените схему базы данных и пакет правил соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="4e490-348">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="4e490-349">Используйте  [планировщик заданий](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page)  для автоматизации действий 2 и 3 в процедуре  [хеширования и отправки конфиденциальных данных](#part-2-hash-and-upload-the-sensitive-data) .</span><span class="sxs-lookup"><span data-stu-id="4e490-349">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="4e490-350">Вы можете планировать задачи с помощью нескольких методов:</span><span class="sxs-lookup"><span data-stu-id="4e490-350">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="4e490-351">Метод</span><span class="sxs-lookup"><span data-stu-id="4e490-351">Method</span></span>             | <span data-ttu-id="4e490-352">Действия</span><span class="sxs-lookup"><span data-stu-id="4e490-352">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="4e490-353">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e490-353">Windows PowerShell</span></span>     | <span data-ttu-id="4e490-354">См. документацию по [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps)  и [пример скрипта PowerShell](#example-powershell-script-for-task-scheduler) в этой статье</span><span class="sxs-lookup"><span data-stu-id="4e490-354">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="4e490-355">API планировщика заданий</span><span class="sxs-lookup"><span data-stu-id="4e490-355">Task Scheduler API</span></span>     | <span data-ttu-id="4e490-356">Ознакомьтесь с документацией по [планировщику заданий](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) </span><span class="sxs-lookup"><span data-stu-id="4e490-356">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="4e490-357">Пользовательский интерфейс Windows</span><span class="sxs-lookup"><span data-stu-id="4e490-357">Windows user interface</span></span> | <span data-ttu-id="4e490-358">В Windows нажмите кнопку **Пуск** и введите "Планировщик заданий".</span><span class="sxs-lookup"><span data-stu-id="4e490-358">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="4e490-359">Затем в списке результатов щелкните правой кнопкой мыши **Планировщик заданий** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="4e490-359">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="4e490-360">Пример скрипта PowerShell для планировщика заданий</span><span class="sxs-lookup"><span data-stu-id="4e490-360">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="4e490-361">Этот раздел содержит пример скрипта PowerShell, который можно использовать для планирования задач по хешированию данных и отправке хешированных данных:</span><span class="sxs-lookup"><span data-stu-id="4e490-361">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="4e490-362">Планирование хеширования и отправки одним действием</span><span class="sxs-lookup"><span data-stu-id="4e490-362">To schedule hashing and upload in a combined step</span></span>

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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="4e490-363">Планирование хеширования и отправки отдельными действиями</span><span class="sxs-lookup"><span data-stu-id="4e490-363">To schedule hashing and upload as separate steps</span></span>

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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="4e490-364">Часть 3. Использование классификации на основе EDM с помощью облачных служб Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4e490-364">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="4e490-365">Типы конфиденциальной информации EDM поддерживаются для следующих расположений::</span><span class="sxs-lookup"><span data-stu-id="4e490-365">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="4e490-366">DLP для Exchange Online (электронная почта)</span><span class="sxs-lookup"><span data-stu-id="4e490-366">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="4e490-367">OneDrive для бизнеса (файлы)</span><span class="sxs-lookup"><span data-stu-id="4e490-367">OneDrive for Business (files)</span></span>
- <span data-ttu-id="4e490-368">Microsoft Teams (беседы)</span><span class="sxs-lookup"><span data-stu-id="4e490-368">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="4e490-369">DLP для SharePoint (файлы)</span><span class="sxs-lookup"><span data-stu-id="4e490-369">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="4e490-370">Политики DLP Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4e490-370">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="4e490-371">Типы конфиденциальной информации EDM для указанных ниже сценариев сейчас находятся в процессе разработки и пока недоступны.</span><span class="sxs-lookup"><span data-stu-id="4e490-371">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="4e490-372">Автоматическая классификация меток конфиденциальности и хранения</span><span class="sxs-lookup"><span data-stu-id="4e490-372">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="4e490-373">Создание политики защиты от потери данных с EDM</span><span class="sxs-lookup"><span data-stu-id="4e490-373">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="4e490-374">Перейдите в Центр безопасности и соответствия требованиям, воспользовавшись соответствующей [ссылкой для вашей подписки](#portal-links-for-your-subscription).</span><span class="sxs-lookup"><span data-stu-id="4e490-374">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="4e490-375">Выберите пункты **Защита от потери данных** \> **Политика**.</span><span class="sxs-lookup"><span data-stu-id="4e490-375">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="4e490-376">Нажмите **Создать политику** \> **Настраиваемая** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4e490-376">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="4e490-377">На вкладке **Назовите политику** укажите название и описание, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4e490-377">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="4e490-378">На вкладке **Выберите расположения** щелкните **Позволить мне выбрать расположения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4e490-378">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="4e490-379">В столбце **Состояние** выберите **электронную почту Exchange, учетные записи OneDrive, чат и канал сообщений Teams** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4e490-379">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="4e490-380">На вкладке **Параметры политики** установите флажок **Использование дополнительных параметров** и нажмите кнопку  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4e490-380">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="4e490-381">Нажмите кнопку **+ Создать правило**.</span><span class="sxs-lookup"><span data-stu-id="4e490-381">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="4e490-382">В разделе **Название** укажите название и описание правила.</span><span class="sxs-lookup"><span data-stu-id="4e490-382">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="4e490-383">В разделе **Условия** в списке **+ Добавить условие** выберите вариант **Контент содержит типы конфиденциальной информации**.</span><span class="sxs-lookup"><span data-stu-id="4e490-383">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![Контент содержит типы конфиденциальной информации](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="4e490-385">Найдите тип конфиденциальной информации, созданный при настройке пакета правил, и нажмите кнопку **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="4e490-385">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="4e490-386">Затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="4e490-386">Then choose **Done**.</span></span>

12. <span data-ttu-id="4e490-387">Выберите остальные параметры для правила, например **Уведомления пользователей**, **Переопределения пользователя**, **Отчеты об инцидентах** и т. д., а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4e490-387">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="4e490-388">На вкладке **Параметры политики** проверьте свои правила и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4e490-388">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="4e490-389">Укажите, включить политику сразу, проверить ее или оставить выключенной.</span><span class="sxs-lookup"><span data-stu-id="4e490-389">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="4e490-390">Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4e490-390">Then choose **Next**.</span></span>

15. <span data-ttu-id="4e490-391">На вкладке **Проверьте параметры** просмотрите свою политику.</span><span class="sxs-lookup"><span data-stu-id="4e490-391">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="4e490-392">Внесите все необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="4e490-392">Make any needed changes.</span></span> <span data-ttu-id="4e490-393">Когда все будет готово, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="4e490-393">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="4e490-394">Потребуется примерно один час, чтобы новая политика защиты от потери данных распространилась по центру обработки данных.</span><span class="sxs-lookup"><span data-stu-id="4e490-394">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4e490-395">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4e490-395">Related articles</span></span>

- [<span data-ttu-id="4e490-396">Определения типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="4e490-396">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="4e490-397">Пользовательские типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="4e490-397">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="4e490-398">Обзор политик защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="4e490-398">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="4e490-399">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4e490-399">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="4e490-400">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="4e490-400">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema?view=exchange-ps)

