---
title: Создание меток хранения и их применение в приложениях для сохранения или удаления содержимого
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Инструкции по созданию и публикации меток хранения, которые можно применять в приложениях для сохранения необходимых сведений и удаления ненужных.
ms.openlocfilehash: c327081109fe9d7c4d85d4cf8f01a9e5466432d1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908423"
---
# <a name="create-retention-labels-and-apply-them-in-apps"></a><span data-ttu-id="dc09c-103">Создание меток хранения и их применение в приложениях</span><span class="sxs-lookup"><span data-stu-id="dc09c-103">Create retention labels and apply them in apps</span></span>

><span data-ttu-id="dc09c-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="dc09c-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="dc09c-105">Этот сценарий поддерживается во всех конфигурациях меток хранения, включая [нормативные записи](records-management.md#records).</span><span class="sxs-lookup"><span data-stu-id="dc09c-105">This scenario is supported for all retention label configurations, including [regulatory records](records-management.md#records).</span></span>

<span data-ttu-id="dc09c-106">Используйте сведения ниже, чтобы создать и опубликовать [метки хранения](retention.md), а затем применить их к документам и сообщениям электронной почты.</span><span class="sxs-lookup"><span data-stu-id="dc09c-106">Use the following information to help you create and publish [retention labels](retention.md), and then apply them to documents and emails.</span></span>

<span data-ttu-id="dc09c-107">Метки хранения помогают сохранить необходимые и удалить ненужные данные на уровне элементов (документ или электронное сообщение).</span><span class="sxs-lookup"><span data-stu-id="dc09c-107">Retention labels help you retain what you need and delete what you don't at the item level (document or email).</span></span> <span data-ttu-id="dc09c-108">Они также используются для объявления элемента записью в роли метода [управления записями](records-management.md) для данных Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc09c-108">They are also used to declare an item as a record as part of a [records management](records-management.md) solution for your Microsoft 365 data.</span></span>

<span data-ttu-id="dc09c-109">Предоставление доступа к меткам хранения для сотрудников вашей организации выполняется в два этапа:</span><span class="sxs-lookup"><span data-stu-id="dc09c-109">Making retention labels available to people in your organization so that they can classify content is a two-step process:</span></span> 

1. <span data-ttu-id="dc09c-110">Создание меток хранения.</span><span class="sxs-lookup"><span data-stu-id="dc09c-110">Create the retention labels.</span></span>

2. <span data-ttu-id="dc09c-111">Публикация меток хранения с помощью их политик.</span><span class="sxs-lookup"><span data-stu-id="dc09c-111">Publish the retention labels by using a retention label policy.</span></span>
  
![Схема ролей и задач для меток](../media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)

<span data-ttu-id="dc09c-113">Следуйте инструкциям ниже, чтобы выполнить два действия администратора.</span><span class="sxs-lookup"><span data-stu-id="dc09c-113">Use the following instructions for the two admin steps.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="dc09c-114">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="dc09c-114">Before you begin</span></span>

<span data-ttu-id="dc09c-115">Глобальный администратор организации имеет все разрешения на создание и изменение меток хранения и их политик.</span><span class="sxs-lookup"><span data-stu-id="dc09c-115">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="dc09c-116">Если вы входите не как глобальный администратор, см. раздел [Разрешения, необходимые для создания и управления политиками хранения и метками хранения](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="dc09c-116">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-create-and-publish-retention-labels"></a><span data-ttu-id="dc09c-117">Создание и публикация меток хранения</span><span class="sxs-lookup"><span data-stu-id="dc09c-117">How to create and publish retention labels</span></span>

<span data-ttu-id="dc09c-118">Сначала создайте метки хранения.</span><span class="sxs-lookup"><span data-stu-id="dc09c-118">First, create your retention labels.</span></span> <span data-ttu-id="dc09c-119">Затем создайте политику меток, чтобы сделать их доступными для приложений.</span><span class="sxs-lookup"><span data-stu-id="dc09c-119">Then create a label policy to make the labels available to apply in apps.</span></span>

<span data-ttu-id="dc09c-120">Место создания и настройки меток хранения, зависит от того, используете ли вы управление записями.</span><span class="sxs-lookup"><span data-stu-id="dc09c-120">Where you create and configure your retention labels depend on whether you're using records management or not.</span></span> <span data-ttu-id="dc09c-121">В обоих случаях доступны соответствующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="dc09c-121">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-retention-labels"></a><span data-ttu-id="dc09c-122">Этап 1. Создание меток хранения</span><span class="sxs-lookup"><span data-stu-id="dc09c-122">Step 1: Create retention labels</span></span>

1. <span data-ttu-id="dc09c-123">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) перейдите в одно из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="dc09c-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="dc09c-124">Если используется управление записями:</span><span class="sxs-lookup"><span data-stu-id="dc09c-124">If you are using records management:</span></span>
        - <span data-ttu-id="dc09c-125">**Решения** > **Управление записями** > вкладка **План хранения** > **+ Создать метку** > **Метка хранения**</span><span class="sxs-lookup"><span data-stu-id="dc09c-125">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="dc09c-126">Если управление записями не используется:</span><span class="sxs-lookup"><span data-stu-id="dc09c-126">If you are not using records management:</span></span>
       - <span data-ttu-id="dc09c-127">**Решения** > **Управление информацией** > вкладка **Метки** > + **Создать метку**</span><span class="sxs-lookup"><span data-stu-id="dc09c-127">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="dc09c-128">Не отображается необходимый параметр?</span><span class="sxs-lookup"><span data-stu-id="dc09c-128">Don't immediately see your option?</span></span> <span data-ttu-id="dc09c-129">Сначала выберите **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="dc09c-129">First select **Show all**.</span></span> 

2. <span data-ttu-id="dc09c-130">Следуйте указаниям мастера.</span><span class="sxs-lookup"><span data-stu-id="dc09c-130">Follow the prompts in the wizard.</span></span> <span data-ttu-id="dc09c-131">Если используется управление записями:</span><span class="sxs-lookup"><span data-stu-id="dc09c-131">If you are using records management:</span></span>
    
    - <span data-ttu-id="dc09c-132">Дополнительные сведения о дескрипторах плана хранения см. в статье [Использование плана хранения для управления метками хранения](file-plan-manager.md).</span><span class="sxs-lookup"><span data-stu-id="dc09c-132">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md).</span></span>
    
    - <span data-ttu-id="dc09c-133">Чтобы использовать метку хранения для объявления элементов записями, нажмите кнопку **Пометить элементы как записи** или **Пометить элементы как нормативные записи**.</span><span class="sxs-lookup"><span data-stu-id="dc09c-133">To use the retention label to declare records, select **Mark items as records**, or **Mark items as regulatory records**.</span></span> <span data-ttu-id="dc09c-134">Дополнительные сведения см. в статье [Настройка меток хранения для объявления элементов записями](declare-records.md#configuring-retention-labels-to-declare-records)</span><span class="sxs-lookup"><span data-stu-id="dc09c-134">For more information, see [Configuring retention labels to declare records](declare-records.md#configuring-retention-labels-to-declare-records).</span></span>

3. <span data-ttu-id="dc09c-135">После того как появятся параметры для публикации метки, автоматического применения метки или просто сохранения метки, выберите **Сохранить метку**, и затем нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="dc09c-135">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Just save the label for now**, and then select **Done**.</span></span>

4. <span data-ttu-id="dc09c-136">Повторите эти действия для создания дополнительных меток.</span><span class="sxs-lookup"><span data-stu-id="dc09c-136">Repeat these steps to create more labels.</span></span>

<span data-ttu-id="dc09c-137">Чтобы изменить существующую метку, выберите ее и нажмите **Изменить метку** для запуска Мастера изменения хранения, который позволяет изменить описания меток и любые [доступные параметры](#updating-retention-labels-and-their-policies) на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="dc09c-137">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>

### <a name="step-2-publish-retention-labels"></a><span data-ttu-id="dc09c-138">Этап 2. Публикация меток хранения</span><span class="sxs-lookup"><span data-stu-id="dc09c-138">Step 2: Publish retention labels</span></span>

<span data-ttu-id="dc09c-139">Опубликуйте метки хранения, чтобы пользователи в приложениях, например в SharePoint и Outlook, могли их использовать.</span><span class="sxs-lookup"><span data-stu-id="dc09c-139">Publish retention labels so that they can be applied by users in apps, such as SharePoint and Outlook.</span></span>

1. <span data-ttu-id="dc09c-140">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) перейдите в одно из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="dc09c-140">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="dc09c-141">Если используется управление записями:</span><span class="sxs-lookup"><span data-stu-id="dc09c-141">If you are using records management:</span></span>
        - <span data-ttu-id="dc09c-142">**Решения** > **Управление записями** > > вкладка **Политики меток** > **Опубликовать метки**</span><span class="sxs-lookup"><span data-stu-id="dc09c-142">**Solutions** > **Records management** > > **Label policies** tab > **Publish labels**</span></span>
    
    - <span data-ttu-id="dc09c-143">Если управление записями не используется:</span><span class="sxs-lookup"><span data-stu-id="dc09c-143">If you are not using records management:</span></span>
        - <span data-ttu-id="dc09c-144">**Решения** > **Управление информацией** >  вкладка **Политики меток** > **Опубликовать метки**</span><span class="sxs-lookup"><span data-stu-id="dc09c-144">**Solutions** > **Information governance** > **Label policies** tab > **Publish labels**</span></span>
    
    <span data-ttu-id="dc09c-145">Не отображается необходимый параметр?</span><span class="sxs-lookup"><span data-stu-id="dc09c-145">Don't immediately see your option?</span></span> <span data-ttu-id="dc09c-146">Сначала выберите **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="dc09c-146">First select **Show all**.</span></span> 

2. <span data-ttu-id="dc09c-147">Следуйте указаниям мастера.</span><span class="sxs-lookup"><span data-stu-id="dc09c-147">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="dc09c-148">Сведения о расположениях, поддерживаемых метками хранения, см. в статье [Метки хранения и расположения](retention.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="dc09c-148">For information about the locations supported by retention labels, see [Retention labels and locations](retention.md#retention-label-policies-and-locations).</span></span> 

<span data-ttu-id="dc09c-149">Чтобы изменить существующую политику меток хранения (тип политики **Опубликовать**), выберите ее и нажмите кнопку **Изменить**, чтобы запустить изменение политики хранения.</span><span class="sxs-lookup"><span data-stu-id="dc09c-149">To edit an existing retention label policy (the policy type is **Publish**), select it, and then select the **Edit** option to start the Edit retention policy.</span></span> <span data-ttu-id="dc09c-150">С помощью этого мастера можно изменить описание политики и любые [допустимые параметры](#updating-retention-labels-and-their-policies) из шага 2.</span><span class="sxs-lookup"><span data-stu-id="dc09c-150">This wizard lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


## <a name="when-retention-labels-become-available-to-apply"></a><span data-ttu-id="dc09c-151">Доступность меток хранения для применения</span><span class="sxs-lookup"><span data-stu-id="dc09c-151">When retention labels become available to apply</span></span>

<span data-ttu-id="dc09c-152">Если вы публикуете метки хранения в SharePoint или OneDrive, обычно они отображаются для пользователей в течение одного дня.</span><span class="sxs-lookup"><span data-stu-id="dc09c-152">If you publish retention labels to SharePoint or OneDrive, those labels  typically appear for end users to select within one day.</span></span> <span data-ttu-id="dc09c-153">Однако, это может занять до семи дней.</span><span class="sxs-lookup"><span data-stu-id="dc09c-153">However, allow up to seven days.</span></span> 

<span data-ttu-id="dc09c-154">С момента публикации меток хранения в Exchange может пройти до семи дней, пока они станут видны конечным пользователям. При этом в почтовом ящике должно быть по крайней мере 10 МБ данных.</span><span class="sxs-lookup"><span data-stu-id="dc09c-154">If you publish retention labels to Exchange, it can take up to seven days for those retention labels to appear for end users, and the mailbox must contain at least 10 MB of data.</span></span>

<span data-ttu-id="dc09c-155">Например:</span><span class="sxs-lookup"><span data-stu-id="dc09c-155">For example:</span></span>
  
![Схема, иллюстрирующая, когда вручную применяемые метки вступают в силу](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  

<span data-ttu-id="dc09c-157">Если после семи дней метки не появляются, проверьте **Состояние** политики меток, выбрав ее на странице **Политики меток** в Центре соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="dc09c-157">If the labels don't appear after seven days, check the **Status** of the label policy by selecting it from the **Label policies** page in the compliance center.</span></span> <span data-ttu-id="dc09c-158">Для повторного развертывания политики (для OneDrive) или если отображается состояние **Отключено (ошибка)**, а в сведениях расположений выводится сообщение о том, что развертывание политики (для SharePoint) занимает больше времени, чем ожидалось, попробуйте выполнить команду [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) в PowerShell, чтобы повторно распространить политику:</span><span class="sxs-lookup"><span data-stu-id="dc09c-158">If you see the status of **Off (Error)** and in the details for the locations see a message that it's taking longer than expected to deploy the policy (for SharePoint) or to try redeploying the policy (for OneDrive), try running [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy), a PowerShell command, to retry the policy distribution:</span></span>

1. [<span data-ttu-id="dc09c-159">Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="dc09c-159">Connect to Security & Compliance Center PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell)

2. <span data-ttu-id="dc09c-160">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="dc09c-160">Run the following command:</span></span>
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```

### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="dc09c-161">Проверка состояния меток хранения, опубликованных в Exchange</span><span class="sxs-lookup"><span data-stu-id="dc09c-161">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="dc09c-162">В Exchange Online метки хранения доступны конечным пользователям благодаря процессу, который выполняется каждые семь дней.</span><span class="sxs-lookup"><span data-stu-id="dc09c-162">In Exchange Online, retention labels are made available to end users by a process that runs every seven days.</span></span> <span data-ttu-id="dc09c-163">С помощью PowerShell можно узнать, когда этот процесс запускался в последний раз и, соответственно, когда он будет запущен снова.</span><span class="sxs-lookup"><span data-stu-id="dc09c-163">By using PowerShell, you can see when this process last ran and therefore identify when it will run again.</span></span>
  
1. <span data-ttu-id="dc09c-164">[Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="dc09c-164">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="dc09c-165">Выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="dc09c-165">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}

In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox. If it has not happened since the time you created the policy, the labels are not going to appear. To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.
    
If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).
    

## How to apply published retention labels

Use the following sections to learn how published retention labels can be applied in apps:

- [Manually apply retention labels](#manually-apply-retention-labels)

- [Applying a default retention label to all content in a SharePoint library, folder, or document set](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)

- [Automatically applying a retention label to email by using rules](#automatically-applying-a-retention-label-to-email-by-using-rules)

In addition, when you use [SharePoint Syntex](../contentunderstanding/index.md) and publish retention labels to SharePoint locations, you can [apply a retention label to a document understanding model](../contentunderstanding/apply-a-retention-label-to-a-model.md) so that identified documents are automatically labeled.

After content is labeled, see the following information to understand when the applied label can be removed or changed: [Only one retention label at a time](retention.md#only-one-retention-label-at-a-time).

### Manually apply retention labels 

End users, as well as administrators, can manually apply retention labels from the following locations:  

- Outlook and Outlook on the web
    
- OneDrive
    
- SharePoint
    
- Microsoft 365 groups (both the group site and group mailbox in Outlook on the web)
    
Use the following sections to understand how to apply retention labels. 

#### Applying retention labels in Outlook

To label an item in the Outlook desktop client, select the item. On the **Home** tab on the ribbon, click **Assign Policy**, and then choose the retention label. 
  
![Assign Policy button](../media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
You can also right-click an item, click **Assign Policy** in the context menu, and then choose the retention label. 

After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email has a retention label applied that has an associated retention period, you can see at a glance when the email expires.

##### Applying a default retention label to an Outlook folder

You can apply retention labels to Outlook folders as a default label that can be inherited by messages in that folder. Right-click the folder, select **Properties**, the **Policy** tab, and select the retention label you want to use as that folder's default retention label.

When you use a a standard retention label as your default label for an Outlook folder:
  
- All unlabeled items in the folder have this retention label applied.

- The inheritance flows to any child folders and items inherit the label from their nearest folder.

- Items that are already labeled retain their retention label, unless it was applied by a different default label.

- If you change or remove the default retention label for the folder: Existing retention labels applied to items in that folder are also changed or removed only if those labels were applied by a default label.

- If you move an item with a default retention label from one folder to another folder with a different default retention label: The item gets the new default retention label.

- If you move an item with a default retention label from one folder to another folder with no default retention label: The old default retention label is removed.

When labels are applied that aren't standard retention labels but mark items as [records (or regulatory records)](records-management.md#records), these labels can only be manually changed or removed.

#### Applying retention labels in Outlook on the web

To label an item in Outlook on the web, right-click the item \> **Assign policy** \> choose the retention label. 
  
![Assign policy menu in Outlook on the web](../media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.
  
![Label assigned to email in Outlook on the web](../media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
As with the desktop version of Outlook on the web, you can also apply retention labels to folders. Right-click the folder, select **Assign policy**, and change **Use parent folder policy** to the retention label you want to use as that folder's default retention label.

#### Applying retention labels in OneDrive and SharePoint

To label a document (including OneNote files) in OneDrive or SharePoint, select the item \> in the upper-right corner, choose **Open the details pane**![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Apply retention label** \> choose the retention label. 
  
You can also apply a retention label to a folder or document set, and you can set a [default retention label for a document library](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).
  
![Apply label list for an item in SharePoint](../media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
After a retention label is applied to an item, you can view it in the details pane when that item's selected.
  
![Applied label shown in Details pane](../media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)

For SharePoint, but not OneDrive, you can create a view of the library that contains the **Labels** column or **Item is a Record** column. This view lets you see at a glance the retention labels assigned to all items and which items are records. Note, however, that you can't filter the view by the **Item is a Record** column. For instructions how to add columns, see [Show or hide columns in a list or library](https://support.microsoft.com/en-us/office/show-or-hide-columns-in-a-list-or-library-b820db0d-9e3e-4ff9-8b8b-0b2dbefa87e2).


#### Applying retention labels in Microsoft 365 groups

When you publish retention labels to Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), the retention labels appear in both the group site and group mailbox in Outlook on the web. The experience of applying a retention label to content is identical to that for email and documents.

To retain content for a Microsoft 365 group, use the **Microsoft 365 Groups** location. Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire Exchange location won't include content in Microsoft 365 group mailboxes.

In addition, it's not possible to use the Exchange location to include or exclude a specific group mailbox. Although the Exchange location initially allows a group mailbox to be selected, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.
  
First, create and configure the sensitivity labels that you want to make available for apps and other services. For example, the labels you want users to see and apply from Office apps. 

Then, create one or more label policies that contain the labels and policy settings that you configure. It's the label policy that publishes the labels and settings for your chosen users and locations.

### Applying a default retention label to all content in a SharePoint library, folder, or document set

This method requires retention labels to be published to a retention label policy.

In addition to letting people apply a retention label to individual documents, you can also apply a default retention label to a SharePoint library, folder, or document set. In this scenario, documents in that location can inherit your selected default retention label. Although the same label is applied, each document will be retained and deleted separately, according to the start of the retention period setting in the label. 
  
For a document library, the default label configuration is done on the **Library settings** page for a document library. When you choose the default retention label, you can also choose to apply it to existing items in the library.
  
For example, if you have a retention label for marketing materials, and you know a specific document library contains only that type of content, you can make the **Marketing Materials** retention label the default label for all documents in that library.
  
![Apply label option on library Settings page](../media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)

#### Label behavior when you use a default label for SharePoint

For standard retention labels that you apply as a default retention label to a library, folder, or document set:

- All new, unlabeled items in the container will have this retention label applied.

- For folders, the inheritance flows to any child folders and items inherit the label from their nearest folder.

- If you selected the option to apply the default label to existing items: Items that are already labeled retain their retention label, unless it was applied by a different default label.
    
- If you change the default retention label for the container: Existing retention labels applied to items in that container are changed only if you selected the option to apply the default label to existing items and those labels were applied by a default label.

- If you remove the default retention label for the container: Items retain their labels.
    
- If you move an item with a default retention label applied from one container to another container: The item keeps its existing default retention label, even if the new location has a different default retention label. Only if you then change the default label for this new location can the moved item inherit the default label from its current location.

When labels are applied that aren't standard retention labels but mark items as [records (or regulatory records)](records-management.md#records), these labels can only be manually changed or removed.

### Automatically applying a retention label to email by using rules

In Outlook, you can create rules to apply a retention label.
  
For example, you can create a rule that applies a specific retention label to all messages sent to or from a specific distribution group.
  
To create a rule, right-click an item \> **Rules** \> **Create Rule** \> **Advanced Options** \> **Rules Wizard** \> **apply retention policy**.
  
![Rules wizard with option to apply retention policies](../media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)

Although the UI refers to retention policies, it's your retention labels that display here and can be selected, not your retention policies.

## Updating retention labels and their policies

When you edit a retention label or retention label policy, and the retention label or policy is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.

Some settings can't be changed after the label or policy is created and saved, which include:
- The retention label and policy name, and the retention settings except the retention period. However, you can't change the retention period when the retention period is based on when items were labeled.
- The option to mark items as a record.

### Deleting retention labels

You can delete retention labels that aren't currently included in any retention label policies, that aren't configured for event-based retention, or mark items as regulatory records. The ability to delete retention labels that mark items as records is currently rolling out in preview.

For retention labels that you can delete, if they have been applied to items, the deletion fails and you see a link to content explorer to identify the labeled items.

However, it can take up to two days for content explorer to show the items that are labeled. In this scenario, the retention label might be deleted without showing you the link to content explorer.

## Locking the policy to prevent changes

If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).

## Next steps

Event-based retention is another supported scenario for retention labels. For more information, see the following articles:

- [Start retention when an event occurs](event-driven-retention.md)
- [Automate event-based retention](./event-driven-retention.md#automate-events-by-using-a-rest-api)
- [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md)