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
ms.openlocfilehash: d08589ec9465142e772c3190954ed7f93fbc68fe
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648754"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="a7e85-103">Создание пользовательских типов конфиденциальной информации с помощью классификации на основе точного совпадения данных</span><span class="sxs-lookup"><span data-stu-id="a7e85-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="a7e85-104">[Пользовательские типы конфиденциальной информации](custom-sensitive-info-types.md) используются для предотвращения непреднамеренного или неприемлемого предоставления общего доступа к конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="a7e85-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help prevent inadvertent or inappropriate sharing of sensitive information.</span></span> <span data-ttu-id="a7e85-105">Как администратор вы можете использовать Центр безопасности и соответствия требованиям или PowerShell для определения пользовательского типа конфиденциальной информации на основе шаблонов, признаков (ключевых слов, например  *сотрудник*,  *эмблема*,  *идентификатор* и т. д), расстояния между символами (как близко располагается признак к символам в определенном шаблоне) и доверительных уровней.</span><span class="sxs-lookup"><span data-stu-id="a7e85-105">As an administrator, you can use the Security & Compliance Center or PowerShell to define a custom sensitive information type based on patterns, evidence (keywords such as *employee*, *badge*, *ID*, and so on), character proximity (how close evidence is to characters in a particular pattern), and confidence levels.</span></span> <span data-ttu-id="a7e85-106">Такие пользовательские типы конфиденциальной информации соответствуют бизнес-требованиям большинства организаций.</span><span class="sxs-lookup"><span data-stu-id="a7e85-106">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="a7e85-107">Но что если вам нужен пользовательский тип конфиденциальной информации для сопоставления с точными значениями данных, а не универсальными шаблонами?</span><span class="sxs-lookup"><span data-stu-id="a7e85-107">But what if you wanted a custom sensitive information type that uses exact data values, instead of matching only with generic patterns?</span></span> <span data-ttu-id="a7e85-108">С помощью классификации на основе точного совпадения данных (EDM) вы можете создать пользовательский тип конфиденциальной информации с такими характеристиками:</span><span class="sxs-lookup"><span data-stu-id="a7e85-108">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="a7e85-109">динамичный и обновляемый;</span><span class="sxs-lookup"><span data-stu-id="a7e85-109">be dynamic and refreshable;</span></span>
- <span data-ttu-id="a7e85-110">дополнительные возможности масштабирования;</span><span class="sxs-lookup"><span data-stu-id="a7e85-110">be more scalable;</span></span>
- <span data-ttu-id="a7e85-111">снижает число ошибочно положительных результатов;</span><span class="sxs-lookup"><span data-stu-id="a7e85-111">result in fewer false-positives;</span></span>
- <span data-ttu-id="a7e85-112">поддерживает структурированные конфиденциальные данные;</span><span class="sxs-lookup"><span data-stu-id="a7e85-112">work with structured sensitive data;</span></span>
- <span data-ttu-id="a7e85-113">более безопасная обработка конфиденциальной информации;</span><span class="sxs-lookup"><span data-stu-id="a7e85-113">handle sensitive information more securely; and</span></span>
- <span data-ttu-id="a7e85-114">использование с несколькими облачными службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a7e85-114">be used with several Microsoft cloud services.</span></span>

![Классификация на основе EDM](../media/EDMClassification.png)

<span data-ttu-id="a7e85-116">Классификация на основе EDM позволяет создавать пользовательские типы конфиденциальной информации, ссылающиеся на точные значения в базе данных конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="a7e85-116">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="a7e85-117">Базу данных можно обновлять ежедневно или еженедельно, и она может содержать до 100 миллионов строк данных.</span><span class="sxs-lookup"><span data-stu-id="a7e85-117">The database can be refreshed daily or weekly, and it can contain up to 100 million rows of data.</span></span> <span data-ttu-id="a7e85-118">Таким образом, ваши пользовательские типы конфиденциальной информации остаются актуальными и применимыми при смене сотрудников, пациентов или клиентов, а также при изменении записей.</span><span class="sxs-lookup"><span data-stu-id="a7e85-118">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="a7e85-119">Вы также можете использовать классификацию на основе EDM с политиками, такими как [политики защиты от потери данных](data-loss-prevention-policies.md) (DLP) или [политики файлов Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="a7e85-119">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="a7e85-120">Обязательные лицензии и разрешения</span><span class="sxs-lookup"><span data-stu-id="a7e85-120">Required licenses and permissions</span></span>

<span data-ttu-id="a7e85-121">Для выполнения задач, описанных в данной статье, вы должны быть глобальным администратором, администратором соответствия требованиям или администратором Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a7e85-121">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="a7e85-122">Дополнительные сведения о разрешениях DLP см. в разделе [Разрешения](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="a7e85-122">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="a7e85-123">Классификация на основе EDM включена в следующие подписки:</span><span class="sxs-lookup"><span data-stu-id="a7e85-123">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="a7e85-124">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="a7e85-124">Office 365 E5</span></span>
- <span data-ttu-id="a7e85-125">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="a7e85-125">Microsoft 365 E5</span></span>
- <span data-ttu-id="a7e85-126">Соответствие требованиям Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="a7e85-126">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="a7e85-127">Защита информации и управление данными в Microsoft E5/A5</span><span class="sxs-lookup"><span data-stu-id="a7e85-127">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="a7e85-128">Ссылки на портал для вашей подписки</span><span class="sxs-lookup"><span data-stu-id="a7e85-128">Portal links for your subscription</span></span>


|<span data-ttu-id="a7e85-129">Портал</span><span class="sxs-lookup"><span data-stu-id="a7e85-129">Portal</span></span>  |<span data-ttu-id="a7e85-130">Интернет/GCC</span><span class="sxs-lookup"><span data-stu-id="a7e85-130">World Wide/GCC</span></span>  |<span data-ttu-id="a7e85-131">GCC High</span><span class="sxs-lookup"><span data-stu-id="a7e85-131">GCC-High</span></span>  |<span data-ttu-id="a7e85-132">DOD</span><span class="sxs-lookup"><span data-stu-id="a7e85-132">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="a7e85-133">Office SCC</span><span class="sxs-lookup"><span data-stu-id="a7e85-133">Office SCC</span></span>     |  <span data-ttu-id="a7e85-134">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="a7e85-134">protection.office.com</span></span>       |<span data-ttu-id="a7e85-135">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="a7e85-135">scc.office365.us</span></span>         |<span data-ttu-id="a7e85-136">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="a7e85-136">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="a7e85-137">Центр безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a7e85-137">Microsoft 365 Security center</span></span>     |<span data-ttu-id="a7e85-138">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a7e85-138">security.microsoft.com</span></span>         |<span data-ttu-id="a7e85-139">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="a7e85-139">security.microsoft.us</span></span>         |<span data-ttu-id="a7e85-140">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="a7e85-140">security.apps.mil</span></span>|
|<span data-ttu-id="a7e85-141">Центр соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a7e85-141">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="a7e85-142">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a7e85-142">compliance.microsoft.com</span></span>         |<span data-ttu-id="a7e85-143">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="a7e85-143">compliance.microsoft.us</span></span>         |<span data-ttu-id="a7e85-144">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="a7e85-144">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="a7e85-145">Обзор рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="a7e85-145">The work flow at a glance</span></span>

|<span data-ttu-id="a7e85-146">Этап</span><span class="sxs-lookup"><span data-stu-id="a7e85-146">Phase</span></span>  |<span data-ttu-id="a7e85-147">Требуемые параметры</span><span class="sxs-lookup"><span data-stu-id="a7e85-147">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="a7e85-148">Часть 1. Настройка классификации на основе EDM</span><span class="sxs-lookup"><span data-stu-id="a7e85-148">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="a7e85-149">(При необходимости)</span><span class="sxs-lookup"><span data-stu-id="a7e85-149">(As needed)</span></span><br/><span data-ttu-id="a7e85-150">- [Изменение схемы базы данных](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="a7e85-150">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="a7e85-151">- [Удаление схемы](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="a7e85-151">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="a7e85-152">– Доступ для чтения конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="a7e85-152">- Read access to the sensitive data</span></span><br/><span data-ttu-id="a7e85-153">– Схема базы данных в формате XML (доступен пример)</span><span class="sxs-lookup"><span data-stu-id="a7e85-153">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="a7e85-154">– Пакет правил в формате XML (доступен пример)</span><span class="sxs-lookup"><span data-stu-id="a7e85-154">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="a7e85-155">– Разрешения администратора на доступ к Центру безопасности и соответствия требованиям (с помощью PowerShell)</span><span class="sxs-lookup"><span data-stu-id="a7e85-155">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="a7e85-156">Часть 2. Хеширование и отправка конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="a7e85-156">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="a7e85-157">(При необходимости)</span><span class="sxs-lookup"><span data-stu-id="a7e85-157">(As needed)</span></span><br/>[<span data-ttu-id="a7e85-158">Обновление данных</span><span class="sxs-lookup"><span data-stu-id="a7e85-158">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="a7e85-159">– Настраиваемая группа безопасности и учетная запись пользователя</span><span class="sxs-lookup"><span data-stu-id="a7e85-159">- Custom security group and user account</span></span><br/><span data-ttu-id="a7e85-160">– Доступ локального администратора к компьютеру с агентом отправки EDM</span><span class="sxs-lookup"><span data-stu-id="a7e85-160">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="a7e85-161">– Доступ для чтения конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="a7e85-161">- Read access to the sensitive data</span></span><br/><span data-ttu-id="a7e85-162">– Процесс и расписание для обновления данных</span><span class="sxs-lookup"><span data-stu-id="a7e85-162">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="a7e85-163">Часть 3. Использование классификации на основе EDM с помощью облачных служб Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a7e85-163">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="a7e85-164">– Подписка на Microsoft 365 с DLP</span><span class="sxs-lookup"><span data-stu-id="a7e85-164">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="a7e85-165">– Включенная функция классификации на основе EDM</span><span class="sxs-lookup"><span data-stu-id="a7e85-165">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="a7e85-166">Часть 1. Настройка классификации на основе EDM</span><span class="sxs-lookup"><span data-stu-id="a7e85-166">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="a7e85-167">Установка и настройка классификации на основе EDM включает сохранение конфиденциальных данных в формате CSV, определение схемы для базы данных конфиденциальной информации и создание пакета правил с последующей отправкой схемы и пакета правил.</span><span class="sxs-lookup"><span data-stu-id="a7e85-167">Setting up and configuring EDM-based classification involves saving sensitive data in .csv format, defining a schema for your database of sensitive information, creating a rule package, and then uploading the schema and rule package.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="a7e85-168">Определение схемы для базы данных конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="a7e85-168">Define the schema for your database of sensitive information</span></span>

1. <span data-ttu-id="a7e85-169">Определите конфиденциальную информацию, которую нужно использовать.</span><span class="sxs-lookup"><span data-stu-id="a7e85-169">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="a7e85-170">Экспортируйте данные в приложение, например Microsoft Excel, и сохраните файл в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="a7e85-170">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="a7e85-171">Файл данных может содержать:</span><span class="sxs-lookup"><span data-stu-id="a7e85-171">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="a7e85-172">до 100 миллионов строк конфиденциальных данных;</span><span class="sxs-lookup"><span data-stu-id="a7e85-172">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="a7e85-173">до 32 столбцов (полей) на источник данных;</span><span class="sxs-lookup"><span data-stu-id="a7e85-173">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="a7e85-174">до 5 столбцов (полей), отмеченных как доступные для поиска.</span><span class="sxs-lookup"><span data-stu-id="a7e85-174">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="a7e85-175">Структурируйте конфиденциальные данные в CSV-файле таким образом, чтобы первая строка включала имена полей, которые используются для классификации на основе EDM.</span><span class="sxs-lookup"><span data-stu-id="a7e85-175">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="a7e85-176">В CSV-файле можно применять такие имена полей, как ssn, birthdate, firstname, lastname и т. д.</span><span class="sxs-lookup"><span data-stu-id="a7e85-176">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname", and so on.</span></span> <span data-ttu-id="a7e85-177">Обратите внимание: в заголовках столбцов не должно быть пробелов и символов подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="a7e85-177">Please note that column headers can't include spaces or underscores in their names.</span></span> <span data-ttu-id="a7e85-178">Например, наш CSV-файл называется  *PatientRecords.csv*, а его столбцы включают *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN* и другие.</span><span class="sxs-lookup"><span data-stu-id="a7e85-178">As an example, our .csv file is called *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="a7e85-179">Определите схему для базы данных конфиденциальной информации в формате XML (как в примере ниже).</span><span class="sxs-lookup"><span data-stu-id="a7e85-179">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="a7e85-180">Назовите этот файл схемы  **edm.xml** и настройте его так, чтобы для каждого столбца в базе данных была строка, использующая синтаксис:</span><span class="sxs-lookup"><span data-stu-id="a7e85-180">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="a7e85-181">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="a7e85-181">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="a7e85-182">Используйте имена столбцов для значений *Field name* .</span><span class="sxs-lookup"><span data-stu-id="a7e85-182">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="a7e85-183">Используйте параметр *searchable="true"* для 5 полей, которые должны поддерживать поиск.</span><span class="sxs-lookup"><span data-stu-id="a7e85-183">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="a7e85-184">Поиск должно поддерживать хотя бы одно поле.</span><span class="sxs-lookup"><span data-stu-id="a7e85-184">You must designate a minimum of one field as searchable.</span></span>

      <span data-ttu-id="a7e85-185">Например, в следующем XML-файле определяется схема для базы данных записей пациентов с пятью полями, поддерживающими поиск: *PatientID*, *MRN*, *SSN*, *Phone* и *DOB*.</span><span class="sxs-lookup"><span data-stu-id="a7e85-185">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="a7e85-186">(Вы можете скопировать, изменить и использовать наш пример.)</span><span class="sxs-lookup"><span data-stu-id="a7e85-186">(You can copy, modify, and use our example.)</span></span>

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

4. <span data-ttu-id="a7e85-187">Подключитесь к Центру безопасности и соответствия требованиям, используя процедуры, описанные в статье [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="a7e85-187">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

5. <span data-ttu-id="a7e85-188">Чтобы добавить схему базы данных, выполните по отдельности указанные ниже командлеты.</span><span class="sxs-lookup"><span data-stu-id="a7e85-188">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="a7e85-189">Появится запрос на подтверждение, показанный ниже.</span><span class="sxs-lookup"><span data-stu-id="a7e85-189">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="a7e85-190">Подтверждение</span><span class="sxs-lookup"><span data-stu-id="a7e85-190">Confirm</span></span>
      >
      > <span data-ttu-id="a7e85-191">Вы действительно хотите выполнить это действие?</span><span class="sxs-lookup"><span data-stu-id="a7e85-191">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="a7e85-192">Будет импортирована новая схема модели EDM для хранилища данных "patientrecords".</span><span class="sxs-lookup"><span data-stu-id="a7e85-192">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="a7e85-193">\[Y\] Да \[A\] Да для всех \[N\] Нет \[L\] Нет для всех \[?\] Справка (значение по умолчанию "Y"):</span><span class="sxs-lookup"><span data-stu-id="a7e85-193">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="a7e85-194">Чтобы изменения вносились без запроса подтверждения, используйте вместо указанного в действии 5 командлета следующий: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="a7e85-194">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="a7e85-195">Обновление EDMSchema с дополнениями может занять от 10 до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="a7e85-195">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="a7e85-196">Перед выполнением действий, в которых используется дополнение, необходимо выполнить обновление.</span><span class="sxs-lookup"><span data-stu-id="a7e85-196">The update must complete before you execute steps that use the additions.</span></span>

<span data-ttu-id="a7e85-197">Теперь, когда схема базы данных конфиденциальной информации определена, нужно настроить пакет правил.</span><span class="sxs-lookup"><span data-stu-id="a7e85-197">Now that the schema for your database of sensitive information is defined, the next step is to set up a rule package.</span></span> <span data-ttu-id="a7e85-198">Перейдите к разделу [Настройка пакета правил](#set-up-a-rule-package).</span><span class="sxs-lookup"><span data-stu-id="a7e85-198">Proceed to the section [Set up a rule package](#set-up-a-rule-package).</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="a7e85-199">Редактирование схемы для классификации на основе EDM</span><span class="sxs-lookup"><span data-stu-id="a7e85-199">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="a7e85-200">Если нужно внести изменения в файл **edm.xml**, например изменить поля, используемые для классификации на основе EDM, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a7e85-200">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="a7e85-201">Измените файл **edm.xml** (файл, обсуждаемый в разделе [Определение схемы](#define-the-schema-for-your-database-of-sensitive-information)  этой статьи).</span><span class="sxs-lookup"><span data-stu-id="a7e85-201">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="a7e85-202">Подключитесь к Центру безопасности и соответствия требованиям, используя процедуры, описанные в статье [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="a7e85-202">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="a7e85-203">Чтобы обновить схему базы данных, выполните по отдельности указанные ниже командлеты.</span><span class="sxs-lookup"><span data-stu-id="a7e85-203">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="a7e85-204">Появится запрос на подтверждение, показанный ниже.</span><span class="sxs-lookup"><span data-stu-id="a7e85-204">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="a7e85-205">Подтверждение</span><span class="sxs-lookup"><span data-stu-id="a7e85-205">Confirm</span></span>
      >
      > <span data-ttu-id="a7e85-206">Вы действительно хотите выполнить это действие?</span><span class="sxs-lookup"><span data-stu-id="a7e85-206">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="a7e85-207">Схема модели EDM для хранилища данных "patientrecords" будет обновлена.</span><span class="sxs-lookup"><span data-stu-id="a7e85-207">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="a7e85-208">\[Y\] Да \[A\] Да для всех \[N\] Нет \[L\] Нет для всех \[?\] Справка (значение по умолчанию "Y"):</span><span class="sxs-lookup"><span data-stu-id="a7e85-208">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="a7e85-209">Чтобы изменения вносились без запроса подтверждения, используйте вместо указанного в действии 3 командлета следующий: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="a7e85-209">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="a7e85-210">Обновление EDMSchema с дополнениями может занять от 10 до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="a7e85-210">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="a7e85-211">Перед выполнением действий, в которых используется дополнение, необходимо выполнить обновление.</span><span class="sxs-lookup"><span data-stu-id="a7e85-211">The update must complete before you execute steps that use the additions.</span></span>

## <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="a7e85-212">Удаление схемы для классификации на основе EDM</span><span class="sxs-lookup"><span data-stu-id="a7e85-212">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="a7e85-213">(При необходимости.) Чтобы удалить схему, используемую для классификации на основе EDM, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a7e85-213">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="a7e85-214">Подключитесь к Центру безопасности и соответствия требованиям, используя процедуры, описанные в статье [Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="a7e85-214">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="a7e85-215">Выполните приведенные ниже командлеты PowerShell, заменив имя хранилища данных "patientrecords" на имя удаляемого хранилища.</span><span class="sxs-lookup"><span data-stu-id="a7e85-215">Run the following PowerShell cmdlets, substituting the data store name of "patientrecords" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="a7e85-216">Появится запрос на подтверждение, показанный ниже.</span><span class="sxs-lookup"><span data-stu-id="a7e85-216">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="a7e85-217">Подтверждение</span><span class="sxs-lookup"><span data-stu-id="a7e85-217">Confirm</span></span>
      >
      > <span data-ttu-id="a7e85-218">Вы действительно хотите выполнить это действие?</span><span class="sxs-lookup"><span data-stu-id="a7e85-218">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="a7e85-219">Схема модели EDM для хранилища данных "patientrecords" будет удалена.</span><span class="sxs-lookup"><span data-stu-id="a7e85-219">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="a7e85-220">\[Y\] Да \[A\] Да для всех \[N\] Нет \[L\] Нет для всех \[?\] Справка (значение по умолчанию "Y"):</span><span class="sxs-lookup"><span data-stu-id="a7e85-220">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="a7e85-221">Чтобы изменения вносились без запроса подтверждения, используйте вместо указанного в действии 2 командлета следующий: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="a7e85-221">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="set-up-a-rule-package"></a><span data-ttu-id="a7e85-222">Настройка пакета правил</span><span class="sxs-lookup"><span data-stu-id="a7e85-222">Set up a rule package</span></span>

1. <span data-ttu-id="a7e85-223">Создайте пакет правил в формате XML (в кодировке Юникод), как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="a7e85-223">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="a7e85-224">(Вы можете скопировать, изменить и использовать наш пример.)</span><span class="sxs-lookup"><span data-stu-id="a7e85-224">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="a7e85-225">Настраивая пакет правил, убедитесь, что в нем используются правильные ссылки на CSV-файл и файл **edm.xml**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-225">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="a7e85-226">Вы можете скопировать, изменить и использовать наш пример.</span><span class="sxs-lookup"><span data-stu-id="a7e85-226">You can copy, modify, and use our example.</span></span> <span data-ttu-id="a7e85-227">В этом примере XML для создания типа конфиденциальной информации EDM должны быть настроены перечисленные ниже поля.</span><span class="sxs-lookup"><span data-stu-id="a7e85-227">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="a7e85-228">**Идентификаторы RulePack и ExactMatch**. Используйте командлет [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) для создания GUID.</span><span class="sxs-lookup"><span data-stu-id="a7e85-228">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="a7e85-229">**Datastore**. В этом поле указывается, какое хранилище данных подстановки EDM будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="a7e85-229">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="a7e85-230">Вы указываете имя источника данных для настроенной схемы EDM.</span><span class="sxs-lookup"><span data-stu-id="a7e85-230">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="a7e85-231">**idMatch**. Это поле указывает на основной элемент EDM.</span><span class="sxs-lookup"><span data-stu-id="a7e85-231">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="a7e85-232">Matches. Указывает поле, которое будет использоваться при точном поиске.</span><span class="sxs-lookup"><span data-stu-id="a7e85-232">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="a7e85-233">Вы указываете имя поля для поиска в схеме EDM для DataStore.</span><span class="sxs-lookup"><span data-stu-id="a7e85-233">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="a7e85-234">Classification. В этом поле указывается соответствие типа конфиденциальной информации, которое активирует поиск EDM.</span><span class="sxs-lookup"><span data-stu-id="a7e85-234">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="a7e85-235">Вы можете указать имя или идентификатор GUID имеющейся встроенной или настраиваемой классификации.</span><span class="sxs-lookup"><span data-stu-id="a7e85-235">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="a7e85-236">**Match**. В этом поле указываются дополнительные свидетельства, находящиеся близко к idMatch.</span><span class="sxs-lookup"><span data-stu-id="a7e85-236">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="a7e85-237">Matches. Вы указываете имя поля для поиска в схеме EDM для DataStore.</span><span class="sxs-lookup"><span data-stu-id="a7e85-237">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="a7e85-238">**Resource**. В этом разделе указываются имя и описание типа конфиденциальной информации в нескольких языковых средах.</span><span class="sxs-lookup"><span data-stu-id="a7e85-238">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="a7e85-239">idRef. Укажите GUID для идентификатора ExactMatch.</span><span class="sxs-lookup"><span data-stu-id="a7e85-239">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="a7e85-240">Имена & описания: настройте в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="a7e85-240">Name & descriptions: customize as required.</span></span>

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

1. <span data-ttu-id="a7e85-241">Отправьте пакет правил, выполнив по отдельности указанные ниже командлеты PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a7e85-241">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="a7e85-242">На этом этапе вы настроили классификацию на основе EDM.</span><span class="sxs-lookup"><span data-stu-id="a7e85-242">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="a7e85-243">На следующем этапе необходимо хешировать конфиденциальные данные, а затем отправить хеши на индексацию.</span><span class="sxs-lookup"><span data-stu-id="a7e85-243">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="a7e85-244">Помните, что схема PatientRecords определяет пять полей как доступные для поиска:  *PatientID*,  *MRN*,  *SSN*,  *Phone* и  *DOB*.</span><span class="sxs-lookup"><span data-stu-id="a7e85-244">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="a7e85-245">В нашем примере пакет правил включает эти поля и ссылки на файл схемы базы данных (**edm.xml**), предусматривая один элемент *ExactMatch* для каждого доступного для поиска поля.</span><span class="sxs-lookup"><span data-stu-id="a7e85-245">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* items per searchable field.</span></span> <span data-ttu-id="a7e85-246">Рассмотрим приведенный ниже элемент ExactMatch.</span><span class="sxs-lookup"><span data-stu-id="a7e85-246">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="a7e85-247">В этом примере обратите внимание на следующее:</span><span class="sxs-lookup"><span data-stu-id="a7e85-247">In this example, note the following:</span></span>

- <span data-ttu-id="a7e85-248">Имя хранилища данных dataStore ссылается на ранее созданный файл CSV:  **dataStore = "PatientRecords"**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-248">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="a7e85-249">Значение idMatch ссылается на доступное для поиска поле, которое указано в файле схемы базы данных: **idMatch matches = "SSN"**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-249">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="a7e85-250">Значение классификации ссылается на существующий или пользовательский тип конфиденциальной информации:  **classification = "U.S. Social Security Number (SSN)"**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-250">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="a7e85-251">(В этом случае используется существующий тип конфиденциальной информации, содержащий номер социального страхования США.)</span><span class="sxs-lookup"><span data-stu-id="a7e85-251">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="a7e85-252">Обновление EDMSchema с дополнениями может занять от 10 до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="a7e85-252">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="a7e85-253">Перед выполнением действий, в которых используется дополнение, необходимо выполнить обновление.</span><span class="sxs-lookup"><span data-stu-id="a7e85-253">The update must complete before you execute steps that use the additions.</span></span>

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="a7e85-254">Часть 2. Хеширование и отправка конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="a7e85-254">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="a7e85-255">На этом этапе выполняется настройка пользовательской группы безопасности и учетной записи пользователя, а также настройка агента отправки EDM.</span><span class="sxs-lookup"><span data-stu-id="a7e85-255">During this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="a7e85-256">Затем используется средство для хеширования конфиденциальных данных и отправляются хешированные данные, чтобы их можно было индексировать.</span><span class="sxs-lookup"><span data-stu-id="a7e85-256">Then, you use the tool to hash the sensitive data, and upload the hashed data so it can be indexed.</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="a7e85-257">Настройка группы безопасности и учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="a7e85-257">Set up the security group and user account</span></span>

1. <span data-ttu-id="a7e85-258">Как глобальный администратор перейдите в центр администрирования с помощью соответствующей [ссылки для вашей подписки](#portal-links-for-your-subscription) и [создайте группу безопасности](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) с именем **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-258">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="a7e85-259">Добавьте одного или нескольких пользователей в группу безопасности **EDM\_DataUploaders** .</span><span class="sxs-lookup"><span data-stu-id="a7e85-259">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="a7e85-260">(Эти пользователи будут управлять базой данных конфиденциальной информации.)</span><span class="sxs-lookup"><span data-stu-id="a7e85-260">(These users will manage the database of sensitive information.)</span></span>

3. <span data-ttu-id="a7e85-261">Убедитесь, что каждый пользователь, управляющий конфиденциальными данными, является локальным администратором на компьютере, используемом для агента отправки EDM.</span><span class="sxs-lookup"><span data-stu-id="a7e85-261">Make sure each user who is managing the sensitive data is a local admin on the machine used for the EDM Upload Agent.</span></span>

#### <a name="set-up-the-edm-upload-agent"></a><span data-ttu-id="a7e85-262">Настройка агента отправки EDM</span><span class="sxs-lookup"><span data-stu-id="a7e85-262">Set up the EDM Upload Agent</span></span>

>[!NOTE]
> <span data-ttu-id="a7e85-263">Перед началом этой процедуры убедитесь, что вы являетесь участником группы безопасности **EDM\_DataUploaders** и локальным администратором на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="a7e85-263">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group and a local admin on your machine.</span></span>

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="a7e85-264">Ссылки на агента отправки EDM по типу подписки</span><span class="sxs-lookup"><span data-stu-id="a7e85-264">Links to EDM upload agent by subscription type</span></span>

- [<span data-ttu-id="a7e85-265">Коммерческий + GCC</span><span class="sxs-lookup"><span data-stu-id="a7e85-265">Commercial + GCC</span></span>](https://go.microsoft.com/fwlink/?linkid=2088639)
- [<span data-ttu-id="a7e85-266">GCC-High</span><span class="sxs-lookup"><span data-stu-id="a7e85-266">GCC-High</span></span>](https://go.microsoft.com/fwlink/?linkid=2137521)
- [<span data-ttu-id="a7e85-267">DoD</span><span class="sxs-lookup"><span data-stu-id="a7e85-267">DoD</span></span>](https://go.microsoft.com/fwlink/?linkid=2137807)

1. <span data-ttu-id="a7e85-268">Скачайте и установите соответствующий [агент отправки EDM](#links-to-edm-upload-agent-by-subscription-type) для своей подписки.</span><span class="sxs-lookup"><span data-stu-id="a7e85-268">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription.</span></span> <span data-ttu-id="a7e85-269">По умолчанию в качестве расположения установки необходимо использовать **C:\\Program Files\\Microsoft\\EdmUploadAgent**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-269">By default, the installation location should be **C:\\Program Files\\Microsoft\\EdmUploadAgent**.</span></span>

   > [!TIP]
   > <span data-ttu-id="a7e85-270">Чтобы получить список поддерживаемых параметров команды, запустите агент без аргументов.</span><span class="sxs-lookup"><span data-stu-id="a7e85-270">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="a7e85-271">Например, EdmUploadAgent.exe.</span><span class="sxs-lookup"><span data-stu-id="a7e85-271">For example 'EdmUploadAgent.exe'.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a7e85-272">Вы можете отправлять данные с помощью EDMUploadAgent в любое указанное хранилище данных только дважды в день.</span><span class="sxs-lookup"><span data-stu-id="a7e85-272">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

2. <span data-ttu-id="a7e85-273">Чтобы авторизовать агент отправки EDM, откройте командную строку Windows (как администратор) и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a7e85-273">To authorize the EDM Upload Agent, open Windows Command Prompt (as an administrator), and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="a7e85-274">Войдите с помощью своей рабочей или учебной учетной записи Office 365, добавленной в группу безопасности EDM_DataUploaders.</span><span class="sxs-lookup"><span data-stu-id="a7e85-274">Sign in with your work or school account for Office 365 that was added to the EDM_DataUploaders security group.</span></span>

<span data-ttu-id="a7e85-275">Следующий этап состоит в использовании агента отправки EDM для хеширования конфиденциальных данных с последующей отправкой хешированных данных.</span><span class="sxs-lookup"><span data-stu-id="a7e85-275">The next step is to use the EDM Upload Agent to hash the sensitive data, and then upload the hashed data.</span></span>

#### <a name="hash-and-upload-the-sensitive-data"></a><span data-ttu-id="a7e85-276">Хеширование и отправка конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="a7e85-276">Hash and upload the sensitive data</span></span>

<span data-ttu-id="a7e85-277">Сохраните файл конфиденциальных данных (помните, что в нашем примере это файл  **PatientRecords.csv**) на локальном диске компьютера.</span><span class="sxs-lookup"><span data-stu-id="a7e85-277">Save the sensitive data file (recall our example is **PatientRecords.csv**) to the local drive on the machine.</span></span> <span data-ttu-id="a7e85-278">(В нашем примере мы сохранили файл **PatientRecords.csv** в папке **C:\\EDM\\**.)</span><span class="sxs-lookup"><span data-stu-id="a7e85-278">(We saved our example **PatientRecords.csv** file to **C:\\Edm\\Data**.)</span></span>

<span data-ttu-id="a7e85-279">Чтобы хешировать и отправить конфиденциальные данные, выполните следующую команду в командной строке Windows:</span><span class="sxs-lookup"><span data-stu-id="a7e85-279">To hash and upload the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="a7e85-280">Пример: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="a7e85-280">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="a7e85-281">Чтобы отделить хеширование конфиденциальных данных и выполнить его в изолированной среде, выполняйте хеширование и отправку по отдельности.</span><span class="sxs-lookup"><span data-stu-id="a7e85-281">To separate and execute the hashing of sensitive data in an isolated environment, execute the hashing and upload steps separately.</span></span>

<span data-ttu-id="a7e85-282">Чтобы хешировать конфиденциальные данные, выполните следующую команду в командной строке Windows:</span><span class="sxs-lookup"><span data-stu-id="a7e85-282">To hash the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="a7e85-283">Например:</span><span class="sxs-lookup"><span data-stu-id="a7e85-283">For example:</span></span>

> <span data-ttu-id="a7e85-284">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="a7e85-284">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="a7e85-285">Чтобы отправить хешированные данные, выполните следующую команду в командной строке Windows:</span><span class="sxs-lookup"><span data-stu-id="a7e85-285">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="a7e85-286">Например:</span><span class="sxs-lookup"><span data-stu-id="a7e85-286">For example:</span></span>

> <span data-ttu-id="a7e85-287">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="a7e85-287">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


<span data-ttu-id="a7e85-288">Чтобы убедиться, что конфиденциальные данные были отправлены, выполните следующую команду в окне командной строки:</span><span class="sxs-lookup"><span data-stu-id="a7e85-288">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>


`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="a7e85-289">Появится список хранилищ данных и время их последнего обновления.</span><span class="sxs-lookup"><span data-stu-id="a7e85-289">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="a7e85-290">Если вы хотите просмотреть все отправки данных в определенное хранилище, выполните следующую команду в командной строке Windows:</span><span class="sxs-lookup"><span data-stu-id="a7e85-290">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="a7e85-291">Перейдите к настройке процесса и расписания для  [обновления базы данных конфиденциальной информации](#refreshing-your-sensitive-information-database).</span><span class="sxs-lookup"><span data-stu-id="a7e85-291">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="a7e85-292">На этом этапе вы готовы использовать классификацию на основе EDM с помощью облачных служб Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a7e85-292">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="a7e85-293">Например, вы можете [настроить политику защиты от потери данных с помощью классификации на основе EDM](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="a7e85-293">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="a7e85-294">Обновление базы данных конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="a7e85-294">Refreshing your sensitive information database</span></span>

<span data-ttu-id="a7e85-295">Вы можете обновлять базу данных конфиденциальной информации ежедневно или еженедельно, а средство отправки EDM может повторно хешировать конфиденциальные данные и повторно отправлять хешированные данные.</span><span class="sxs-lookup"><span data-stu-id="a7e85-295">You can refresh your sensitive information database daily or weekly, and the EDM Upload Tool can re-hash the sensitive data and then reupload the hashed data.</span></span>

1. <span data-ttu-id="a7e85-296">Определите процесс и частоту (ежедневно или еженедельно) обновления базы данных конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="a7e85-296">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="a7e85-297">Повторно экспортируйте конфиденциальные данные в приложение, например Microsoft Excel, и сохраните файл в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="a7e85-297">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="a7e85-298">Не изменяйте имя и расположение файла, которые использовались при выполнении действий, описанных в разделе  [Хеширование и отправка конфиденциальных данных](#hash-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="a7e85-298">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="a7e85-299">Если в структуру (имена полей) CSV-файла не вносится никаких изменений, то вам не нужно вносить изменения в файл схемы базы данных при обновлении данных.</span><span class="sxs-lookup"><span data-stu-id="a7e85-299">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="a7e85-300">Но если нужно внести изменения, измените схему базы данных и пакет правил соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="a7e85-300">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="a7e85-301">Используйте  [планировщик заданий](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page)  для автоматизации действий 2 и 3 в процедуре  [хеширования и отправки конфиденциальных данных](#hash-and-upload-the-sensitive-data) .</span><span class="sxs-lookup"><span data-stu-id="a7e85-301">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="a7e85-302">Вы можете планировать задачи с помощью нескольких методов:</span><span class="sxs-lookup"><span data-stu-id="a7e85-302">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="a7e85-303">Метод</span><span class="sxs-lookup"><span data-stu-id="a7e85-303">Method</span></span>             | <span data-ttu-id="a7e85-304">Действия</span><span class="sxs-lookup"><span data-stu-id="a7e85-304">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="a7e85-305">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7e85-305">Windows PowerShell</span></span>     | <span data-ttu-id="a7e85-306">См. документацию по [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps)  и [пример скрипта PowerShell](#example-powershell-script-for-task-scheduler) в этой статье</span><span class="sxs-lookup"><span data-stu-id="a7e85-306">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="a7e85-307">API планировщика заданий</span><span class="sxs-lookup"><span data-stu-id="a7e85-307">Task Scheduler API</span></span>     | <span data-ttu-id="a7e85-308">Ознакомьтесь с документацией по [планировщику заданий](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) </span><span class="sxs-lookup"><span data-stu-id="a7e85-308">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="a7e85-309">Пользовательский интерфейс Windows</span><span class="sxs-lookup"><span data-stu-id="a7e85-309">Windows user interface</span></span> | <span data-ttu-id="a7e85-310">В Windows нажмите кнопку **Пуск** и введите "Планировщик заданий".</span><span class="sxs-lookup"><span data-stu-id="a7e85-310">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="a7e85-311">Затем в списке результатов щелкните правой кнопкой мыши **Планировщик заданий** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-311">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="a7e85-312">Пример скрипта PowerShell для планировщика заданий</span><span class="sxs-lookup"><span data-stu-id="a7e85-312">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="a7e85-313">Этот раздел содержит пример скрипта PowerShell, который можно использовать для планирования задач по хешированию данных и отправке хешированных данных:</span><span class="sxs-lookup"><span data-stu-id="a7e85-313">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="a7e85-314">Планирование хеширования и отправки одним действием</span><span class="sxs-lookup"><span data-stu-id="a7e85-314">To schedule hashing and upload in a combined step</span></span>

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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="a7e85-315">Планирование хеширования и отправки отдельными действиями</span><span class="sxs-lookup"><span data-stu-id="a7e85-315">To schedule hashing and upload as separate steps</span></span>

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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="a7e85-316">Часть 3. Использование классификации на основе EDM с помощью облачных служб Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a7e85-316">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="a7e85-317">Типы конфиденциальной информации EDM поддерживаются для следующих расположений::</span><span class="sxs-lookup"><span data-stu-id="a7e85-317">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="a7e85-318">DLP для Exchange Online (электронная почта)</span><span class="sxs-lookup"><span data-stu-id="a7e85-318">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="a7e85-319">OneDrive для бизнеса (файлы)</span><span class="sxs-lookup"><span data-stu-id="a7e85-319">OneDrive for Business (files)</span></span>
- <span data-ttu-id="a7e85-320">Microsoft Teams (беседы)</span><span class="sxs-lookup"><span data-stu-id="a7e85-320">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="a7e85-321">DLP для SharePoint (файлы)</span><span class="sxs-lookup"><span data-stu-id="a7e85-321">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="a7e85-322">Политики DLP Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a7e85-322">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="a7e85-323">Типы конфиденциальной информации EDM для указанных ниже сценариев сейчас находятся в процессе разработки и пока недоступны.</span><span class="sxs-lookup"><span data-stu-id="a7e85-323">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="a7e85-324">Автоматическая классификация меток конфиденциальности и хранения</span><span class="sxs-lookup"><span data-stu-id="a7e85-324">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="a7e85-325">Создание политики защиты от потери данных с EDM</span><span class="sxs-lookup"><span data-stu-id="a7e85-325">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="a7e85-326">Перейдите в Центр безопасности и соответствия требованиям, воспользовавшись соответствующей [ссылкой для вашей подписки](#portal-links-for-your-subscription).</span><span class="sxs-lookup"><span data-stu-id="a7e85-326">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="a7e85-327">Выберите пункты **Защита от потери данных** \> **Политика**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-327">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="a7e85-328">Нажмите **Создать политику** \> **Настраиваемая** \> **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-328">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="a7e85-329">На вкладке **Назовите политику** укажите название и описание, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-329">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="a7e85-330">На вкладке **Выберите расположения** щелкните **Позволить мне выбрать расположения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-330">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="a7e85-331">В столбце **Состояние** выберите **электронную почту Exchange, учетные записи OneDrive, чат и канал сообщений Teams** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-331">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="a7e85-332">На вкладке **Параметры политики** установите флажок **Использование дополнительных параметров** и нажмите кнопку  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-332">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="a7e85-333">Нажмите кнопку **+ Создать правило**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-333">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="a7e85-334">В разделе **Название** укажите название и описание правила.</span><span class="sxs-lookup"><span data-stu-id="a7e85-334">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="a7e85-335">В разделе **Условия** в списке **+ Добавить условие** выберите вариант **Контент содержит типы конфиденциальной информации**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-335">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![Контент содержит типы конфиденциальной информации](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="a7e85-337">Найдите тип конфиденциальной информации, созданный при настройке пакета правил, и нажмите кнопку **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-337">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="a7e85-338">Затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-338">Then choose **Done**.</span></span>

12. <span data-ttu-id="a7e85-339">Выберите остальные параметры для правила, например **Уведомления пользователей**, **Переопределения пользователя**, **Отчеты об инцидентах** и т. д., а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-339">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="a7e85-340">На вкладке **Параметры политики** проверьте свои правила и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-340">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="a7e85-341">Укажите, включить политику сразу, проверить ее или оставить выключенной.</span><span class="sxs-lookup"><span data-stu-id="a7e85-341">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="a7e85-342">Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-342">Then choose **Next**.</span></span>

15. <span data-ttu-id="a7e85-343">На вкладке **Проверьте параметры** просмотрите свою политику.</span><span class="sxs-lookup"><span data-stu-id="a7e85-343">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="a7e85-344">Внесите все необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="a7e85-344">Make any needed changes.</span></span> <span data-ttu-id="a7e85-345">Когда все будет готово, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a7e85-345">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="a7e85-346">Потребуется примерно один час, чтобы новая политика защиты от потери данных распространилась по центру обработки данных.</span><span class="sxs-lookup"><span data-stu-id="a7e85-346">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a7e85-347">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a7e85-347">Related articles</span></span>

- [<span data-ttu-id="a7e85-348">Определения типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="a7e85-348">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="a7e85-349">Пользовательские типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="a7e85-349">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="a7e85-350">Обзор политик защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="a7e85-350">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="a7e85-351">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a7e85-351">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="a7e85-352">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="a7e85-352">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema?view=exchange-ps)

