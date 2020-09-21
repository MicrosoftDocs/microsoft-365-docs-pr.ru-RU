---
title: Развертывание надстроек в Центре администрирования
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
ms.openlocfilehash: 5806b2a33446a8e273c2aaf78e082c6fd753bbe4
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171284"
---
# <a name="deploy-add-ins-in-the-admin-center"></a><span data-ttu-id="a0f6b-103">Развертывание надстроек в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="a0f6b-103">Deploy add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a0f6b-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-104">The admin center is changing.</span></span> <span data-ttu-id="a0f6b-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="a0f6b-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="a0f6b-106">Надстройки Office помогают настраивать документы и оптимизировать способ доступа к данным в Интернете (см. раздел [Начало работы с надстройкой Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="a0f6b-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="a0f6b-107">Как администратор вы можете развертывать надстройки Office для пользователей в Организации с помощью функции централизованного развертывания в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-107">As an admin, you can deploy Office add-ins for the users in your organization by using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a0f6b-108">Централизованное развертывание — это рекомендуемый и наиболее полнофункциональный способ развертывания надстроек для пользователей и групп в Организации с широкими функциональными возможностями.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-108">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span> 

<span data-ttu-id="a0f6b-109">Дополнительные сведения о том, как определить, поддерживает ли Организация централизованное развертывание, можно узнать в статье определение того, [работает ли централизованное развертывание надстроек для вашей организации](centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="a0f6b-109">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

<span data-ttu-id="a0f6b-110">Дополнительные сведения об управлении надстройками после развертывания см в разделе Управление надстройками [в центре администрирования](manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="a0f6b-110">To learn more about managing add-ins after deployment, see [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)</span></span>
  
> [!NOTE]
>  <span data-ttu-id="a0f6b-111">В Word, Excel и PowerPoint с помощью [каталога приложений SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) можно развертывать надстройки для пользователей в локальной среде без подключения к Microsoft 365 и/или поддержки надстроек SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-111">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="a0f6b-112">Для Outlook используйте панель управления Exchange для развертывания в локальной среде без подключения к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-112">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="a0f6b-113">Рекомендуемый подход к развертыванию надстроек Office</span><span class="sxs-lookup"><span data-stu-id="a0f6b-113">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="a0f6b-114">Чтобы развернуть надстройки с помощью поэтапного подхода, рекомендуется выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a0f6b-114">To roll out add-ins by using a phased approach, we recommend the following:</span></span>
  
1. <span data-ttu-id="a0f6b-115">Развертывание надстройки для небольшой группы заинтересованных лиц и участников ИТ-отдела.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-115">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="a0f6b-116">Если развертывание прошло успешно, перейдите к шагу 2.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-116">If the deployment is successful, move to step 2.</span></span>
    
2. <span data-ttu-id="a0f6b-117">Развертывание надстройки для большего числа пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-117">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="a0f6b-118">Опять же, оцените результаты и при успешном завершении переходите к полному развертыванию.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-118">Again, evaluate the results and, if successful, continue with full deployment.</span></span>
    
3. <span data-ttu-id="a0f6b-119">Выполните полное развертывание для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-119">Perform a full rollout to all users.</span></span>
    
<span data-ttu-id="a0f6b-120">В зависимости от размера целевой аудитории вы можете добавить или удалить этапы развертывания.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-120">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="a0f6b-121">Развертывание надстройки Office с помощью центра администрирования</span><span class="sxs-lookup"><span data-stu-id="a0f6b-121">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="a0f6b-122">Прежде чем приступать к работе, ознакомьтесь со статьей определение того, [работает ли централизованное развертывание надстроек для вашей организации](centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="a0f6b-122">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
1. <span data-ttu-id="a0f6b-123">В центре администрирования откройте страницу "параметры надстроек **Settings** \> **"** .</span><span class="sxs-lookup"><span data-stu-id="a0f6b-123">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span>
    
2. <span data-ttu-id="a0f6b-124">Выберите **развернуть надстройку** в верхней части страницы, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-124">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="a0f6b-125">Центр администрирования обновлен до развертывания интегрированных приложений.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-125">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="a0f6b-126">Если вы не видите эти действия, перейдите к разделу централизованное развертывание, перейдя к разделу " **Параметры**  >  **интегрированных приложений**".</span><span class="sxs-lookup"><span data-stu-id="a0f6b-126">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="a0f6b-127">В верхней части страницы **интегрированные приложения** **выберите надстройки.**</span><span class="sxs-lookup"><span data-stu-id="a0f6b-127">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="a0f6b-128">Выберите параметр и следуйте инструкциям.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-128">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="a0f6b-129">Если вы выбрали вариант добавления надстройки из магазина Office, сделайте выбор в надстройке.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-129">If you selected the option to add an add-in from the Office Store, make your add-in selection.</span></span> </br>

    <span data-ttu-id="a0f6b-130">Вы можете просматривать доступные надстройки по категориям: **предложено для вас**, **рейтинга**или **имени**.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-130">You can view available add-ins by categories: **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="a0f6b-131">Из магазина Office доступны только бесплатные надстройки.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-131">Only free add-ins are available from the Office Store.</span></span> <span data-ttu-id="a0f6b-132">В настоящее время возможность добавления платных надстроек не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-132">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="a0f6b-133">После выбора надстройки примите условия и условия, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-133">After you select an add-in, accept the terms and conditions to proceed.</span></span> <br/> 

    > [!NOTE] 
    > <span data-ttu-id="a0f6b-134">С помощью параметра магазин Office пользователи автоматически обновляются и улучшаются.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-134">With the Office Store option, updates and enhancements are automatically to users.</span></span>

5. <span data-ttu-id="a0f6b-135">На следующей странице выберите " **все**", " **конкретные пользователи/группы**" или " **только я** ", чтобы указать, в кого развернута надстройка.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-135">On the next page, select **Everyone**, **Specific users/groups**, or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="a0f6b-136">Используйте поле поиска для поиска определенных пользователей или групп.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-136">Use the Search box to find specific users or groups.</span></span> <br/>

    > [!NOTE] 
    > <span data-ttu-id="a0f6b-137">Сведения о других состояниях, применяемых к надстройке, можно узнать в статье [состояния надстроек](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).</span><span class="sxs-lookup"><span data-stu-id="a0f6b-137">To learn about other states that apply to an add-in, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).</span></span>
  
6. <span data-ttu-id="a0f6b-138">Нажмите **Развернуть**.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-138">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="a0f6b-139">При развертывании надстройки отображается зеленый импульс.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-139">A green tick appears when the add-in is deployed.</span></span> <span data-ttu-id="a0f6b-140">Следуйте инструкциям на странице, чтобы протестировать надстройку.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-140">Follow the on-page instructions to test the add-in.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0f6b-141">Пользователям может потребоваться перезапустить Office, чтобы просмотреть значок надстройки на ленте приложения.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-141">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="a0f6b-142">Для отображения на лентах приложений надстройки Outlook могут занимать до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-142">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span>
    
8. <span data-ttu-id="a0f6b-143">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-143">When finished, select **Next**.</span></span> <span data-ttu-id="a0f6b-144">Если вы развернули только себя, вы можете выбрать команду **изменить, кто имеет доступ к надстройке** , чтобы развернуть ее для большего числа пользователей.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-144">If you've deployed to just yourself, you can select **Change who has access to add-in** to deploy to more users.</span></span>

    <span data-ttu-id="a0f6b-145">Если вы развернули надстройку для других участников Организации, следуйте указаниям, чтобы объявить о развертывании надстройки.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-145">If you've deployed the add-in to other members of your organization, follow the instructions to announce the deployment of the add-in.</span></span> <br/>
  
    <span data-ttu-id="a0f6b-146">Рекомендуется проинформировать пользователей и группы о том, что развернутая Надстройка доступна.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-146">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="a0f6b-147">Рассмотрите возможность отправки электронной почты, в которой описывается, когда и как использовать надстройку.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-147">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="a0f6b-148">Включение или ссылка на справочные материалы или часто задаваемые вопросы, которые могут помочь пользователям при возникновении проблем с надстройкой.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-148">Include or link to Help content or FAQs that might help users if they have problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="a0f6b-149">Рекомендации при назначении надстройки пользователям и группам</span><span class="sxs-lookup"><span data-stu-id="a0f6b-149">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="a0f6b-150">Администраторы могут назначить надстройку всем или отдельным пользователям и группам.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-150">Admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="a0f6b-151">Каждый вариант имеет ряд особенностей.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-151">Each option has implications:</span></span>
  
- <span data-ttu-id="a0f6b-152">**Все пользователи** Этот параметр назначает надстройку каждому пользователю в Организации.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-152">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="a0f6b-153">Используйте этот вариант осторожно и только для тех надстроек, которые действительно применяются во всей организации.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-153">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span> 
    
- <span data-ttu-id="a0f6b-154">**Users (пользователи** ) Если вы назначаете надстройку отдельному пользователю и затем развертываете надстройку для нового пользователя, необходимо сначала добавить нового пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-154">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span>
    
- <span data-ttu-id="a0f6b-155">**Groups (группы** ) При назначении надстройке группе пользователям, добавленным в группу, автоматически назначается эта надстройка.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-155">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="a0f6b-156">Когда пользователь удаляется из группы, он теряет доступ к надстройке.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-156">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="a0f6b-157">В любом случае в администраторе не требуются дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-157">In either case, no additional action is required from the admin.</span></span> 

- <span data-ttu-id="a0f6b-158">**Только я** Если вы назначаете надстройку только для себя, надстройка будет назначена только вашей учетной записи, что лучше всего подходит для тестирования надстройки.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-158">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span>
    
<span data-ttu-id="a0f6b-159">Правильный вариант вашей организации зависит от конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-159">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="a0f6b-160">Тем не менее, рекомендуется делать назначения с помощью групп.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-160">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="a0f6b-161">Администратор может упростить управление надстройками с помощью групп и управления членством в этих группах, а не назначать отдельных пользователей каждый раз.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-161">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="a0f6b-162">В некоторых случаях может потребоваться ограничить доступ к небольшому набору пользователей, выполнив назначения определенным пользователям вручную.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-162">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span>
  
## <a name="more-about-office-add-ins-security"></a><span data-ttu-id="a0f6b-163">Дополнительные сведения о безопасности надстроек Office</span><span class="sxs-lookup"><span data-stu-id="a0f6b-163">More about Office add-ins security</span></span>

<span data-ttu-id="a0f6b-p117">Надстройки Office включают XML-файл манифеста, содержащий метаданные и, что главное, указывающий на веб-приложение, которое содержит весь код и алгоритмы. У разных настроек разные возможности. Например, надстройки могут:</span><span class="sxs-lookup"><span data-stu-id="a0f6b-p117">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
  
- <span data-ttu-id="a0f6b-167">Выводить данные.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-167">Display data.</span></span>
    
- <span data-ttu-id="a0f6b-168">Читать документ пользователя для предоставления контекстных услуг.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-168">Read a user's document to provide contextual services.</span></span>
    
- <span data-ttu-id="a0f6b-169">Считывать данные из документа пользователя и записывать их в него для предоставления значений.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-169">Read and write data to and from a user's document to provide value to that user.</span></span>
    
<span data-ttu-id="a0f6b-170">Дополнительные сведения о типах и возможностях надстроек Office см. в статье [Общие сведения о платформе надстроек Office](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins) (на английском языке). Особое внимание обратите на раздел "Структура надстройки Office".</span><span class="sxs-lookup"><span data-stu-id="a0f6b-170">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="a0f6b-p118">Для взаимодействия с документом пользователя надстройке необходимо объявить нужные ей разрешения в манифесте. Пятиуровневая модель разрешений на доступ API JavaScript обеспечивает конфиденциальность и безопасность для надстроек области задач. Большинство надстроек в Магазине Office относятся к уровню ReadWriteDocument, а почти все из них поддерживают по крайней мере уровень ReadDocument. Дополнительные сведения об уровнях разрешений см. в статье [Запрос разрешений на использование API в контенте и в надстройках области задач](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span><span class="sxs-lookup"><span data-stu-id="a0f6b-p118">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span>
  
<span data-ttu-id="a0f6b-p119">При обновлении манифеста обычно изменения связаны со значком и текстом надстройки. Иногда изменяются сами ее команды. Однако разрешения надстройки не изменяются. Веб-приложение, где выполняется весь код и алгоритм надстроек, может измениться в любое время.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-p119">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="a0f6b-178">Надстройки обновляются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a0f6b-178">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="a0f6b-p120">**Бизнес-надстройки**: так как в этом случае администратор добавил манифест вручную, ему потребуется добавить новый файл манифеста, чтобы применить изменения метаданных. При следующем запуске соответствующего приложения Office надстройка будут обновлена. Веб-приложение может изменяться в любое время.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-p120">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="a0f6b-182">Администратору не нужно удалять бизнес-надстройку для обновления.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-182">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="a0f6b-183">В разделе надстройки администратор может просто щелкнуть надстройку LOB и нажать **кнопку Обновить** в правом нижнем углу.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-183">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="a0f6b-184">Обновление будет работать только в том случае, если версия новой надстройки больше, чем у существующей надстройки.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-184">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>   
    
- <span data-ttu-id="a0f6b-p122">**Надстройка из Магазина Office**: если надстройка, которую администратор выбрал из Магазина Office, изменилась, она будет обновлена с помощью функции централизованного развертывания при следующем запуске соответствующего приложения Office. Веб-приложение может изменяться в любое время.</span><span class="sxs-lookup"><span data-stu-id="a0f6b-p122">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 
  
## <a name="learn-more"></a><span data-ttu-id="a0f6b-188">Подробнее</span><span class="sxs-lookup"><span data-stu-id="a0f6b-188">Learn more</span></span>

[<span data-ttu-id="a0f6b-189">Управление надстройками в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="a0f6b-189">Manage add-ins in the admin center</span></span>](manage-addins-in-the-admin-center.md)

<span data-ttu-id="a0f6b-190">[Создание надстроек Office](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins-fundamentals).</span><span class="sxs-lookup"><span data-stu-id="a0f6b-190">[Building Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins-fundamentals).</span></span>

[<span data-ttu-id="a0f6b-191">Вспомогательные и приобретение надстроек из магазина</span><span class="sxs-lookup"><span data-stu-id="a0f6b-191">Minors and acquiring add-ins from the store</span></span>](minors-and-acquiring-addins-from-the-store.md)
  
[<span data-ttu-id="a0f6b-192">Использование командлетов PowerShell для централизованного развертывания для управления надстройками</span><span class="sxs-lookup"><span data-stu-id="a0f6b-192">Use Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[<span data-ttu-id="a0f6b-193">Устранение неполадок: пользователь не видит надстройки</span><span class="sxs-lookup"><span data-stu-id="a0f6b-193">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
