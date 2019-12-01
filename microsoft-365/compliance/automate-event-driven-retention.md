---
title: Хранение, зависящее от возникновения события
ms.author: laurawi
author: laurawi
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
ms.openlocfilehash: b4ae97ad9564f61e65b990a0054fcf13d88f1d8d
ms.sourcegitcommit: bf30a2314376f0b7d577741b97df017969737d11
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2019
ms.locfileid: "39631069"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="59242-103">Автоматизация хранения на основе событий</span><span class="sxs-lookup"><span data-stu-id="59242-103">Automate event-based retention</span></span>

<span data-ttu-id="59242-p101">Процессы развертывания содержимого в организации, а также обнаружения избыточных, устаревших и тривиальных данных играют важную роль. Чтобы продолжать соответствовать юридическим, нормативным и бизнес-требованиям, организации должны обеспечить хранение и защиту важной информации, а также быстрый поиск необходимых данных. Хранение только важной и подходящей информации является ключевым фактором успеха организаций.</span><span class="sxs-lookup"><span data-stu-id="59242-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, businesses must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to a business’s success.</span></span>

<span data-ttu-id="59242-p102">Чтобы помочь удовлетворить эту потребность, организации могут использовать преимущества решений для хранения в Центре безопасности и соответствия требованиям Office 365. Связанные с хранением операции можно активировать с помощью [меток хранения](labels.md). У метки хранения есть параметр для [определения периода хранения на основе конкретного события](event-driven-retention.md). Обычно период хранения зависит от известной даты, например даты создания или последнего изменения содержимого. Однако у организаций также есть требования по удалению содержимого на основе возникновения событий, например через 7 лет после того, как сотрудник уволился из организации.</span><span class="sxs-lookup"><span data-stu-id="59242-p102">Hence organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as 7 years after an employee leaves an organization.</span></span>

<span data-ttu-id="59242-p103">Чтобы обеспечить удаление содержимого в соответствии с требованиями, важно знать, когда происходят события. Из-за стремительного роста объема содержимого становится сложно хранить и удалять данные своевременно и в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="59242-p103">In order to ensure compliant disposal of content, it is imperative to know when an event takes place. With the volume of content increasing rapidly, it is becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="59242-p104">Хранения на основе событий решает эту проблему. В этой статье описывается, как настроить операции бизнес-процесса, чтобы автоматизировать хранение с помощью событий, используя REST API Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="59242-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="59242-116">О хранении на основе событий</span><span class="sxs-lookup"><span data-stu-id="59242-116">About event-based retention</span></span>

<span data-ttu-id="59242-p105">Независимо от размера организации количество деловых документов, юридических документов, файлов сотрудников, договоров и документов о продукции, которые ежедневно создаются и которыми необходимо управлять, стремительно растет.</span><span class="sxs-lookup"><span data-stu-id="59242-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day to day basis is increasing dramatically.</span></span>

<span data-ttu-id="59242-p106">Например, каждый день десятки и сотни сотрудников устраиваются на работу в организации или увольняются. Отдел кадров постоянно создает, обновляет или удаляет связанные с сотрудниками документы в соответствии с бизнес-требованиями. Этот процесс регулируется различными политиками, определяемыми для компании:</span><span class="sxs-lookup"><span data-stu-id="59242-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="59242-p107">**Период хранения содержимого может зависеть от известной даты**, например даты создания, последнего изменения содержимого или присвоения ему метки. Пример: вы можете хранить документы в течение семи лет после создания, а затем удалить их.</span><span class="sxs-lookup"><span data-stu-id="59242-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="59242-p108">**Период хранения содержимого может зависеть от неизвестной даты**. Например, с помощью меток хранения можно определять зависимость периода хранения от возникновения определенного типа события, такого как увольнение сотрудника из организации.</span><span class="sxs-lookup"><span data-stu-id="59242-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="59242-p109">Событие активирует начало периода хранения, и ко всему содержимому с меткой, относящейся к событию данного типа, применяются действия хранения. Этот процесс называется хранением на основе событий. Дополнительные сведения о нем см. в статье [Общие сведения о хранении, зависящем от возникновения события](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="59242-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention - to learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="59242-129">Настройка хранении на основе событий</span><span class="sxs-lookup"><span data-stu-id="59242-129">Set up event-based retention</span></span>

<span data-ttu-id="59242-130">В этом разделе описываются действия, которые необходимо выполнить до момента подготовки хранения содержимого.</span><span class="sxs-lookup"><span data-stu-id="59242-130">This section describes what needs to be done prior to retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="59242-131">Определение ролей</span><span class="sxs-lookup"><span data-stu-id="59242-131">Identify roles</span></span>

<span data-ttu-id="59242-132">Определите различные роли в организации, которые будут выполнять задачи управления записями и будут обеспечивать эффективное хранение деловых документов.</span><span class="sxs-lookup"><span data-stu-id="59242-132">Identify the different roles in an organization that perform Record Management tasks that would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="59242-133">**Роль**</span><span class="sxs-lookup"><span data-stu-id="59242-133">**Persona**</span></span>| <span data-ttu-id="59242-134">**Role**</span><span class="sxs-lookup"><span data-stu-id="59242-134">**Role**</span></span>|
  | - | - |
  | <span data-ttu-id="59242-135">Администратор</span><span class="sxs-lookup"><span data-stu-id="59242-135">Admin</span></span> | <span data-ttu-id="59242-136">Создает типы событий хранения, метки хранения и репозитории записей в SharePoint</span><span class="sxs-lookup"><span data-stu-id="59242-136">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="59242-137">Управляющий записями</span><span class="sxs-lookup"><span data-stu-id="59242-137">Records Manager</span></span>                                  | <span data-ttu-id="59242-138">Предоставляет указания по политикам и расписанию хранения, а также сведения о соответствии требованиям</span><span class="sxs-lookup"><span data-stu-id="59242-138">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="59242-139">Системный администратор (компания)</span><span class="sxs-lookup"><span data-stu-id="59242-139">System Admin (business)</span></span>                          | <span data-ttu-id="59242-140">Настраивает внешние системы для работы с Microsoft 365 и управляет ими</span><span class="sxs-lookup"><span data-stu-id="59242-140">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="59242-141">Информационный работник</span><span class="sxs-lookup"><span data-stu-id="59242-141">Information Worker</span></span>                               | <span data-ttu-id="59242-142">Управляет жизненным циклом своих бизнес-процессов (отдела кадров, финансового отдела, ИТ-отдела и т. д.)</span><span class="sxs-lookup"><span data-stu-id="59242-142">Manages the lifecycle of their business process (HR, Finance, IT etc)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="59242-143">Настройка Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="59242-143">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="59242-144">Администратор соответствия требованиям создает тип события — например, увольняется сотрудник, истекает срок действия договора или завершается производство продукта</span><span class="sxs-lookup"><span data-stu-id="59242-144">Compliance admin creates an event type – for example, Employee Termination or Contract Expiration or End of Product Manufacturing (Please refer to step by step process in &ndash;.</span></span> <span data-ttu-id="59242-145">(см. пошаговое описание процесса в статье [Хранение на основе событий](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="59242-145">(See the step-by-step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
2. <span data-ttu-id="59242-146">Администратор соответствия требованиям создает метку хранения на основе некоего события и связывает ее с типом события.</span><span class="sxs-lookup"><span data-stu-id="59242-146">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
    <span data-ttu-id="59242-147">Существует четыре типа триггеров меток хранения:</span><span class="sxs-lookup"><span data-stu-id="59242-147">There are 4 types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="59242-148">Дата создания</span><span class="sxs-lookup"><span data-stu-id="59242-148">Create date</span></span>
                
    2. <span data-ttu-id="59242-149">Дата последнего изменения</span><span class="sxs-lookup"><span data-stu-id="59242-149">Last modified</span></span>
                
    3. <span data-ttu-id="59242-150">Дата метки (когда содержимому была присвоена метка)</span><span class="sxs-lookup"><span data-stu-id="59242-150">Label date (when the content was labeled)</span></span>
                
    4. <span data-ttu-id="59242-151">На основе события</span><span class="sxs-lookup"><span data-stu-id="59242-151">Event-based</span></span>
    
3. <span data-ttu-id="59242-152">Администратор соответствия требованиям публикует метку хранения.</span><span class="sxs-lookup"><span data-stu-id="59242-152">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="59242-153">Настройка SharePoint</span><span class="sxs-lookup"><span data-stu-id="59242-153">Set up SharePoint</span></span>
   
<span data-ttu-id="59242-154">Чтобы создать репозиторий записей, администратор соответствия требованиям выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="59242-154">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="59242-155">Создает сайт SharePoint.</span><span class="sxs-lookup"><span data-stu-id="59242-155">Creates a SharePoint site.</span></span>

2. <span data-ttu-id="59242-156">Выполняет одно из указанных ниже действий:</span><span class="sxs-lookup"><span data-stu-id="59242-156">Does one of the following:</span></span>
        
    - <span data-ttu-id="59242-p111">Создает библиотеку SharePoint: задает метку на основе события на уровне библиотеки. Дополнительные сведения см. в разделе "Применение метки хранения по умолчанию ко всему контенту в библиотеке SharePoint, папке или набору документов" [этой статьи](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="59242-p111">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
    - <span data-ttu-id="59242-159">Настройка набора документов в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="59242-159">Sets up a document set in SharePoint.</span></span> <span data-ttu-id="59242-160">Дополнительные сведения см. в статье [Общие сведения о наборах документов](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span><span class="sxs-lookup"><span data-stu-id="59242-160">Sets up a Document set in SharePoint. For more information, see [Introduction to document sets](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span></span>
      
3. <span data-ttu-id="59242-161">Назначает ИД ресурса для каждого набора документов сотрудников.</span><span class="sxs-lookup"><span data-stu-id="59242-161">Assigns an asset ID to each employee document set.</span></span> <span data-ttu-id="59242-162">ИД ресурса — это наименование продукта или код, который используется организацией, например код сотрудника может быть кодом ресурса.</span><span class="sxs-lookup"><span data-stu-id="59242-162">An asset ID is a product name or code used by the organization, for example, Employee number can be an asset ID.</span></span> <span data-ttu-id="59242-163">При назначении ИД ресурса папке, каждый элемент в этой папке автоматически наследует тот же самый ИД ресурса.</span><span class="sxs-lookup"><span data-stu-id="59242-163">By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID.</span></span> <span data-ttu-id="59242-164">Это означает, что срок хранения всех элементов может быть вызван тем же событием.</span><span class="sxs-lookup"><span data-stu-id="59242-164">This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="59242-165">Способы запуска хранения на основе события</span><span class="sxs-lookup"><span data-stu-id="59242-165">Ways to trigger event-based retention</span></span>

<span data-ttu-id="59242-166">Существует два способа запуска хранения на основе события:</span><span class="sxs-lookup"><span data-stu-id="59242-166">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="59242-167">\*\*Использование пользовательского интерфейса центра администрирования \*\* С помощью этого процесса можно уменьшить объем содержимого, сохраняемого за один раз, или запускать хранение реже, например, раз в месяц или раз в год.</span><span class="sxs-lookup"><span data-stu-id="59242-167">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention isn't often, such as monthly or yearly.</span></span> <span data-ttu-id="59242-168">Дополнительные сведения об использовании этого метода см. в статье [Обзор хранения на основе события](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="59242-168">For more information about labels, see [Overview of retention labels](event-driven-retention.md).</span></span> <span data-ttu-id="59242-169">Тем не менее, этот способ запуска хранения может потребовать значительных временных затрат и подвержен ошибкам, что препятствует масштабированию.</span><span class="sxs-lookup"><span data-stu-id="59242-169">However, this method of triggering retention can be time consuming and prone to error, thus stunting scalability.</span></span> <span data-ttu-id="59242-170">Таким образом, автоматизированное беспрепятственное решение для запуска хранения может повысить безопасность и улучшить соответствие требованиям в отношении данных.</span><span class="sxs-lookup"><span data-stu-id="59242-170">Therefore, an automated, seamless solution to trigger retention can enhance data security and compliance.</span></span>

- <span data-ttu-id="59242-p115">**С помощью REST API M365.** Этот процесс можно использовать для хранения большого объема данных и/или в случае частой активации хранения (каждый день или каждую неделю). Этот процесс определяет, когда событие возникает в вашей бизнес-системе, и автоматически создает связанное событие в Центре безопасности и соответствия требованиям. Вам не нужно вручную создавать связанное событие в пользовательском интерфейсе каждый раз, когда происходит исходное событие.</span><span class="sxs-lookup"><span data-stu-id="59242-p115">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="59242-174">Существует два способа использования REST API:</span><span class="sxs-lookup"><span data-stu-id="59242-174">There are two options for using the REST API:</span></span>

- <span data-ttu-id="59242-175">**Microsoft Flow или подобное приложение** можно использовать для автоматического запуска события.</span><span class="sxs-lookup"><span data-stu-id="59242-175">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically. Microsoft Flow is an orchestrator for connecting to other systems. Using Microsoft Flow does not require a custom solution.</span></span> <span data-ttu-id="59242-176">Microsoft Flow является оркестратором подключения к другим системам.</span><span class="sxs-lookup"><span data-stu-id="59242-176">Microsoft Flow is an orchestrator for connecting to other systems.</span></span> <span data-ttu-id="59242-177">Использование Microsoft Flow не требует настраиваемого решения.</span><span class="sxs-lookup"><span data-stu-id="59242-177">Using Microsoft Flow doesn't require a custom solution.</span></span>

- <span data-ttu-id="59242-178">**PowerShell или HTTP-клиент для вызова REST API**. Используйте PowerShell (версии 6 или выше) для вызова REST API Microsoft 365, чтобы создать события.</span><span class="sxs-lookup"><span data-stu-id="59242-178">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="59242-179">Rest API — это конечная точка службы, поддерживающая наборы операций HTTP (методов), которые обеспечивают создание / получение / обновление / удаление доступа к ресурсам службы.</span><span class="sxs-lookup"><span data-stu-id="59242-179">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="59242-180">Дополнительные сведения см. в статье [Компоненты запросов и ответов REST API](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="59242-180">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="59242-181">В этом случае с помощью REST API Microsoft 365 можно создавать и получать события, используя операции (методы) POST и GET.</span><span class="sxs-lookup"><span data-stu-id="59242-181">In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="59242-182">Примеры сценариев</span><span class="sxs-lookup"><span data-stu-id="59242-182">Example scenarios</span></span>

<span data-ttu-id="59242-183">Давайте рассмотрим следующие сценарии.</span><span class="sxs-lookup"><span data-stu-id="59242-183">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="59242-184">Сценарий 1. Сотрудники увольняются из организации</span><span class="sxs-lookup"><span data-stu-id="59242-184">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="59242-185">В организации создается и хранится множество документов, связанных с сотрудниками, для каждого сотрудника.</span><span class="sxs-lookup"><span data-stu-id="59242-185">An organization creates and stores numerous employee-related documents per employee.</span></span> <span data-ttu-id="59242-186">Эти документы управляются и сохраняются в течение работы в организации каждого сотрудника.</span><span class="sxs-lookup"><span data-stu-id="59242-186">These documents are managed and retained during the employment of each employee.</span></span> <span data-ttu-id="59242-187">Тем не менее, когда работник покидает организацию или в случае его увольнения, организация обязана в соответствии с требованиями законодательства и бизнеса сохранять документы этого работника в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="59242-187">An organization creates and stores numerous employee related documents per employee. These documents are managed and retained during the employment of each employee. However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="59242-188">Если из организации ежедневно увольняется несколько сотрудников, необходимо запускать счетчики хранения сотен или даже тысяч документов каждый день.</span><span class="sxs-lookup"><span data-stu-id="59242-188">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="59242-189">Кроме того, для каждого сотрудника период хранения рассчитывается на основе типа записи сотрудника (дата увольнения сотрудника + количество дней, месяцев или лет).</span><span class="sxs-lookup"><span data-stu-id="59242-189">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months or years based on the type of the employee record. For example, worker’s compensation of the employee vs benefits filings of the same employee may need different retention.</span></span> <span data-ttu-id="59242-190">Например, у документов о зарплате и документов о премии одного и того же сотрудника могут быть разные периоды хранения.</span><span class="sxs-lookup"><span data-stu-id="59242-190">For example, worker’s compensation of the employee vs. benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="59242-191">На схеме далее показано, как может существовать несколько меток, связанных с одним событием.</span><span class="sxs-lookup"><span data-stu-id="59242-191">The diagram below shows how there can be multiple labels that are associated with a single event.</span></span> <span data-ttu-id="59242-192">Здесь все файлы под меткой “Компенсации работника” и все файлы под меткой “Льготы сотрудников” связаны с одним событием — уход сотрудника из организации.</span><span class="sxs-lookup"><span data-stu-id="59242-192">Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event, which is the employee leaving the organization.</span></span> <span data-ttu-id="59242-193">Каждый из этих различных файлов имеет различные счетчики хранения.</span><span class="sxs-lookup"><span data-stu-id="59242-193">Each of these different files has different retention clocks.</span></span> <span data-ttu-id="59242-194">Таким образом, когда сотрудник покидает организацию, эти файлы под каждой меткой имеют различный срок хранения.</span><span class="sxs-lookup"><span data-stu-id="59242-194">So, when an employee leaves the organization, these files within each label experience a different retention period.</span></span> <span data-ttu-id="59242-195">Запуск всех этих разных счетчиков хранения для каждого типа файла или метки для каждого сотрудника является очень сложной задачей.</span><span class="sxs-lookup"><span data-stu-id="59242-195">Triggering all these different retention clocks for each file type or label for each employee is a very challenging task.</span></span> <span data-ttu-id="59242-196">Представьте, что это необходимо выполнить для нескольких сотрудников.</span><span class="sxs-lookup"><span data-stu-id="59242-196">Imagine doing this for multiple employees.</span></span>

![Схема типов событий, событий и меток](media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="59242-198">Поэтому автоматизированный процесс запуска всех этих различных счетчиков хранения для нескольких сотрудников должен работать быстро, быть безошибочным и очень эффективным.</span><span class="sxs-lookup"><span data-stu-id="59242-198">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free and extremely efficient .</span></span>

<span data-ttu-id="59242-199">**Настройка автоматизированного хранения на основе событий для этого сценария:**</span><span class="sxs-lookup"><span data-stu-id="59242-199">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Схема ролей и действий для сценария, когда сотрудник увольняется из организации](media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="59242-201">Администратор создает папки сотрудников в наборе документов, например "Евгения Артемьева", "Артем Кузнецов".</span><span class="sxs-lookup"><span data-stu-id="59242-201">Admin c reates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="59242-202">Администратор добавляет в каждую папку файлы сотрудников, например с данными о премиях и зарплате.</span><span class="sxs-lookup"><span data-stu-id="59242-202">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder</span></span>

  - <span data-ttu-id="59242-203">Администратор назначает идентификатор ресурса для каждой папки сотрудников.</span><span class="sxs-lookup"><span data-stu-id="59242-203">Admin assigns Asset Id to each employee folder.</span></span> 

  - <span data-ttu-id="59242-204">Администратор Центра безопасности и соответствия требованиям выполняет вход в Центр безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="59242-204">SCC Admin logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="59242-205">Администратор безопасности и соответствия требованиям создает типы событий, связанные с сотрудником, например "Увольнение сотрудника" и "Прием сотрудника на работу".</span><span class="sxs-lookup"><span data-stu-id="59242-205">SCC Admin creates employee related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="59242-206">Администратор безопасности и соответствия требованиям создает метку "Хранение для сотрудника".</span><span class="sxs-lookup"><span data-stu-id="59242-206">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="59242-207">Эта метка "Хранение для сотрудника" публикуется и вручную или автоматически применяется к файлам сотрудника в SharePoint</span><span class="sxs-lookup"><span data-stu-id="59242-207">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint</span></span>

  - <span data-ttu-id="59242-208">Система управления отдела кадров, например Workday, может работать совместно с Microsoft Flow для периодического управления файлами сотрудников</span><span class="sxs-lookup"><span data-stu-id="59242-208">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files</span></span>

  - <span data-ttu-id="59242-209">Если сотрудник увольняется из организации, Flow активирует REST API хранения на основе событий M365, который запустит счетчик хранения для файлов определенного сотрудника.</span><span class="sxs-lookup"><span data-stu-id="59242-209">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="59242-210">Использование Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="59242-210">Using Microsoft Flow</span></span>

<span data-ttu-id="59242-211">Шаг 1. Создайте процесс создания события с помощью REST API Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="59242-211">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Использование Flow для создания события](media/automate-event-driven-retention-flow-1.png)

![Использование Flow для вызова REST API](media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="59242-214">Создание события</span><span class="sxs-lookup"><span data-stu-id="59242-214">Create an event</span></span>

<span data-ttu-id="59242-215">Пример кода для вызова REST API</span><span class="sxs-lookup"><span data-stu-id="59242-215">Sample code to call the REST API</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="59242-216">Метод</span><span class="sxs-lookup"><span data-stu-id="59242-216">Method</span></span></th>
<th><span data-ttu-id="59242-217">POST</span><span class="sxs-lookup"><span data-stu-id="59242-217">POST</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="59242-218">URL-адрес</span><span class="sxs-lookup"><span data-stu-id="59242-218">URL</span></span></td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="59242-219">Заголовки</span><span class="sxs-lookup"><span data-stu-id="59242-219">Headers</span></span></td>
<td><span data-ttu-id="59242-220">Content-Type</span><span class="sxs-lookup"><span data-stu-id="59242-220">Content-Type</span></span></td>
<td><span data-ttu-id="59242-221">приложение/atom+xml</span><span class="sxs-lookup"><span data-stu-id="59242-221">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="59242-222">Основной текст</span><span class="sxs-lookup"><span data-stu-id="59242-222">Body</span></span></td>
<td><p><span data-ttu-id="59242-223">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-223">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="59242-224">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="59242-224">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="59242-225">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="59242-225">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="59242-226">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-226">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="59242-227">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-227">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="59242-228">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-228">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="59242-229">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-229">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="59242-230">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-230">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="59242-231">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-231">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="59242-232">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-232">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="59242-233">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-233">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="59242-234">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-234">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span></span></p>
<p><span data-ttu-id="59242-235">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-235">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="59242-236">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-236">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="59242-237">&lt;/entry&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-237">&lt;/entry&gt;</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="59242-238">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="59242-238">Authentication</span></span></td>
<td><span data-ttu-id="59242-239">Базовая</span><span class="sxs-lookup"><span data-stu-id="59242-239">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="59242-240">Имя пользователя</span><span class="sxs-lookup"><span data-stu-id="59242-240">Username</span></span></td>
<td><span data-ttu-id="59242-241">"Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="59242-241">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="59242-242">Пароль</span><span class="sxs-lookup"><span data-stu-id="59242-242">Password</span></span></td>
<td><span data-ttu-id="59242-243">"Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="59242-243">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a><span data-ttu-id="59242-244">Доступные параметры</span><span class="sxs-lookup"><span data-stu-id="59242-244">Available parameters</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="59242-245"><strong>Параметры</strong></span><span class="sxs-lookup"><span data-stu-id="59242-245"><strong>Parameters</strong></span></span></th>
<th><span data-ttu-id="59242-246"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="59242-246"><strong>Description</strong></span></span></th>
<th><span data-ttu-id="59242-247"><strong>Примечания</strong></span><span class="sxs-lookup"><span data-stu-id="59242-247"><strong>Notes</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="59242-248">&lt;d:Name&gt;&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-248">&lt;d:Name&gt;&lt;/d:Name&gt;</span></span></td>
<td><span data-ttu-id="59242-249">Указание уникального имени события.</span><span class="sxs-lookup"><span data-stu-id="59242-249">Provide a unique name for the event,</span></span></td>
<td><span data-ttu-id="59242-p121">Не может содержать начальные и конечные пробелы и следующие символы: % \* \ &amp; &lt; &gt; | # ? , : ;</span><span class="sxs-lookup"><span data-stu-id="59242-p121">Cannot contain trailing spaces, and the following characters: % \* \ &amp; &lt; &gt; | # ? , : ;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="59242-252">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-252">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span></span></td>
<td><span data-ttu-id="59242-253">Введите название типа события (или Guid).</span><span class="sxs-lookup"><span data-stu-id="59242-253">Enter event type name (or Guid),</span></span></td>
<td><span data-ttu-id="59242-p122">Пример: "Увольнение сотрудника". Тип события должен быть связан с меткой хранения.</span><span class="sxs-lookup"><span data-stu-id="59242-p122">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="59242-256">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-256">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span></span></td>
<td><span data-ttu-id="59242-257">Введите "ComplianceAssetId:" + код сотрудника</span><span class="sxs-lookup"><span data-stu-id="59242-257">Enter “ComplianceAssetId:” + employee Id</span></span></td>
<td><span data-ttu-id="59242-258">Пример: &quot;ComplianceAssetId:12345&quot;</span><span class="sxs-lookup"><span data-stu-id="59242-258">Example:&quot;ComplianceAssetId:12345&quot;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="59242-259">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-259">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span></span></td>
<td><span data-ttu-id="59242-260">Дата и время события</span><span class="sxs-lookup"><span data-stu-id="59242-260">Event Date and Time</span></span></td>
<td><p><span data-ttu-id="59242-261">Формат: ГГГГ-ММ-ДДTчч:мм:ссZ. Пример:</span><span class="sxs-lookup"><span data-stu-id="59242-261">Format: yyyy-MM-ddTHH:mm:ssZ, Example:</span></span></p>
<p><span data-ttu-id="59242-262">2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="59242-262">2018-12-01T00:00:00Z</span></span></p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="59242-263">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="59242-263">Response codes</span></span>

| <span data-ttu-id="59242-264">**Код ответа**</span><span class="sxs-lookup"><span data-stu-id="59242-264">**Response Code**</span></span> | <span data-ttu-id="59242-265">**Описание**</span><span class="sxs-lookup"><span data-stu-id="59242-265">**Description**</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="59242-266">302</span><span class="sxs-lookup"><span data-stu-id="59242-266">302 seconds</span></span>               | <span data-ttu-id="59242-267">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="59242-267">Redirect</span></span>              |
| <span data-ttu-id="59242-268">201</span><span class="sxs-lookup"><span data-stu-id="59242-268">201</span></span>               | <span data-ttu-id="59242-269">Создано</span><span class="sxs-lookup"><span data-stu-id="59242-269">Created</span></span>               |
| <span data-ttu-id="59242-270">403</span><span class="sxs-lookup"><span data-stu-id="59242-270">403 Forbidden</span></span>               | <span data-ttu-id="59242-271">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="59242-271">Authorization Failed</span></span>  |
| <span data-ttu-id="59242-272">401</span><span class="sxs-lookup"><span data-stu-id="59242-272">401</span></span>               | <span data-ttu-id="59242-273">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="59242-273">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="59242-274">Получение событий на основе диапазона времени</span><span class="sxs-lookup"><span data-stu-id="59242-274">Get Events based on time range</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="59242-275">Метод</span><span class="sxs-lookup"><span data-stu-id="59242-275">Method</span></span></th>
<th><span data-ttu-id="59242-276">GET</span><span class="sxs-lookup"><span data-stu-id="59242-276">GET</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="59242-277">URL-адрес</span><span class="sxs-lookup"><span data-stu-id="59242-277">URL</span></span></td>
<td><ol start="4" type="1">
<li><p><span data-ttu-id="59242-278">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span><span class="sxs-lookup"><span data-stu-id="59242-278">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span></span></p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="59242-279">Заголовки</span><span class="sxs-lookup"><span data-stu-id="59242-279">Headers</span></span></td>
<td><span data-ttu-id="59242-280">Content-Type</span><span class="sxs-lookup"><span data-stu-id="59242-280">Content-Type</span></span></td>
<td><span data-ttu-id="59242-281">приложение/atom+xml</span><span class="sxs-lookup"><span data-stu-id="59242-281">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="59242-282">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="59242-282">Authentication</span></span></td>
<td><span data-ttu-id="59242-283">Базовая</span><span class="sxs-lookup"><span data-stu-id="59242-283">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="59242-284">Имя пользователя</span><span class="sxs-lookup"><span data-stu-id="59242-284">Username</span></span></td>
<td><span data-ttu-id="59242-285">"Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="59242-285">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="59242-286">Пароль</span><span class="sxs-lookup"><span data-stu-id="59242-286">Password</span></span></td>
<td><span data-ttu-id="59242-287">"Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="59242-287">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="59242-288">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="59242-288">Response codes</span></span>

| <span data-ttu-id="59242-289">**Код ответа**</span><span class="sxs-lookup"><span data-stu-id="59242-289">**Response Code**</span></span> | <span data-ttu-id="59242-290">**Описание**</span><span class="sxs-lookup"><span data-stu-id="59242-290">**Description**</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="59242-291">200</span><span class="sxs-lookup"><span data-stu-id="59242-291">200 OK</span></span>               | <span data-ttu-id="59242-292">Все в порядке, список событий в формате atom+xml</span><span class="sxs-lookup"><span data-stu-id="59242-292">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="59242-293">404</span><span class="sxs-lookup"><span data-stu-id="59242-293">404 errors</span></span>               | <span data-ttu-id="59242-294">Не найдено</span><span class="sxs-lookup"><span data-stu-id="59242-294">Not found</span></span>                         |
| <span data-ttu-id="59242-295">302</span><span class="sxs-lookup"><span data-stu-id="59242-295">302 seconds</span></span>               | <span data-ttu-id="59242-296">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="59242-296">Redirect</span></span>                          |
| <span data-ttu-id="59242-297">401</span><span class="sxs-lookup"><span data-stu-id="59242-297">401</span></span>               | <span data-ttu-id="59242-298">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="59242-298">Authorization Failed</span></span>              |
| <span data-ttu-id="59242-299">403</span><span class="sxs-lookup"><span data-stu-id="59242-299">403 Forbidden</span></span>               | <span data-ttu-id="59242-300">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="59242-300">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="59242-301">Получение события по идентификатору</span><span class="sxs-lookup"><span data-stu-id="59242-301">Get an event by ID</span></span>

| <span data-ttu-id="59242-302">Метод</span><span class="sxs-lookup"><span data-stu-id="59242-302">Method</span></span>         | <span data-ttu-id="59242-303">GET</span><span class="sxs-lookup"><span data-stu-id="59242-303">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="59242-304">URL-адрес</span><span class="sxs-lookup"><span data-stu-id="59242-304">URL</span></span>            | <span data-ttu-id="59242-305">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="59242-305">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="59242-306">Заголовок</span><span class="sxs-lookup"><span data-stu-id="59242-306">Header</span></span>         | <span data-ttu-id="59242-307">Content-Type</span><span class="sxs-lookup"><span data-stu-id="59242-307">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="59242-308">приложение/atom+xml</span><span class="sxs-lookup"><span data-stu-id="59242-308">application/atom+xml</span></span> |
| <span data-ttu-id="59242-309">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="59242-309">Authentication</span></span> | <span data-ttu-id="59242-310">Базовая</span><span class="sxs-lookup"><span data-stu-id="59242-310">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="59242-311">Имя пользователя</span><span class="sxs-lookup"><span data-stu-id="59242-311">Username</span></span>       | <span data-ttu-id="59242-312">"Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="59242-312">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="59242-313">Пароль</span><span class="sxs-lookup"><span data-stu-id="59242-313">Password</span></span>       | <span data-ttu-id="59242-314">"Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="59242-314">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="59242-315">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="59242-315">Response codes</span></span>

| <span data-ttu-id="59242-316">**Код ответа**</span><span class="sxs-lookup"><span data-stu-id="59242-316">**Response Code**</span></span> | <span data-ttu-id="59242-317">**Описание**</span><span class="sxs-lookup"><span data-stu-id="59242-317">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="59242-318">200</span><span class="sxs-lookup"><span data-stu-id="59242-318">200 OK</span></span>               | <span data-ttu-id="59242-319">Все в порядке, текст ответа содержит событие в формате atom+xml</span><span class="sxs-lookup"><span data-stu-id="59242-319">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="59242-320">404</span><span class="sxs-lookup"><span data-stu-id="59242-320">404 errors</span></span>               | <span data-ttu-id="59242-321">Не найдено</span><span class="sxs-lookup"><span data-stu-id="59242-321">Not found</span></span>                                            |
| <span data-ttu-id="59242-322">302</span><span class="sxs-lookup"><span data-stu-id="59242-322">302 seconds</span></span>               | <span data-ttu-id="59242-323">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="59242-323">Redirect</span></span>                                             |
| <span data-ttu-id="59242-324">401</span><span class="sxs-lookup"><span data-stu-id="59242-324">401</span></span>               | <span data-ttu-id="59242-325">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="59242-325">Authorization Failed</span></span>                                 |
| <span data-ttu-id="59242-326">403</span><span class="sxs-lookup"><span data-stu-id="59242-326">403 Forbidden</span></span>               | <span data-ttu-id="59242-327">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="59242-327">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="59242-328">Получение события по имени</span><span class="sxs-lookup"><span data-stu-id="59242-328">Get an event by name</span></span>

| <span data-ttu-id="59242-329">Метод</span><span class="sxs-lookup"><span data-stu-id="59242-329">Method</span></span>         | <span data-ttu-id="59242-330">GET</span><span class="sxs-lookup"><span data-stu-id="59242-330">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="59242-331">URL-адрес</span><span class="sxs-lookup"><span data-stu-id="59242-331">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="59242-332">Заголовки</span><span class="sxs-lookup"><span data-stu-id="59242-332">Headers</span></span>        | <span data-ttu-id="59242-333">Content-Type</span><span class="sxs-lookup"><span data-stu-id="59242-333">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="59242-334">приложение/atom+xml</span><span class="sxs-lookup"><span data-stu-id="59242-334">application/atom+xml</span></span> |
| <span data-ttu-id="59242-335">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="59242-335">Authentication</span></span> | <span data-ttu-id="59242-336">Базовая</span><span class="sxs-lookup"><span data-stu-id="59242-336">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="59242-337">Имя пользователя</span><span class="sxs-lookup"><span data-stu-id="59242-337">Username</span></span>       | <span data-ttu-id="59242-338">"Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="59242-338">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="59242-339">Пароль</span><span class="sxs-lookup"><span data-stu-id="59242-339">Password</span></span>       | <span data-ttu-id="59242-340">"Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="59242-340">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="59242-341">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="59242-341">Response codes</span></span>

| <span data-ttu-id="59242-342">**Код ответа**</span><span class="sxs-lookup"><span data-stu-id="59242-342">**Response Code**</span></span> | <span data-ttu-id="59242-343">**Описание**</span><span class="sxs-lookup"><span data-stu-id="59242-343">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="59242-344">200</span><span class="sxs-lookup"><span data-stu-id="59242-344">200 OK</span></span>               | <span data-ttu-id="59242-345">Все в порядке, текст ответа содержит событие в формате atom+xml</span><span class="sxs-lookup"><span data-stu-id="59242-345">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="59242-346">404</span><span class="sxs-lookup"><span data-stu-id="59242-346">404 errors</span></span>               | <span data-ttu-id="59242-347">Не найдено</span><span class="sxs-lookup"><span data-stu-id="59242-347">Not found</span></span>                                            |
| <span data-ttu-id="59242-348">302</span><span class="sxs-lookup"><span data-stu-id="59242-348">302 seconds</span></span>               | <span data-ttu-id="59242-349">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="59242-349">Redirect</span></span>                                             |
| <span data-ttu-id="59242-350">401</span><span class="sxs-lookup"><span data-stu-id="59242-350">401</span></span>               | <span data-ttu-id="59242-351">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="59242-351">Authorization Failed</span></span>                                 |
| <span data-ttu-id="59242-352">403</span><span class="sxs-lookup"><span data-stu-id="59242-352">403 Forbidden</span></span>               | <span data-ttu-id="59242-353">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="59242-353">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="59242-354">Использование PowerShell (версии 6 или выше) или любого HTTP-клиента</span><span class="sxs-lookup"><span data-stu-id="59242-354">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="59242-355">Шаг 1. Подключитесь к PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59242-355">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="59242-356">Шаг 2. Запустите указанный ниже сценарий.</span><span class="sxs-lookup"><span data-stu-id="59242-356">Step 2: Run the following script.</span></span>

<table>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59242-357">param([string]$baseUri)</span><span class="sxs-lookup"><span data-stu-id="59242-357">param([string]$baseUri)</span></span></p>
<p><span data-ttu-id="59242-358">$userName = &quot;UserName&quot;</span><span class="sxs-lookup"><span data-stu-id="59242-358">$userName = &quot;UserName&quot;</span></span></p>
<p><span data-ttu-id="59242-359">$password = &quot;Password&quot;</span><span class="sxs-lookup"><span data-stu-id="59242-359">$password = &quot;Password&quot;</span></span></p>
<p><span data-ttu-id="59242-360">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span><span class="sxs-lookup"><span data-stu-id="59242-360">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span></span></p>
<p><span data-ttu-id="59242-361">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span><span class="sxs-lookup"><span data-stu-id="59242-361">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span></span></p>
<p><span data-ttu-id="59242-362">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span><span class="sxs-lookup"><span data-stu-id="59242-362">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span></span></p>
<p><span data-ttu-id="59242-363">Write-Host &quot;Start to create an event with name: $EventName&quot;</span><span class="sxs-lookup"><span data-stu-id="59242-363">Write-Host &quot;Start to create an event with name: $EventName&quot;</span></span></p>
<p><span data-ttu-id="59242-364">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-364">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="59242-365">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="59242-365">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="59242-366">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="59242-366">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="59242-367">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-367">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="59242-368">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-368">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="59242-369">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-369">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="59242-370">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-370">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="59242-371">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-371">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="59242-372">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-372">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="59242-373">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-373">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="59242-374">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-374">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="59242-375">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-375">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="59242-376">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="59242-376">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="59242-377">&lt;/entry&gt;&quot;</span><span class="sxs-lookup"><span data-stu-id="59242-377">&lt;/entry&gt;&quot;</span></span></p>
<p><span data-ttu-id="59242-378">$event = $null</span><span class="sxs-lookup"><span data-stu-id="59242-378">$event = $null</span></span></p>
<p><span data-ttu-id="59242-379">try</span><span class="sxs-lookup"><span data-stu-id="59242-379">try</span></span></p>
<p><span data-ttu-id="59242-380">{</span><span class="sxs-lookup"><span data-stu-id="59242-380"></span></span></p>
<p><span data-ttu-id="59242-381">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="59242-381">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="59242-382">}</span><span class="sxs-lookup"><span data-stu-id="59242-382"></span></span></p>
<p><span data-ttu-id="59242-383">catch</span><span class="sxs-lookup"><span data-stu-id="59242-383">catch</span></span></p>
<p><span data-ttu-id="59242-384">{</span><span class="sxs-lookup"><span data-stu-id="59242-384"></span></span></p>
<p><span data-ttu-id="59242-385">$response = $_.Exception.Response</span><span class="sxs-lookup"><span data-stu-id="59242-385">$response = $_.Exception.Response</span></span></p>
<p><span data-ttu-id="59242-386">if($response.StatusCode -eq &quot;Redirect&quot;)</span><span class="sxs-lookup"><span data-stu-id="59242-386">if($response.StatusCode -eq &quot;Redirect&quot;)</span></span></p>
<p><span data-ttu-id="59242-387">{</span><span class="sxs-lookup"><span data-stu-id="59242-387"></span></span></p>
<p><span data-ttu-id="59242-388">$url = $response.Headers.Location</span><span class="sxs-lookup"><span data-stu-id="59242-388">$url = $response.Headers.Location</span></span></p>
<p><span data-ttu-id="59242-389">Write-Host &quot;redirected to $url&quot;</span><span class="sxs-lookup"><span data-stu-id="59242-389">Write-Host &quot;redirected to $url&quot;</span></span></p>
<p><span data-ttu-id="59242-390">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="59242-390">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="59242-391">}</span><span class="sxs-lookup"><span data-stu-id="59242-391"></span></span></p>
<p><span data-ttu-id="59242-392">}</span><span class="sxs-lookup"><span data-stu-id="59242-392"></span></span></p>
<p><span data-ttu-id="59242-393">$event | fl \*</span><span class="sxs-lookup"><span data-stu-id="59242-393">$event | fl \*</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="59242-394">Проверка результатов обоих вариантов</span><span class="sxs-lookup"><span data-stu-id="59242-394">Verify the outcome in both options</span></span>

<span data-ttu-id="59242-395">Шаг 1. Перейдите в Центр безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="59242-395">Step 1: Go to Security & Compliance Center</span></span>

<span data-ttu-id="59242-396">Шаг 2. Выберите пункт **События** в разделе **Управление данными**.</span><span class="sxs-lookup"><span data-stu-id="59242-396">Step 2: Click on Events under Data Governance</span></span>

<span data-ttu-id="59242-397">Шаг 3. Убедитесь, что событие создано.</span><span class="sxs-lookup"><span data-stu-id="59242-397">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="59242-398">Аналогичным образом описанные выше варианты автоматизации хранения на основе событий можно использовать и для следующих сценариев.</span><span class="sxs-lookup"><span data-stu-id="59242-398">Similarly, the above options to automate event based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="59242-399">Сценарий 2. Окончание действия договоров</span><span class="sxs-lookup"><span data-stu-id="59242-399">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="59242-400">Организация может иметь несколько записей для одного договора с клиентами, поставщиками и партнерами.</span><span class="sxs-lookup"><span data-stu-id="59242-400">An organization can have multiple records for a single contract with customers, vendors, and partners.</span></span> <span data-ttu-id="59242-401">Эти документы можно хранить в библиотеке документов, например в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="59242-401">These documents can reside in a document library like SharePoint.</span></span> <span data-ttu-id="59242-402">Окончание договора определяет начало срока хранения документов, связанных с договором.</span><span class="sxs-lookup"><span data-stu-id="59242-402">The end of a contract determines the start of the retention period of the documents associated with the contract.</span></span> <span data-ttu-id="59242-403">Например, все записи, связанные с договорами, нужно хранить в течение пяти лет с момента истечения срока действия договора.</span><span class="sxs-lookup"><span data-stu-id="59242-403">Contract expiration Suppose that all records related to contracts need to be retained for five years from the time the contract expires. The event that triggers the five-year retention period is the expiration of the contract.</span></span> <span data-ttu-id="59242-404">Событием, активирующим пятилетнее хранение, будет окончание срока действия договора.</span><span class="sxs-lookup"><span data-stu-id="59242-404">The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="59242-405">Система управления отношениями с клиентами может работать совместно с Microsoft 365 и активировать хранение документов договора.</span><span class="sxs-lookup"><span data-stu-id="59242-405">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents</span></span>

<span data-ttu-id="59242-406">**Настройка автоматизированного хранения на основе событий для этого сценария:**</span><span class="sxs-lookup"><span data-stu-id="59242-406">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Схема ролей и задач для сценария окончания действия договора](media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="59242-408">Администратор создает библиотеку SharePoint с различными папками для каждого типа договора.</span><span class="sxs-lookup"><span data-stu-id="59242-408">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="59242-409">Администратор добавляет файлы договора, например лицензионные соглашения, договоры о разработке, в папку каждого договора.</span><span class="sxs-lookup"><span data-stu-id="59242-409">Admin adds contract files such as License Contracts, Development Contracts to each contract folder</span></span>

  - <span data-ttu-id="59242-410">Администратор назначает идентификатор ресурса для каждой папки договора.</span><span class="sxs-lookup"><span data-stu-id="59242-410">Admin assigns Asset Id to each contract folder</span></span>

  - <span data-ttu-id="59242-411">Администратор Центра безопасности и соответствия требованиям выполняет вход в Центр безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="59242-411">SCC Admin logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="59242-412">Администратор безопасности и соответствия требованиям создает типы событий, связанные с договором, например "Создание договора" и "Завершение действия договора".</span><span class="sxs-lookup"><span data-stu-id="59242-412">SCC Admin creates contract related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="59242-413">Администратор безопасности и соответствия требованиям создает метку "Завершение действия договора".</span><span class="sxs-lookup"><span data-stu-id="59242-413">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="59242-414">Эта метка "Завершение действия договора" публикуется и вручную или автоматически применяется к файлам договора в SharePoint</span><span class="sxs-lookup"><span data-stu-id="59242-414">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint</span></span>

  - <span data-ttu-id="59242-415">Система управления договорами может работать совместно с Microsoft Flow или аналогичным приложением для периодического управления файлами договоров.</span><span class="sxs-lookup"><span data-stu-id="59242-415">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files</span></span>

  - <span data-ttu-id="59242-416">Если срок действия договора завершается, Microsoft Flow активирует REST API хранения на основе событий M365, который запустит счетчик хранения для файлов определенного договора.</span><span class="sxs-lookup"><span data-stu-id="59242-416">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="59242-417">Сценарий 3. Прекращение производства продукта</span><span class="sxs-lookup"><span data-stu-id="59242-417">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="59242-p124">Производственная компания, которая изготавливает различные линейки продуктов, создает множество документов с техническими характеристиками производства и ценами. Если продукт перестает производится, все технические характеристики и документы, связанные с этим продуктом, следует хранить в течение определенного периода времени после окончания существования продукта.</span><span class="sxs-lookup"><span data-stu-id="59242-p124">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="59242-420">Система планирования ресурсов предприятия (ERP) может работать совместно с Microsoft 365 и Microsoft Flow для активации хранения.</span><span class="sxs-lookup"><span data-stu-id="59242-420">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="59242-421">**Настройка автоматизированного хранения на основе событий для этого сценария:**</span><span class="sxs-lookup"><span data-stu-id="59242-421">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Схема ролей и задач для сценария жизненного цикла продукта](media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="59242-423">Администратор создает папки продуктов в наборе документов, например "Продукт 1", "Продукт 2" и т. д.</span><span class="sxs-lookup"><span data-stu-id="59242-423">Admin creates product folders in the Document set such as Product 1, Product 2, etc.</span></span>

  - <span data-ttu-id="59242-424">Администратор добавляет файлы продуктов, например технические характеристики производства, цены продуктов и лицензирование продуктов, в каждую папку продукта.</span><span class="sxs-lookup"><span data-stu-id="59242-424">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder</span></span>

  - <span data-ttu-id="59242-425">Администратор назначает ИД ресурса для каждой папки продукта.</span><span class="sxs-lookup"><span data-stu-id="59242-425">Admin assigns Asset Id to each contract folder</span></span>

  - <span data-ttu-id="59242-426">Администратор Центра безопасности и соответствия требованиям выполняет вход в Центр безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="59242-426">SCC Admin logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="59242-427">Администратор безопасности и соответствия требованиям создает типы событий, связанные с сотрудником, например "Начало производства продукта" и "Окончание производства продукта".</span><span class="sxs-lookup"><span data-stu-id="59242-427">SCC Admin creates employee related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="59242-428">Администратор безопасности и соответствия требованиям создает метку "Окончание производства продукта".</span><span class="sxs-lookup"><span data-stu-id="59242-428">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="59242-429">Эта метка "Завершение изготовление продукта" публикуется и вручную или автоматически применяется к файлам продукта в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="59242-429">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint</span></span>

  - <span data-ttu-id="59242-430">Система ERP может работать совместно с Microsoft Flow или аналогичным приложением для периодического управления файлами продуктов.</span><span class="sxs-lookup"><span data-stu-id="59242-430">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files</span></span>

  - <span data-ttu-id="59242-431">Если изготовление продукта завершается, Microsoft Flow активирует REST API хранения на основе событий M365, который запустит счетчик хранения для файлов определенного продукта.</span><span class="sxs-lookup"><span data-stu-id="59242-431">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="59242-432">Приложение</span><span class="sxs-lookup"><span data-stu-id="59242-432">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="59242-433">Использование результатов ответа 302 (перенаправление) для вызова REST API</span><span class="sxs-lookup"><span data-stu-id="59242-433">Using Redirect 302 response results to call the REST API</span></span>

1. <span data-ttu-id="59242-434">Вызовите событие хранения POST с помощью URL-адреса REST API <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (требуются разрешения глобального администратора)</span><span class="sxs-lookup"><span data-stu-id="59242-434">Invoke a POST retention event call using the REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required)</span></span>

2. <span data-ttu-id="59242-p125">Проверьте код ответа. Если получен код 302, получите URL-адрес перенаправления из свойства Location (Расположение) заголовка ответа</span><span class="sxs-lookup"><span data-stu-id="59242-p125">Check the response code. If it’s 302, then get the redirected URL from Location property of the response header</span></span>

3. <span data-ttu-id="59242-437">Вызовите событие хранения POST еще раз с помощью URL-адреса перенаправления</span><span class="sxs-lookup"><span data-stu-id="59242-437">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="59242-438">Сведения об авторах</span><span class="sxs-lookup"><span data-stu-id="59242-438">Credits</span></span>

<span data-ttu-id="59242-439">Редактор статьи:</span><span class="sxs-lookup"><span data-stu-id="59242-439">This topic was reviewed by:</span></span>

<span data-ttu-id="59242-440">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="59242-440">Antonio Maio</span></span><br/><span data-ttu-id="59242-441">MVP в сфере приложений и служб Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="59242-441">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="59242-442">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="59242-442">Antonio.Maio@Protiviti.com</span></span>
