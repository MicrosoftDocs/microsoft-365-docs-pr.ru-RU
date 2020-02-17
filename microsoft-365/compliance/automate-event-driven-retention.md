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
ms.openlocfilehash: 692671ca5e7d956cb168ac0de2e409e7023cfd04
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079109"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="3077e-103">Автоматизация хранения на основе событий</span><span class="sxs-lookup"><span data-stu-id="3077e-103">Automate event-based retention</span></span>

<span data-ttu-id="3077e-p101">Процессы развертывания содержимого в организации, а также обнаружения избыточных, устаревших и тривиальных данных играют важную роль. Чтобы продолжать соответствовать юридическим, нормативным и бизнес-требованиям, организации должны обеспечить хранение и защиту важной информации, а также быстрый поиск необходимых данных. Хранение только важной и подходящей информации является ключевым фактором успеха организаций.</span><span class="sxs-lookup"><span data-stu-id="3077e-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to an organization's success.</span></span>

<span data-ttu-id="3077e-p102">Чтобы помочь удовлетворить эту потребность, организации могут использовать преимущества решений для хранения в Центре безопасности и соответствия требованиям Office 365. Связанные с хранением операции можно активировать с помощью [меток хранения](labels.md). У метки хранения есть параметр для [определения периода хранения на основе конкретного события](event-driven-retention.md). Обычно период хранения зависит от известной даты, например даты создания или последнего изменения содержимого. Однако у организаций также есть требования по удалению содержимого на основе возникновения событий, например через 7 лет после того, как сотрудник уволился из организации.</span><span class="sxs-lookup"><span data-stu-id="3077e-p102">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span></span>

<span data-ttu-id="3077e-p103">Чтобы обеспечить удаление содержимого в соответствии с требованиями, важно знать, когда происходят события. Из-за стремительного роста объема содержимого становится сложно хранить и удалять данные своевременно и в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="3077e-p103">To ensure compliant disposal of content, it's imperative to know when an event takes place. With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="3077e-p104">Хранения на основе событий решает эту проблему. В этой статье описывается, как настроить операции бизнес-процесса, чтобы автоматизировать хранение с помощью событий, используя REST API Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3077e-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="3077e-116">О хранении на основе событий</span><span class="sxs-lookup"><span data-stu-id="3077e-116">About event-based retention</span></span>

<span data-ttu-id="3077e-p105">Независимо от размера организации количество деловых документов, юридических документов, файлов сотрудников, договоров и документов о продукции, которые ежедневно создаются и которыми необходимо управлять, стремительно растет.</span><span class="sxs-lookup"><span data-stu-id="3077e-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span></span>

<span data-ttu-id="3077e-p106">Например, каждый день десятки и сотни сотрудников устраиваются на работу в организации или увольняются. Отдел кадров постоянно создает, обновляет или удаляет связанные с сотрудниками документы в соответствии с бизнес-требованиями. Этот процесс регулируется различными политиками, определяемыми для компании:</span><span class="sxs-lookup"><span data-stu-id="3077e-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="3077e-p107">**Период хранения содержимого может зависеть от известной даты**, например даты создания, последнего изменения содержимого или присвоения ему метки. Пример: вы можете хранить документы в течение семи лет после создания, а затем удалить их.</span><span class="sxs-lookup"><span data-stu-id="3077e-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="3077e-p108">**Период хранения содержимого может зависеть от неизвестной даты**. Например, с помощью меток хранения можно определять зависимость периода хранения от возникновения определенного типа события, такого как увольнение сотрудника из организации.</span><span class="sxs-lookup"><span data-stu-id="3077e-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="3077e-p109">Событие активирует начало периода хранения, и ко всему содержимому с меткой, относящейся к событию данного типа, применяются действия хранения. Этот процесс называется хранением на основе событий. Дополнительные сведения о нем см. в статье [Общие сведения о хранении, зависящем от возникновения события](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="3077e-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention. To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="3077e-129">Настройка хранении на основе событий</span><span class="sxs-lookup"><span data-stu-id="3077e-129">Set up event-based retention</span></span>

<span data-ttu-id="3077e-130">В этом разделе описываются действия, которые необходимо выполнить до момента подготовки хранения содержимого.</span><span class="sxs-lookup"><span data-stu-id="3077e-130">This section describes what needs to be done before retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="3077e-131">Определение ролей</span><span class="sxs-lookup"><span data-stu-id="3077e-131">Identify roles</span></span>

<span data-ttu-id="3077e-132">Определите различные роли в организации, которые будут выполнять задачи управления записями и будут обеспечивать эффективное хранение деловых документов.</span><span class="sxs-lookup"><span data-stu-id="3077e-132">Identify the different roles in an organization that perform Record Management tasks and would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="3077e-133">**Роль**</span><span class="sxs-lookup"><span data-stu-id="3077e-133">**Persona**</span></span>| <span data-ttu-id="3077e-134">**Role**</span><span class="sxs-lookup"><span data-stu-id="3077e-134">**Role**</span></span>|
  | - | - |
  | <span data-ttu-id="3077e-135">Администратор</span><span class="sxs-lookup"><span data-stu-id="3077e-135">Admin</span></span> | <span data-ttu-id="3077e-136">Создает типы событий хранения, метки хранения и репозитории записей в SharePoint</span><span class="sxs-lookup"><span data-stu-id="3077e-136">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="3077e-137">Управляющий записями</span><span class="sxs-lookup"><span data-stu-id="3077e-137">Records Manager</span></span>                                  | <span data-ttu-id="3077e-138">Предоставляет указания по политикам и расписанию хранения, а также сведения о соответствии требованиям</span><span class="sxs-lookup"><span data-stu-id="3077e-138">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="3077e-139">Системный администратор (компания)</span><span class="sxs-lookup"><span data-stu-id="3077e-139">System Admin (business)</span></span>                          | <span data-ttu-id="3077e-140">Настраивает внешние системы для работы с Microsoft 365 и управляет ими</span><span class="sxs-lookup"><span data-stu-id="3077e-140">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="3077e-141">Информационный работник</span><span class="sxs-lookup"><span data-stu-id="3077e-141">Information Worker</span></span>                               | <span data-ttu-id="3077e-142">Управляет жизненным циклом своих бизнес-процессов (отдела кадров, финансового отдела, ИТ-отдела и т. д.)</span><span class="sxs-lookup"><span data-stu-id="3077e-142">Manages the lifecycle of their business process (HR, Finance, IT, and so on)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="3077e-143">Настройка Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="3077e-143">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="3077e-144">Администратор соответствия требованиям создает тип события — например, увольняется сотрудник, истекает срок действия договора или завершается производство продукта</span><span class="sxs-lookup"><span data-stu-id="3077e-144">Compliance admin creates an event type &ndash; for example, Employee Termination or Contract Expiration or End of Product Manufacturing.</span></span> <span data-ttu-id="3077e-145">(см. пошаговое описание процесса в статье [Хранение на основе событий](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="3077e-145">(See the step-by-step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
2. <span data-ttu-id="3077e-146">Администратор соответствия требованиям создает метку хранения на основе некоего события и связывает ее с типом события.</span><span class="sxs-lookup"><span data-stu-id="3077e-146">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
    <span data-ttu-id="3077e-147">Существует четыре типа триггеров меток хранения:</span><span class="sxs-lookup"><span data-stu-id="3077e-147">There are four types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="3077e-148">Дата создания</span><span class="sxs-lookup"><span data-stu-id="3077e-148">Create date</span></span>
                
    2. <span data-ttu-id="3077e-149">Дата последнего изменения</span><span class="sxs-lookup"><span data-stu-id="3077e-149">Last modified</span></span>
                
    3. <span data-ttu-id="3077e-150">Дата метки (когда содержимому была присвоена метка)</span><span class="sxs-lookup"><span data-stu-id="3077e-150">Label date (when the content was labeled)</span></span>
                
    4. <span data-ttu-id="3077e-151">На основе события</span><span class="sxs-lookup"><span data-stu-id="3077e-151">Event-based</span></span>
    
3. <span data-ttu-id="3077e-152">Администратор соответствия требованиям публикует метку хранения.</span><span class="sxs-lookup"><span data-stu-id="3077e-152">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="3077e-153">Настройка SharePoint</span><span class="sxs-lookup"><span data-stu-id="3077e-153">Set up SharePoint</span></span>
   
<span data-ttu-id="3077e-154">Чтобы создать репозиторий записей, администратор соответствия требованиям выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3077e-154">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="3077e-155">Создает сайт SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3077e-155">Creates a SharePoint site.</span></span>

2. <span data-ttu-id="3077e-156">Выполняет одно из указанных ниже действий:</span><span class="sxs-lookup"><span data-stu-id="3077e-156">Does one of the following:</span></span>
        
    - <span data-ttu-id="3077e-p111">Создает библиотеку SharePoint: задает метку на основе события на уровне библиотеки. Дополнительные сведения см. в разделе "Применение метки хранения по умолчанию ко всему контенту в библиотеке SharePoint, папке или набору документов" [этой статьи](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="3077e-p111">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
    - <span data-ttu-id="3077e-159">Настройка набора документов в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3077e-159">Sets up a document set in SharePoint.</span></span> <span data-ttu-id="3077e-160">Дополнительные сведения см. в статье [Общие сведения о наборах документов](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span><span class="sxs-lookup"><span data-stu-id="3077e-160">For more information, see [Introduction to document sets](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span></span>
      
3. <span data-ttu-id="3077e-161">Назначает ИД ресурса для каждого набора документов сотрудников.</span><span class="sxs-lookup"><span data-stu-id="3077e-161">Assigns an asset ID to each employee document set.</span></span> <span data-ttu-id="3077e-162">ИД ресурса — это наименование продукта или код, который используется организацией, например код сотрудника может быть кодом ресурса.</span><span class="sxs-lookup"><span data-stu-id="3077e-162">An asset ID is a product name or code used by the organization, for example, Employee number can be an asset ID.</span></span> <span data-ttu-id="3077e-163">При назначении ИД ресурса папке, каждый элемент в этой папке автоматически наследует тот же самый ИД ресурса.</span><span class="sxs-lookup"><span data-stu-id="3077e-163">By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID.</span></span> <span data-ttu-id="3077e-164">Это означает, что срок хранения всех элементов может быть вызван тем же событием.</span><span class="sxs-lookup"><span data-stu-id="3077e-164">This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="3077e-165">Способы запуска хранения на основе события</span><span class="sxs-lookup"><span data-stu-id="3077e-165">Ways to trigger event-based retention</span></span>

<span data-ttu-id="3077e-166">Существует два способа запуска хранения на основе события:</span><span class="sxs-lookup"><span data-stu-id="3077e-166">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="3077e-167">\*\*Использование пользовательского интерфейса центра администрирования \*\* С помощью этого процесса можно уменьшить объем содержимого, сохраняемого за один раз, или запускать хранение реже, например, раз в месяц или раз в год.</span><span class="sxs-lookup"><span data-stu-id="3077e-167">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention isn't often, such as monthly or yearly.</span></span> <span data-ttu-id="3077e-168">Дополнительные сведения об использовании этого метода см. в статье [Обзор хранения на основе события](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="3077e-168">For more information about this method, see [Overview of event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="3077e-169">Тем не менее, этот способ запуска хранения может потребовать значительных временных затрат и подвержен ошибкам, что препятствует масштабированию.</span><span class="sxs-lookup"><span data-stu-id="3077e-169">However, this method of triggering retention can be time consuming and prone to error, thus stunting scalability.</span></span> <span data-ttu-id="3077e-170">Таким образом, автоматизированное беспрепятственное решение для запуска хранения может повысить безопасность и улучшить соответствие требованиям в отношении данных.</span><span class="sxs-lookup"><span data-stu-id="3077e-170">Therefore, an automated, seamless solution to trigger retention can enhance data security and compliance.</span></span>

- <span data-ttu-id="3077e-p115">**С помощью REST API M365.** Этот процесс можно использовать для хранения большого объема данных и/или в случае частой активации хранения (каждый день или каждую неделю). Этот процесс определяет, когда событие возникает в вашей бизнес-системе, и автоматически создает связанное событие в Центре безопасности и соответствия требованиям. Вам не нужно вручную создавать связанное событие в пользовательском интерфейсе каждый раз, когда происходит исходное событие.</span><span class="sxs-lookup"><span data-stu-id="3077e-p115">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="3077e-174">Существует два способа использования REST API:</span><span class="sxs-lookup"><span data-stu-id="3077e-174">There are two options for using the REST API:</span></span>

- <span data-ttu-id="3077e-175">**Microsoft Flow или подобное приложение** можно использовать для автоматического запуска события.</span><span class="sxs-lookup"><span data-stu-id="3077e-175">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="3077e-176">Microsoft Flow является оркестратором подключения к другим системам.</span><span class="sxs-lookup"><span data-stu-id="3077e-176">Microsoft Flow is an orchestrator for connecting to other systems.</span></span> <span data-ttu-id="3077e-177">Использование Microsoft Flow не требует настраиваемого решения.</span><span class="sxs-lookup"><span data-stu-id="3077e-177">Using Microsoft Flow doesn't require a custom solution.</span></span>

- <span data-ttu-id="3077e-178">**PowerShell или HTTP-клиент для вызова REST API**. Используйте PowerShell (версии 6 или выше) для вызова REST API Microsoft 365, чтобы создать события.</span><span class="sxs-lookup"><span data-stu-id="3077e-178">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="3077e-179">Rest API — это конечная точка службы, поддерживающая наборы операций HTTP (методов), которые обеспечивают создание / получение / обновление / удаление доступа к ресурсам службы.</span><span class="sxs-lookup"><span data-stu-id="3077e-179">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="3077e-180">Дополнительные сведения см. в статье [Компоненты запросов и ответов REST API](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="3077e-180">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="3077e-181">В этом случае с помощью REST API Microsoft 365 можно создавать и получать события, используя операции (методы) POST и GET.</span><span class="sxs-lookup"><span data-stu-id="3077e-181">In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="3077e-182">Примеры сценариев</span><span class="sxs-lookup"><span data-stu-id="3077e-182">Example scenarios</span></span>

<span data-ttu-id="3077e-183">Давайте рассмотрим следующие сценарии.</span><span class="sxs-lookup"><span data-stu-id="3077e-183">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="3077e-184">Сценарий 1. Сотрудники увольняются из организации</span><span class="sxs-lookup"><span data-stu-id="3077e-184">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="3077e-185">В организации создается и хранится множество документов, связанных с сотрудниками, для каждого сотрудника.</span><span class="sxs-lookup"><span data-stu-id="3077e-185">An organization creates and stores numerous employee-related documents per employee.</span></span> <span data-ttu-id="3077e-186">Эти документы управляются и сохраняются в течение работы в организации каждого сотрудника.</span><span class="sxs-lookup"><span data-stu-id="3077e-186">These documents are managed and retained during the employment of each employee.</span></span> <span data-ttu-id="3077e-187">Тем не менее, когда работник покидает организацию или в случае его увольнения, организация обязана в соответствии с требованиями законодательства и бизнеса сохранять документы этого работника в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="3077e-187">However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="3077e-188">Если из организации ежедневно увольняется несколько сотрудников, необходимо запускать счетчики хранения сотен или даже тысяч документов каждый день.</span><span class="sxs-lookup"><span data-stu-id="3077e-188">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="3077e-189">Кроме того, для каждого сотрудника период хранения рассчитывается на основе типа записи сотрудника (дата увольнения сотрудника + количество дней, месяцев или лет).</span><span class="sxs-lookup"><span data-stu-id="3077e-189">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months, or years based on the type of the employee record.</span></span> <span data-ttu-id="3077e-190">Например, у документов о зарплате и документов о премии одного и того же сотрудника могут быть разные периоды хранения.</span><span class="sxs-lookup"><span data-stu-id="3077e-190">For example, worker’s compensation of the employee vs. benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="3077e-191">На схеме далее показано, как может существовать несколько меток, связанных с одним событием.</span><span class="sxs-lookup"><span data-stu-id="3077e-191">The diagram below shows how there can be multiple labels that are associated with a single event.</span></span> <span data-ttu-id="3077e-192">Здесь все файлы под меткой “Компенсации работника” и все файлы под меткой “Льготы сотрудников” связаны с одним событием — уход сотрудника из организации.</span><span class="sxs-lookup"><span data-stu-id="3077e-192">Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event, which is the employee leaving the organization.</span></span> <span data-ttu-id="3077e-193">Каждый из этих различных файлов имеет различные счетчики хранения.</span><span class="sxs-lookup"><span data-stu-id="3077e-193">Each of these different files has different retention clocks.</span></span> <span data-ttu-id="3077e-194">Таким образом, когда сотрудник покидает организацию, эти файлы под каждой меткой имеют различный срок хранения.</span><span class="sxs-lookup"><span data-stu-id="3077e-194">So, when an employee leaves the organization, these files within each label experience a different retention period.</span></span> <span data-ttu-id="3077e-195">Запуск всех этих разных счетчиков хранения для каждого типа файла или метки для каждого сотрудника является очень сложной задачей.</span><span class="sxs-lookup"><span data-stu-id="3077e-195">Triggering all these different retention clocks for each file type or label for each employee is a very challenging task.</span></span> <span data-ttu-id="3077e-196">Представьте, что это необходимо выполнить для нескольких сотрудников.</span><span class="sxs-lookup"><span data-stu-id="3077e-196">Imagine doing this for multiple employees.</span></span>

![Схема типов событий, событий и меток](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="3077e-198">Поэтому автоматизированный процесс запуска всех этих различных счетчиков хранения для нескольких сотрудников должен работать быстро, быть безошибочным и очень эффективным.</span><span class="sxs-lookup"><span data-stu-id="3077e-198">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free, and extremely efficient.</span></span>

<span data-ttu-id="3077e-199">**Настройка автоматизированного хранения на основе событий для этого сценария:**</span><span class="sxs-lookup"><span data-stu-id="3077e-199">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Схема ролей и действий для сценария, когда сотрудник увольняется из организации](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="3077e-201">Администратор создает папки сотрудников в наборе документов, например "Евгения Артемьева", "Артем Кузнецов".</span><span class="sxs-lookup"><span data-stu-id="3077e-201">Admin creates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="3077e-202">Администратор добавляет в каждую папку файлы сотрудников, например с данными о премиях и зарплате.</span><span class="sxs-lookup"><span data-stu-id="3077e-202">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder.</span></span>

  - <span data-ttu-id="3077e-203">Администратор назначает идентификатор ресурса для каждой папки сотрудников.</span><span class="sxs-lookup"><span data-stu-id="3077e-203">Admin assigns Asset ID to each employee folder.</span></span> 

  - <span data-ttu-id="3077e-204">Администратор Центра безопасности и соответствия требованиям выполняет вход в Центр безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3077e-204">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="3077e-205">Администратор безопасности и соответствия требованиям создает типы событий, связанные с сотрудником, например "Увольнение сотрудника" и "Прием сотрудника на работу".</span><span class="sxs-lookup"><span data-stu-id="3077e-205">SCC Admin creates employee-related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="3077e-206">Администратор безопасности и соответствия требованиям создает метку "Хранение для сотрудника".</span><span class="sxs-lookup"><span data-stu-id="3077e-206">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="3077e-207">Эта метка "Хранение для сотрудника" публикуется и вручную или автоматически применяется к файлам сотрудника в SharePoint</span><span class="sxs-lookup"><span data-stu-id="3077e-207">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint.</span></span>

  - <span data-ttu-id="3077e-208">Система управления отдела кадров, например Workday, может работать совместно с Microsoft Flow для периодического управления файлами сотрудников</span><span class="sxs-lookup"><span data-stu-id="3077e-208">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files.</span></span>

  - <span data-ttu-id="3077e-209">Если сотрудник увольняется из организации, Flow активирует REST API хранения на основе событий M365, который запустит счетчик хранения для файлов определенного сотрудника.</span><span class="sxs-lookup"><span data-stu-id="3077e-209">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="3077e-210">Использование Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="3077e-210">Using Microsoft Flow</span></span>

<span data-ttu-id="3077e-211">Шаг 1. Создайте процесс создания события с помощью REST API Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3077e-211">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Использование Flow для создания события](../media/automate-event-driven-retention-flow-1.png)

![Использование Flow для вызова REST API](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="3077e-214">Создание события</span><span class="sxs-lookup"><span data-stu-id="3077e-214">Create an event</span></span>

<span data-ttu-id="3077e-215">Пример кода для вызова REST API</span><span class="sxs-lookup"><span data-stu-id="3077e-215">Sample code to call the REST API</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="3077e-216">Метод</span><span class="sxs-lookup"><span data-stu-id="3077e-216">Method</span></span></th>
<th><span data-ttu-id="3077e-217">POST</span><span class="sxs-lookup"><span data-stu-id="3077e-217">POST</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3077e-218">URL-адрес</span><span class="sxs-lookup"><span data-stu-id="3077e-218">URL</span></span></td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3077e-219">Заголовки</span><span class="sxs-lookup"><span data-stu-id="3077e-219">Headers</span></span></td>
<td><span data-ttu-id="3077e-220">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3077e-220">Content-Type</span></span></td>
<td><span data-ttu-id="3077e-221">приложение/atom+xml</span><span class="sxs-lookup"><span data-stu-id="3077e-221">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3077e-222">Основной текст</span><span class="sxs-lookup"><span data-stu-id="3077e-222">Body</span></span></td>
<td><p><span data-ttu-id="3077e-223">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-223">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="3077e-224">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="3077e-224">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="3077e-225">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="3077e-225">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="3077e-226">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-226">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="3077e-227">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-227">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="3077e-228">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-228">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="3077e-229">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-229">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="3077e-230">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-230">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="3077e-231">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-231">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="3077e-232">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-232">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="3077e-233">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-233">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="3077e-234">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-234">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span></span></p>
<p><span data-ttu-id="3077e-235">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-235">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="3077e-236">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-236">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="3077e-237">&lt;/entry&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-237">&lt;/entry&gt;</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3077e-238">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="3077e-238">Authentication</span></span></td>
<td><span data-ttu-id="3077e-239">Базовая</span><span class="sxs-lookup"><span data-stu-id="3077e-239">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3077e-240">Имя пользователя</span><span class="sxs-lookup"><span data-stu-id="3077e-240">Username</span></span></td>
<td><span data-ttu-id="3077e-241">"Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="3077e-241">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3077e-242">Пароль</span><span class="sxs-lookup"><span data-stu-id="3077e-242">Password</span></span></td>
<td><span data-ttu-id="3077e-243">"Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="3077e-243">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a><span data-ttu-id="3077e-244">Доступные параметры</span><span class="sxs-lookup"><span data-stu-id="3077e-244">Available parameters</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="3077e-245"><strong>Параметры</strong></span><span class="sxs-lookup"><span data-stu-id="3077e-245"><strong>Parameters</strong></span></span></th>
<th><span data-ttu-id="3077e-246"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="3077e-246"><strong>Description</strong></span></span></th>
<th><span data-ttu-id="3077e-247"><strong>Примечания</strong></span><span class="sxs-lookup"><span data-stu-id="3077e-247"><strong>Notes</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3077e-248">&lt;d:Name&gt;&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-248">&lt;d:Name&gt;&lt;/d:Name&gt;</span></span></td>
<td><span data-ttu-id="3077e-249">Указание уникального имени события.</span><span class="sxs-lookup"><span data-stu-id="3077e-249">Provide a unique name for the event,</span></span></td>
<td><span data-ttu-id="3077e-p121">Не может содержать начальные и конечные пробелы и следующие символы: % \* \ &amp; &lt; &gt; | # ? , : ;</span><span class="sxs-lookup"><span data-stu-id="3077e-p121">Cannot contain trailing spaces, and the following characters: % \* \ &amp; &lt; &gt; | # ? , : ;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3077e-252">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-252">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span></span></td>
<td><span data-ttu-id="3077e-253">Введите название типа события (или Guid).</span><span class="sxs-lookup"><span data-stu-id="3077e-253">Enter event type name (or Guid),</span></span></td>
<td><span data-ttu-id="3077e-p122">Пример: "Увольнение сотрудника". Тип события должен быть связан с меткой хранения.</span><span class="sxs-lookup"><span data-stu-id="3077e-p122">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3077e-256">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-256">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span></span></td>
<td><span data-ttu-id="3077e-257">Введите "ComplianceAssetId:" + код сотрудника</span><span class="sxs-lookup"><span data-stu-id="3077e-257">Enter “ComplianceAssetId:” + employee Id</span></span></td>
<td><span data-ttu-id="3077e-258">Пример: &quot;ComplianceAssetId:12345&quot;</span><span class="sxs-lookup"><span data-stu-id="3077e-258">Example:&quot;ComplianceAssetId:12345&quot;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3077e-259">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-259">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span></span></td>
<td><span data-ttu-id="3077e-260">Дата и время события</span><span class="sxs-lookup"><span data-stu-id="3077e-260">Event Date and Time</span></span></td>
<td><p><span data-ttu-id="3077e-261">Формат: ГГГГ-ММ-ДДTчч:мм:ссZ. Пример:</span><span class="sxs-lookup"><span data-stu-id="3077e-261">Format: yyyy-MM-ddTHH:mm:ssZ, Example:</span></span></p>
<p><span data-ttu-id="3077e-262">2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="3077e-262">2018-12-01T00:00:00Z</span></span></p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="3077e-263">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="3077e-263">Response codes</span></span>

| <span data-ttu-id="3077e-264">**Код ответа**</span><span class="sxs-lookup"><span data-stu-id="3077e-264">**Response Code**</span></span> | <span data-ttu-id="3077e-265">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3077e-265">**Description**</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="3077e-266">302</span><span class="sxs-lookup"><span data-stu-id="3077e-266">302</span></span>               | <span data-ttu-id="3077e-267">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="3077e-267">Redirect</span></span>              |
| <span data-ttu-id="3077e-268">201</span><span class="sxs-lookup"><span data-stu-id="3077e-268">201</span></span>               | <span data-ttu-id="3077e-269">Создано</span><span class="sxs-lookup"><span data-stu-id="3077e-269">Created</span></span>               |
| <span data-ttu-id="3077e-270">403</span><span class="sxs-lookup"><span data-stu-id="3077e-270">403</span></span>               | <span data-ttu-id="3077e-271">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="3077e-271">Authorization Failed</span></span>  |
| <span data-ttu-id="3077e-272">401</span><span class="sxs-lookup"><span data-stu-id="3077e-272">401</span></span>               | <span data-ttu-id="3077e-273">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="3077e-273">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="3077e-274">Получение событий на основе диапазона времени</span><span class="sxs-lookup"><span data-stu-id="3077e-274">Get Events based on time range</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="3077e-275">Метод</span><span class="sxs-lookup"><span data-stu-id="3077e-275">Method</span></span></th>
<th><span data-ttu-id="3077e-276">GET</span><span class="sxs-lookup"><span data-stu-id="3077e-276">GET</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3077e-277">URL-адрес</span><span class="sxs-lookup"><span data-stu-id="3077e-277">URL</span></span></td>
<td><ol start="4" type="1">
<li><p><span data-ttu-id="3077e-278">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span><span class="sxs-lookup"><span data-stu-id="3077e-278">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span></span></p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3077e-279">Заголовки</span><span class="sxs-lookup"><span data-stu-id="3077e-279">Headers</span></span></td>
<td><span data-ttu-id="3077e-280">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3077e-280">Content-Type</span></span></td>
<td><span data-ttu-id="3077e-281">приложение/atom+xml</span><span class="sxs-lookup"><span data-stu-id="3077e-281">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3077e-282">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="3077e-282">Authentication</span></span></td>
<td><span data-ttu-id="3077e-283">Базовая</span><span class="sxs-lookup"><span data-stu-id="3077e-283">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3077e-284">Имя пользователя</span><span class="sxs-lookup"><span data-stu-id="3077e-284">Username</span></span></td>
<td><span data-ttu-id="3077e-285">"Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="3077e-285">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3077e-286">Пароль</span><span class="sxs-lookup"><span data-stu-id="3077e-286">Password</span></span></td>
<td><span data-ttu-id="3077e-287">"Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="3077e-287">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="3077e-288">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="3077e-288">Response codes</span></span>

| <span data-ttu-id="3077e-289">**Код ответа**</span><span class="sxs-lookup"><span data-stu-id="3077e-289">**Response Code**</span></span> | <span data-ttu-id="3077e-290">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3077e-290">**Description**</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="3077e-291">200</span><span class="sxs-lookup"><span data-stu-id="3077e-291">200</span></span>               | <span data-ttu-id="3077e-292">Все в порядке, список событий в формате atom+xml</span><span class="sxs-lookup"><span data-stu-id="3077e-292">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="3077e-293">404</span><span class="sxs-lookup"><span data-stu-id="3077e-293">404</span></span>               | <span data-ttu-id="3077e-294">Не найдено</span><span class="sxs-lookup"><span data-stu-id="3077e-294">Not found</span></span>                         |
| <span data-ttu-id="3077e-295">302</span><span class="sxs-lookup"><span data-stu-id="3077e-295">302</span></span>               | <span data-ttu-id="3077e-296">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="3077e-296">Redirect</span></span>                          |
| <span data-ttu-id="3077e-297">401</span><span class="sxs-lookup"><span data-stu-id="3077e-297">401</span></span>               | <span data-ttu-id="3077e-298">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="3077e-298">Authorization Failed</span></span>              |
| <span data-ttu-id="3077e-299">403</span><span class="sxs-lookup"><span data-stu-id="3077e-299">403</span></span>               | <span data-ttu-id="3077e-300">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="3077e-300">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="3077e-301">Получение события по идентификатору</span><span class="sxs-lookup"><span data-stu-id="3077e-301">Get an event by ID</span></span>

| <span data-ttu-id="3077e-302">Метод</span><span class="sxs-lookup"><span data-stu-id="3077e-302">Method</span></span>         | <span data-ttu-id="3077e-303">GET</span><span class="sxs-lookup"><span data-stu-id="3077e-303">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="3077e-304">URL-адрес</span><span class="sxs-lookup"><span data-stu-id="3077e-304">URL</span></span>            | <span data-ttu-id="3077e-305">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="3077e-305">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="3077e-306">Заголовок</span><span class="sxs-lookup"><span data-stu-id="3077e-306">Header</span></span>         | <span data-ttu-id="3077e-307">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3077e-307">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="3077e-308">приложение/atom+xml</span><span class="sxs-lookup"><span data-stu-id="3077e-308">application/atom+xml</span></span> |
| <span data-ttu-id="3077e-309">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="3077e-309">Authentication</span></span> | <span data-ttu-id="3077e-310">Базовая</span><span class="sxs-lookup"><span data-stu-id="3077e-310">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="3077e-311">Имя пользователя</span><span class="sxs-lookup"><span data-stu-id="3077e-311">Username</span></span>       | <span data-ttu-id="3077e-312">"Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="3077e-312">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="3077e-313">Пароль</span><span class="sxs-lookup"><span data-stu-id="3077e-313">Password</span></span>       | <span data-ttu-id="3077e-314">"Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="3077e-314">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="3077e-315">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="3077e-315">Response codes</span></span>

| <span data-ttu-id="3077e-316">**Код ответа**</span><span class="sxs-lookup"><span data-stu-id="3077e-316">**Response Code**</span></span> | <span data-ttu-id="3077e-317">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3077e-317">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="3077e-318">200</span><span class="sxs-lookup"><span data-stu-id="3077e-318">200</span></span>               | <span data-ttu-id="3077e-319">Все в порядке, текст ответа содержит событие в формате atom+xml</span><span class="sxs-lookup"><span data-stu-id="3077e-319">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="3077e-320">404</span><span class="sxs-lookup"><span data-stu-id="3077e-320">404</span></span>               | <span data-ttu-id="3077e-321">Не найдено</span><span class="sxs-lookup"><span data-stu-id="3077e-321">Not found</span></span>                                            |
| <span data-ttu-id="3077e-322">302</span><span class="sxs-lookup"><span data-stu-id="3077e-322">302</span></span>               | <span data-ttu-id="3077e-323">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="3077e-323">Redirect</span></span>                                             |
| <span data-ttu-id="3077e-324">401</span><span class="sxs-lookup"><span data-stu-id="3077e-324">401</span></span>               | <span data-ttu-id="3077e-325">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="3077e-325">Authorization Failed</span></span>                                 |
| <span data-ttu-id="3077e-326">403</span><span class="sxs-lookup"><span data-stu-id="3077e-326">403</span></span>               | <span data-ttu-id="3077e-327">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="3077e-327">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="3077e-328">Получение события по имени</span><span class="sxs-lookup"><span data-stu-id="3077e-328">Get an event by name</span></span>

| <span data-ttu-id="3077e-329">Метод</span><span class="sxs-lookup"><span data-stu-id="3077e-329">Method</span></span>         | <span data-ttu-id="3077e-330">GET</span><span class="sxs-lookup"><span data-stu-id="3077e-330">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="3077e-331">URL-адрес</span><span class="sxs-lookup"><span data-stu-id="3077e-331">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="3077e-332">Заголовки</span><span class="sxs-lookup"><span data-stu-id="3077e-332">Headers</span></span>        | <span data-ttu-id="3077e-333">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3077e-333">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="3077e-334">приложение/atom+xml</span><span class="sxs-lookup"><span data-stu-id="3077e-334">application/atom+xml</span></span> |
| <span data-ttu-id="3077e-335">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="3077e-335">Authentication</span></span> | <span data-ttu-id="3077e-336">Базовая</span><span class="sxs-lookup"><span data-stu-id="3077e-336">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="3077e-337">Имя пользователя</span><span class="sxs-lookup"><span data-stu-id="3077e-337">Username</span></span>       | <span data-ttu-id="3077e-338">"Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="3077e-338">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="3077e-339">Пароль</span><span class="sxs-lookup"><span data-stu-id="3077e-339">Password</span></span>       | <span data-ttu-id="3077e-340">"Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="3077e-340">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="3077e-341">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="3077e-341">Response codes</span></span>

| <span data-ttu-id="3077e-342">**Код ответа**</span><span class="sxs-lookup"><span data-stu-id="3077e-342">**Response Code**</span></span> | <span data-ttu-id="3077e-343">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3077e-343">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="3077e-344">200</span><span class="sxs-lookup"><span data-stu-id="3077e-344">200</span></span>               | <span data-ttu-id="3077e-345">Все в порядке, текст ответа содержит событие в формате atom+xml</span><span class="sxs-lookup"><span data-stu-id="3077e-345">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="3077e-346">404</span><span class="sxs-lookup"><span data-stu-id="3077e-346">404</span></span>               | <span data-ttu-id="3077e-347">Не найдено</span><span class="sxs-lookup"><span data-stu-id="3077e-347">Not found</span></span>                                            |
| <span data-ttu-id="3077e-348">302</span><span class="sxs-lookup"><span data-stu-id="3077e-348">302</span></span>               | <span data-ttu-id="3077e-349">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="3077e-349">Redirect</span></span>                                             |
| <span data-ttu-id="3077e-350">401</span><span class="sxs-lookup"><span data-stu-id="3077e-350">401</span></span>               | <span data-ttu-id="3077e-351">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="3077e-351">Authorization Failed</span></span>                                 |
| <span data-ttu-id="3077e-352">403</span><span class="sxs-lookup"><span data-stu-id="3077e-352">403</span></span>               | <span data-ttu-id="3077e-353">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="3077e-353">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="3077e-354">Использование PowerShell (версии 6 или выше) или любого HTTP-клиента</span><span class="sxs-lookup"><span data-stu-id="3077e-354">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="3077e-355">Шаг 1. Подключитесь к PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3077e-355">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="3077e-356">Шаг 2. Запустите указанный ниже сценарий.</span><span class="sxs-lookup"><span data-stu-id="3077e-356">Step 2: Run the following script.</span></span>

<table>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3077e-357">param([string]$baseUri)</span><span class="sxs-lookup"><span data-stu-id="3077e-357">param([string]$baseUri)</span></span></p>
<p><span data-ttu-id="3077e-358">$userName = &quot;UserName&quot;</span><span class="sxs-lookup"><span data-stu-id="3077e-358">$userName = &quot;UserName&quot;</span></span></p>
<p><span data-ttu-id="3077e-359">$password = &quot;Password&quot;</span><span class="sxs-lookup"><span data-stu-id="3077e-359">$password = &quot;Password&quot;</span></span></p>
<p><span data-ttu-id="3077e-360">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span><span class="sxs-lookup"><span data-stu-id="3077e-360">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span></span></p>
<p><span data-ttu-id="3077e-361">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span><span class="sxs-lookup"><span data-stu-id="3077e-361">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span></span></p>
<p><span data-ttu-id="3077e-362">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span><span class="sxs-lookup"><span data-stu-id="3077e-362">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span></span></p>
<p><span data-ttu-id="3077e-363">Write-Host &quot;Start to create an event with name: $EventName&quot;</span><span class="sxs-lookup"><span data-stu-id="3077e-363">Write-Host &quot;Start to create an event with name: $EventName&quot;</span></span></p>
<p><span data-ttu-id="3077e-364">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-364">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="3077e-365">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="3077e-365">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="3077e-366">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="3077e-366">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="3077e-367">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-367">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="3077e-368">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-368">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="3077e-369">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-369">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="3077e-370">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-370">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="3077e-371">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-371">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="3077e-372">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-372">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="3077e-373">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-373">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="3077e-374">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-374">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="3077e-375">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-375">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="3077e-376">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="3077e-376">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="3077e-377">&lt;/entry&gt;&quot;</span><span class="sxs-lookup"><span data-stu-id="3077e-377">&lt;/entry&gt;&quot;</span></span></p>
<p><span data-ttu-id="3077e-378">$event = $null</span><span class="sxs-lookup"><span data-stu-id="3077e-378">$event = $null</span></span></p>
<p><span data-ttu-id="3077e-379">try</span><span class="sxs-lookup"><span data-stu-id="3077e-379">try</span></span></p>
<p><span data-ttu-id="3077e-380">{</span><span class="sxs-lookup"><span data-stu-id="3077e-380">{</span></span></p>
<p><span data-ttu-id="3077e-381">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="3077e-381">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="3077e-382">}</span><span class="sxs-lookup"><span data-stu-id="3077e-382">}</span></span></p>
<p><span data-ttu-id="3077e-383">catch</span><span class="sxs-lookup"><span data-stu-id="3077e-383">catch</span></span></p>
<p><span data-ttu-id="3077e-384">{</span><span class="sxs-lookup"><span data-stu-id="3077e-384">{</span></span></p>
<p><span data-ttu-id="3077e-385">$response = $_.Exception.Response</span><span class="sxs-lookup"><span data-stu-id="3077e-385">$response = $_.Exception.Response</span></span></p>
<p><span data-ttu-id="3077e-386">if($response.StatusCode -eq &quot;Redirect&quot;)</span><span class="sxs-lookup"><span data-stu-id="3077e-386">if($response.StatusCode -eq &quot;Redirect&quot;)</span></span></p>
<p><span data-ttu-id="3077e-387">{</span><span class="sxs-lookup"><span data-stu-id="3077e-387">{</span></span></p>
<p><span data-ttu-id="3077e-388">$url = $response.Headers.Location</span><span class="sxs-lookup"><span data-stu-id="3077e-388">$url = $response.Headers.Location</span></span></p>
<p><span data-ttu-id="3077e-389">Write-Host &quot;redirected to $url&quot;</span><span class="sxs-lookup"><span data-stu-id="3077e-389">Write-Host &quot;redirected to $url&quot;</span></span></p>
<p><span data-ttu-id="3077e-390">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="3077e-390">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="3077e-391">}</span><span class="sxs-lookup"><span data-stu-id="3077e-391">}</span></span></p>
<p><span data-ttu-id="3077e-392">}</span><span class="sxs-lookup"><span data-stu-id="3077e-392">}</span></span></p>
<p><span data-ttu-id="3077e-393">$event | fl \*</span><span class="sxs-lookup"><span data-stu-id="3077e-393">$event | fl \*</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="3077e-394">Проверка результатов обоих вариантов</span><span class="sxs-lookup"><span data-stu-id="3077e-394">Verify the outcome in both options</span></span>

<span data-ttu-id="3077e-395">Шаг 1. Перейдите в Центр безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3077e-395">Step 1: Go to the Security & Compliance Center.</span></span>

<span data-ttu-id="3077e-396">Шаг 2. Выберите **События** в разделе **Управление информацией**.</span><span class="sxs-lookup"><span data-stu-id="3077e-396">Step 2: Select **Events** under **Information governance**.</span></span>

<span data-ttu-id="3077e-397">Шаг 3. Убедитесь, что событие создано.</span><span class="sxs-lookup"><span data-stu-id="3077e-397">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="3077e-398">Аналогичным образом описанные выше варианты автоматизации хранения на основе событий можно использовать и для следующих сценариев.</span><span class="sxs-lookup"><span data-stu-id="3077e-398">Similarly, the above options to automate event-based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="3077e-399">Сценарий 2. Окончание действия договоров</span><span class="sxs-lookup"><span data-stu-id="3077e-399">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="3077e-400">Организация может иметь несколько записей для одного договора с клиентами, поставщиками и партнерами.</span><span class="sxs-lookup"><span data-stu-id="3077e-400">An organization can have multiple records for a single contract with customers, vendors, and partners.</span></span> <span data-ttu-id="3077e-401">Эти документы можно хранить в библиотеке документов, например в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3077e-401">These documents can reside in a document library like SharePoint.</span></span> <span data-ttu-id="3077e-402">Окончание договора определяет начало срока хранения документов, связанных с договором.</span><span class="sxs-lookup"><span data-stu-id="3077e-402">The end of a contract determines the start of the retention period of the documents associated with the contract.</span></span> <span data-ttu-id="3077e-403">Например, все записи, связанные с договорами, нужно хранить в течение пяти лет с момента истечения срока действия договора.</span><span class="sxs-lookup"><span data-stu-id="3077e-403">For example, all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="3077e-404">Событием, активирующим пятилетнее хранение, будет окончание срока действия договора.</span><span class="sxs-lookup"><span data-stu-id="3077e-404">The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="3077e-405">Система управления отношениями с клиентами может работать совместно с Microsoft 365 и активировать хранение документов договора.</span><span class="sxs-lookup"><span data-stu-id="3077e-405">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents</span></span>

<span data-ttu-id="3077e-406">**Настройка автоматизированного хранения на основе событий для этого сценария:**</span><span class="sxs-lookup"><span data-stu-id="3077e-406">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Схема ролей и задач для сценария окончания действия договора](../media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="3077e-408">Администратор создает библиотеку SharePoint с различными папками для каждого типа договора.</span><span class="sxs-lookup"><span data-stu-id="3077e-408">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="3077e-409">Администратор добавляет файлы договора, например лицензионные соглашения, договоры о разработке, в папку каждого договора.</span><span class="sxs-lookup"><span data-stu-id="3077e-409">Admin adds contract files such as License Contracts, Development Contracts to each contract folder.</span></span>

  - <span data-ttu-id="3077e-410">Администратор назначает идентификатор ресурса для каждой папки договора.</span><span class="sxs-lookup"><span data-stu-id="3077e-410">Admin assigns Asset ID to each contract folder.</span></span>

  - <span data-ttu-id="3077e-411">Администратор Центра безопасности и соответствия требованиям выполняет вход в Центр безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3077e-411">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="3077e-412">Администратор безопасности и соответствия требованиям создает типы событий, связанные с договором, например "Создание договора" и "Завершение действия договора".</span><span class="sxs-lookup"><span data-stu-id="3077e-412">SCC Admin creates contract-related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="3077e-413">Администратор безопасности и соответствия требованиям создает метку "Завершение действия договора".</span><span class="sxs-lookup"><span data-stu-id="3077e-413">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="3077e-414">Эта метка "Завершение действия договора" публикуется и вручную или автоматически применяется к файлам договора в SharePoint</span><span class="sxs-lookup"><span data-stu-id="3077e-414">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint.</span></span>

  - <span data-ttu-id="3077e-415">Система управления договорами может работать совместно с Microsoft Flow или аналогичным приложением для периодического управления файлами договоров.</span><span class="sxs-lookup"><span data-stu-id="3077e-415">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files.</span></span>

  - <span data-ttu-id="3077e-416">Если срок действия договора завершается, Microsoft Flow активирует REST API хранения на основе событий M365, который запустит счетчик хранения для файлов определенного договора.</span><span class="sxs-lookup"><span data-stu-id="3077e-416">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="3077e-417">Сценарий 3. Прекращение производства продукта</span><span class="sxs-lookup"><span data-stu-id="3077e-417">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="3077e-p124">Производственная компания, которая изготавливает различные линейки продуктов, создает множество документов с техническими характеристиками производства и ценами. Если продукт перестает производится, все технические характеристики и документы, связанные с этим продуктом, следует хранить в течение определенного периода времени после окончания существования продукта.</span><span class="sxs-lookup"><span data-stu-id="3077e-p124">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="3077e-420">Система планирования ресурсов предприятия (ERP) может работать совместно с Microsoft 365 и Microsoft Flow для активации хранения.</span><span class="sxs-lookup"><span data-stu-id="3077e-420">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="3077e-421">**Настройка автоматизированного хранения на основе событий для этого сценария:**</span><span class="sxs-lookup"><span data-stu-id="3077e-421">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Схема ролей и задач для сценария жизненного цикла продукта](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="3077e-423">Администратор создает папки продуктов в наборе документов, например "Продукт 1", "Продукт 2" и т. д.</span><span class="sxs-lookup"><span data-stu-id="3077e-423">Admin creates product folders in the Document set such as Product 1, Product 2, and so on.</span></span>

  - <span data-ttu-id="3077e-424">Администратор добавляет файлы продуктов, например технические характеристики производства, цены продуктов и лицензирование продуктов, в каждую папку продукта.</span><span class="sxs-lookup"><span data-stu-id="3077e-424">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder.</span></span>

  - <span data-ttu-id="3077e-425">Администратор назначает ИД ресурса для каждой папки продукта.</span><span class="sxs-lookup"><span data-stu-id="3077e-425">Admin assigns Asset ID to each product folder.</span></span>

  - <span data-ttu-id="3077e-426">Администратор Центра безопасности и соответствия требованиям выполняет вход в Центр безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3077e-426">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="3077e-427">Администратор безопасности и соответствия требованиям создает типы событий, связанные с сотрудником, например "Начало производства продукта" и "Окончание производства продукта".</span><span class="sxs-lookup"><span data-stu-id="3077e-427">SCC Admin creates employee-related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="3077e-428">Администратор безопасности и соответствия требованиям создает метку "Окончание производства продукта".</span><span class="sxs-lookup"><span data-stu-id="3077e-428">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="3077e-429">Эта метка "Завершение изготовление продукта" публикуется и вручную или автоматически применяется к файлам продукта в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3077e-429">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint.</span></span>

  - <span data-ttu-id="3077e-430">Система ERP может работать совместно с Microsoft Flow или аналогичным приложением для периодического управления файлами продуктов.</span><span class="sxs-lookup"><span data-stu-id="3077e-430">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files.</span></span>

  - <span data-ttu-id="3077e-431">Если изготовление продукта завершается, Microsoft Flow активирует REST API хранения на основе событий M365, который запустит счетчик хранения для файлов определенного продукта.</span><span class="sxs-lookup"><span data-stu-id="3077e-431">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="3077e-432">Приложение</span><span class="sxs-lookup"><span data-stu-id="3077e-432">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="3077e-433">Использование результатов ответа 302 (перенаправление) для вызова REST API</span><span class="sxs-lookup"><span data-stu-id="3077e-433">Using Redirect 302 response results to call the REST API</span></span>

1. <span data-ttu-id="3077e-434">Вызовите событие хранения POST с помощью URL-адреса REST API <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (требуются разрешения глобального администратора)</span><span class="sxs-lookup"><span data-stu-id="3077e-434">Invoke a POST retention event call using the REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required)</span></span>

2. <span data-ttu-id="3077e-p125">Проверьте код ответа. Если получен код 302, получите URL-адрес перенаправления из свойства Location (Расположение) заголовка ответа</span><span class="sxs-lookup"><span data-stu-id="3077e-p125">Check the response code. If it’s 302, then get the redirected URL from Location property of the response header</span></span>

3. <span data-ttu-id="3077e-437">Вызовите событие хранения POST еще раз с помощью URL-адреса перенаправления</span><span class="sxs-lookup"><span data-stu-id="3077e-437">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="3077e-438">Сведения об авторах</span><span class="sxs-lookup"><span data-stu-id="3077e-438">Credits</span></span>

<span data-ttu-id="3077e-439">Редактор статьи:</span><span class="sxs-lookup"><span data-stu-id="3077e-439">This topic was reviewed by:</span></span>

<span data-ttu-id="3077e-440">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="3077e-440">Antonio Maio</span></span><br/><span data-ttu-id="3077e-441">MVP в сфере приложений и служб Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="3077e-441">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="3077e-442">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="3077e-442">Antonio.Maio@Protiviti.com</span></span>
