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
ms.openlocfilehash: 75816512878bc6e42b5330309b99e72095d5546f
ms.sourcegitcommit: 56772bed89516cebc5eb370e292ccfbb4889cb38
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "44330825"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="4c789-103">Автоматизация хранения на основе событий</span><span class="sxs-lookup"><span data-stu-id="4c789-103">Automate event-based retention</span></span>

><span data-ttu-id="4c789-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="4c789-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="4c789-p101">Процессы развертывания содержимого в организации, а также обнаружения избыточных, устаревших и тривиальных данных играют важную роль. Чтобы продолжать соответствовать юридическим, нормативным и бизнес-требованиям, организации должны обеспечить хранение и защиту важной информации, а также быстрый поиск необходимых данных. Хранение только важной и подходящей информации является ключевым фактором успеха организаций.</span><span class="sxs-lookup"><span data-stu-id="4c789-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to an organization's success.</span></span>

<span data-ttu-id="4c789-p102">Чтобы помочь удовлетворить эту потребность, организации могут использовать преимущества решений для хранения в Центре безопасности и соответствия требованиям Office 365. Связанные с хранением операции можно активировать с помощью [меток хранения](labels.md). У метки хранения есть параметр для [определения периода хранения на основе конкретного события](event-driven-retention.md). Обычно период хранения зависит от известной даты, например даты создания или последнего изменения содержимого. Однако у организаций также есть требования по удалению содержимого на основе возникновения событий, например через 7 лет после того, как сотрудник уволился из организации.</span><span class="sxs-lookup"><span data-stu-id="4c789-p102">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span></span>

<span data-ttu-id="4c789-p103">Чтобы обеспечить удаление содержимого в соответствии с требованиями, важно знать, когда происходят события. Из-за стремительного роста объема содержимого становится сложно хранить и удалять данные своевременно и в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="4c789-p103">To ensure compliant disposal of content, it's imperative to know when an event takes place. With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="4c789-p104">Хранения на основе событий решает эту проблему. В этой статье описывается, как настроить операции бизнес-процесса, чтобы автоматизировать хранение с помощью событий, используя REST API Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c789-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="4c789-117">О хранении на основе событий</span><span class="sxs-lookup"><span data-stu-id="4c789-117">About event-based retention</span></span>

<span data-ttu-id="4c789-p105">Независимо от размера организации количество деловых документов, юридических документов, файлов сотрудников, договоров и документов о продукции, которые ежедневно создаются и которыми необходимо управлять, стремительно растет.</span><span class="sxs-lookup"><span data-stu-id="4c789-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span></span>

<span data-ttu-id="4c789-p106">Например, каждый день десятки и сотни сотрудников устраиваются на работу в организации или увольняются. Отдел кадров постоянно создает, обновляет или удаляет связанные с сотрудниками документы в соответствии с бизнес-требованиями. Этот процесс регулируется различными политиками, определяемыми для компании:</span><span class="sxs-lookup"><span data-stu-id="4c789-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="4c789-p107">**Период хранения содержимого может зависеть от известной даты**, например даты создания, последнего изменения содержимого или присвоения ему метки. Пример: вы можете хранить документы в течение семи лет после создания, а затем удалить их.</span><span class="sxs-lookup"><span data-stu-id="4c789-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="4c789-p108">**Период хранения содержимого может зависеть от неизвестной даты**. Например, с помощью меток хранения можно определять зависимость периода хранения от возникновения определенного типа события, такого как увольнение сотрудника из организации.</span><span class="sxs-lookup"><span data-stu-id="4c789-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="4c789-p109">Событие активирует начало периода хранения, и ко всему содержимому с меткой, относящейся к событию данного типа, применяются действия хранения. Этот процесс называется хранением на основе событий. Дополнительные сведения о нем см. в статье [Общие сведения о хранении, зависящем от возникновения события](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="4c789-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention. To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="4c789-130">Настройка хранении на основе событий</span><span class="sxs-lookup"><span data-stu-id="4c789-130">Set up event-based retention</span></span>

<span data-ttu-id="4c789-131">В этом разделе описываются действия, которые необходимо выполнить до момента подготовки хранения содержимого.</span><span class="sxs-lookup"><span data-stu-id="4c789-131">This section describes what needs to be done before retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="4c789-132">Определение ролей</span><span class="sxs-lookup"><span data-stu-id="4c789-132">Identify roles</span></span>

<span data-ttu-id="4c789-133">Определите различные роли в организации, которые будут выполнять задачи управления записями и будут обеспечивать эффективное хранение деловых документов.</span><span class="sxs-lookup"><span data-stu-id="4c789-133">Identify the different roles in an organization that perform Record Management tasks and would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="4c789-134">**Роль**</span><span class="sxs-lookup"><span data-stu-id="4c789-134">**Persona**</span></span>| <span data-ttu-id="4c789-135">**Role**</span><span class="sxs-lookup"><span data-stu-id="4c789-135">**Role**</span></span>|
  | - | - |
  | <span data-ttu-id="4c789-136">Администратор</span><span class="sxs-lookup"><span data-stu-id="4c789-136">Admin</span></span> | <span data-ttu-id="4c789-137">Создает типы событий хранения, метки хранения и репозитории записей в SharePoint</span><span class="sxs-lookup"><span data-stu-id="4c789-137">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="4c789-138">Управляющий записями</span><span class="sxs-lookup"><span data-stu-id="4c789-138">Records Manager</span></span>                                  | <span data-ttu-id="4c789-139">Предоставляет указания по политикам и расписанию хранения, а также сведения о соответствии требованиям</span><span class="sxs-lookup"><span data-stu-id="4c789-139">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="4c789-140">Системный администратор (компания)</span><span class="sxs-lookup"><span data-stu-id="4c789-140">System Admin (business)</span></span>                          | <span data-ttu-id="4c789-141">Настраивает внешние системы для работы с Microsoft 365 и управляет ими</span><span class="sxs-lookup"><span data-stu-id="4c789-141">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="4c789-142">Информационный работник</span><span class="sxs-lookup"><span data-stu-id="4c789-142">Information Worker</span></span>                               | <span data-ttu-id="4c789-143">Управляет жизненным циклом своих бизнес-процессов (отдела кадров, финансового отдела, ИТ-отдела и т. д.)</span><span class="sxs-lookup"><span data-stu-id="4c789-143">Manages the lifecycle of their business process (HR, Finance, IT, and so on)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="4c789-144">Настройка Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4c789-144">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="4c789-145">Администратор соответствия требованиям создает тип события — например, увольняется сотрудник, истекает срок действия договора или завершается производство продукта</span><span class="sxs-lookup"><span data-stu-id="4c789-145">Compliance admin creates an event type &ndash; for example, Employee Termination or Contract Expiration or End of Product Manufacturing.</span></span> <span data-ttu-id="4c789-146">(см. пошаговое описание процесса в статье [Хранение на основе событий](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="4c789-146">(See the step-by-step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
2. <span data-ttu-id="4c789-147">Администратор соответствия требованиям создает метку хранения на основе некоего события и связывает ее с типом события.</span><span class="sxs-lookup"><span data-stu-id="4c789-147">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
    <span data-ttu-id="4c789-148">Существует четыре типа триггеров меток хранения:</span><span class="sxs-lookup"><span data-stu-id="4c789-148">There are four types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="4c789-149">Дата создания</span><span class="sxs-lookup"><span data-stu-id="4c789-149">Create date</span></span>
                
    2. <span data-ttu-id="4c789-150">Дата последнего изменения</span><span class="sxs-lookup"><span data-stu-id="4c789-150">Last modified</span></span>
                
    3. <span data-ttu-id="4c789-151">Дата метки (когда содержимому была присвоена метка)</span><span class="sxs-lookup"><span data-stu-id="4c789-151">Label date (when the content was labeled)</span></span>
                
    4. <span data-ttu-id="4c789-152">На основе события</span><span class="sxs-lookup"><span data-stu-id="4c789-152">Event-based</span></span>
    
3. <span data-ttu-id="4c789-153">Администратор соответствия требованиям публикует метку хранения.</span><span class="sxs-lookup"><span data-stu-id="4c789-153">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="4c789-154">Настройка SharePoint</span><span class="sxs-lookup"><span data-stu-id="4c789-154">Set up SharePoint</span></span>
   
<span data-ttu-id="4c789-155">Чтобы создать репозиторий записей, администратор соответствия требованиям выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4c789-155">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="4c789-156">Создает сайт SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4c789-156">Creates a SharePoint site.</span></span>

2. <span data-ttu-id="4c789-157">Выполняет одно из указанных ниже действий:</span><span class="sxs-lookup"><span data-stu-id="4c789-157">Does one of the following:</span></span>
        
    - <span data-ttu-id="4c789-p111">Создает библиотеку SharePoint: задает метку на основе события на уровне библиотеки. Дополнительные сведения см. в разделе "Применение метки хранения по умолчанию ко всему контенту в библиотеке SharePoint, папке или набору документов" [этой статьи](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="4c789-p111">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
    - <span data-ttu-id="4c789-160">Настройка набора документов в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4c789-160">Sets up a document set in SharePoint.</span></span> <span data-ttu-id="4c789-161">Дополнительные сведения см. в статье [Общие сведения о наборах документов](https://support.microsoft.com/ru-RU/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).</span><span class="sxs-lookup"><span data-stu-id="4c789-161">For more information, see [Introduction to document sets](https://support.microsoft.com/ru-RU/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).</span></span>
      
3. <span data-ttu-id="4c789-162">Назначает ИД ресурса для каждого набора документов сотрудников.</span><span class="sxs-lookup"><span data-stu-id="4c789-162">Assigns an asset ID to each employee document set.</span></span> <span data-ttu-id="4c789-163">ИД ресурса — это наименование продукта или код, который используется организацией, например код сотрудника может быть кодом ресурса.</span><span class="sxs-lookup"><span data-stu-id="4c789-163">An asset ID is a product name or code used by the organization, for example, Employee number can be an asset ID.</span></span> <span data-ttu-id="4c789-164">При назначении ИД ресурса папке, каждый элемент в этой папке автоматически наследует тот же самый ИД ресурса.</span><span class="sxs-lookup"><span data-stu-id="4c789-164">By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID.</span></span> <span data-ttu-id="4c789-165">Это означает, что срок хранения всех элементов может быть вызван тем же событием.</span><span class="sxs-lookup"><span data-stu-id="4c789-165">This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="4c789-166">Способы запуска хранения на основе события</span><span class="sxs-lookup"><span data-stu-id="4c789-166">Ways to trigger event-based retention</span></span>

<span data-ttu-id="4c789-167">Существует два способа запуска хранения на основе события:</span><span class="sxs-lookup"><span data-stu-id="4c789-167">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="4c789-168">\*\*Использование пользовательского интерфейса центра администрирования \*\* С помощью этого процесса можно уменьшить объем содержимого, сохраняемого за один раз, или запускать хранение реже, например, раз в месяц или раз в год.</span><span class="sxs-lookup"><span data-stu-id="4c789-168">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention isn't often, such as monthly or yearly.</span></span> <span data-ttu-id="4c789-169">Дополнительные сведения об использовании этого метода см. в статье [Обзор хранения на основе события](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="4c789-169">For more information about this method, see [Overview of event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="4c789-170">Тем не менее, этот способ запуска хранения может потребовать значительных временных затрат и подвержен ошибкам, что препятствует масштабированию.</span><span class="sxs-lookup"><span data-stu-id="4c789-170">However, this method of triggering retention can be time consuming and prone to error, thus stunting scalability.</span></span> <span data-ttu-id="4c789-171">Таким образом, автоматизированное беспрепятственное решение для запуска хранения может повысить безопасность и улучшить соответствие требованиям в отношении данных.</span><span class="sxs-lookup"><span data-stu-id="4c789-171">Therefore, an automated, seamless solution to trigger retention can enhance data security and compliance.</span></span>

- <span data-ttu-id="4c789-p115">**С помощью REST API M365.** Этот процесс можно использовать для хранения большого объема данных и/или в случае частой активации хранения (каждый день или каждую неделю). Этот процесс определяет, когда событие возникает в вашей бизнес-системе, и автоматически создает связанное событие в Центре безопасности и соответствия требованиям. Вам не нужно вручную создавать связанное событие в пользовательском интерфейсе каждый раз, когда происходит исходное событие.</span><span class="sxs-lookup"><span data-stu-id="4c789-p115">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="4c789-175">Существует два способа использования REST API:</span><span class="sxs-lookup"><span data-stu-id="4c789-175">There are two options for using the REST API:</span></span>

- <span data-ttu-id="4c789-176">**Microsoft Flow или подобное приложение** можно использовать для автоматического запуска события.</span><span class="sxs-lookup"><span data-stu-id="4c789-176">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="4c789-177">Microsoft Flow является оркестратором подключения к другим системам.</span><span class="sxs-lookup"><span data-stu-id="4c789-177">Microsoft Flow is an orchestrator for connecting to other systems.</span></span> <span data-ttu-id="4c789-178">Использование Microsoft Flow не требует настраиваемого решения.</span><span class="sxs-lookup"><span data-stu-id="4c789-178">Using Microsoft Flow doesn't require a custom solution.</span></span>

- <span data-ttu-id="4c789-179">**PowerShell или HTTP-клиент для вызова REST API**. Используйте PowerShell (версии 6 или выше) для вызова REST API Microsoft 365, чтобы создать события.</span><span class="sxs-lookup"><span data-stu-id="4c789-179">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="4c789-180">Rest API — это конечная точка службы, поддерживающая наборы операций HTTP (методов), которые обеспечивают создание / получение / обновление / удаление доступа к ресурсам службы.</span><span class="sxs-lookup"><span data-stu-id="4c789-180">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="4c789-181">Дополнительные сведения см. в статье [Компоненты запросов и ответов REST API](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="4c789-181">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="4c789-182">В этом случае с помощью REST API Microsoft 365 можно создавать и получать события, используя операции (методы) POST и GET.</span><span class="sxs-lookup"><span data-stu-id="4c789-182">In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="4c789-183">Примеры сценариев</span><span class="sxs-lookup"><span data-stu-id="4c789-183">Example scenarios</span></span>

<span data-ttu-id="4c789-184">Давайте рассмотрим следующие сценарии.</span><span class="sxs-lookup"><span data-stu-id="4c789-184">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="4c789-185">Сценарий 1. Сотрудники увольняются из организации</span><span class="sxs-lookup"><span data-stu-id="4c789-185">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="4c789-186">В организации создается и хранится множество документов, связанных с сотрудниками, для каждого сотрудника.</span><span class="sxs-lookup"><span data-stu-id="4c789-186">An organization creates and stores numerous employee-related documents per employee.</span></span> <span data-ttu-id="4c789-187">Эти документы управляются и сохраняются в течение работы в организации каждого сотрудника.</span><span class="sxs-lookup"><span data-stu-id="4c789-187">These documents are managed and retained during the employment of each employee.</span></span> <span data-ttu-id="4c789-188">Тем не менее, когда работник покидает организацию или в случае его увольнения, организация обязана в соответствии с требованиями законодательства и бизнеса сохранять документы этого работника в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="4c789-188">However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="4c789-189">Если из организации ежедневно увольняется несколько сотрудников, необходимо запускать счетчики хранения сотен или даже тысяч документов каждый день.</span><span class="sxs-lookup"><span data-stu-id="4c789-189">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="4c789-190">Кроме того, для каждого сотрудника период хранения рассчитывается на основе типа записи сотрудника (дата увольнения сотрудника + количество дней, месяцев или лет).</span><span class="sxs-lookup"><span data-stu-id="4c789-190">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months, or years based on the type of the employee record.</span></span> <span data-ttu-id="4c789-191">Например, у документов о зарплате и документов о премии одного и того же сотрудника могут быть разные периоды хранения.</span><span class="sxs-lookup"><span data-stu-id="4c789-191">For example, worker’s compensation of the employee vs. benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="4c789-192">На схеме далее показано, как может существовать несколько меток, связанных с одним событием.</span><span class="sxs-lookup"><span data-stu-id="4c789-192">The diagram below shows how there can be multiple labels that are associated with a single event.</span></span> <span data-ttu-id="4c789-193">Здесь все файлы под меткой “Компенсации работника” и все файлы под меткой “Льготы сотрудников” связаны с одним событием — уход сотрудника из организации.</span><span class="sxs-lookup"><span data-stu-id="4c789-193">Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event, which is the employee leaving the organization.</span></span> <span data-ttu-id="4c789-194">Каждый из этих различных файлов имеет различные счетчики хранения.</span><span class="sxs-lookup"><span data-stu-id="4c789-194">Each of these different files has different retention clocks.</span></span> <span data-ttu-id="4c789-195">Таким образом, когда сотрудник покидает организацию, эти файлы под каждой меткой имеют различный срок хранения.</span><span class="sxs-lookup"><span data-stu-id="4c789-195">So, when an employee leaves the organization, these files within each label experience a different retention period.</span></span> <span data-ttu-id="4c789-196">Запуск всех этих разных счетчиков хранения для каждого типа файла или метки для каждого сотрудника является очень сложной задачей.</span><span class="sxs-lookup"><span data-stu-id="4c789-196">Triggering all these different retention clocks for each file type or label for each employee is a very challenging task.</span></span> <span data-ttu-id="4c789-197">Представьте, что это необходимо выполнить для нескольких сотрудников.</span><span class="sxs-lookup"><span data-stu-id="4c789-197">Imagine doing this for multiple employees.</span></span>

![Схема типов событий, событий и меток](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="4c789-199">Поэтому автоматизированный процесс запуска всех этих различных счетчиков хранения для нескольких сотрудников должен работать быстро, быть безошибочным и очень эффективным.</span><span class="sxs-lookup"><span data-stu-id="4c789-199">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free, and extremely efficient.</span></span>

<span data-ttu-id="4c789-200">**Настройка автоматизированного хранения на основе событий для этого сценария:**</span><span class="sxs-lookup"><span data-stu-id="4c789-200">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Схема ролей и действий для сценария, когда сотрудник увольняется из организации](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="4c789-202">Администратор создает папки сотрудников в наборе документов, например "Евгения Артемьева", "Артем Кузнецов".</span><span class="sxs-lookup"><span data-stu-id="4c789-202">Admin creates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="4c789-203">Администратор добавляет в каждую папку файлы сотрудников, например с данными о премиях и зарплате.</span><span class="sxs-lookup"><span data-stu-id="4c789-203">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder.</span></span>

  - <span data-ttu-id="4c789-204">Администратор назначает идентификатор ресурса для каждой папки сотрудников.</span><span class="sxs-lookup"><span data-stu-id="4c789-204">Admin assigns Asset ID to each employee folder.</span></span> 

  - <span data-ttu-id="4c789-205">Администратор Центра безопасности и соответствия требованиям выполняет вход в Центр безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4c789-205">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="4c789-206">Администратор безопасности и соответствия требованиям создает типы событий, связанные с сотрудником, например "Увольнение сотрудника" и "Прием сотрудника на работу".</span><span class="sxs-lookup"><span data-stu-id="4c789-206">SCC Admin creates employee-related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="4c789-207">Администратор безопасности и соответствия требованиям создает метку "Хранение для сотрудника".</span><span class="sxs-lookup"><span data-stu-id="4c789-207">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="4c789-208">Эта метка "Хранение для сотрудника" публикуется и вручную или автоматически применяется к файлам сотрудника в SharePoint</span><span class="sxs-lookup"><span data-stu-id="4c789-208">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint.</span></span>

  - <span data-ttu-id="4c789-209">Система управления отдела кадров, например Workday, может работать совместно с Microsoft Flow для периодического управления файлами сотрудников</span><span class="sxs-lookup"><span data-stu-id="4c789-209">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files.</span></span>

  - <span data-ttu-id="4c789-210">Если сотрудник увольняется из организации, Flow активирует REST API хранения на основе событий M365, который запустит счетчик хранения для файлов определенного сотрудника.</span><span class="sxs-lookup"><span data-stu-id="4c789-210">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="4c789-211">Использование Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="4c789-211">Using Microsoft Flow</span></span>

<span data-ttu-id="4c789-212">Шаг 1. Создайте процесс создания события с помощью REST API Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c789-212">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Использование Flow для создания события](../media/automate-event-driven-retention-flow-1.png)

![Использование Flow для вызова REST API](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="4c789-215">Создание события</span><span class="sxs-lookup"><span data-stu-id="4c789-215">Create an event</span></span>

<span data-ttu-id="4c789-216">Пример кода для вызова REST API</span><span class="sxs-lookup"><span data-stu-id="4c789-216">Sample code to call the REST API</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="4c789-217">Метод</span><span class="sxs-lookup"><span data-stu-id="4c789-217">Method</span></span></th>
<th><span data-ttu-id="4c789-218">POST</span><span class="sxs-lookup"><span data-stu-id="4c789-218">POST</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4c789-219">URL-адрес</span><span class="sxs-lookup"><span data-stu-id="4c789-219">URL</span></span></td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4c789-220">Заголовки</span><span class="sxs-lookup"><span data-stu-id="4c789-220">Headers</span></span></td>
<td><span data-ttu-id="4c789-221">Content-Type</span><span class="sxs-lookup"><span data-stu-id="4c789-221">Content-Type</span></span></td>
<td><span data-ttu-id="4c789-222">приложение/atom+xml</span><span class="sxs-lookup"><span data-stu-id="4c789-222">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4c789-223">Основной текст</span><span class="sxs-lookup"><span data-stu-id="4c789-223">Body</span></span></td>
<td><p><span data-ttu-id="4c789-224">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-224">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="4c789-225">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="4c789-225">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="4c789-226">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="4c789-226">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="4c789-227">xmlns='http://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-227">xmlns='http://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="4c789-228">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-228">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="4c789-229">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-229">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="4c789-230">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-230">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="4c789-231">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-231">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="4c789-232">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-232">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="4c789-233">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-233">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="4c789-234">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-234">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="4c789-235">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-235">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span></span></p>
<p><span data-ttu-id="4c789-236">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-236">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="4c789-237">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-237">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="4c789-238">&lt;/entry&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-238">&lt;/entry&gt;</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4c789-239">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="4c789-239">Authentication</span></span></td>
<td><span data-ttu-id="4c789-240">Базовая</span><span class="sxs-lookup"><span data-stu-id="4c789-240">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4c789-241">Имя пользователя</span><span class="sxs-lookup"><span data-stu-id="4c789-241">Username</span></span></td>
<td><span data-ttu-id="4c789-242">"Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="4c789-242">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4c789-243">Пароль</span><span class="sxs-lookup"><span data-stu-id="4c789-243">Password</span></span></td>
<td><span data-ttu-id="4c789-244">"Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="4c789-244">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a><span data-ttu-id="4c789-245">Доступные параметры</span><span class="sxs-lookup"><span data-stu-id="4c789-245">Available parameters</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="4c789-246"><strong>Параметры</strong></span><span class="sxs-lookup"><span data-stu-id="4c789-246"><strong>Parameters</strong></span></span></th>
<th><span data-ttu-id="4c789-247"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="4c789-247"><strong>Description</strong></span></span></th>
<th><span data-ttu-id="4c789-248"><strong>Примечания</strong></span><span class="sxs-lookup"><span data-stu-id="4c789-248"><strong>Notes</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4c789-249">&lt;d:Name&gt;&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-249">&lt;d:Name&gt;&lt;/d:Name&gt;</span></span></td>
<td><span data-ttu-id="4c789-250">Указание уникального имени события.</span><span class="sxs-lookup"><span data-stu-id="4c789-250">Provide a unique name for the event,</span></span></td>
<td><span data-ttu-id="4c789-p121">Не может содержать начальные и конечные пробелы и следующие символы: % \* \ &amp; &lt; &gt; | # ? , : ;</span><span class="sxs-lookup"><span data-stu-id="4c789-p121">Cannot contain trailing spaces, and the following characters: % \* \ &amp; &lt; &gt; | # ? , : ;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4c789-253">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-253">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span></span></td>
<td><span data-ttu-id="4c789-254">Введите название типа события (или Guid).</span><span class="sxs-lookup"><span data-stu-id="4c789-254">Enter event type name (or Guid),</span></span></td>
<td><span data-ttu-id="4c789-p122">Пример: "Увольнение сотрудника". Тип события должен быть связан с меткой хранения.</span><span class="sxs-lookup"><span data-stu-id="4c789-p122">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4c789-257">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-257">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span></span></td>
<td><span data-ttu-id="4c789-258">Введите "ComplianceAssetId:" + код сотрудника</span><span class="sxs-lookup"><span data-stu-id="4c789-258">Enter “ComplianceAssetId:” + employee Id</span></span></td>
<td><span data-ttu-id="4c789-259">Пример: &quot;ComplianceAssetId:12345&quot;</span><span class="sxs-lookup"><span data-stu-id="4c789-259">Example:&quot;ComplianceAssetId:12345&quot;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4c789-260">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-260">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span></span></td>
<td><span data-ttu-id="4c789-261">Дата и время события</span><span class="sxs-lookup"><span data-stu-id="4c789-261">Event Date and Time</span></span></td>
<td><p><span data-ttu-id="4c789-262">Формат: ГГГГ-ММ-ДДTчч:мм:ссZ. Пример:</span><span class="sxs-lookup"><span data-stu-id="4c789-262">Format: yyyy-MM-ddTHH:mm:ssZ, Example:</span></span></p>
<p><span data-ttu-id="4c789-263">2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="4c789-263">2018-12-01T00:00:00Z</span></span></p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="4c789-264">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="4c789-264">Response codes</span></span>

| <span data-ttu-id="4c789-265">**Код ответа**</span><span class="sxs-lookup"><span data-stu-id="4c789-265">**Response Code**</span></span> | <span data-ttu-id="4c789-266">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4c789-266">**Description**</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="4c789-267">302</span><span class="sxs-lookup"><span data-stu-id="4c789-267">302</span></span>               | <span data-ttu-id="4c789-268">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="4c789-268">Redirect</span></span>              |
| <span data-ttu-id="4c789-269">201</span><span class="sxs-lookup"><span data-stu-id="4c789-269">201</span></span>               | <span data-ttu-id="4c789-270">Создано</span><span class="sxs-lookup"><span data-stu-id="4c789-270">Created</span></span>               |
| <span data-ttu-id="4c789-271">403</span><span class="sxs-lookup"><span data-stu-id="4c789-271">403</span></span>               | <span data-ttu-id="4c789-272">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="4c789-272">Authorization Failed</span></span>  |
| <span data-ttu-id="4c789-273">401</span><span class="sxs-lookup"><span data-stu-id="4c789-273">401</span></span>               | <span data-ttu-id="4c789-274">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="4c789-274">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="4c789-275">Получение событий на основе диапазона времени</span><span class="sxs-lookup"><span data-stu-id="4c789-275">Get Events based on time range</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="4c789-276">Метод</span><span class="sxs-lookup"><span data-stu-id="4c789-276">Method</span></span></th>
<th><span data-ttu-id="4c789-277">GET</span><span class="sxs-lookup"><span data-stu-id="4c789-277">GET</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4c789-278">URL-адрес</span><span class="sxs-lookup"><span data-stu-id="4c789-278">URL</span></span></td>
<td><ol start="4" type="1">
<li><p><span data-ttu-id="4c789-279">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span><span class="sxs-lookup"><span data-stu-id="4c789-279">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span></span></p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4c789-280">Заголовки</span><span class="sxs-lookup"><span data-stu-id="4c789-280">Headers</span></span></td>
<td><span data-ttu-id="4c789-281">Content-Type</span><span class="sxs-lookup"><span data-stu-id="4c789-281">Content-Type</span></span></td>
<td><span data-ttu-id="4c789-282">приложение/atom+xml</span><span class="sxs-lookup"><span data-stu-id="4c789-282">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4c789-283">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="4c789-283">Authentication</span></span></td>
<td><span data-ttu-id="4c789-284">Базовая</span><span class="sxs-lookup"><span data-stu-id="4c789-284">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4c789-285">Имя пользователя</span><span class="sxs-lookup"><span data-stu-id="4c789-285">Username</span></span></td>
<td><span data-ttu-id="4c789-286">"Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="4c789-286">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4c789-287">Пароль</span><span class="sxs-lookup"><span data-stu-id="4c789-287">Password</span></span></td>
<td><span data-ttu-id="4c789-288">"Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="4c789-288">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="4c789-289">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="4c789-289">Response codes</span></span>

| <span data-ttu-id="4c789-290">**Код ответа**</span><span class="sxs-lookup"><span data-stu-id="4c789-290">**Response Code**</span></span> | <span data-ttu-id="4c789-291">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4c789-291">**Description**</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="4c789-292">200</span><span class="sxs-lookup"><span data-stu-id="4c789-292">200</span></span>               | <span data-ttu-id="4c789-293">Все в порядке, список событий в формате atom+xml</span><span class="sxs-lookup"><span data-stu-id="4c789-293">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="4c789-294">404</span><span class="sxs-lookup"><span data-stu-id="4c789-294">404</span></span>               | <span data-ttu-id="4c789-295">Не найдено</span><span class="sxs-lookup"><span data-stu-id="4c789-295">Not found</span></span>                         |
| <span data-ttu-id="4c789-296">302</span><span class="sxs-lookup"><span data-stu-id="4c789-296">302</span></span>               | <span data-ttu-id="4c789-297">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="4c789-297">Redirect</span></span>                          |
| <span data-ttu-id="4c789-298">401</span><span class="sxs-lookup"><span data-stu-id="4c789-298">401</span></span>               | <span data-ttu-id="4c789-299">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="4c789-299">Authorization Failed</span></span>              |
| <span data-ttu-id="4c789-300">403</span><span class="sxs-lookup"><span data-stu-id="4c789-300">403</span></span>               | <span data-ttu-id="4c789-301">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="4c789-301">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="4c789-302">Получение события по идентификатору</span><span class="sxs-lookup"><span data-stu-id="4c789-302">Get an event by ID</span></span>

| <span data-ttu-id="4c789-303">Метод</span><span class="sxs-lookup"><span data-stu-id="4c789-303">Method</span></span>         | <span data-ttu-id="4c789-304">GET</span><span class="sxs-lookup"><span data-stu-id="4c789-304">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="4c789-305">URL-адрес</span><span class="sxs-lookup"><span data-stu-id="4c789-305">URL</span></span>            | <span data-ttu-id="4c789-306">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="4c789-306">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="4c789-307">Заголовок</span><span class="sxs-lookup"><span data-stu-id="4c789-307">Header</span></span>         | <span data-ttu-id="4c789-308">Content-Type</span><span class="sxs-lookup"><span data-stu-id="4c789-308">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="4c789-309">приложение/atom+xml</span><span class="sxs-lookup"><span data-stu-id="4c789-309">application/atom+xml</span></span> |
| <span data-ttu-id="4c789-310">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="4c789-310">Authentication</span></span> | <span data-ttu-id="4c789-311">Базовая</span><span class="sxs-lookup"><span data-stu-id="4c789-311">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="4c789-312">Имя пользователя</span><span class="sxs-lookup"><span data-stu-id="4c789-312">Username</span></span>       | <span data-ttu-id="4c789-313">"Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="4c789-313">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="4c789-314">Пароль</span><span class="sxs-lookup"><span data-stu-id="4c789-314">Password</span></span>       | <span data-ttu-id="4c789-315">"Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="4c789-315">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="4c789-316">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="4c789-316">Response codes</span></span>

| <span data-ttu-id="4c789-317">**Код ответа**</span><span class="sxs-lookup"><span data-stu-id="4c789-317">**Response Code**</span></span> | <span data-ttu-id="4c789-318">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4c789-318">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="4c789-319">200</span><span class="sxs-lookup"><span data-stu-id="4c789-319">200</span></span>               | <span data-ttu-id="4c789-320">Все в порядке, текст ответа содержит событие в формате atom+xml</span><span class="sxs-lookup"><span data-stu-id="4c789-320">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="4c789-321">404</span><span class="sxs-lookup"><span data-stu-id="4c789-321">404</span></span>               | <span data-ttu-id="4c789-322">Не найдено</span><span class="sxs-lookup"><span data-stu-id="4c789-322">Not found</span></span>                                            |
| <span data-ttu-id="4c789-323">302</span><span class="sxs-lookup"><span data-stu-id="4c789-323">302</span></span>               | <span data-ttu-id="4c789-324">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="4c789-324">Redirect</span></span>                                             |
| <span data-ttu-id="4c789-325">401</span><span class="sxs-lookup"><span data-stu-id="4c789-325">401</span></span>               | <span data-ttu-id="4c789-326">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="4c789-326">Authorization Failed</span></span>                                 |
| <span data-ttu-id="4c789-327">403</span><span class="sxs-lookup"><span data-stu-id="4c789-327">403</span></span>               | <span data-ttu-id="4c789-328">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="4c789-328">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="4c789-329">Получение события по имени</span><span class="sxs-lookup"><span data-stu-id="4c789-329">Get an event by name</span></span>

| <span data-ttu-id="4c789-330">Метод</span><span class="sxs-lookup"><span data-stu-id="4c789-330">Method</span></span>         | <span data-ttu-id="4c789-331">GET</span><span class="sxs-lookup"><span data-stu-id="4c789-331">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="4c789-332">URL-адрес</span><span class="sxs-lookup"><span data-stu-id="4c789-332">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="4c789-333">Заголовки</span><span class="sxs-lookup"><span data-stu-id="4c789-333">Headers</span></span>        | <span data-ttu-id="4c789-334">Content-Type</span><span class="sxs-lookup"><span data-stu-id="4c789-334">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="4c789-335">приложение/atom+xml</span><span class="sxs-lookup"><span data-stu-id="4c789-335">application/atom+xml</span></span> |
| <span data-ttu-id="4c789-336">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="4c789-336">Authentication</span></span> | <span data-ttu-id="4c789-337">Базовая</span><span class="sxs-lookup"><span data-stu-id="4c789-337">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="4c789-338">Имя пользователя</span><span class="sxs-lookup"><span data-stu-id="4c789-338">Username</span></span>       | <span data-ttu-id="4c789-339">"Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="4c789-339">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="4c789-340">Пароль</span><span class="sxs-lookup"><span data-stu-id="4c789-340">Password</span></span>       | <span data-ttu-id="4c789-341">"Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="4c789-341">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="4c789-342">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="4c789-342">Response codes</span></span>

| <span data-ttu-id="4c789-343">**Код ответа**</span><span class="sxs-lookup"><span data-stu-id="4c789-343">**Response Code**</span></span> | <span data-ttu-id="4c789-344">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4c789-344">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="4c789-345">200</span><span class="sxs-lookup"><span data-stu-id="4c789-345">200</span></span>               | <span data-ttu-id="4c789-346">Все в порядке, текст ответа содержит событие в формате atom+xml</span><span class="sxs-lookup"><span data-stu-id="4c789-346">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="4c789-347">404</span><span class="sxs-lookup"><span data-stu-id="4c789-347">404</span></span>               | <span data-ttu-id="4c789-348">Не найдено</span><span class="sxs-lookup"><span data-stu-id="4c789-348">Not found</span></span>                                            |
| <span data-ttu-id="4c789-349">302</span><span class="sxs-lookup"><span data-stu-id="4c789-349">302</span></span>               | <span data-ttu-id="4c789-350">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="4c789-350">Redirect</span></span>                                             |
| <span data-ttu-id="4c789-351">401</span><span class="sxs-lookup"><span data-stu-id="4c789-351">401</span></span>               | <span data-ttu-id="4c789-352">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="4c789-352">Authorization Failed</span></span>                                 |
| <span data-ttu-id="4c789-353">403</span><span class="sxs-lookup"><span data-stu-id="4c789-353">403</span></span>               | <span data-ttu-id="4c789-354">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="4c789-354">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="4c789-355">Использование PowerShell (версии 6 или выше) или любого HTTP-клиента</span><span class="sxs-lookup"><span data-stu-id="4c789-355">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="4c789-356">Шаг 1. Подключитесь к PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c789-356">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="4c789-357">Шаг 2. Запустите указанный ниже сценарий.</span><span class="sxs-lookup"><span data-stu-id="4c789-357">Step 2: Run the following script.</span></span>

<table>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c789-358">param([string]$baseUri)</span><span class="sxs-lookup"><span data-stu-id="4c789-358">param([string]$baseUri)</span></span></p>
<p><span data-ttu-id="4c789-359">$userName = &quot;UserName&quot;</span><span class="sxs-lookup"><span data-stu-id="4c789-359">$userName = &quot;UserName&quot;</span></span></p>
<p><span data-ttu-id="4c789-360">$password = &quot;Password&quot;</span><span class="sxs-lookup"><span data-stu-id="4c789-360">$password = &quot;Password&quot;</span></span></p>
<p><span data-ttu-id="4c789-361">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span><span class="sxs-lookup"><span data-stu-id="4c789-361">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span></span></p>
<p><span data-ttu-id="4c789-362">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span><span class="sxs-lookup"><span data-stu-id="4c789-362">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span></span></p>
<p><span data-ttu-id="4c789-363">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span><span class="sxs-lookup"><span data-stu-id="4c789-363">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span></span></p>
<p><span data-ttu-id="4c789-364">Write-Host &quot;Start to create an event with name: $EventName&quot;</span><span class="sxs-lookup"><span data-stu-id="4c789-364">Write-Host &quot;Start to create an event with name: $EventName&quot;</span></span></p>
<p><span data-ttu-id="4c789-365">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-365">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="4c789-366">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="4c789-366">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="4c789-367">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="4c789-367">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="4c789-368">xmlns='http://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-368">xmlns='http://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="4c789-369">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-369">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="4c789-370">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-370">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="4c789-371">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-371">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="4c789-372">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-372">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="4c789-373">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-373">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="4c789-374">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-374">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="4c789-375">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-375">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="4c789-376">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-376">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="4c789-377">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="4c789-377">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="4c789-378">&lt;/entry&gt;&quot;</span><span class="sxs-lookup"><span data-stu-id="4c789-378">&lt;/entry&gt;&quot;</span></span></p>
<p><span data-ttu-id="4c789-379">$event = $null</span><span class="sxs-lookup"><span data-stu-id="4c789-379">$event = $null</span></span></p>
<p><span data-ttu-id="4c789-380">try</span><span class="sxs-lookup"><span data-stu-id="4c789-380">try</span></span></p>
<p><span data-ttu-id="4c789-381">{</span><span class="sxs-lookup"><span data-stu-id="4c789-381">{</span></span></p>
<p><span data-ttu-id="4c789-382">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="4c789-382">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="4c789-383">}</span><span class="sxs-lookup"><span data-stu-id="4c789-383">}</span></span></p>
<p><span data-ttu-id="4c789-384">catch</span><span class="sxs-lookup"><span data-stu-id="4c789-384">catch</span></span></p>
<p><span data-ttu-id="4c789-385">{</span><span class="sxs-lookup"><span data-stu-id="4c789-385">{</span></span></p>
<p><span data-ttu-id="4c789-386">$response = $_.Exception.Response</span><span class="sxs-lookup"><span data-stu-id="4c789-386">$response = $_.Exception.Response</span></span></p>
<p><span data-ttu-id="4c789-387">if($response.StatusCode -eq &quot;Redirect&quot;)</span><span class="sxs-lookup"><span data-stu-id="4c789-387">if($response.StatusCode -eq &quot;Redirect&quot;)</span></span></p>
<p><span data-ttu-id="4c789-388">{</span><span class="sxs-lookup"><span data-stu-id="4c789-388">{</span></span></p>
<p><span data-ttu-id="4c789-389">$url = $response.Headers.Location</span><span class="sxs-lookup"><span data-stu-id="4c789-389">$url = $response.Headers.Location</span></span></p>
<p><span data-ttu-id="4c789-390">Write-Host &quot;redirected to $url&quot;</span><span class="sxs-lookup"><span data-stu-id="4c789-390">Write-Host &quot;redirected to $url&quot;</span></span></p>
<p><span data-ttu-id="4c789-391">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="4c789-391">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="4c789-392">}</span><span class="sxs-lookup"><span data-stu-id="4c789-392">}</span></span></p>
<p><span data-ttu-id="4c789-393">}</span><span class="sxs-lookup"><span data-stu-id="4c789-393">}</span></span></p>
<p><span data-ttu-id="4c789-394">$event | fl \*</span><span class="sxs-lookup"><span data-stu-id="4c789-394">$event | fl \*</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="4c789-395">Проверка результатов обоих вариантов</span><span class="sxs-lookup"><span data-stu-id="4c789-395">Verify the outcome in both options</span></span>

<span data-ttu-id="4c789-396">Шаг 1. Перейдите в Центр безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4c789-396">Step 1: Go to the Security & Compliance Center.</span></span>

<span data-ttu-id="4c789-397">Шаг 2. Выберите **События** в разделе **Управление информацией**.</span><span class="sxs-lookup"><span data-stu-id="4c789-397">Step 2: Select **Events** under **Information governance**.</span></span>

<span data-ttu-id="4c789-398">Шаг 3. Убедитесь, что событие создано.</span><span class="sxs-lookup"><span data-stu-id="4c789-398">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="4c789-399">Аналогичным образом описанные выше варианты автоматизации хранения на основе событий можно использовать и для следующих сценариев.</span><span class="sxs-lookup"><span data-stu-id="4c789-399">Similarly, the above options to automate event-based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="4c789-400">Сценарий 2. Окончание действия договоров</span><span class="sxs-lookup"><span data-stu-id="4c789-400">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="4c789-401">Организация может иметь несколько записей для одного договора с клиентами, поставщиками и партнерами.</span><span class="sxs-lookup"><span data-stu-id="4c789-401">An organization can have multiple records for a single contract with customers, vendors, and partners.</span></span> <span data-ttu-id="4c789-402">Эти документы можно хранить в библиотеке документов, например в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4c789-402">These documents can reside in a document library like SharePoint.</span></span> <span data-ttu-id="4c789-403">Окончание договора определяет начало срока хранения документов, связанных с договором.</span><span class="sxs-lookup"><span data-stu-id="4c789-403">The end of a contract determines the start of the retention period of the documents associated with the contract.</span></span> <span data-ttu-id="4c789-404">Например, все записи, связанные с договорами, нужно хранить в течение пяти лет с момента истечения срока действия договора.</span><span class="sxs-lookup"><span data-stu-id="4c789-404">For example, all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="4c789-405">Событием, активирующим пятилетнее хранение, будет окончание срока действия договора.</span><span class="sxs-lookup"><span data-stu-id="4c789-405">The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="4c789-406">Система управления отношениями с клиентами может работать совместно с Microsoft 365 и активировать хранение документов договора.</span><span class="sxs-lookup"><span data-stu-id="4c789-406">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents</span></span>

<span data-ttu-id="4c789-407">**Настройка автоматизированного хранения на основе событий для этого сценария:**</span><span class="sxs-lookup"><span data-stu-id="4c789-407">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Схема ролей и задач для сценария окончания действия договора](../media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="4c789-409">Администратор создает библиотеку SharePoint с различными папками для каждого типа договора.</span><span class="sxs-lookup"><span data-stu-id="4c789-409">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="4c789-410">Администратор добавляет файлы договора, например лицензионные соглашения, договоры о разработке, в папку каждого договора.</span><span class="sxs-lookup"><span data-stu-id="4c789-410">Admin adds contract files such as License Contracts, Development Contracts to each contract folder.</span></span>

  - <span data-ttu-id="4c789-411">Администратор назначает идентификатор ресурса для каждой папки договора.</span><span class="sxs-lookup"><span data-stu-id="4c789-411">Admin assigns Asset ID to each contract folder.</span></span>

  - <span data-ttu-id="4c789-412">Администратор Центра безопасности и соответствия требованиям выполняет вход в Центр безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4c789-412">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="4c789-413">Администратор безопасности и соответствия требованиям создает типы событий, связанные с договором, например "Создание договора" и "Завершение действия договора".</span><span class="sxs-lookup"><span data-stu-id="4c789-413">SCC Admin creates contract-related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="4c789-414">Администратор безопасности и соответствия требованиям создает метку "Завершение действия договора".</span><span class="sxs-lookup"><span data-stu-id="4c789-414">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="4c789-415">Эта метка "Завершение действия договора" публикуется и вручную или автоматически применяется к файлам договора в SharePoint</span><span class="sxs-lookup"><span data-stu-id="4c789-415">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint.</span></span>

  - <span data-ttu-id="4c789-416">Система управления договорами может работать совместно с Microsoft Flow или аналогичным приложением для периодического управления файлами договоров.</span><span class="sxs-lookup"><span data-stu-id="4c789-416">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files.</span></span>

  - <span data-ttu-id="4c789-417">Если срок действия договора завершается, Microsoft Flow активирует REST API хранения на основе событий M365, который запустит счетчик хранения для файлов определенного договора.</span><span class="sxs-lookup"><span data-stu-id="4c789-417">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="4c789-418">Сценарий 3. Прекращение производства продукта</span><span class="sxs-lookup"><span data-stu-id="4c789-418">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="4c789-p124">Производственная компания, которая изготавливает различные линейки продуктов, создает множество документов с техническими характеристиками производства и ценами. Если продукт перестает производится, все технические характеристики и документы, связанные с этим продуктом, следует хранить в течение определенного периода времени после окончания существования продукта.</span><span class="sxs-lookup"><span data-stu-id="4c789-p124">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="4c789-421">Система планирования ресурсов предприятия (ERP) может работать совместно с Microsoft 365 и Microsoft Flow для активации хранения.</span><span class="sxs-lookup"><span data-stu-id="4c789-421">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="4c789-422">**Настройка автоматизированного хранения на основе событий для этого сценария:**</span><span class="sxs-lookup"><span data-stu-id="4c789-422">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Схема ролей и задач для сценария жизненного цикла продукта](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="4c789-424">Администратор создает папки продуктов в наборе документов, например "Продукт 1", "Продукт 2" и т. д.</span><span class="sxs-lookup"><span data-stu-id="4c789-424">Admin creates product folders in the Document set such as Product 1, Product 2, and so on.</span></span>

  - <span data-ttu-id="4c789-425">Администратор добавляет файлы продуктов, например технические характеристики производства, цены продуктов и лицензирование продуктов, в каждую папку продукта.</span><span class="sxs-lookup"><span data-stu-id="4c789-425">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder.</span></span>

  - <span data-ttu-id="4c789-426">Администратор назначает ИД ресурса для каждой папки продукта.</span><span class="sxs-lookup"><span data-stu-id="4c789-426">Admin assigns Asset ID to each product folder.</span></span>

  - <span data-ttu-id="4c789-427">Администратор Центра безопасности и соответствия требованиям выполняет вход в Центр безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4c789-427">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="4c789-428">Администратор безопасности и соответствия требованиям создает типы событий, связанные с сотрудником, например "Начало производства продукта" и "Окончание производства продукта".</span><span class="sxs-lookup"><span data-stu-id="4c789-428">SCC Admin creates employee-related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="4c789-429">Администратор безопасности и соответствия требованиям создает метку "Окончание производства продукта".</span><span class="sxs-lookup"><span data-stu-id="4c789-429">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="4c789-430">Эта метка "Завершение изготовление продукта" публикуется и вручную или автоматически применяется к файлам продукта в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4c789-430">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint.</span></span>

  - <span data-ttu-id="4c789-431">Система ERP может работать совместно с Microsoft Flow или аналогичным приложением для периодического управления файлами продуктов.</span><span class="sxs-lookup"><span data-stu-id="4c789-431">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files.</span></span>

  - <span data-ttu-id="4c789-432">Если изготовление продукта завершается, Microsoft Flow активирует REST API хранения на основе событий M365, который запустит счетчик хранения для файлов определенного продукта.</span><span class="sxs-lookup"><span data-stu-id="4c789-432">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="4c789-433">Приложение</span><span class="sxs-lookup"><span data-stu-id="4c789-433">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="4c789-434">Использование результатов ответа 302 (перенаправление) для вызова REST API</span><span class="sxs-lookup"><span data-stu-id="4c789-434">Using Redirect 302 response results to call the REST API</span></span>

1. <span data-ttu-id="4c789-435">Вызовите событие хранения POST с помощью URL-адреса REST API <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (требуются разрешения глобального администратора)</span><span class="sxs-lookup"><span data-stu-id="4c789-435">Invoke a POST retention event call using the REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required)</span></span>

2. <span data-ttu-id="4c789-p125">Проверьте код ответа. Если получен код 302, получите URL-адрес перенаправления из свойства Location (Расположение) заголовка ответа</span><span class="sxs-lookup"><span data-stu-id="4c789-p125">Check the response code. If it’s 302, then get the redirected URL from Location property of the response header</span></span>

3. <span data-ttu-id="4c789-438">Вызовите событие хранения POST еще раз с помощью URL-адреса перенаправления</span><span class="sxs-lookup"><span data-stu-id="4c789-438">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="4c789-439">Сведения об авторах</span><span class="sxs-lookup"><span data-stu-id="4c789-439">Credits</span></span>

<span data-ttu-id="4c789-440">Редактор статьи:</span><span class="sxs-lookup"><span data-stu-id="4c789-440">This topic was reviewed by:</span></span>

<span data-ttu-id="4c789-441">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="4c789-441">Antonio Maio</span></span><br/><span data-ttu-id="4c789-442">MVP в сфере приложений и служб Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="4c789-442">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="4c789-443">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="4c789-443">Antonio.Maio@Protiviti.com</span></span>
