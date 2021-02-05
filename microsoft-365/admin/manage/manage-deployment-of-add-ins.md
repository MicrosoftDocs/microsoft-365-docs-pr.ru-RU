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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Узнайте, как развертывать надстройки для пользователей и групп в организации с помощью централизованного развертывания в Центре администрирования.
ms.openlocfilehash: 5d17242d98f0e58ec4bfbcfd5b7014e6a6e0a6c5
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114505"
---
# <a name="deploy-add-ins-in-the-admin-center"></a><span data-ttu-id="7b6d7-103">Развертывание надстроек в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="7b6d7-103">Deploy add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="7b6d7-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-104">The admin center is changing.</span></span> <span data-ttu-id="7b6d7-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="7b6d7-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="7b6d7-106">Надстройки Office помогают персонализировать документы и упрощают доступ к информации в Интернете (см. "Пуск с помощью [надстройки Office").](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="7b6d7-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="7b6d7-107">Как администратор вы можете развертывать надстройки Office для пользователей в организации с помощью функции централизованного развертывания в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-107">As an admin, you can deploy Office add-ins for the users in your organization by using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="7b6d7-108">Централизованное развертывание — это рекомендуемый и наиболее сложный способ для большинства администраторов развертывать надстройки для пользователей и групп в организации.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-108">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span> 

<span data-ttu-id="7b6d7-109">Дополнительные сведения о том, как определить, поддерживает ли ваша организация централизованное развертывание, см. в подстройки "Определение работы централизованного развертывания надстройки" в [организации.](centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="7b6d7-109">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

<span data-ttu-id="7b6d7-110">Дополнительные информацию об управлении надстройки после развертывания см. в центре администрирования "Управление [надстройкими"](manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="7b6d7-110">To learn more about managing add-ins after deployment, see [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)</span></span>
  
> [!NOTE]
>  <span data-ttu-id="7b6d7-111">Для Word, Excel и PowerPoint используйте каталог приложений [SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) для развертывания надстройки для пользователей в локальной среде без подключения к Microsoft 365 и/или поддержки надстройки SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-111">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="7b6d7-112">Outlook использует панель управления Exchange для развертывания в локальной среде без подключения к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-112">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="7b6d7-113">Рекомендуемый подход для развертывания надстройки Office</span><span class="sxs-lookup"><span data-stu-id="7b6d7-113">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="7b6d7-114">Для поэтапного применения надстройки рекомендуется следующее:</span><span class="sxs-lookup"><span data-stu-id="7b6d7-114">To roll out add-ins by using a phased approach, we recommend the following:</span></span>
  
1. <span data-ttu-id="7b6d7-115">Развернуть надстройку для небольшого набора заинтересованных лиц и сотрудников ИТ-отдела.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-115">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="7b6d7-116">Если развертывание успешно, переходить к шагу 2.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-116">If the deployment is successful, move to step 2.</span></span>
    
2. <span data-ttu-id="7b6d7-117">Развяйте надстройку для большей информации в компании.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-117">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="7b6d7-118">Снова оцените результаты и в случае успеха продолжите полное развертывание.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-118">Again, evaluate the results and, if successful, continue with full deployment.</span></span>
    
3. <span data-ttu-id="7b6d7-119">Выполните полный выкат для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-119">Perform a full rollout to all users.</span></span>
    
<span data-ttu-id="7b6d7-120">В зависимости от размера целевой аудитории можно добавлять или удалять этапы.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-120">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="7b6d7-121">Развертывание надстройки Office с помощью Центра администрирования</span><span class="sxs-lookup"><span data-stu-id="7b6d7-121">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="7b6d7-122">Прежде чем приступить к работе, определите, работает ли централизованное развертывание [надстройки для вашей организации.](centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="7b6d7-122">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
1. <span data-ttu-id="7b6d7-123">В Центре администрирования перейдите **на** страницу \> **"Надстройки параметров".**</span><span class="sxs-lookup"><span data-stu-id="7b6d7-123">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span> <span data-ttu-id="7b6d7-124">Если вы не видите **страницу** надстройки, перейдите на страницу "Надстройки интегрированных приложений  \>  \> **параметров".**</span><span class="sxs-lookup"><span data-stu-id="7b6d7-124">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** page.</span></span>
    
2. <span data-ttu-id="7b6d7-125">Выберите **"Развернуть надстройки"** в верхней части страницы, а затем — **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="7b6d7-125">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="7b6d7-126">Центр администрирования обновляется до интерфейса развертывания с помощью интегрированных приложений.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-126">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="7b6d7-127">Если вы не видите вышеперечисленные действия, перейдите в раздел "Централизованное развертывание", перейдите в раздел **"Интегрированные** приложения  >  **параметров".**</span><span class="sxs-lookup"><span data-stu-id="7b6d7-127">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="7b6d7-128">В верхней части страницы **"Интегрированные приложения"** выберите **"Надстройки".**</span><span class="sxs-lookup"><span data-stu-id="7b6d7-128">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="7b6d7-129">Выберите параметр и следуйте инструкциям.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-129">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="7b6d7-130">Если вы выбрали вариант добавления надстройки из Магазина Office, выберите надстройку.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-130">If you selected the option to add an add-in from the Office Store, make your add-in selection.</span></span> </br>

    <span data-ttu-id="7b6d7-131">Вы можете просматривать доступные надстройки по категориям: **"Предложено",** **"Оценка"** или **"Имя".**</span><span class="sxs-lookup"><span data-stu-id="7b6d7-131">You can view available add-ins by categories: **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="7b6d7-132">В Магазине Office доступны только бесплатные надстройки.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-132">Only free add-ins are available from the Office Store.</span></span> <span data-ttu-id="7b6d7-133">В настоящее время возможность добавления платных надстроек не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-133">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="7b6d7-134">После выбора надстройки примите условия, которые необходимо продолжить.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-134">After you select an add-in, accept the terms and conditions to proceed.</span></span> <br/> 

    > [!NOTE] 
    > <span data-ttu-id="7b6d7-135">С помощью параметра Магазина Office обновления и улучшения автоматически развертываются для пользователей.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-135">With the Office Store option, updates and enhancements are automatically deployed to users.</span></span>

5. <span data-ttu-id="7b6d7-136">На следующей странице выберите "Все",  "Определенные пользователи **или** группы" или "Просто я", чтобы указать, на кого развернута надстройка. </span><span class="sxs-lookup"><span data-stu-id="7b6d7-136">On the next page, select **Everyone**, **Specific users/groups**, or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="7b6d7-137">Используйте поле поиска для поиска определенных пользователей или групп.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-137">Use the Search box to find specific users or groups.</span></span> <br/>

    > [!NOTE] 
    > <span data-ttu-id="7b6d7-138">Чтобы узнать о других состояниях надстройки, см. [статью "Состояния надстройки".](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="7b6d7-138">To learn about other states that apply to an add-in, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).</span></span>
  
6. <span data-ttu-id="7b6d7-139">Нажмите **Развернуть**.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-139">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="7b6d7-140">При развертывании надстройки появляется зеленый тик.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-140">A green tick appears when the add-in is deployed.</span></span> <span data-ttu-id="7b6d7-141">Следуйте инструкциям на странице, чтобы протестировать надстройки.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-141">Follow the on-page instructions to test the add-in.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7b6d7-142">Пользователям может потребоваться перезапустить Office, чтобы просмотреть значок надстройки на ленте приложения.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-142">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="7b6d7-143">Надстройки Outlook могут отображаться на лентах приложений в течение 24 часов.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-143">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span>
    
8. <span data-ttu-id="7b6d7-144">По завершению выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="7b6d7-144">When finished, select **Next**.</span></span> <span data-ttu-id="7b6d7-145">Если вы развернули только для себя,  вы можете выбрать "Изменить пользователей, у которых есть доступ к надстройкам", чтобы развернуть их для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-145">If you've deployed to just yourself, you can select **Change who has access to add-in** to deploy to more users.</span></span>

    <span data-ttu-id="7b6d7-146">Если вы развернули надстройки для других сотрудников организации, следуйте инструкциям, чтобы объявить о ее развертывании.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-146">If you've deployed the add-in to other members of your organization, follow the instructions to announce the deployment of the add-in.</span></span> <br/>
  
    <span data-ttu-id="7b6d7-147">Мы сообщите пользователям и группам о том, что развернутая надстройка доступна.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-147">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="7b6d7-148">Рассмотрите возможность отправки сообщения электронной почты с описанием того, когда и как использовать надстройки.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-148">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="7b6d7-149">Включайте или ссылайте на содержимое справки или вопросы и вопросы и вопросы, которые могут помочь пользователям при проблемах с надстройка.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-149">Include or link to Help content or FAQs that might help users if they have problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="7b6d7-150">Рекомендации при назначении надстройки пользователям и группам</span><span class="sxs-lookup"><span data-stu-id="7b6d7-150">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="7b6d7-151">Администраторы могут назначить надстройку всем или отдельным пользователям и группам.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-151">Admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="7b6d7-152">Каждый вариант имеет ряд особенностей.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-152">Each option has implications:</span></span>
  
- <span data-ttu-id="7b6d7-153">**Все** Этот параметр назначает надстройки каждому пользователю в организации.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-153">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="7b6d7-154">Используйте этот вариант осторожно и только для тех надстроек, которые действительно применяются во всей организации.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-154">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span> 
    
- <span data-ttu-id="7b6d7-155">**Пользователи** Если вы назначаете надстройки отдельному пользователю, а затем развертываете надстройки для нового пользователя, необходимо сначала добавить нового пользователя.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-155">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span>
    
- <span data-ttu-id="7b6d7-156">**Группы** При назначении надстройки группе пользователи, добавленные в группу, автоматически назначаются надстройка.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-156">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="7b6d7-157">Когда пользователь удаляется из группы, он теряет доступ к надстройки.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-157">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="7b6d7-158">В любом случае никаких дополнительных действий от администратора не требуется.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-158">In either case, no additional action is required from the admin.</span></span> 

- <span data-ttu-id="7b6d7-159">**Только я** Если вы назначаете надстройки только себе, она назначается только вашей учетной записи, что идеально подходит для тестирования надстройки.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-159">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span>
    
<span data-ttu-id="7b6d7-160">Выбор правильного варианта для организации зависит от конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-160">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="7b6d7-161">Однако рекомендуется выполнять назначения с помощью групп.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-161">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="7b6d7-162">Администратор может упростить управление надстройки с помощью групп и контроля членства в этих группах, а не назначать отдельных пользователей каждый раз.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-162">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="7b6d7-163">В некоторых случаях может потребоваться ограничить доступ для небольшого набора пользователей, назначая их определенным пользователям вручную.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-163">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span>
  
## <a name="more-about-office-add-ins-security"></a><span data-ttu-id="7b6d7-164">Дополнительные информация о безопасности надстройки Office</span><span class="sxs-lookup"><span data-stu-id="7b6d7-164">More about Office add-ins security</span></span>

<span data-ttu-id="7b6d7-p118">Надстройки Office включают XML-файл манифеста, содержащий метаданные и, что главное, указывающий на веб-приложение, которое содержит весь код и алгоритмы. У разных настроек разные возможности. Например, надстройки могут:</span><span class="sxs-lookup"><span data-stu-id="7b6d7-p118">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
  
- <span data-ttu-id="7b6d7-168">Выводить данные.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-168">Display data.</span></span>
    
- <span data-ttu-id="7b6d7-169">Читать документ пользователя для предоставления контекстных услуг.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-169">Read a user's document to provide contextual services.</span></span>
    
- <span data-ttu-id="7b6d7-170">Считывать данные из документа пользователя и записывать их в него для предоставления значений.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-170">Read and write data to and from a user's document to provide value to that user.</span></span>
    
<span data-ttu-id="7b6d7-171">Дополнительные сведения о типах и возможностях надстроек Office см. в статье [Общие сведения о платформе надстроек Office](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins) (на английском языке). Особое внимание обратите на раздел "Структура надстройки Office".</span><span class="sxs-lookup"><span data-stu-id="7b6d7-171">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="7b6d7-p119">Для взаимодействия с документом пользователя надстройке необходимо объявить нужные ей разрешения в манифесте. Пятиуровневая модель разрешений на доступ API JavaScript обеспечивает конфиденциальность и безопасность для надстроек области задач. Большинство надстроек в Магазине Office относятся к уровню ReadWriteDocument, а почти все из них поддерживают по крайней мере уровень ReadDocument. Дополнительные сведения об уровнях разрешений см. в статье [Запрос разрешений на использование API в контенте и в надстройках области задач](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span><span class="sxs-lookup"><span data-stu-id="7b6d7-p119">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span>
  
<span data-ttu-id="7b6d7-p120">При обновлении манифеста обычно изменения связаны со значком и текстом надстройки. Иногда изменяются сами ее команды. Однако разрешения надстройки не изменяются. Веб-приложение, где выполняется весь код и алгоритм надстроек, может измениться в любое время.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-p120">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="7b6d7-179">Надстройки обновляются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7b6d7-179">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="7b6d7-p121">**Бизнес-надстройки**: так как в этом случае администратор добавил манифест вручную, ему потребуется добавить новый файл манифеста, чтобы применить изменения метаданных. При следующем запуске соответствующего приложения Office надстройка будут обновлена. Веб-приложение может изменяться в любое время.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-p121">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="7b6d7-183">Администратору не нужно удалять бизнес-надстройку для обновления.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-183">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="7b6d7-184">В разделе "Надстройки" администратор может просто щелкнуть надстройку для LOB и нажать кнопку обновления в правом нижнем углу. </span><span class="sxs-lookup"><span data-stu-id="7b6d7-184">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="7b6d7-185">Обновление будет работать только в том случае, если версия новой надстройки больше, чем версия существующей надстройки.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-185">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>   
    
- <span data-ttu-id="7b6d7-p123">**Надстройка из Магазина Office**: если надстройка, которую администратор выбрал из Магазина Office, изменилась, она будет обновлена с помощью функции централизованного развертывания при следующем запуске соответствующего приложения Office. Веб-приложение может изменяться в любое время.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-p123">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 
  
## <a name="learn-more"></a><span data-ttu-id="7b6d7-189">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="7b6d7-189">Learn more</span></span>

[<span data-ttu-id="7b6d7-190">Управление надстройками в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="7b6d7-190">Manage add-ins in the admin center</span></span>](manage-addins-in-the-admin-center.md)

<span data-ttu-id="7b6d7-191">[Создайте свою первую надстройку области задач Word.](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)</span><span class="sxs-lookup"><span data-stu-id="7b6d7-191">[Build your first Word task pane add-in](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator).</span></span>

[<span data-ttu-id="7b6d7-192">Несовершеннолетних и приобретение надстройки в Магазине</span><span class="sxs-lookup"><span data-stu-id="7b6d7-192">Minors and acquiring add-ins from the store</span></span>](minors-and-acquiring-addins-from-the-store.md)
  
[<span data-ttu-id="7b6d7-193">Использование централизованного развертывания powerShell для управления надстройки</span><span class="sxs-lookup"><span data-stu-id="7b6d7-193">Use Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[<span data-ttu-id="7b6d7-194">Устранение неполадок: пользователь не видит надстройки</span><span class="sxs-lookup"><span data-stu-id="7b6d7-194">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
