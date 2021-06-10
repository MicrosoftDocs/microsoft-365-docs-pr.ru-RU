---
title: Управление надстройками в Центре администрирования
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Узнайте об использовании централизованных надстройок для развертывания надстройок для пользователей и групп в организации.
ms.openlocfilehash: d678755b28daea1578ce2a5d2e387492cf32d368
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636062"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="f786f-103">Управление надстройками в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="f786f-103">Manage add-ins in the admin center</span></span>

<span data-ttu-id="f786f-104">Office надстройки помогут вам персонализировать документы и упростить доступ к информации в Интернете (см. в руб. Начало использования Office [надстройки).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="f786f-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="f786f-105">После развертывания администратором надстройки для пользователей в организации администратор может отключить или включить надстройки, изменить, удалить и управлять доступом к надстройки.</span><span class="sxs-lookup"><span data-stu-id="f786f-105">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="f786f-106">Дополнительные сведения об установке надстройок из центра администрирования см. в дополнительных сведениях о развертывании надстройок [в центре администрирования.](./manage-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="f786f-106">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="f786f-107">Состояния надстроек</span><span class="sxs-lookup"><span data-stu-id="f786f-107">Add-in states</span></span>

<span data-ttu-id="f786f-108">Надстройка может быть в состоянии **On** или **Off.**</span><span class="sxs-lookup"><span data-stu-id="f786f-108">An add-in can be in either the **On** or **Off** state.</span></span>
  
| <span data-ttu-id="f786f-109">Состояние</span><span class="sxs-lookup"><span data-stu-id="f786f-109">State</span></span> | <span data-ttu-id="f786f-110">Причины</span><span class="sxs-lookup"><span data-stu-id="f786f-110">How the state occurs</span></span> | <span data-ttu-id="f786f-111">Влияние</span><span class="sxs-lookup"><span data-stu-id="f786f-111">Impact</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="f786f-112">**Активна**</span><span class="sxs-lookup"><span data-stu-id="f786f-112">**Active**</span></span>  <br/> |<span data-ttu-id="f786f-113">Администратор загрузил надстройки и назначен пользователям или группам.</span><span class="sxs-lookup"><span data-stu-id="f786f-113">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="f786f-114">Пользователи и группы, которым назначена эта надстройка, видят ее в соответствующих клиентах.</span><span class="sxs-lookup"><span data-stu-id="f786f-114">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="f786f-115">**Отключена**</span><span class="sxs-lookup"><span data-stu-id="f786f-115">**Turned off**</span></span>  <br/> |<span data-ttu-id="f786f-116">Администратор отключил надстройку.</span><span class="sxs-lookup"><span data-stu-id="f786f-116">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="f786f-117">Пользователи и группы, которым назначена эта надстройка, больше не имеют к ней доступа.</span><span class="sxs-lookup"><span data-stu-id="f786f-117">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="f786f-118">Если изменить состояние надстройки на "Активна", пользователи и группы снова получат к ней доступ.</span><span class="sxs-lookup"><span data-stu-id="f786f-118">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="f786f-119">**Deleted**</span><span class="sxs-lookup"><span data-stu-id="f786f-119">**Deleted**</span></span>  <br/> |<span data-ttu-id="f786f-120">Администратор удалил надстройку.</span><span class="sxs-lookup"><span data-stu-id="f786f-120">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="f786f-121">Пользователи и группы, которым назначена эта надстройка, больше не имеют к ней доступа.</span><span class="sxs-lookup"><span data-stu-id="f786f-121">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="f786f-122">Если надстройка больше не используется, рассмотрите возможность удаления надстройки.</span><span class="sxs-lookup"><span data-stu-id="f786f-122">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="f786f-123">Например, отключение надстройки может иметь смысл, если надстройка используется только в определенное время года.</span><span class="sxs-lookup"><span data-stu-id="f786f-123">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="f786f-124">Удаление надстройки</span><span class="sxs-lookup"><span data-stu-id="f786f-124">Delete an add-in</span></span>

<span data-ttu-id="f786f-125">Можно также удалить развернутую надстройка.</span><span class="sxs-lookup"><span data-stu-id="f786f-125">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="f786f-126">В центре администрирования перейдите на **страницу Параметры**  >  **services & надстройки.**</span><span class="sxs-lookup"><span data-stu-id="f786f-126">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f786f-127">Центр администрирования обновляется до развертывания с интегрированными приложениями.</span><span class="sxs-lookup"><span data-stu-id="f786f-127">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="f786f-128">Если вы не видите вышеперечисленные действия, перейдите в раздел Централизованное развертывание, **Параметры**  >  **интегрированные приложения.**</span><span class="sxs-lookup"><span data-stu-id="f786f-128">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="f786f-129">В верхней части страницы **Интегрированные приложения** выберите **надстройки.**</span><span class="sxs-lookup"><span data-stu-id="f786f-129">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="f786f-130">Выберите развернутую надстройка.</span><span class="sxs-lookup"><span data-stu-id="f786f-130">Select the deployed add-in.</span></span>

3. <span data-ttu-id="f786f-131">Нажмите **кнопку Удалить надстройки**.</span><span class="sxs-lookup"><span data-stu-id="f786f-131">Click on **Delete Add-In**.</span></span> <span data-ttu-id="f786f-132">Снимите кнопку надстройки в правом нижнем углу.</span><span class="sxs-lookup"><span data-stu-id="f786f-132">Remove the Add-in button on the bottom-right corner.</span></span>

4. <span data-ttu-id="f786f-133">Проверьте выбор и нажмите кнопку **Удалить надстройку**.</span><span class="sxs-lookup"><span data-stu-id="f786f-133">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="f786f-134">Изменение доступа к надстройкам</span><span class="sxs-lookup"><span data-stu-id="f786f-134">Edit add-in access</span></span>

<span data-ttu-id="f786f-135">После развертывания администраторы также могут управлять доступом пользователей к надстройки.</span><span class="sxs-lookup"><span data-stu-id="f786f-135">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="f786f-136">В центре администрирования перейдите на **страницу Параметры**  >  **services & надстройки.**</span><span class="sxs-lookup"><span data-stu-id="f786f-136">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f786f-137">Центр администрирования обновляется до развертывания с интегрированными приложениями.</span><span class="sxs-lookup"><span data-stu-id="f786f-137">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="f786f-138">Если вы не видите вышеперечисленные действия, перейдите в раздел Централизованное развертывание, **Параметры**  >  **интегрированные приложения.**</span><span class="sxs-lookup"><span data-stu-id="f786f-138">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="f786f-139">В верхней части страницы **Интегрированные приложения** выберите **надстройки.**</span><span class="sxs-lookup"><span data-stu-id="f786f-139">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="f786f-140">Выберите развернутую надстройка.</span><span class="sxs-lookup"><span data-stu-id="f786f-140">Select the deployed add-in.</span></span>

3. <span data-ttu-id="f786f-141">Нажмите **кнопку Изменить** в **Кто имеет доступ**.</span><span class="sxs-lookup"><span data-stu-id="f786f-141">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="f786f-142">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="f786f-142">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="f786f-143">Предотвращение скачивания надстройки путем отключения Office магазина для всех клиентов (кроме Outlook)</span><span class="sxs-lookup"><span data-stu-id="f786f-143">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="f786f-144">Outlook установки надстройки управляется другим [процессом.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)</span><span class="sxs-lookup"><span data-stu-id="f786f-144">Outlook add-in installation is managed by a [different process](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span></span>

<span data-ttu-id="f786f-145">Как организация вы можете запретить скачивание новых надстройок Office из Office Store.</span><span class="sxs-lookup"><span data-stu-id="f786f-145">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="f786f-146">Это можно использовать совместно с централизованным развертыванием, чтобы обеспечить развертывание только утвержденных организацией надстройок для пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="f786f-146">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="f786f-147">**Отключение приобретения надстройки**</span><span class="sxs-lookup"><span data-stu-id="f786f-147">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="f786f-148">В центре администрирования перейдите в раздел **Параметры** \> [Услуги&amp;](https://go.microsoft.com/fwlink/p/?linkid=2053743) надстроек.</span><span class="sxs-lookup"><span data-stu-id="f786f-148">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f786f-149">Центр администрирования обновляется до развертывания с интегрированными приложениями.</span><span class="sxs-lookup"><span data-stu-id="f786f-149">The admin center is getting updated to deployment experience with Integrated Apps.</span></span> <span data-ttu-id="f786f-150">Если вы не видите вышеперечисленные действия, перейдите в раздел Централизованное развертывание, **Параметры**  >  **интегрированные приложения.**</span><span class="sxs-lookup"><span data-stu-id="f786f-150">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="f786f-151">В верхней части страницы **Интегрированные приложения** выберите **надстройки.**</span><span class="sxs-lookup"><span data-stu-id="f786f-151">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="f786f-152">Выберите **Приложения и службы пользователей**.</span><span class="sxs-lookup"><span data-stu-id="f786f-152">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="f786f-153">Отмените выбор параметра, разрешающего доступ к магазину Office для пользователей.</span><span class="sxs-lookup"><span data-stu-id="f786f-153">Clear the option to let users access the Office store.</span></span>

    <span data-ttu-id="f786f-154">Это предотвратит получение всеми пользователями следующих надстройок из магазина.</span><span class="sxs-lookup"><span data-stu-id="f786f-154">This will prevent all users from acquiring the following add-ins from the store.</span></span>
      
    - <span data-ttu-id="f786f-155">Надстройки для Word, Excel и PowerPoint 2016 из:</span><span class="sxs-lookup"><span data-stu-id="f786f-155">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
        
      - <span data-ttu-id="f786f-156">Windows</span><span class="sxs-lookup"><span data-stu-id="f786f-156">Windows</span></span>
      - <span data-ttu-id="f786f-157">Mac</span><span class="sxs-lookup"><span data-stu-id="f786f-157">Mac</span></span>
      - <span data-ttu-id="f786f-158">Office</span><span class="sxs-lookup"><span data-stu-id="f786f-158">Office</span></span>
        
        
    - <span data-ttu-id="f786f-159">Приобретения, начиная с **AppSource**</span><span class="sxs-lookup"><span data-stu-id="f786f-159">Acquisitions starting within **AppSource**</span></span>
        
    - <span data-ttu-id="f786f-160">Надстройки в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f786f-160">Add-ins within Microsoft 365</span></span>
        
    <span data-ttu-id="f786f-161">Пользователь, который пытается получить доступ к магазину, увидит следующее сообщение: Sorry, Microsoft 365 было настроено, чтобы предотвратить индивидуальное приобретение надстройок **Office Store.**</span><span class="sxs-lookup"><span data-stu-id="f786f-161">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="f786f-162">Поддержка отключения Office Store доступна в следующих версиях:</span><span class="sxs-lookup"><span data-stu-id="f786f-162">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="f786f-163">Windows: 16.0.9001 . В настоящее время доступно.</span><span class="sxs-lookup"><span data-stu-id="f786f-163">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="f786f-164">Mac: 16.10.18011401 - В настоящее время доступен.</span><span class="sxs-lookup"><span data-stu-id="f786f-164">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="f786f-165">iOS: 2.9.18010804 .</span><span class="sxs-lookup"><span data-stu-id="f786f-165">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="f786f-166">Веб - в настоящее время доступен.</span><span class="sxs-lookup"><span data-stu-id="f786f-166">The web - Currently available.</span></span>
    
<span data-ttu-id="f786f-167">Это не мешает администратору использовать централизованное развертывание для назначения надстройки из Office Store.</span><span class="sxs-lookup"><span data-stu-id="f786f-167">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="f786f-168">Чтобы предотвратить вход пользователя в учетную запись Майкрософт, можно ограничить использование только учетной записи организации.</span><span class="sxs-lookup"><span data-stu-id="f786f-168">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="f786f-169">Дополнительные сведения см. в [рублях Identity, authentication и authorization in Office 2016.](/DeployOffice/security/identity-authentication-and-authorization-in-office)</span><span class="sxs-lookup"><span data-stu-id="f786f-169">For more information, see [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span></span>  

> [!NOTE] 
> <span data-ttu-id="f786f-170">Предотвращение доступа пользователей в офисный магазин также помешает им Office надстройки для тестирования из [сетевой сети.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)</span><span class="sxs-lookup"><span data-stu-id="f786f-170">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing from a network share](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="f786f-171">Дополнительные данные об опыте работы конечных пользователей с надстройкими</span><span class="sxs-lookup"><span data-stu-id="f786f-171">More about the end-user experience with add-ins</span></span>

<span data-ttu-id="f786f-172">После развертывания надстройки конечные пользователи могут начать использовать ее в Office приложениях (см. статью Начните использовать [Office надстройки).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="f786f-172">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="f786f-173">Надстройка отображается на всех платформах, которые поддерживает надстройка.</span><span class="sxs-lookup"><span data-stu-id="f786f-173">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="f786f-p109">Если надстройка поддерживает команды, они будут отображаться на ленте Office. В приведенном ниже примере для надстройки **Цитаты** отображается команда **Найти цитату**.</span><span class="sxs-lookup"><span data-stu-id="f786f-p109">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Office лента с цитациями поиска](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="f786f-177">Если развернутая надстройка не поддерживает команды надстройки или вы хотите просмотреть все развернутые надстройки, их можно просмотреть с помощью **моих надстройок.**</span><span class="sxs-lookup"><span data-stu-id="f786f-177">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="f786f-178">В Word 2016, Excel 2016 или PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="f786f-178">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="f786f-179">Выберите **\> Вставьте мои надстройки.**</span><span class="sxs-lookup"><span data-stu-id="f786f-179">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="f786f-180">Откройте вкладку **Управляются администратором** в окне "Надстройки Office".</span><span class="sxs-lookup"><span data-stu-id="f786f-180">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="f786f-181">Дважды щелкните развернутую ранее надстройка (в этом примере **Citations).**</span><span class="sxs-lookup"><span data-stu-id="f786f-181">Double-click the add-in you deployed earlier (in this example, **Citations**).</span></span>

    ![Вкладка Администрирование управляемый страницы Office надстройки](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a><span data-ttu-id="f786f-183">В Outlook</span><span class="sxs-lookup"><span data-stu-id="f786f-183">In Outlook</span></span>

1. <span data-ttu-id="f786f-184">На **ленте Главная** выберите **Получить надстройки**.</span><span class="sxs-lookup"><span data-stu-id="f786f-184">On the **Home** ribbon, select **Get Add-ins**.</span></span>

    ![Кнопка "Хранилище" в Outlook](../../media/getaddinsicon.png)
  
2. <span data-ttu-id="f786f-186">Выберите **Управляемые администратором** в области навигации слева.</span><span class="sxs-lookup"><span data-stu-id="f786f-186">Select **Admin-managed** in the left nav.</span></span> 

## <a name="related-content"></a><span data-ttu-id="f786f-187">См. также:</span><span class="sxs-lookup"><span data-stu-id="f786f-187">Related content</span></span>

<span data-ttu-id="f786f-188">[Развертывание надстройок в центре администрирования](./manage-deployment-of-add-ins.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="f786f-188">[Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md) (article)</span></span>\
<span data-ttu-id="f786f-189">Дополнительные данные о создании и [создании Office надстроек](/office/dev/add-ins/overview/office-add-ins) (статья)</span><span class="sxs-lookup"><span data-stu-id="f786f-189">Learn more about creating and building [Office Add-ins](/office/dev/add-ins/overview/office-add-ins) (article)</span></span>\
<span data-ttu-id="f786f-190">Для управления надстройкими (статья)\ используйте централизованные [cmdlets Deployment PowerShell](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="f786f-190">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (article)\</span></span>
<span data-ttu-id="f786f-191">[Устранение неполадок. Пользователь не видит надстройки](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (статья)</span><span class="sxs-lookup"><span data-stu-id="f786f-191">[Troubleshoot: User not seeing add-ins](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (article)</span></span>\
<span data-ttu-id="f786f-192">[Несовершеннолетние и приобретение надстройок из Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="f786f-192">[Minors and acquiring add-ins from the Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (article)</span></span>