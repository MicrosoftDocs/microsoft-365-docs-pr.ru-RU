---
title: Управление надстройками в Центре администрирования
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
description: Узнайте об использовании централизованных надстройок для развертывания надстройок для пользователей и групп в организации.
ms.openlocfilehash: 836dfa7a0c1b6cf1550e5c139bc0ca36be8f5424
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470945"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="b114b-103">Управление надстройками в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="b114b-103">Manage add-ins in the admin center</span></span>

<span data-ttu-id="b114b-104">Надстройки Office помогут вам персонализировать документы и упростить доступ к информации в Интернете (см. в руб. Начало использования надстройки [Office).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="b114b-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="b114b-105">После развертывания администратором надстройки для пользователей в организации администратор может отключить или включить надстройки, изменить, удалить и управлять доступом к надстройки.</span><span class="sxs-lookup"><span data-stu-id="b114b-105">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="b114b-106">Дополнительные сведения об установке надстройок из центра администрирования см. в дополнительных сведениях о развертывании надстройок [в центре администрирования.](./manage-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="b114b-106">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="b114b-107">Состояния надстроек</span><span class="sxs-lookup"><span data-stu-id="b114b-107">Add-in states</span></span>

<span data-ttu-id="b114b-108">Надстройка может быть в состоянии **On** или **Off.**</span><span class="sxs-lookup"><span data-stu-id="b114b-108">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="b114b-109">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="b114b-109">**State**</span></span>|<span data-ttu-id="b114b-110">**Механизм перехода**</span><span class="sxs-lookup"><span data-stu-id="b114b-110">**How the state occurs**</span></span>|<span data-ttu-id="b114b-111">**Влияние**</span><span class="sxs-lookup"><span data-stu-id="b114b-111">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b114b-112">**Active**</span><span class="sxs-lookup"><span data-stu-id="b114b-112">**Active**</span></span>  <br/> |<span data-ttu-id="b114b-113">Администратор загрузил надстройки и назначен пользователям или группам.</span><span class="sxs-lookup"><span data-stu-id="b114b-113">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="b114b-114">Пользователи и группы, которым назначена эта надстройка, видят ее в соответствующих клиентах.</span><span class="sxs-lookup"><span data-stu-id="b114b-114">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="b114b-115">**Отключена**</span><span class="sxs-lookup"><span data-stu-id="b114b-115">**Turned off**</span></span>  <br/> |<span data-ttu-id="b114b-116">Администратор отключил надстройку.</span><span class="sxs-lookup"><span data-stu-id="b114b-116">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="b114b-117">Пользователи и группы, которым назначена эта надстройка, больше не имеют к ней доступа.</span><span class="sxs-lookup"><span data-stu-id="b114b-117">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="b114b-118">Если изменить состояние надстройки на "Активна", пользователи и группы снова получат к ней доступ.</span><span class="sxs-lookup"><span data-stu-id="b114b-118">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="b114b-119">**Deleted**</span><span class="sxs-lookup"><span data-stu-id="b114b-119">**Deleted**</span></span>  <br/> |<span data-ttu-id="b114b-120">Администратор удалил надстройку.</span><span class="sxs-lookup"><span data-stu-id="b114b-120">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="b114b-121">Пользователи и группы, которым назначена эта надстройка, больше не имеют к ней доступа.</span><span class="sxs-lookup"><span data-stu-id="b114b-121">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="b114b-122">Если надстройка больше не используется, рассмотрите возможность удаления надстройки.</span><span class="sxs-lookup"><span data-stu-id="b114b-122">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="b114b-123">Например, отключение надстройки может иметь смысл, если надстройка используется только в определенное время года.</span><span class="sxs-lookup"><span data-stu-id="b114b-123">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="b114b-124">Удаление надстройки</span><span class="sxs-lookup"><span data-stu-id="b114b-124">Delete an add-in</span></span>

<span data-ttu-id="b114b-125">Можно также удалить развернутую надстройка.</span><span class="sxs-lookup"><span data-stu-id="b114b-125">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="b114b-126">В центре администрирования перейдите на страницу **Службы** параметров &  >  **надстройки.**</span><span class="sxs-lookup"><span data-stu-id="b114b-126">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="b114b-127">Центр администрирования обновляется до развертывания с интегрированными приложениями.</span><span class="sxs-lookup"><span data-stu-id="b114b-127">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="b114b-128">Если вы не видите вышеперечисленные действия, перейдите в раздел Централизованное развертывание, перейдите в **приложения Settings**  >  **Integrated.**</span><span class="sxs-lookup"><span data-stu-id="b114b-128">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="b114b-129">В верхней части страницы **Интегрированные приложения** выберите **надстройки.**</span><span class="sxs-lookup"><span data-stu-id="b114b-129">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="b114b-130">Выберите развернутую надстройка.</span><span class="sxs-lookup"><span data-stu-id="b114b-130">Select the deployed add-in.</span></span>

3. <span data-ttu-id="b114b-131">Нажмите **кнопку Удалить надстройки**.</span><span class="sxs-lookup"><span data-stu-id="b114b-131">Click on **Delete Add-In**.</span></span> <span data-ttu-id="b114b-132">Снимите кнопку надстройки в правом нижнем углу.</span><span class="sxs-lookup"><span data-stu-id="b114b-132">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="b114b-133">Проверьте выбор и выберите **Удаление надстройки.**</span><span class="sxs-lookup"><span data-stu-id="b114b-133">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="b114b-134">Изменение доступа к надстройки</span><span class="sxs-lookup"><span data-stu-id="b114b-134">Edit add-in access</span></span>

<span data-ttu-id="b114b-135">После развертывания администраторы также могут управлять доступом пользователей к надстройки.</span><span class="sxs-lookup"><span data-stu-id="b114b-135">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="b114b-136">В центре администрирования перейдите на страницу **Службы** параметров &  >  **надстройки.**</span><span class="sxs-lookup"><span data-stu-id="b114b-136">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="b114b-137">Центр администрирования обновляется до развертывания с интегрированными приложениями.</span><span class="sxs-lookup"><span data-stu-id="b114b-137">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="b114b-138">Если вы не видите вышеперечисленные действия, перейдите в раздел Централизованное развертывание, перейдите в **приложения Settings**  >  **Integrated.**</span><span class="sxs-lookup"><span data-stu-id="b114b-138">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="b114b-139">В верхней части страницы **Интегрированные приложения** выберите **надстройки.**</span><span class="sxs-lookup"><span data-stu-id="b114b-139">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="b114b-140">Выберите развернутую надстройка.</span><span class="sxs-lookup"><span data-stu-id="b114b-140">Select the deployed add-in.</span></span>

3. <span data-ttu-id="b114b-141">Нажмите **кнопку Изменить** в **статье Кто имеет доступ**.</span><span class="sxs-lookup"><span data-stu-id="b114b-141">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="b114b-142">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="b114b-142">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="b114b-143">Предотвращение скачивания надстройки путем отключения магазина Office для всех клиентов (кроме Outlook)</span><span class="sxs-lookup"><span data-stu-id="b114b-143">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="b114b-144">Установка надстройки Outlook управляется другим [процессом.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)</span><span class="sxs-lookup"><span data-stu-id="b114b-144">Outlook add-in installation is managed by a [different process](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span></span>

<span data-ttu-id="b114b-145">Как организация вы можете запретить скачивание новых надстройок Office из Магазина Office.</span><span class="sxs-lookup"><span data-stu-id="b114b-145">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="b114b-146">Это можно использовать совместно с централизованным развертыванием, чтобы обеспечить развертывание только утвержденных организацией надстройок для пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="b114b-146">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="b114b-147">**Отключение приобретения надстройки**</span><span class="sxs-lookup"><span data-stu-id="b114b-147">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="b114b-148">В центре администрирования перейдите в раздел **Параметры** \> [Услуги&amp;](https://go.microsoft.com/fwlink/p/?linkid=2053743) надстроек.</span><span class="sxs-lookup"><span data-stu-id="b114b-148">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="b114b-149">Центр администрирования обновляется до развертывания с интегрированными приложениями.</span><span class="sxs-lookup"><span data-stu-id="b114b-149">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="b114b-150">Если вы не видите вышеперечисленные действия, перейдите в раздел Централизованное развертывание, перейдите в **приложения Settings**  >  **Integrated.**</span><span class="sxs-lookup"><span data-stu-id="b114b-150">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="b114b-151">В верхней части страницы **Интегрированные приложения** выберите **надстройки.**</span><span class="sxs-lookup"><span data-stu-id="b114b-151">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="b114b-152">Выберите **приложения и службы,** которые принадлежат пользователю.</span><span class="sxs-lookup"><span data-stu-id="b114b-152">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="b114b-153">Упусти возможность доступа пользователей к магазину Office.</span><span class="sxs-lookup"><span data-stu-id="b114b-153">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="b114b-154">Это предотвратит получение всеми пользователями следующих надстройок из магазина.</span><span class="sxs-lookup"><span data-stu-id="b114b-154">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="b114b-155">Надстройки для Word, Excel и PowerPoint 2016 из:</span><span class="sxs-lookup"><span data-stu-id="b114b-155">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="b114b-156">Windows</span><span class="sxs-lookup"><span data-stu-id="b114b-156">Windows</span></span>
    
  - <span data-ttu-id="b114b-157">Mac</span><span class="sxs-lookup"><span data-stu-id="b114b-157">Mac</span></span>
    
  - <span data-ttu-id="b114b-158">Office</span><span class="sxs-lookup"><span data-stu-id="b114b-158">Office</span></span>
    
    
- <span data-ttu-id="b114b-159">Приобретения, начиная с **AppSource**</span><span class="sxs-lookup"><span data-stu-id="b114b-159">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="b114b-160">Надстройки в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b114b-160">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="b114b-161">Пользователь, который пытается получить доступ к магазину, увидит следующее сообщение: **К сожалению, Microsoft 365** была настроена для предотвращения индивидуального приобретения надстройок Office Store.</span><span class="sxs-lookup"><span data-stu-id="b114b-161">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="b114b-162">Поддержка отключения Магазина Office доступна в следующих версиях:</span><span class="sxs-lookup"><span data-stu-id="b114b-162">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="b114b-163">Windows: 16.0.9001 . В настоящее время доступно.</span><span class="sxs-lookup"><span data-stu-id="b114b-163">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="b114b-164">Mac: 16.10.18011401 - В настоящее время доступен.</span><span class="sxs-lookup"><span data-stu-id="b114b-164">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="b114b-165">iOS: 2.9.18010804 .</span><span class="sxs-lookup"><span data-stu-id="b114b-165">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="b114b-166">Веб - в настоящее время доступен.</span><span class="sxs-lookup"><span data-stu-id="b114b-166">The web - Currently available.</span></span>
    
<span data-ttu-id="b114b-167">Это не мешает администратору использовать централизованное развертывание для назначения надстройки из магазина Office.</span><span class="sxs-lookup"><span data-stu-id="b114b-167">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="b114b-168">Чтобы предотвратить вход пользователя в учетную запись Майкрософт, можно ограничить использование только учетной записи организации.</span><span class="sxs-lookup"><span data-stu-id="b114b-168">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="b114b-169">Дополнительные сведения см. в [рублях Identity, authentication и authorization in Office 2016.](/DeployOffice/security/identity-authentication-and-authorization-in-office)</span><span class="sxs-lookup"><span data-stu-id="b114b-169">For more information, see [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span></span>  

> [!NOTE]
> <span data-ttu-id="b114b-170">Если пользователи не смогут получить доступ в офисный магазин, они также не смогут выгружать надстройки [Office для тестирования.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)</span><span class="sxs-lookup"><span data-stu-id="b114b-170">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="b114b-171">Дополнительные данные о пользовательском интерфейсе с надстройки</span><span class="sxs-lookup"><span data-stu-id="b114b-171">More about the end user experience with add-ins</span></span>

<span data-ttu-id="b114b-172">После развертывания надстройки конечные пользователи могут начать использовать ее в своих приложениях Office (см. статью Начните использовать надстройки [Office).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="b114b-172">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="b114b-173">Надстройка отображается на всех платформах, которые поддерживает надстройка.</span><span class="sxs-lookup"><span data-stu-id="b114b-173">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="b114b-p109">Если надстройка поддерживает команды, они будут отображаться на ленте Office. В приведенном ниже примере для надстройки **Цитаты** отображается команда **Найти цитату**.</span><span class="sxs-lookup"><span data-stu-id="b114b-p109">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Лента Office с ссылками на поиск](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="b114b-177">Если развернутая надстройка не поддерживает команды надстройки или вы хотите просмотреть все развернутые надстройки, их можно просмотреть с помощью **моих надстройок.**</span><span class="sxs-lookup"><span data-stu-id="b114b-177">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="b114b-178">В Word 2016, Excel 2016 или PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="b114b-178">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="b114b-179">Выберите **\> Вставьте мои надстройки.**</span><span class="sxs-lookup"><span data-stu-id="b114b-179">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="b114b-180">Откройте вкладку **Управляются администратором** в окне "Надстройки Office".</span><span class="sxs-lookup"><span data-stu-id="b114b-180">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="b114b-181">Дважды щелкните надстройку, которую вы развернули ранее (в данном примере  **Цитаты** ).</span><span class="sxs-lookup"><span data-stu-id="b114b-181">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="b114b-182">![Вкладка Управление администрированием страницы надстройки Office](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="b114b-182">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="b114b-183">В Outlook</span><span class="sxs-lookup"><span data-stu-id="b114b-183">In Outlook</span></span>

1. <span data-ttu-id="b114b-184">На **ленте Главная** выберите **Получить надстройки**.</span><span class="sxs-lookup"><span data-stu-id="b114b-184">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="b114b-185">![Кнопка "Хранилище" в Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="b114b-185">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="b114b-186">Выберите **управляемый администратором** в левом nav.</span><span class="sxs-lookup"><span data-stu-id="b114b-186">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="b114b-187">Подробнее</span><span class="sxs-lookup"><span data-stu-id="b114b-187">Learn more</span></span>

[<span data-ttu-id="b114b-188">Развертывание надстроек в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="b114b-188">Deploy add-ins in the admin center</span></span>](./manage-deployment-of-add-ins.md)

<span data-ttu-id="b114b-189">Получите дополнительные сведения о создании [надстроек Office](/office/dev/add-ins/overview/office-add-ins).</span><span class="sxs-lookup"><span data-stu-id="b114b-189">Learn more about creating and building [Office Add-ins](/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="b114b-190">Для управления надстройными надстройки используйте централизованные [комлеты Deployment PowerShell.](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="b114b-190">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md).</span></span>
  
[<span data-ttu-id="b114b-191">Устранение неполадок. Пользователь не видит надстройки</span><span class="sxs-lookup"><span data-stu-id="b114b-191">Troubleshoot: User not seeing add-ins</span></span>](/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="b114b-192">Несовершеннолетние и приобретение надстройок в Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="b114b-192">Minors and acquiring add-ins from the Microsoft Store</span></span>](./minors-and-acquiring-addins-from-the-store.md)