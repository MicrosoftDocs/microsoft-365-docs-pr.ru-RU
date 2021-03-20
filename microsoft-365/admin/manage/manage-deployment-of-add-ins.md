---
title: Развертывание надстроек в Центре администрирования
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Научитесь развертывать надстройки для пользователей и групп в организации с помощью центраализованного развертывания в центре администрирования.
ms.openlocfilehash: 9ded0294912a3c3c99e62913bcdc349de7bae1b5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915390"
---
# <a name="deploy-add-ins-in-the-admin-center"></a><span data-ttu-id="38fa8-103">Развертывание надстроек в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="38fa8-103">Deploy add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="38fa8-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="38fa8-104">The admin center is changing.</span></span> <span data-ttu-id="38fa8-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="38fa8-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="38fa8-106">Надстройки Office помогают персонализировать документы и упростить доступ к информации в Интернете (см. в руб. Начало использования надстройки [Office).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="38fa8-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="38fa8-107">В качестве администратора можно развернуть надстройки Office для пользователей в организации с помощью функции централизованного развертывания в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="38fa8-107">As an admin, you can deploy Office add-ins for the users in your organization by using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="38fa8-108">Централизованное развертывание — это рекомендуемый и наиболее насыщенный функцией способ для большинства администраторов развернуть надстройки для пользователей и групп в организации.</span><span class="sxs-lookup"><span data-stu-id="38fa8-108">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span>

<span data-ttu-id="38fa8-109">Дополнительные сведения о том, как определить, может ли организация поддерживать централизованное развертывание, см. в статью Определение, работает ли централизованное развертывание надстройок [для вашей организации.](centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="38fa8-109">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

<span data-ttu-id="38fa8-110">Дополнительные информацию об управлении надстройкими после развертывания см. в рублях Управление надстройкими [в центре администрирования](manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="38fa8-110">To learn more about managing add-ins after deployment, see [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)</span></span>
  
> [!NOTE]
>  <span data-ttu-id="38fa8-111">Для Word Excel и PowerPoint используют каталог [приложений SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) для развертывания надстройок для пользователей в локальной среде без подключения к Microsoft 365 и/или поддержки надстройок SharePoint.</span><span class="sxs-lookup"><span data-stu-id="38fa8-111">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="38fa8-112">Для Outlook используйте панель управления Exchange для развертывания в локальной среде без подключения к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="38fa8-112">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="38fa8-113">Рекомендуемый подход к развертыванию надстройок Office</span><span class="sxs-lookup"><span data-stu-id="38fa8-113">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="38fa8-114">Чтобы выкатать надстройки с помощью поэтапного подхода, рекомендуется следующее:</span><span class="sxs-lookup"><span data-stu-id="38fa8-114">To roll out add-ins by using a phased approach, we recommend the following:</span></span>
  
1. <span data-ttu-id="38fa8-115">Развернуть надстройку небольшому набору бизнес-заинтересованных лиц и сотрудников ИТ-отдела.</span><span class="sxs-lookup"><span data-stu-id="38fa8-115">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="38fa8-116">Если развертывание успешно, переходить на шаг 2.</span><span class="sxs-lookup"><span data-stu-id="38fa8-116">If the deployment is successful, move to step 2.</span></span>
    
2. <span data-ttu-id="38fa8-117">Развяйте надстройку для большего числе пользователей в бизнесе.</span><span class="sxs-lookup"><span data-stu-id="38fa8-117">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="38fa8-118">Снова оцените результаты и в случае успешного развертывания продолжайте развертывание в полном объеме.</span><span class="sxs-lookup"><span data-stu-id="38fa8-118">Again, evaluate the results and, if successful, continue with full deployment.</span></span>
    
3. <span data-ttu-id="38fa8-119">Выполните полный выкат для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="38fa8-119">Perform a full rollout to all users.</span></span>
    
<span data-ttu-id="38fa8-120">В зависимости от размера целевой аудитории можно добавлять или удалять этапы выкатки.</span><span class="sxs-lookup"><span data-stu-id="38fa8-120">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="38fa8-121">Развертывание надстройки Office с помощью центра администрирования</span><span class="sxs-lookup"><span data-stu-id="38fa8-121">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="38fa8-122">Прежде чем приступить к работе, см. в рубриках Определите, работает ли централизованное развертывание [надстройок для вашей организации.](centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="38fa8-122">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
1. <span data-ttu-id="38fa8-123">В центре администрирования перейдите на страницу  \> **Надстройки параметров.**</span><span class="sxs-lookup"><span data-stu-id="38fa8-123">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span> <span data-ttu-id="38fa8-124">Если вы не видите страницу **надстройки,** перейдите на страницу Надстройки **"Параметры** \>  \> **интегрированные приложения".**</span><span class="sxs-lookup"><span data-stu-id="38fa8-124">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** page.</span></span>

2. <span data-ttu-id="38fa8-125">Выберите **развертывание надстройки** в верхней части страницы, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="38fa8-125">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="38fa8-126">Центр администрирования обновляется до развертывания с интегрированными приложениями.</span><span class="sxs-lookup"><span data-stu-id="38fa8-126">The admin center is getting updated to deployment experience with Integrated Apps.</span></span> <span data-ttu-id="38fa8-127">Интегрированные приложения видны только глобальным администраторам, в то время как для других существует старый опыт.</span><span class="sxs-lookup"><span data-stu-id="38fa8-127">Integrated Apps is only visible to Global administrators, while for others the old experience still exists.</span></span> <span data-ttu-id="38fa8-128">Если вы не видите вышеперечисленные действия, перейдите в раздел Централизованное развертывание, переехав в **приложения Settings**  >  **Integrated** Apps.</span><span class="sxs-lookup"><span data-stu-id="38fa8-128">If you don't see the above steps, go to the Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="38fa8-129">В верхней части страницы **Интегрированные приложения** выберите **надстройки.**</span><span class="sxs-lookup"><span data-stu-id="38fa8-129">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

3. <span data-ttu-id="38fa8-130">Выберите параметр и следуйте инструкциям.</span><span class="sxs-lookup"><span data-stu-id="38fa8-130">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="38fa8-131">Если вы выбрали вариант добавления надстройки из Магазина Office, выберите надстройку.</span><span class="sxs-lookup"><span data-stu-id="38fa8-131">If you selected the option to add an add-in from the Office Store, make your add-in selection.</span></span> </br>

    <span data-ttu-id="38fa8-132">Доступные надстройки можно просматривать по категориям: **"Предложено",** **"Оценка"** или **"Имя".**</span><span class="sxs-lookup"><span data-stu-id="38fa8-132">You can view available add-ins by categories: **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="38fa8-133">Только бесплатные надстройки доступны в Магазине Office.</span><span class="sxs-lookup"><span data-stu-id="38fa8-133">Only free add-ins are available from the Office Store.</span></span> <span data-ttu-id="38fa8-134">В настоящее время возможность добавления платных надстроек не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="38fa8-134">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="38fa8-135">После выбора надстройки примите условия и условия для работы.</span><span class="sxs-lookup"><span data-stu-id="38fa8-135">After you select an add-in, accept the terms and conditions to proceed.</span></span> <br/> 

    > [!NOTE]
    > <span data-ttu-id="38fa8-136">С помощью параметра Office Store обновления и улучшения автоматически развертываются для пользователей.</span><span class="sxs-lookup"><span data-stu-id="38fa8-136">With the Office Store option, updates and enhancements are automatically deployed to users.</span></span>

5. <span data-ttu-id="38fa8-137">На следующей странице выберите **"Все",**  **"Конкретные пользователи/группы"** или "Просто я", чтобы указать, кому развернута надстройка.</span><span class="sxs-lookup"><span data-stu-id="38fa8-137">On the next page, select **Everyone**, **Specific users/groups**, or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="38fa8-138">Используйте поле Поиска для поиска определенных пользователей или групп.</span><span class="sxs-lookup"><span data-stu-id="38fa8-138">Use the Search box to find specific users or groups.</span></span> <br/>

    > [!NOTE]
    > <span data-ttu-id="38fa8-139">Дополнительные информацию о других состояниях, применимых к надстройки, см. в статью ["Состояния надстройки".](./manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="38fa8-139">To learn about other states that apply to an add-in, see [Add-in states](./manage-addins-in-the-admin-center.md).</span></span>
  
6. <span data-ttu-id="38fa8-140">Нажмите **Развернуть**.</span><span class="sxs-lookup"><span data-stu-id="38fa8-140">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="38fa8-141">При развертывании надстройки появляется зеленый тик.</span><span class="sxs-lookup"><span data-stu-id="38fa8-141">A green tick appears when the add-in is deployed.</span></span> <span data-ttu-id="38fa8-142">Выполните инструкции по проверке надстройки на странице.</span><span class="sxs-lookup"><span data-stu-id="38fa8-142">Follow the on-page instructions to test the add-in.</span></span>

    > [!NOTE]
    > <span data-ttu-id="38fa8-143">Пользователям может потребоваться перезапустить Office, чтобы просмотреть значок надстройки на ленте приложения.</span><span class="sxs-lookup"><span data-stu-id="38fa8-143">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="38fa8-144">Добавление Outlook может занять до 24 часов, чтобы отображаться на лентах приложений.</span><span class="sxs-lookup"><span data-stu-id="38fa8-144">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span>

8. <span data-ttu-id="38fa8-145">По завершению выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="38fa8-145">When finished, select **Next**.</span></span> <span data-ttu-id="38fa8-146">Если вы развернули только для себя, вы можете выбрать **Изменение,** у которого есть доступ к надстройки, чтобы развернуть больше пользователей.</span><span class="sxs-lookup"><span data-stu-id="38fa8-146">If you've deployed to just yourself, you can select **Change who has access to add-in** to deploy to more users.</span></span>

    <span data-ttu-id="38fa8-147">Если надстройка развернута другим членам организации, следуйте инструкциям, чтобы объявить о развертывании надстройки.</span><span class="sxs-lookup"><span data-stu-id="38fa8-147">If you've deployed the add-in to other members of your organization, follow the instructions to announce the deployment of the add-in.</span></span> <br/>
  
    <span data-ttu-id="38fa8-148">Это хорошая практика для информирования пользователей и групп о том, что развернутая надстройка доступна.</span><span class="sxs-lookup"><span data-stu-id="38fa8-148">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="38fa8-149">Рассмотрите возможность отправки электронной почты с описанием того, когда и как использовать надстройки.</span><span class="sxs-lookup"><span data-stu-id="38fa8-149">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="38fa8-150">Включайте или ссылки на содержимое справки или вопросы, которые могут помочь пользователям, если у них возникли проблемы с надстройки.</span><span class="sxs-lookup"><span data-stu-id="38fa8-150">Include or link to Help content or FAQs that might help users if they have problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="38fa8-151">Рекомендации при назначении надстройки пользователям и группам</span><span class="sxs-lookup"><span data-stu-id="38fa8-151">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="38fa8-152">Глобальные администраторы и администраторы Exchange могут назначать надстройки всем пользователям и группам.</span><span class="sxs-lookup"><span data-stu-id="38fa8-152">Global admins and Exchange admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="38fa8-153">Каждый вариант имеет ряд особенностей.</span><span class="sxs-lookup"><span data-stu-id="38fa8-153">Each option has implications:</span></span>
  
- <span data-ttu-id="38fa8-154">**Все** Этот параметр назначает надстройки каждому пользователю организации.</span><span class="sxs-lookup"><span data-stu-id="38fa8-154">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="38fa8-155">Используйте этот вариант осторожно и только для тех надстроек, которые действительно применяются во всей организации.</span><span class="sxs-lookup"><span data-stu-id="38fa8-155">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span>

- <span data-ttu-id="38fa8-156">**Пользователи** Если вы назначите надстройки отдельному пользователю, а затем развернете надстройки новому пользователю, сначала необходимо добавить нового пользователя.</span><span class="sxs-lookup"><span data-stu-id="38fa8-156">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span>

- <span data-ttu-id="38fa8-157">**Группы** Если надстройка назначается группе, пользователям, добавляемой в группу, автоматически назначается надстройка.</span><span class="sxs-lookup"><span data-stu-id="38fa8-157">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="38fa8-158">При удалении пользователя из группы пользователь теряет доступ к надстройки.</span><span class="sxs-lookup"><span data-stu-id="38fa8-158">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="38fa8-159">В любом случае от администратора не требуется никаких дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="38fa8-159">In either case, no additional action is required from the admin.</span></span>

- <span data-ttu-id="38fa8-160">**Только я** Если надстройка назначается только себе, надстройка назначается только вашей учетной записи, которая идеально подходит для тестирования надстройки.</span><span class="sxs-lookup"><span data-stu-id="38fa8-160">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span>

<span data-ttu-id="38fa8-161">Правильный вариант для организации зависит от конфигурации.</span><span class="sxs-lookup"><span data-stu-id="38fa8-161">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="38fa8-162">Однако мы рекомендуем выполнять назначения с помощью групп.</span><span class="sxs-lookup"><span data-stu-id="38fa8-162">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="38fa8-163">В качестве администратора может быть проще управлять надстройки с помощью групп и управления членством этих групп, а не назначать отдельных пользователей каждый раз.</span><span class="sxs-lookup"><span data-stu-id="38fa8-163">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="38fa8-164">В некоторых ситуациях может потребоваться ограничить доступ к небольшому набору пользователей, назначив пользователям назначения вручную.</span><span class="sxs-lookup"><span data-stu-id="38fa8-164">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span>
  
## <a name="more-about-office-add-ins-security"></a><span data-ttu-id="38fa8-165">Подробнее о безопасности надстройок Office</span><span class="sxs-lookup"><span data-stu-id="38fa8-165">More about Office add-ins security</span></span>

<span data-ttu-id="38fa8-p118">Надстройки Office включают XML-файл манифеста, содержащий метаданные и, что главное, указывающий на веб-приложение, которое содержит весь код и алгоритмы. У разных настроек разные возможности. Например, надстройки могут:</span><span class="sxs-lookup"><span data-stu-id="38fa8-p118">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
  
- <span data-ttu-id="38fa8-169">Выводить данные.</span><span class="sxs-lookup"><span data-stu-id="38fa8-169">Display data.</span></span>

- <span data-ttu-id="38fa8-170">Читать документ пользователя для предоставления контекстных услуг.</span><span class="sxs-lookup"><span data-stu-id="38fa8-170">Read a user's document to provide contextual services.</span></span>

- <span data-ttu-id="38fa8-171">Считывать данные из документа пользователя и записывать их в него для предоставления значений.</span><span class="sxs-lookup"><span data-stu-id="38fa8-171">Read and write data to and from a user's document to provide value to that user.</span></span>

<span data-ttu-id="38fa8-172">Дополнительные сведения о типах и возможностях надстроек Office см. в статье [Общие сведения о платформе надстроек Office](/office/dev/add-ins/overview/office-add-ins) (на английском языке). Особое внимание обратите на раздел "Структура надстройки Office".</span><span class="sxs-lookup"><span data-stu-id="38fa8-172">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="38fa8-p119">Для взаимодействия с документом пользователя надстройке необходимо объявить нужные ей разрешения в манифесте. Пятиуровневая модель разрешений на доступ API JavaScript обеспечивает конфиденциальность и безопасность для надстроек области задач. Большинство надстроек в Магазине Office относятся к уровню ReadWriteDocument, а почти все из них поддерживают по крайней мере уровень ReadDocument. Дополнительные сведения об уровнях разрешений см. в статье [Запрос разрешений на использование API в контенте и в надстройках области задач](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span><span class="sxs-lookup"><span data-stu-id="38fa8-p119">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span>
  
<span data-ttu-id="38fa8-p120">При обновлении манифеста обычно изменения связаны со значком и текстом надстройки. Иногда изменяются сами ее команды. Однако разрешения надстройки не изменяются. Веб-приложение, где выполняется весь код и алгоритм надстроек, может измениться в любое время.</span><span class="sxs-lookup"><span data-stu-id="38fa8-p120">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="38fa8-180">Надстройки обновляются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="38fa8-180">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="38fa8-p121">**Бизнес-надстройки**: так как в этом случае администратор добавил манифест вручную, ему потребуется добавить новый файл манифеста, чтобы применить изменения метаданных. При следующем запуске соответствующего приложения Office надстройка будут обновлена. Веб-приложение может изменяться в любое время.</span><span class="sxs-lookup"><span data-stu-id="38fa8-p121">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span>

    > [!NOTE]
    > <span data-ttu-id="38fa8-184">Администратору не нужно удалять надстройку LOB для обновления.</span><span class="sxs-lookup"><span data-stu-id="38fa8-184">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="38fa8-185">В разделе Надстройки администратор может просто щелкнуть надстройку LOB и выбрать кнопку **Обновления** в правом нижнем углу.</span><span class="sxs-lookup"><span data-stu-id="38fa8-185">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="38fa8-186">Обновление будет работать только в том случае, если версия новой надстройки больше, чем у существующей надстройки.</span><span class="sxs-lookup"><span data-stu-id="38fa8-186">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>

- <span data-ttu-id="38fa8-p123">**Надстройка из Магазина Office**: если надстройка, которую администратор выбрал из Магазина Office, изменилась, она будет обновлена с помощью функции централизованного развертывания при следующем запуске соответствующего приложения Office. Веб-приложение может изменяться в любое время.</span><span class="sxs-lookup"><span data-stu-id="38fa8-p123">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span>
  
## <a name="learn-more"></a><span data-ttu-id="38fa8-190">Подробнее</span><span class="sxs-lookup"><span data-stu-id="38fa8-190">Learn more</span></span>

[<span data-ttu-id="38fa8-191">Управление надстройками в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="38fa8-191">Manage add-ins in the admin center</span></span>](manage-addins-in-the-admin-center.md)

<span data-ttu-id="38fa8-192">[Создайте первую надстройку](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)области задач Word.</span><span class="sxs-lookup"><span data-stu-id="38fa8-192">[Build your first Word task pane add-in](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator).</span></span>

[<span data-ttu-id="38fa8-193">Несовершеннолетние и приобретение надстройок из магазина</span><span class="sxs-lookup"><span data-stu-id="38fa8-193">Minors and acquiring add-ins from the store</span></span>](minors-and-acquiring-addins-from-the-store.md)
  
[<span data-ttu-id="38fa8-194">Для управления надстройными надстройки используйте централизованные cmdlets deployment PowerShell</span><span class="sxs-lookup"><span data-stu-id="38fa8-194">Use Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md)
  
[<span data-ttu-id="38fa8-195">Устранение неполадок. Пользователь не видит надстройки</span><span class="sxs-lookup"><span data-stu-id="38fa8-195">Troubleshoot: User not seeing add-ins</span></span>](/office365/troubleshoot/access-management/user-not-seeing-add-ins)