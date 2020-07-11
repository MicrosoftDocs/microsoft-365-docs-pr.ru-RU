---
title: Управление надстройками в центре администрирования
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Узнайте, как развертывать надстройки для пользователей и групп в Организации с помощью централизованного развертывания в центре администрирования.
ms.openlocfilehash: caaea8404c099f56704d21684323a4b20e61f52d
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103115"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="c0682-103">Управление надстройками в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="c0682-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c0682-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="c0682-104">The admin center is changing.</span></span> <span data-ttu-id="c0682-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="c0682-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="c0682-106">Надстройки Office помогают настраивать документы и оптимизировать способ доступа к данным в Интернете (см. раздел [Начало работы с надстройкой Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="c0682-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="c0682-107">После того как Администратор развертывает надстройки для пользователей в Организации, администратор может отключить надстройку или включить, изменить, удалить и управлять доступом к надстройкам.</span><span class="sxs-lookup"><span data-stu-id="c0682-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="c0682-108">Дополнительные сведения об установке надстроек из центра администрирования содержатся [в разделе Развертывание надстроек в центре администрирования](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="c0682-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="c0682-109">Состояния надстроек</span><span class="sxs-lookup"><span data-stu-id="c0682-109">Add-in states</span></span>

<span data-ttu-id="c0682-110">Надстройка может находиться в состоянии " **включено** " или " **отключено** ".</span><span class="sxs-lookup"><span data-stu-id="c0682-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="c0682-111">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="c0682-111">**State**</span></span>|<span data-ttu-id="c0682-112">**Механизм перехода**</span><span class="sxs-lookup"><span data-stu-id="c0682-112">**How the state occurs**</span></span>|<span data-ttu-id="c0682-113">**Влияние**</span><span class="sxs-lookup"><span data-stu-id="c0682-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c0682-114">**Active**</span><span class="sxs-lookup"><span data-stu-id="c0682-114">**Active**</span></span>  <br/> |<span data-ttu-id="c0682-115">Администратор отправил надстройку и назначил ее пользователям или группам.</span><span class="sxs-lookup"><span data-stu-id="c0682-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="c0682-116">Пользователи и группы, которым назначена эта надстройка, видят ее в соответствующих клиентах.</span><span class="sxs-lookup"><span data-stu-id="c0682-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="c0682-117">**Отключена**</span><span class="sxs-lookup"><span data-stu-id="c0682-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="c0682-118">Администратор отключил надстройку.</span><span class="sxs-lookup"><span data-stu-id="c0682-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="c0682-119">Пользователи и группы, которым назначена эта надстройка, больше не имеют к ней доступа.</span><span class="sxs-lookup"><span data-stu-id="c0682-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="c0682-120">Если изменить состояние надстройки на "Активна", пользователи и группы снова получат к ней доступ.</span><span class="sxs-lookup"><span data-stu-id="c0682-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="c0682-121">**Deleted**</span><span class="sxs-lookup"><span data-stu-id="c0682-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="c0682-122">Администратор удалил надстройку.</span><span class="sxs-lookup"><span data-stu-id="c0682-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="c0682-123">Пользователи и группы, которым назначена эта надстройка, больше не имеют к ней доступа.</span><span class="sxs-lookup"><span data-stu-id="c0682-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="c0682-124">Рекомендуется удалить надстройку, если она больше не используется.</span><span class="sxs-lookup"><span data-stu-id="c0682-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="c0682-125">Например, отключение надстройки может быть целесообразной, если надстройка используется только в определенное время года.</span><span class="sxs-lookup"><span data-stu-id="c0682-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="c0682-126">Удаление надстройки</span><span class="sxs-lookup"><span data-stu-id="c0682-126">Delete an add-in</span></span>

<span data-ttu-id="c0682-127">Вы также можете удалить развернутую надстройку.</span><span class="sxs-lookup"><span data-stu-id="c0682-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="c0682-128">В центре администрирования откройте страницу " **Параметры**  >  **служб &** надстроек".</span><span class="sxs-lookup"><span data-stu-id="c0682-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="c0682-129">Выберите развернутую надстройку.</span><span class="sxs-lookup"><span data-stu-id="c0682-129">Select the deployed add-in.</span></span>

3. <span data-ttu-id="c0682-130">Нажмите кнопку **удалить надстройку**.</span><span class="sxs-lookup"><span data-stu-id="c0682-130">Click on **Delete Add-In**.</span></span> <span data-ttu-id="c0682-131">Удалите кнопку надстройки в правом нижнем углу.</span><span class="sxs-lookup"><span data-stu-id="c0682-131">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="c0682-132">Проверяйте выбранные параметры и нажмите кнопку **удалить надстройку**.</span><span class="sxs-lookup"><span data-stu-id="c0682-132">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="c0682-133">Изменение доступа к надстройке</span><span class="sxs-lookup"><span data-stu-id="c0682-133">Edit add-in access</span></span>

<span data-ttu-id="c0682-134">После развертывания администраторы также могут управлять доступом пользователей к надстройкам.</span><span class="sxs-lookup"><span data-stu-id="c0682-134">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="c0682-135">В центре администрирования откройте страницу " **Параметры**  >  **служб &** надстроек".</span><span class="sxs-lookup"><span data-stu-id="c0682-135">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="c0682-136">Выберите развернутую надстройку.</span><span class="sxs-lookup"><span data-stu-id="c0682-136">Select the deployed add-in.</span></span>

3. <span data-ttu-id="c0682-137">Щелкните элемент **изменить** в разделе **у кого есть доступ**.</span><span class="sxs-lookup"><span data-stu-id="c0682-137">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="c0682-138">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="c0682-138">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="c0682-139">Запрет загрузки надстроек путем отключения магазина Office между всеми клиентами (кроме Outlook)</span><span class="sxs-lookup"><span data-stu-id="c0682-139">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="c0682-140">Установка надстройки Outlook осуществляется с помощью [другого процесса](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="c0682-140">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="c0682-141">В качестве организации вы можете запретить загрузку новых надстроек Office из магазина Office.</span><span class="sxs-lookup"><span data-stu-id="c0682-141">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="c0682-142">Это можно использовать совместно с централизованным развертыванием, чтобы обеспечить развертывание только утвержденных в Организации надстроек для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c0682-142">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="c0682-143">**Отключение приобретения надстройки**</span><span class="sxs-lookup"><span data-stu-id="c0682-143">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="c0682-144">В центре администрирования перейдите в раздел \*\*Параметры \*\* \> [Услуги&amp;](https://go.microsoft.com/fwlink/p/?linkid=2053743) надстроек.</span><span class="sxs-lookup"><span data-stu-id="c0682-144">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>
    
3. <span data-ttu-id="c0682-145">Выберите **приложения и службы, принадлежащие пользователю**.</span><span class="sxs-lookup"><span data-stu-id="c0682-145">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="c0682-146">Снимите флажок, чтобы предоставить пользователям доступ к магазину Office.</span><span class="sxs-lookup"><span data-stu-id="c0682-146">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="c0682-147">Это предотвратит получение всеми пользователями следующих надстроек из хранилища.</span><span class="sxs-lookup"><span data-stu-id="c0682-147">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="c0682-148">Надстройки для Word, Excel и PowerPoint 2016 из:</span><span class="sxs-lookup"><span data-stu-id="c0682-148">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="c0682-149">Windows</span><span class="sxs-lookup"><span data-stu-id="c0682-149">Windows</span></span>
    
  - <span data-ttu-id="c0682-150">Mac</span><span class="sxs-lookup"><span data-stu-id="c0682-150">Mac</span></span>
    
  - <span data-ttu-id="c0682-151">Office</span><span class="sxs-lookup"><span data-stu-id="c0682-151">Office</span></span>
    
    
- <span data-ttu-id="c0682-152">Ввод в эксплуатацию, начиная с **AppSource**</span><span class="sxs-lookup"><span data-stu-id="c0682-152">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="c0682-153">Надстройки в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c0682-153">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="c0682-154">Пользователь, пытающийся получить доступ к хранилищу, увидит следующее сообщение: **к сожалению, Microsoft 365 настроен для предотвращения индивидуального приобретения надстроек магазина Office.**</span><span class="sxs-lookup"><span data-stu-id="c0682-154">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="c0682-155">Поддержка отключения магазина Office доступна в следующих версиях:</span><span class="sxs-lookup"><span data-stu-id="c0682-155">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="c0682-156">Windows: 16.0.9001, в настоящее время доступен.</span><span class="sxs-lookup"><span data-stu-id="c0682-156">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="c0682-157">Mac: 16.10.18011401 — в настоящее время доступен.</span><span class="sxs-lookup"><span data-stu-id="c0682-157">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="c0682-158">iOS: 2.9.18010804, доступные в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="c0682-158">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="c0682-159">Веб-в настоящее время доступен.</span><span class="sxs-lookup"><span data-stu-id="c0682-159">The web - Currently available.</span></span>
    
<span data-ttu-id="c0682-160">Это не запрещает администратору использовать централизованное развертывание для назначения надстройки из магазина Office.</span><span class="sxs-lookup"><span data-stu-id="c0682-160">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="c0682-161">Чтобы запретить пользователю выполнять вход с помощью учетной записи Майкрософт, можно ограничить вход в систему, чтобы использовать только учетную запись организации.</span><span class="sxs-lookup"><span data-stu-id="c0682-161">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="c0682-162">Дополнительные сведения см. [в статье удостоверение, проверка подлинности и авторизация в Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="c0682-162">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="c0682-163">Дополнительные сведения о работе с надстройками для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="c0682-163">More about the end user experience with add-ins</span></span>

<span data-ttu-id="c0682-164">После развертывания надстройки пользователи могут начать использовать ее в приложениях Office (см. раздел [Начало работы с надстройкой Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="c0682-164">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="c0682-165">Надстройка отображается на всех платформах, поддерживаемых надстройкой.</span><span class="sxs-lookup"><span data-stu-id="c0682-165">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="c0682-166">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span><span class="sxs-lookup"><span data-stu-id="c0682-166">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span></span> <span data-ttu-id="c0682-167">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span><span class="sxs-lookup"><span data-stu-id="c0682-167">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Лента Office с ссылками поиска](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="c0682-169">Если развернутая надстройка не поддерживает команды надстроек или вы хотите просмотреть все развернутые надстройки, вы можете просматривать их **с помощью надстроек**.</span><span class="sxs-lookup"><span data-stu-id="c0682-169">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="c0682-170">В Word 2016, Excel 2016 или PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="c0682-170">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="c0682-171">Выберите **Вставить \> Мои надстройки**.</span><span class="sxs-lookup"><span data-stu-id="c0682-171">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="c0682-172">Откройте вкладку **Управляются администратором** в окне "Надстройки Office".</span><span class="sxs-lookup"><span data-stu-id="c0682-172">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="c0682-173">Дважды щелкните надстройку, которую вы развернули ранее (в данном примере  **Цитаты** ).</span><span class="sxs-lookup"><span data-stu-id="c0682-173">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="c0682-174">![Вкладка "управляемая администратором" на странице "надстройки Office"](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="c0682-174">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="c0682-175">В Outlook</span><span class="sxs-lookup"><span data-stu-id="c0682-175">In Outlook</span></span>

1. <span data-ttu-id="c0682-176">На ленте **Главная** щелкните **получить**надстройки.</span><span class="sxs-lookup"><span data-stu-id="c0682-176">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="c0682-177">![Кнопка "Хранилище" в Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="c0682-177">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="c0682-178">Выберите **Управление, управляемое администратором** , в левой панели навигации.</span><span class="sxs-lookup"><span data-stu-id="c0682-178">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="c0682-179">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c0682-179">Learn more</span></span>

[<span data-ttu-id="c0682-180">Развертывание надстроек в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="c0682-180">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="c0682-181">Получите дополнительные сведения о создании [надстроек Office](https://go.microsoft.com/fwlink/p/?linkid=846362).</span><span class="sxs-lookup"><span data-stu-id="c0682-181">Learn more about creating and building [Office Add-ins](https://go.microsoft.com/fwlink/p/?linkid=846362).</span></span>
  
<span data-ttu-id="c0682-182">[Используйте командлеты PowerShell централизованного развертывания для управления](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)надстройками.</span><span class="sxs-lookup"><span data-stu-id="c0682-182">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="c0682-183">Устранение неполадок: пользователь не видит надстройки</span><span class="sxs-lookup"><span data-stu-id="c0682-183">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="c0682-184">Вспомогательные и приобретение надстроек из Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="c0682-184">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)