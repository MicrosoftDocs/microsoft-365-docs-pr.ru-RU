---
title: Хранение, зависящее от возникновения события
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: В этой статье описывается, как настроить операции бизнес-процесса, чтобы автоматизировать хранение с помощью событий, используя REST API Microsoft 365.
ms.openlocfilehash: c97106597733460caeab8d1d398ff81e23dd2727
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068118"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="a28e0-103">Автоматизация хранения на основе событий</span><span class="sxs-lookup"><span data-stu-id="a28e0-103">Automate event-based retention</span></span>

><span data-ttu-id="a28e0-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="a28e0-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="a28e0-105">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business.</span><span class="sxs-lookup"><span data-stu-id="a28e0-105">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business.</span></span> <span data-ttu-id="a28e0-106">To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant.</span><span class="sxs-lookup"><span data-stu-id="a28e0-106">To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant.</span></span> <span data-ttu-id="a28e0-107">Retaining only important, pertinent information is key to an organization's success.</span><span class="sxs-lookup"><span data-stu-id="a28e0-107">Retaining only important, pertinent information is key to an organization's success.</span></span>

<span data-ttu-id="a28e0-108">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="a28e0-108">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="a28e0-109">Retention can be triggered by using [retention labels](labels.md).</span><span class="sxs-lookup"><span data-stu-id="a28e0-109">Retention can be triggered by using [retention labels](labels.md).</span></span> <span data-ttu-id="a28e0-110">A retention label has the option to [base the retention period on a specific event](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="a28e0-110">A retention label has the option to [base the retention period on a specific event](event-driven-retention.md).</span></span> <span data-ttu-id="a28e0-111">Typically, the retention period is based on a known date, such as the creation date or last modified date for the content.</span><span class="sxs-lookup"><span data-stu-id="a28e0-111">Typically, the retention period is based on a known date, such as the creation date or last modified date for the content.</span></span> <span data-ttu-id="a28e0-112">However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span><span class="sxs-lookup"><span data-stu-id="a28e0-112">However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span></span>

<span data-ttu-id="a28e0-113">To ensure compliant disposal of content, it's imperative to know when an event takes place.</span><span class="sxs-lookup"><span data-stu-id="a28e0-113">To ensure compliant disposal of content, it's imperative to know when an event takes place.</span></span> <span data-ttu-id="a28e0-114">With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span><span class="sxs-lookup"><span data-stu-id="a28e0-114">With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="a28e0-115">Event-based retention solves this problem.</span><span class="sxs-lookup"><span data-stu-id="a28e0-115">Event-based retention solves this problem.</span></span> <span data-ttu-id="a28e0-116">This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span><span class="sxs-lookup"><span data-stu-id="a28e0-116">This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="a28e0-117">О хранении на основе событий</span><span class="sxs-lookup"><span data-stu-id="a28e0-117">About event-based retention</span></span>

<span data-ttu-id="a28e0-118">An organization can be small, medium, or large.</span><span class="sxs-lookup"><span data-stu-id="a28e0-118">An organization can be small, medium, or large.</span></span> <span data-ttu-id="a28e0-119">The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span><span class="sxs-lookup"><span data-stu-id="a28e0-119">The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span></span>

<span data-ttu-id="a28e0-120">For example, each day, tens and hundreds of employees are joining and leaving organizations.</span><span class="sxs-lookup"><span data-stu-id="a28e0-120">For example, each day, tens and hundreds of employees are joining and leaving organizations.</span></span> <span data-ttu-id="a28e0-121">The HR department continues to create, update, or delete employee-related documents as per business requirements.</span><span class="sxs-lookup"><span data-stu-id="a28e0-121">The HR department continues to create, update, or delete employee-related documents as per business requirements.</span></span> <span data-ttu-id="a28e0-122">This process is subject to the different retention policies outlined for the business:</span><span class="sxs-lookup"><span data-stu-id="a28e0-122">This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="a28e0-123">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled.</span><span class="sxs-lookup"><span data-stu-id="a28e0-123">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled.</span></span> <span data-ttu-id="a28e0-124">For example, you might retain documents for seven years after they're created and then delete them.</span><span class="sxs-lookup"><span data-stu-id="a28e0-124">For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="a28e0-125">**The period of retention of content can also be an unknown date**.</span><span class="sxs-lookup"><span data-stu-id="a28e0-125">**The period of retention of content can also be an unknown date**.</span></span> <span data-ttu-id="a28e0-126">For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span><span class="sxs-lookup"><span data-stu-id="a28e0-126">For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="a28e0-127">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them.</span><span class="sxs-lookup"><span data-stu-id="a28e0-127">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them.</span></span> <span data-ttu-id="a28e0-128">This is called event-based retention.</span><span class="sxs-lookup"><span data-stu-id="a28e0-128">This is called event-based retention.</span></span> <span data-ttu-id="a28e0-129">To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="a28e0-129">To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="a28e0-130">Настройка хранении на основе событий</span><span class="sxs-lookup"><span data-stu-id="a28e0-130">Set up event-based retention</span></span>

<span data-ttu-id="a28e0-131">В этом разделе описываются действия, которые необходимо выполнить до момента подготовки хранения содержимого.</span><span class="sxs-lookup"><span data-stu-id="a28e0-131">This section describes what needs to be done before retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="a28e0-132">Определение ролей</span><span class="sxs-lookup"><span data-stu-id="a28e0-132">Identify roles</span></span>

<span data-ttu-id="a28e0-133">Определите различные роли в организации, которые будут выполнять задачи управления записями и будут обеспечивать эффективное хранение деловых документов.</span><span class="sxs-lookup"><span data-stu-id="a28e0-133">Identify the different roles in an organization that perform Record Management tasks and would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="a28e0-134">Пользователь</span><span class="sxs-lookup"><span data-stu-id="a28e0-134">Persona</span></span> | <span data-ttu-id="a28e0-135">Роль</span><span class="sxs-lookup"><span data-stu-id="a28e0-135">Role</span></span> |
  | - | - |
  | <span data-ttu-id="a28e0-136">Администратор</span><span class="sxs-lookup"><span data-stu-id="a28e0-136">Admin</span></span> | <span data-ttu-id="a28e0-137">Создает типы событий хранения, метки хранения и репозитории записей в SharePoint</span><span class="sxs-lookup"><span data-stu-id="a28e0-137">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="a28e0-138">Управляющий записями</span><span class="sxs-lookup"><span data-stu-id="a28e0-138">Records Manager</span></span>                                  | <span data-ttu-id="a28e0-139">Предоставляет указания по политикам и расписанию хранения, а также сведения о соответствии требованиям</span><span class="sxs-lookup"><span data-stu-id="a28e0-139">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="a28e0-140">Системный администратор (компания)</span><span class="sxs-lookup"><span data-stu-id="a28e0-140">System Admin (business)</span></span>                          | <span data-ttu-id="a28e0-141">Настраивает внешние системы для работы с Microsoft 365 и управляет ими</span><span class="sxs-lookup"><span data-stu-id="a28e0-141">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="a28e0-142">Информационный работник</span><span class="sxs-lookup"><span data-stu-id="a28e0-142">Information Worker</span></span>                               | <span data-ttu-id="a28e0-143">Управляет жизненным циклом своих бизнес-процессов (отдела кадров, финансового отдела, ИТ-отдела и т. д.)</span><span class="sxs-lookup"><span data-stu-id="a28e0-143">Manages the lifecycle of their business process (HR, Finance, IT, and so on)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="a28e0-144">Настройка Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a28e0-144">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="a28e0-145">Администратор соответствия требованиям создает тип события — например, увольняется сотрудник, истекает срок действия договора или завершается производство продукта</span><span class="sxs-lookup"><span data-stu-id="a28e0-145">Compliance admin creates an event type &ndash; for example, Employee Termination or Contract Expiration or End of Product Manufacturing.</span></span> <span data-ttu-id="a28e0-146">(см. пошаговое описание процесса в статье [Хранение на основе событий](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="a28e0-146">(See the step-by-step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
2. <span data-ttu-id="a28e0-147">Администратор соответствия требованиям создает метку хранения на основе некоего события и связывает ее с типом события.</span><span class="sxs-lookup"><span data-stu-id="a28e0-147">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
    <span data-ttu-id="a28e0-148">Существует четыре типа триггеров меток хранения:</span><span class="sxs-lookup"><span data-stu-id="a28e0-148">There are four types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="a28e0-149">Дата создания</span><span class="sxs-lookup"><span data-stu-id="a28e0-149">Create date</span></span>
                
    2. <span data-ttu-id="a28e0-150">Дата последнего изменения</span><span class="sxs-lookup"><span data-stu-id="a28e0-150">Last modified</span></span>
                
    3. <span data-ttu-id="a28e0-151">Дата метки (когда содержимому была присвоена метка)</span><span class="sxs-lookup"><span data-stu-id="a28e0-151">Label date (when the content was labeled)</span></span>
                
    4. <span data-ttu-id="a28e0-152">На основе события</span><span class="sxs-lookup"><span data-stu-id="a28e0-152">Event-based</span></span>
    
3. <span data-ttu-id="a28e0-153">Администратор соответствия требованиям публикует метку хранения.</span><span class="sxs-lookup"><span data-stu-id="a28e0-153">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="a28e0-154">Настройка SharePoint</span><span class="sxs-lookup"><span data-stu-id="a28e0-154">Set up SharePoint</span></span>
   
<span data-ttu-id="a28e0-155">Чтобы создать репозиторий записей, администратор соответствия требованиям выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a28e0-155">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="a28e0-156">Создает сайт SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a28e0-156">Creates a SharePoint site.</span></span>

2. <span data-ttu-id="a28e0-157">Выполняет одно из указанных ниже действий:</span><span class="sxs-lookup"><span data-stu-id="a28e0-157">Does one of the following:</span></span>
        
   - <span data-ttu-id="a28e0-158">Creates a SharePoint library: Set event-based label at the library level.</span><span class="sxs-lookup"><span data-stu-id="a28e0-158">Creates a SharePoint library: Set event-based label at the library level.</span></span> <span data-ttu-id="a28e0-159">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="a28e0-159">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
   - <span data-ttu-id="a28e0-160">Настройка набора документов в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a28e0-160">Sets up a document set in SharePoint.</span></span> <span data-ttu-id="a28e0-161">Дополнительные сведения см. в статье [Общие сведения о наборах документов](https://support.microsoft.com/ru-RU/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).</span><span class="sxs-lookup"><span data-stu-id="a28e0-161">For more information, see [Introduction to document sets](https://support.microsoft.com/ru-RU/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).</span></span>
      
3. <span data-ttu-id="a28e0-162">Назначает ИД ресурса для каждого набора документов сотрудников.</span><span class="sxs-lookup"><span data-stu-id="a28e0-162">Assigns an asset ID to each employee document set.</span></span> <span data-ttu-id="a28e0-163">ИД ресурса — это наименование продукта или код, который используется организацией, например код сотрудника может быть кодом ресурса.</span><span class="sxs-lookup"><span data-stu-id="a28e0-163">An asset ID is a product name or code used by the organization, for example, Employee number can be an asset ID.</span></span> <span data-ttu-id="a28e0-164">При назначении ИД ресурса папке, каждый элемент в этой папке автоматически наследует тот же самый ИД ресурса.</span><span class="sxs-lookup"><span data-stu-id="a28e0-164">By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID.</span></span> <span data-ttu-id="a28e0-165">Это означает, что срок хранения всех элементов может быть вызван тем же событием.</span><span class="sxs-lookup"><span data-stu-id="a28e0-165">This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="a28e0-166">Способы запуска хранения на основе события</span><span class="sxs-lookup"><span data-stu-id="a28e0-166">Ways to trigger event-based retention</span></span>

<span data-ttu-id="a28e0-167">Существует два способа запуска хранения на основе события:</span><span class="sxs-lookup"><span data-stu-id="a28e0-167">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="a28e0-168">\*\*Использование пользовательского интерфейса центра администрирования \*\* С помощью этого процесса можно уменьшить объем содержимого, сохраняемого за один раз, или запускать хранение реже, например, раз в месяц или раз в год.</span><span class="sxs-lookup"><span data-stu-id="a28e0-168">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention isn't often, such as monthly or yearly.</span></span> <span data-ttu-id="a28e0-169">Дополнительные сведения об использовании этого метода см. в статье [Обзор хранения на основе события](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="a28e0-169">For more information about this method, see [Overview of event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="a28e0-170">Тем не менее, этот способ запуска хранения может потребовать значительных временных затрат и подвержен ошибкам, что препятствует масштабированию.</span><span class="sxs-lookup"><span data-stu-id="a28e0-170">However, this method of triggering retention can be time consuming and prone to error, thus stunting scalability.</span></span> <span data-ttu-id="a28e0-171">Таким образом, автоматизированное беспрепятственное решение для запуска хранения может повысить безопасность и улучшить соответствие требованиям в отношении данных.</span><span class="sxs-lookup"><span data-stu-id="a28e0-171">Therefore, an automated, seamless solution to trigger retention can enhance data security and compliance.</span></span>

- <span data-ttu-id="a28e0-172">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly.</span><span class="sxs-lookup"><span data-stu-id="a28e0-172">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly.</span></span> <span data-ttu-id="a28e0-173">The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="a28e0-173">The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center.</span></span> <span data-ttu-id="a28e0-174">You don't need to manually create an event in the UI each time one occurs.</span><span class="sxs-lookup"><span data-stu-id="a28e0-174">You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="a28e0-175">Существует два способа использования REST API:</span><span class="sxs-lookup"><span data-stu-id="a28e0-175">There are two options for using the REST API:</span></span>

- <span data-ttu-id="a28e0-176">**Microsoft Flow или подобное приложение** можно использовать для автоматического запуска события.</span><span class="sxs-lookup"><span data-stu-id="a28e0-176">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="a28e0-177">Microsoft Flow является оркестратором подключения к другим системам.</span><span class="sxs-lookup"><span data-stu-id="a28e0-177">Microsoft Flow is an orchestrator for connecting to other systems.</span></span> <span data-ttu-id="a28e0-178">Использование Microsoft Flow не требует настраиваемого решения.</span><span class="sxs-lookup"><span data-stu-id="a28e0-178">Using Microsoft Flow doesn't require a custom solution.</span></span>

- <span data-ttu-id="a28e0-179">**PowerShell или HTTP-клиент для вызова REST API**. Используйте PowerShell (версии 6 или выше) для вызова REST API Microsoft 365, чтобы создать события.</span><span class="sxs-lookup"><span data-stu-id="a28e0-179">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="a28e0-180">Rest API — это конечная точка службы, поддерживающая наборы операций HTTP (методов), которые обеспечивают создание / получение / обновление / удаление доступа к ресурсам службы.</span><span class="sxs-lookup"><span data-stu-id="a28e0-180">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="a28e0-181">Дополнительные сведения см. в статье [Компоненты запросов и ответов REST API](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="a28e0-181">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="a28e0-182">В этом случае с помощью REST API Microsoft 365 можно создавать и получать события, используя операции (методы) POST и GET.</span><span class="sxs-lookup"><span data-stu-id="a28e0-182">In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="a28e0-183">Примеры сценариев</span><span class="sxs-lookup"><span data-stu-id="a28e0-183">Example scenarios</span></span>

<span data-ttu-id="a28e0-184">Давайте рассмотрим следующие сценарии.</span><span class="sxs-lookup"><span data-stu-id="a28e0-184">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="a28e0-185">Сценарий 1. Сотрудники увольняются из организации</span><span class="sxs-lookup"><span data-stu-id="a28e0-185">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="a28e0-186">В организации создается и хранится множество документов, связанных с сотрудниками, для каждого сотрудника.</span><span class="sxs-lookup"><span data-stu-id="a28e0-186">An organization creates and stores numerous employee-related documents per employee.</span></span> <span data-ttu-id="a28e0-187">Эти документы управляются и сохраняются в течение работы в организации каждого сотрудника.</span><span class="sxs-lookup"><span data-stu-id="a28e0-187">These documents are managed and retained during the employment of each employee.</span></span> <span data-ttu-id="a28e0-188">Тем не менее, когда работник покидает организацию или в случае его увольнения, организация обязана в соответствии с требованиями законодательства и бизнеса сохранять документы этого работника в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="a28e0-188">However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="a28e0-189">Если из организации ежедневно увольняется несколько сотрудников, необходимо запускать счетчики хранения сотен или даже тысяч документов каждый день.</span><span class="sxs-lookup"><span data-stu-id="a28e0-189">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="a28e0-190">Кроме того, для каждого сотрудника период хранения рассчитывается на основе типа записи сотрудника (дата увольнения сотрудника + количество дней, месяцев или лет).</span><span class="sxs-lookup"><span data-stu-id="a28e0-190">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months, or years based on the type of the employee record.</span></span> <span data-ttu-id="a28e0-191">Например, у документов о зарплате и документов о премии одного и того же сотрудника могут быть разные периоды хранения.</span><span class="sxs-lookup"><span data-stu-id="a28e0-191">For example, worker’s compensation of the employee vs. benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="a28e0-192">На схеме далее показано, как может существовать несколько меток, связанных с одним событием.</span><span class="sxs-lookup"><span data-stu-id="a28e0-192">The diagram below shows how there can be multiple labels that are associated with a single event.</span></span> <span data-ttu-id="a28e0-193">Здесь все файлы под меткой “Компенсации работника” и все файлы под меткой “Льготы сотрудников” связаны с одним событием — уход сотрудника из организации.</span><span class="sxs-lookup"><span data-stu-id="a28e0-193">Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event, which is the employee leaving the organization.</span></span> <span data-ttu-id="a28e0-194">Каждый из этих различных файлов имеет различные счетчики хранения.</span><span class="sxs-lookup"><span data-stu-id="a28e0-194">Each of these different files has different retention clocks.</span></span> <span data-ttu-id="a28e0-195">Таким образом, когда сотрудник покидает организацию, эти файлы под каждой меткой имеют различный срок хранения.</span><span class="sxs-lookup"><span data-stu-id="a28e0-195">So, when an employee leaves the organization, these files within each label experience a different retention period.</span></span> <span data-ttu-id="a28e0-196">Запуск всех этих разных счетчиков хранения для каждого типа файла или метки для каждого сотрудника является очень сложной задачей.</span><span class="sxs-lookup"><span data-stu-id="a28e0-196">Triggering all these different retention clocks for each file type or label for each employee is a very challenging task.</span></span> <span data-ttu-id="a28e0-197">Представьте, что это необходимо выполнить для нескольких сотрудников.</span><span class="sxs-lookup"><span data-stu-id="a28e0-197">Imagine doing this for multiple employees.</span></span>

![Схема типов событий, событий и меток](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="a28e0-199">Поэтому автоматизированный процесс запуска всех этих различных счетчиков хранения для нескольких сотрудников должен работать быстро, быть безошибочным и очень эффективным.</span><span class="sxs-lookup"><span data-stu-id="a28e0-199">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free, and extremely efficient.</span></span>

<span data-ttu-id="a28e0-200">**Настройка автоматизированного хранения на основе событий для этого сценария:**</span><span class="sxs-lookup"><span data-stu-id="a28e0-200">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Схема ролей и действий для сценария, когда сотрудник увольняется из организации](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="a28e0-202">Администратор создает папки сотрудников в наборе документов, например "Евгения Артемьева", "Артем Кузнецов".</span><span class="sxs-lookup"><span data-stu-id="a28e0-202">Admin creates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="a28e0-203">Администратор добавляет в каждую папку файлы сотрудников, например с данными о премиях и зарплате.</span><span class="sxs-lookup"><span data-stu-id="a28e0-203">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder.</span></span>

  - <span data-ttu-id="a28e0-204">Администратор назначает идентификатор ресурса для каждой папки сотрудников.</span><span class="sxs-lookup"><span data-stu-id="a28e0-204">Admin assigns Asset ID to each employee folder.</span></span> 

  - <span data-ttu-id="a28e0-205">Администратор Центра безопасности и соответствия требованиям выполняет вход в Центр безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a28e0-205">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="a28e0-206">Администратор безопасности и соответствия требованиям создает типы событий, связанные с сотрудником, например "Увольнение сотрудника" и "Прием сотрудника на работу".</span><span class="sxs-lookup"><span data-stu-id="a28e0-206">SCC Admin creates employee-related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="a28e0-207">Администратор безопасности и соответствия требованиям создает метку "Хранение для сотрудника".</span><span class="sxs-lookup"><span data-stu-id="a28e0-207">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="a28e0-208">Эта метка "Хранение для сотрудника" публикуется и вручную или автоматически применяется к файлам сотрудника в SharePoint</span><span class="sxs-lookup"><span data-stu-id="a28e0-208">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint.</span></span>

  - <span data-ttu-id="a28e0-209">Система управления отдела кадров, например Workday, может работать совместно с Microsoft Flow для периодического управления файлами сотрудников</span><span class="sxs-lookup"><span data-stu-id="a28e0-209">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files.</span></span>

  - <span data-ttu-id="a28e0-210">Если сотрудник увольняется из организации, Flow активирует REST API хранения на основе событий M365, который запустит счетчик хранения для файлов определенного сотрудника.</span><span class="sxs-lookup"><span data-stu-id="a28e0-210">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="a28e0-211">Использование Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="a28e0-211">Using Microsoft Flow</span></span>

<span data-ttu-id="a28e0-212">Шаг 1. Создайте процесс создания события с помощью REST API Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a28e0-212">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Использование Flow для создания события](../media/automate-event-driven-retention-flow-1.png)

![Использование Flow для вызова REST API](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="a28e0-215">Создание события</span><span class="sxs-lookup"><span data-stu-id="a28e0-215">Create an event</span></span>

<span data-ttu-id="a28e0-216">Пример кода для вызова REST API:</span><span class="sxs-lookup"><span data-stu-id="a28e0-216">Sample code to call the REST API:</span></span>

- <span data-ttu-id="a28e0-217">**Метод**: POST</span><span class="sxs-lookup"><span data-stu-id="a28e0-217">**Method**: POST</span></span>
- <span data-ttu-id="a28e0-218">**URL-адрес**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="a28e0-218">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="a28e0-219">**Заголовки**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="a28e0-219">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="a28e0-220">**Текст**:</span><span class="sxs-lookup"><span data-stu-id="a28e0-220">**Body**:</span></span>
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
- <span data-ttu-id="a28e0-221">**Проверка подлинности**: обычная</span><span class="sxs-lookup"><span data-stu-id="a28e0-221">**Authentication**: Basic</span></span>
- <span data-ttu-id="a28e0-222">**Имя пользователя**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="a28e0-222">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="a28e0-223">**Пароль**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="a28e0-223">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="a28e0-224">Доступные параметры</span><span class="sxs-lookup"><span data-stu-id="a28e0-224">Available parameters</span></span>


|<span data-ttu-id="a28e0-225">Параметры</span><span class="sxs-lookup"><span data-stu-id="a28e0-225">Parameters</span></span>|<span data-ttu-id="a28e0-226">Описание</span><span class="sxs-lookup"><span data-stu-id="a28e0-226">Description</span></span>|<span data-ttu-id="a28e0-227">Примечания</span><span class="sxs-lookup"><span data-stu-id="a28e0-227">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="a28e0-228"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="a28e0-228"><d:Name></d:Name></span></span>|<span data-ttu-id="a28e0-229">Указание уникального имени события.</span><span class="sxs-lookup"><span data-stu-id="a28e0-229">Provide a unique name for the event,</span></span>|<span data-ttu-id="a28e0-230">Не может содержать начальные и конечные пробелы и следующие символы: % \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="a28e0-230">Cannot contain trailing spaces, and the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="a28e0-231">, : ;</span><span class="sxs-lookup"><span data-stu-id="a28e0-231">, : ;</span></span>|
|<span data-ttu-id="a28e0-232"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="a28e0-232"><d:EventType></d:EventType></span></span>|<span data-ttu-id="a28e0-233">Введите название типа события (или Guid).</span><span class="sxs-lookup"><span data-stu-id="a28e0-233">Enter event type name (or Guid),</span></span>|<span data-ttu-id="a28e0-234">Example: “Employee termination”.</span><span class="sxs-lookup"><span data-stu-id="a28e0-234">Example: “Employee termination”.</span></span> <span data-ttu-id="a28e0-235">Event type has to be associated with a retention label.</span><span class="sxs-lookup"><span data-stu-id="a28e0-235">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="a28e0-236"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="a28e0-236"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="a28e0-237">Введите "ComplianceAssetId:" + код сотрудника</span><span class="sxs-lookup"><span data-stu-id="a28e0-237">Enter “ComplianceAssetId:” + employee Id</span></span>|<span data-ttu-id="a28e0-238">Пример: "ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="a28e0-238">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="a28e0-239"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="a28e0-239"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="a28e0-240">Дата и время события</span><span class="sxs-lookup"><span data-stu-id="a28e0-240">Event Date and Time</span></span>|<span data-ttu-id="a28e0-241">Формат: ГГГГ-ММ-ДДTчч:мм:ссZ. Пример: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="a28e0-241">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

##### <a name="response-codes"></a><span data-ttu-id="a28e0-242">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="a28e0-242">Response codes</span></span>

| <span data-ttu-id="a28e0-243">Код ответа</span><span class="sxs-lookup"><span data-stu-id="a28e0-243">Response Code</span></span> | <span data-ttu-id="a28e0-244">Описание</span><span class="sxs-lookup"><span data-stu-id="a28e0-244">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="a28e0-245">302</span><span class="sxs-lookup"><span data-stu-id="a28e0-245">302</span></span>               | <span data-ttu-id="a28e0-246">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="a28e0-246">Redirect</span></span>              |
| <span data-ttu-id="a28e0-247">201</span><span class="sxs-lookup"><span data-stu-id="a28e0-247">201</span></span>               | <span data-ttu-id="a28e0-248">Создано</span><span class="sxs-lookup"><span data-stu-id="a28e0-248">Created</span></span>               |
| <span data-ttu-id="a28e0-249">403</span><span class="sxs-lookup"><span data-stu-id="a28e0-249">403</span></span>               | <span data-ttu-id="a28e0-250">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="a28e0-250">Authorization Failed</span></span>  |
| <span data-ttu-id="a28e0-251">401</span><span class="sxs-lookup"><span data-stu-id="a28e0-251">401</span></span>               | <span data-ttu-id="a28e0-252">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="a28e0-252">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="a28e0-253">Получение событий на основе диапазона времени</span><span class="sxs-lookup"><span data-stu-id="a28e0-253">Get Events based on time range</span></span>

- <span data-ttu-id="a28e0-254">**Метод**: GET</span><span class="sxs-lookup"><span data-stu-id="a28e0-254">**Method**: GET</span></span>

- <span data-ttu-id="a28e0-255">**URL-адрес**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="a28e0-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="a28e0-256">**Заголовки**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="a28e0-256">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="a28e0-257">**Проверка подлинности**: обычная</span><span class="sxs-lookup"><span data-stu-id="a28e0-257">**Authentication**: Basic</span></span>

- <span data-ttu-id="a28e0-258">**Имя пользователя**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="a28e0-258">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="a28e0-259">**Пароль**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="a28e0-259">**Password**: "Compliancepassword"</span></span>


##### <a name="response-codes"></a><span data-ttu-id="a28e0-260">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="a28e0-260">Response codes</span></span>

| <span data-ttu-id="a28e0-261">Код ответа</span><span class="sxs-lookup"><span data-stu-id="a28e0-261">Response Code</span></span> | <span data-ttu-id="a28e0-262">Описание</span><span class="sxs-lookup"><span data-stu-id="a28e0-262">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="a28e0-263">200</span><span class="sxs-lookup"><span data-stu-id="a28e0-263">200</span></span>               | <span data-ttu-id="a28e0-264">Все в порядке, список событий в формате atom+xml</span><span class="sxs-lookup"><span data-stu-id="a28e0-264">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="a28e0-265">404</span><span class="sxs-lookup"><span data-stu-id="a28e0-265">404</span></span>               | <span data-ttu-id="a28e0-266">Не найдено</span><span class="sxs-lookup"><span data-stu-id="a28e0-266">Not found</span></span>                         |
| <span data-ttu-id="a28e0-267">302</span><span class="sxs-lookup"><span data-stu-id="a28e0-267">302</span></span>               | <span data-ttu-id="a28e0-268">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="a28e0-268">Redirect</span></span>                          |
| <span data-ttu-id="a28e0-269">401</span><span class="sxs-lookup"><span data-stu-id="a28e0-269">401</span></span>               | <span data-ttu-id="a28e0-270">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="a28e0-270">Authorization Failed</span></span>              |
| <span data-ttu-id="a28e0-271">403</span><span class="sxs-lookup"><span data-stu-id="a28e0-271">403</span></span>               | <span data-ttu-id="a28e0-272">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="a28e0-272">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="a28e0-273">Получение события по идентификатору</span><span class="sxs-lookup"><span data-stu-id="a28e0-273">Get an event by ID</span></span>

- <span data-ttu-id="a28e0-274">**Метод**: GET</span><span class="sxs-lookup"><span data-stu-id="a28e0-274">**Method**: GET</span></span>

- <span data-ttu-id="a28e0-275">**URL-адрес**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="a28e0-275">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="a28e0-276">**Заголовки**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="a28e0-276">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="a28e0-277">**Проверка подлинности**: обычная</span><span class="sxs-lookup"><span data-stu-id="a28e0-277">**Authentication**: Basic</span></span>

- <span data-ttu-id="a28e0-278">**Имя пользователя**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="a28e0-278">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="a28e0-279">**Пароль**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="a28e0-279">**Password**: "Compliancepassword"</span></span>



##### <a name="response-codes"></a><span data-ttu-id="a28e0-280">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="a28e0-280">Response codes</span></span>

| <span data-ttu-id="a28e0-281">Код ответа</span><span class="sxs-lookup"><span data-stu-id="a28e0-281">Response Code</span></span> | <span data-ttu-id="a28e0-282">Описание</span><span class="sxs-lookup"><span data-stu-id="a28e0-282">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="a28e0-283">200</span><span class="sxs-lookup"><span data-stu-id="a28e0-283">200</span></span>               | <span data-ttu-id="a28e0-284">Все в порядке, текст ответа содержит событие в формате atom+xml</span><span class="sxs-lookup"><span data-stu-id="a28e0-284">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="a28e0-285">404</span><span class="sxs-lookup"><span data-stu-id="a28e0-285">404</span></span>               | <span data-ttu-id="a28e0-286">Не найдено</span><span class="sxs-lookup"><span data-stu-id="a28e0-286">Not found</span></span>                                            |
| <span data-ttu-id="a28e0-287">302</span><span class="sxs-lookup"><span data-stu-id="a28e0-287">302</span></span>               | <span data-ttu-id="a28e0-288">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="a28e0-288">Redirect</span></span>                                             |
| <span data-ttu-id="a28e0-289">401</span><span class="sxs-lookup"><span data-stu-id="a28e0-289">401</span></span>               | <span data-ttu-id="a28e0-290">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="a28e0-290">Authorization Failed</span></span>                                 |
| <span data-ttu-id="a28e0-291">403</span><span class="sxs-lookup"><span data-stu-id="a28e0-291">403</span></span>               | <span data-ttu-id="a28e0-292">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="a28e0-292">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="a28e0-293">Получение события по имени</span><span class="sxs-lookup"><span data-stu-id="a28e0-293">Get an event by name</span></span>

- <span data-ttu-id="a28e0-294">**Метод**: GET</span><span class="sxs-lookup"><span data-stu-id="a28e0-294">**Method**: GET</span></span>

- <span data-ttu-id="a28e0-295">**URL-адрес**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="a28e0-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="a28e0-296">**Заголовки**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="a28e0-296">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="a28e0-297">**Проверка подлинности**: обычная</span><span class="sxs-lookup"><span data-stu-id="a28e0-297">**Authentication**: Basic</span></span>

- <span data-ttu-id="a28e0-298">**Имя пользователя**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="a28e0-298">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="a28e0-299">**Пароль**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="a28e0-299">**Password**: "Compliancepassword"</span></span>


##### <a name="response-codes"></a><span data-ttu-id="a28e0-300">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="a28e0-300">Response codes</span></span>

| <span data-ttu-id="a28e0-301">Код ответа</span><span class="sxs-lookup"><span data-stu-id="a28e0-301">Response Code</span></span> | <span data-ttu-id="a28e0-302">Описание</span><span class="sxs-lookup"><span data-stu-id="a28e0-302">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="a28e0-303">200</span><span class="sxs-lookup"><span data-stu-id="a28e0-303">200</span></span>               | <span data-ttu-id="a28e0-304">Все в порядке, текст ответа содержит событие в формате atom+xml</span><span class="sxs-lookup"><span data-stu-id="a28e0-304">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="a28e0-305">404</span><span class="sxs-lookup"><span data-stu-id="a28e0-305">404</span></span>               | <span data-ttu-id="a28e0-306">Не найдено</span><span class="sxs-lookup"><span data-stu-id="a28e0-306">Not found</span></span>                                            |
| <span data-ttu-id="a28e0-307">302</span><span class="sxs-lookup"><span data-stu-id="a28e0-307">302</span></span>               | <span data-ttu-id="a28e0-308">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="a28e0-308">Redirect</span></span>                                             |
| <span data-ttu-id="a28e0-309">401</span><span class="sxs-lookup"><span data-stu-id="a28e0-309">401</span></span>               | <span data-ttu-id="a28e0-310">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="a28e0-310">Authorization Failed</span></span>                                 |
| <span data-ttu-id="a28e0-311">403</span><span class="sxs-lookup"><span data-stu-id="a28e0-311">403</span></span>               | <span data-ttu-id="a28e0-312">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="a28e0-312">Authentication Failed</span></span>                                |

#### <a name="using-powershell-version-6-or-later-or-any-http-client"></a><span data-ttu-id="a28e0-313">Использование PowerShell (версии 6 или более поздней) или любого HTTP-клиента</span><span class="sxs-lookup"><span data-stu-id="a28e0-313">Using PowerShell (version 6 or later) or any HTTP client</span></span>

<span data-ttu-id="a28e0-314">Шаг 1. Подключитесь к PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a28e0-314">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="a28e0-315">Шаг 2. Запустите указанный ниже сценарий.</span><span class="sxs-lookup"><span data-stu-id="a28e0-315">Step 2: Run the following script.</span></span>

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```


#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="a28e0-316">Проверка результатов обоих вариантов</span><span class="sxs-lookup"><span data-stu-id="a28e0-316">Verify the outcome in both options</span></span>

<span data-ttu-id="a28e0-317">Шаг 1. Перейдите в Центр безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a28e0-317">Step 1: Go to the Security & Compliance Center.</span></span>

<span data-ttu-id="a28e0-318">Шаг 2. Выберите **События** в разделе **Управление информацией**.</span><span class="sxs-lookup"><span data-stu-id="a28e0-318">Step 2: Select **Events** under **Information governance**.</span></span>

<span data-ttu-id="a28e0-319">Шаг 3. Убедитесь, что событие создано.</span><span class="sxs-lookup"><span data-stu-id="a28e0-319">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="a28e0-320">Аналогичным образом описанные выше варианты автоматизации хранения на основе событий можно использовать и для следующих сценариев.</span><span class="sxs-lookup"><span data-stu-id="a28e0-320">Similarly, the above options to automate event-based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="a28e0-321">Сценарий 2. Окончание действия договоров</span><span class="sxs-lookup"><span data-stu-id="a28e0-321">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="a28e0-322">Организация может иметь несколько записей для одного договора с клиентами, поставщиками и партнерами.</span><span class="sxs-lookup"><span data-stu-id="a28e0-322">An organization can have multiple records for a single contract with customers, vendors, and partners.</span></span> <span data-ttu-id="a28e0-323">Эти документы можно хранить в библиотеке документов, например в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a28e0-323">These documents can reside in a document library like SharePoint.</span></span> <span data-ttu-id="a28e0-324">Окончание договора определяет начало срока хранения документов, связанных с договором.</span><span class="sxs-lookup"><span data-stu-id="a28e0-324">The end of a contract determines the start of the retention period of the documents associated with the contract.</span></span> <span data-ttu-id="a28e0-325">Например, все записи, связанные с договорами, нужно хранить в течение пяти лет с момента истечения срока действия договора.</span><span class="sxs-lookup"><span data-stu-id="a28e0-325">For example, all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="a28e0-326">Событием, активирующим пятилетнее хранение, будет окончание срока действия договора.</span><span class="sxs-lookup"><span data-stu-id="a28e0-326">The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="a28e0-327">Система управления отношениями с клиентами может работать совместно с Microsoft 365 и активировать хранение документов договора.</span><span class="sxs-lookup"><span data-stu-id="a28e0-327">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents.</span></span>

<span data-ttu-id="a28e0-328">**Настройка автоматизированного хранения на основе событий для этого сценария:**</span><span class="sxs-lookup"><span data-stu-id="a28e0-328">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Схема ролей и задач для сценария окончания действия договора](../media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="a28e0-330">Администратор создает библиотеку SharePoint с различными папками для каждого типа договора.</span><span class="sxs-lookup"><span data-stu-id="a28e0-330">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="a28e0-331">Администратор добавляет файлы договора, например лицензионные соглашения, договоры о разработке, в папку каждого договора.</span><span class="sxs-lookup"><span data-stu-id="a28e0-331">Admin adds contract files such as License Contracts, Development Contracts to each contract folder.</span></span>

  - <span data-ttu-id="a28e0-332">Администратор назначает идентификатор ресурса для каждой папки договора.</span><span class="sxs-lookup"><span data-stu-id="a28e0-332">Admin assigns Asset ID to each contract folder.</span></span>

  - <span data-ttu-id="a28e0-333">Администратор Центра безопасности и соответствия требованиям выполняет вход в Центр безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a28e0-333">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="a28e0-334">Администратор безопасности и соответствия требованиям создает типы событий, связанные с договором, например "Создание договора" и "Завершение действия договора".</span><span class="sxs-lookup"><span data-stu-id="a28e0-334">SCC Admin creates contract-related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="a28e0-335">Администратор безопасности и соответствия требованиям создает метку "Завершение действия договора".</span><span class="sxs-lookup"><span data-stu-id="a28e0-335">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="a28e0-336">Эта метка "Завершение действия договора" публикуется и вручную или автоматически применяется к файлам договора в SharePoint</span><span class="sxs-lookup"><span data-stu-id="a28e0-336">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint.</span></span>

  - <span data-ttu-id="a28e0-337">Система управления договорами может работать совместно с Microsoft Flow или аналогичным приложением для периодического управления файлами договоров.</span><span class="sxs-lookup"><span data-stu-id="a28e0-337">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files.</span></span>

  - <span data-ttu-id="a28e0-338">Если срок действия договора завершается, Microsoft Flow активирует REST API хранения на основе событий M365, который запустит счетчик хранения для файлов определенного договора.</span><span class="sxs-lookup"><span data-stu-id="a28e0-338">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="a28e0-339">Сценарий 3. Прекращение производства продукта</span><span class="sxs-lookup"><span data-stu-id="a28e0-339">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="a28e0-340">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents.</span><span class="sxs-lookup"><span data-stu-id="a28e0-340">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents.</span></span> <span data-ttu-id="a28e0-341">When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span><span class="sxs-lookup"><span data-stu-id="a28e0-341">When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="a28e0-342">Система планирования ресурсов предприятия (ERP) может работать совместно с Microsoft 365 и Microsoft Flow для активации хранения.</span><span class="sxs-lookup"><span data-stu-id="a28e0-342">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="a28e0-343">**Настройка автоматизированного хранения на основе событий для этого сценария:**</span><span class="sxs-lookup"><span data-stu-id="a28e0-343">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Схема ролей и задач для сценария жизненного цикла продукта](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="a28e0-345">Администратор создает папки продуктов в наборе документов, например "Продукт 1", "Продукт 2" и т. д.</span><span class="sxs-lookup"><span data-stu-id="a28e0-345">Admin creates product folders in the Document set such as Product 1, Product 2, and so on.</span></span>

  - <span data-ttu-id="a28e0-346">Администратор добавляет файлы продуктов, например технические характеристики производства, цены продуктов и лицензирование продуктов, в каждую папку продукта.</span><span class="sxs-lookup"><span data-stu-id="a28e0-346">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder.</span></span>

  - <span data-ttu-id="a28e0-347">Администратор назначает ИД ресурса для каждой папки продукта.</span><span class="sxs-lookup"><span data-stu-id="a28e0-347">Admin assigns Asset ID to each product folder.</span></span>

  - <span data-ttu-id="a28e0-348">Администратор Центра безопасности и соответствия требованиям выполняет вход в Центр безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a28e0-348">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="a28e0-349">Администратор безопасности и соответствия требованиям создает типы событий, связанные с сотрудником, например "Начало производства продукта" и "Окончание производства продукта".</span><span class="sxs-lookup"><span data-stu-id="a28e0-349">SCC Admin creates employee-related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="a28e0-350">Администратор безопасности и соответствия требованиям создает метку "Окончание производства продукта".</span><span class="sxs-lookup"><span data-stu-id="a28e0-350">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="a28e0-351">Эта метка "Завершение изготовление продукта" публикуется и вручную или автоматически применяется к файлам продукта в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a28e0-351">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint.</span></span>

  - <span data-ttu-id="a28e0-352">Система ERP может работать совместно с Microsoft Flow или аналогичным приложением для периодического управления файлами продуктов.</span><span class="sxs-lookup"><span data-stu-id="a28e0-352">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files.</span></span>

  - <span data-ttu-id="a28e0-353">Если изготовление продукта завершается, Microsoft Flow активирует REST API хранения на основе событий M365, который запустит счетчик хранения для файлов определенного продукта.</span><span class="sxs-lookup"><span data-stu-id="a28e0-353">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="a28e0-354">Приложение</span><span class="sxs-lookup"><span data-stu-id="a28e0-354">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="a28e0-355">Использование результатов ответа 302 (перенаправление) для вызова REST API</span><span class="sxs-lookup"><span data-stu-id="a28e0-355">Using Redirect 302 response results to call the REST API</span></span>

1. <span data-ttu-id="a28e0-356">Вызов события хранения POST с помощью URL-адреса REST API: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="a28e0-356">Invoke a POST retention event call by using the REST API URL: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
    
    <span data-ttu-id="a28e0-357">Требуются разрешения глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="a28e0-357">Global administrator permissions are required.</span></span>

2. <span data-ttu-id="a28e0-358">Проверьте код ответа.</span><span class="sxs-lookup"><span data-stu-id="a28e0-358">Check the response code.</span></span> <span data-ttu-id="a28e0-359">Если получен код 302, получите URL-адрес перенаправления из свойства Location (Расположение) заголовка ответа.</span><span class="sxs-lookup"><span data-stu-id="a28e0-359">If it's 302, then get the redirected URL from Location property of the response header.</span></span>

3. <span data-ttu-id="a28e0-360">Вызовите событие хранения POST еще раз с помощью URL-адреса перенаправления</span><span class="sxs-lookup"><span data-stu-id="a28e0-360">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="a28e0-361">Сведения об авторах</span><span class="sxs-lookup"><span data-stu-id="a28e0-361">Credits</span></span>

<span data-ttu-id="a28e0-362">Редактор статьи:</span><span class="sxs-lookup"><span data-stu-id="a28e0-362">This topic was reviewed by:</span></span>

<span data-ttu-id="a28e0-363">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="a28e0-363">Antonio Maio</span></span><br/><span data-ttu-id="a28e0-364">MVP в сфере приложений и служб Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="a28e0-364">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="a28e0-365">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="a28e0-365">Antonio.Maio@Protiviti.com</span></span>
