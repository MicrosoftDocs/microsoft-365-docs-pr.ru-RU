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
description: Научитесь развертывать надстройки для пользователей и групп в вашей организации с помощью централизованного развертывания в центре администратора.
ms.openlocfilehash: 2d3b90a75f38a2c1146c0b0e5470c80b0af2c63f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572277"
---
# <a name="deploy-add-ins-in-the-admin-center"></a><span data-ttu-id="d6def-103">Развертывание надстроек в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="d6def-103">Deploy add-ins in the admin center</span></span>

<span data-ttu-id="d6def-104">Office дополнительные надстройки помогут персонализировать документы и упростить доступ к информации в Интернете (см. [Начало использования Office Add-in).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="d6def-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="d6def-105">В качестве администратора можно развернуть Office дополнительные надстройки для пользователей в вашей организации, используя функцию централизованного развертывания в Microsoft 365 центре.</span><span class="sxs-lookup"><span data-stu-id="d6def-105">As an admin, you can deploy Office add-ins for the users in your organization by using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d6def-106">Централизованное развертывание — это рекомендуемый и наиболее многоастрый способ для большинства администраторов развертывать надстройки для пользователей и групп в организации.</span><span class="sxs-lookup"><span data-stu-id="d6def-106">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span>

<span data-ttu-id="d6def-107">Для получения дополнительной информации о том, как определить, может ли ваша организация поддерживать централизованное развертывание, [см.](centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="d6def-107">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

<span data-ttu-id="d6def-108">Чтобы узнать больше об управлении надстройки после развертывания, [см.](manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="d6def-108">To learn more about managing add-ins after deployment, see [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)</span></span>
  
> [!NOTE]
>  <span data-ttu-id="d6def-109">Для Word, Excel и PowerPoint [используют каталог приложений SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) для развертывания надстройок для пользователей в среде на местах, не имеюной связи с Microsoft 365 и/или поддержкой SharePoint необходимых надстройок.</span><span class="sxs-lookup"><span data-stu-id="d6def-109">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="d6def-110">Для Outlook используйте Exchange управления для развертывания в помещении среды без подключения к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6def-110">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="d6def-111">Рекомендуемый подход к развертыванию надстроек Office</span><span class="sxs-lookup"><span data-stu-id="d6def-111">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="d6def-112">Для развертывание надстройок с помощью поэтапного подхода мы рекомендуем следующее:</span><span class="sxs-lookup"><span data-stu-id="d6def-112">To roll out add-ins by using a phased approach, we recommend the following:</span></span>
  
1. <span data-ttu-id="d6def-113">Разверните надстройку для небольшой группы заинтересованных лиц в организации и сотрудников ИТ-отдела.</span><span class="sxs-lookup"><span data-stu-id="d6def-113">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="d6def-114">Если развертывание успешное, переместись на шаг 2.</span><span class="sxs-lookup"><span data-stu-id="d6def-114">If the deployment is successful, move to step 2.</span></span>
    
2. <span data-ttu-id="d6def-115">Раскатать надстройок для большего чаще лиц в бизнесе.</span><span class="sxs-lookup"><span data-stu-id="d6def-115">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="d6def-116">Опять же, оценить результаты и, в случае успеха, продолжить полное развертывание.</span><span class="sxs-lookup"><span data-stu-id="d6def-116">Again, evaluate the results and, if successful, continue with full deployment.</span></span>
    
3. <span data-ttu-id="d6def-117">Выполните полное развертывание для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="d6def-117">Perform a full rollout to all users.</span></span>
    
<span data-ttu-id="d6def-118">В зависимости от размера целевой аудитории можно добавлять или удалять выкатные шаги.</span><span class="sxs-lookup"><span data-stu-id="d6def-118">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="d6def-119">Развертывание надстройки Office с помощью Центра администрирования</span><span class="sxs-lookup"><span data-stu-id="d6def-119">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="d6def-120">Перед началом работы [определите, работает ли централизованное развертывание надстройок для вашей организации.](centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="d6def-120">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
1. <span data-ttu-id="d6def-121">В центре администратора перейдите на **страницу Параметры** \> **дополнительных ва-си.**</span><span class="sxs-lookup"><span data-stu-id="d6def-121">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span> <span data-ttu-id="d6def-122">Если вы не видите **Страницу дополнения,** перейдите на **страницу Параметры** \>  \> **интегрированных приложений.**</span><span class="sxs-lookup"><span data-stu-id="d6def-122">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** page.</span></span>

2. <span data-ttu-id="d6def-123">Выберите **развертывание надстройок** в верхней части страницы, а затем выберите **Следующий**.</span><span class="sxs-lookup"><span data-stu-id="d6def-123">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d6def-124">Административный центр обновляется для развертывания с помощью интегрированных приложений.</span><span class="sxs-lookup"><span data-stu-id="d6def-124">The admin center is getting updated to deployment experience with Integrated Apps.</span></span> <span data-ttu-id="d6def-125">Интегрированные приложения видны только администраторам Global, в то время как для других старый опыт все еще существует.</span><span class="sxs-lookup"><span data-stu-id="d6def-125">Integrated Apps is only visible to Global administrators, while for others the old experience still exists.</span></span> <span data-ttu-id="d6def-126">Если вы не видите вышеуказанные шаги, перейдите в раздел Централизованное развертывание, **Параметры**  >  **интегрированные приложения.**</span><span class="sxs-lookup"><span data-stu-id="d6def-126">If you don't see the above steps, go to the Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="d6def-127">В верхней части **страницы интегрированных** приложений **выберите дополнения.**</span><span class="sxs-lookup"><span data-stu-id="d6def-127">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

3. <span data-ttu-id="d6def-128">Выберите один из вариантов и следуйте инструкциям.</span><span class="sxs-lookup"><span data-stu-id="d6def-128">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="d6def-129">Если вы выбрали опцию для добавления надстройок из магазина Office Store, сделайте надстройный выбор.</span><span class="sxs-lookup"><span data-stu-id="d6def-129">If you selected the option to add an add-in from the Office Store, make your add-in selection.</span></span> </br>

    <span data-ttu-id="d6def-130">Вы можете просматривать доступные дополнения по категориям: **Предлагаемые для вас ,** **Рейтинг**, или **имя**.</span><span class="sxs-lookup"><span data-stu-id="d6def-130">You can view available add-ins by categories: **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="d6def-131">Только бесплатные надстройки доступны в магазине Office Store.</span><span class="sxs-lookup"><span data-stu-id="d6def-131">Only free add-ins are available from the Office Store.</span></span> <span data-ttu-id="d6def-132">В настоящее время возможность добавления платных надстроек не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="d6def-132">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="d6def-133">После выбора надстройок примите условия для продолжения работы.</span><span class="sxs-lookup"><span data-stu-id="d6def-133">After you select an add-in, accept the terms and conditions to proceed.</span></span> <br/> 

    > [!NOTE]
    > <span data-ttu-id="d6def-134">С помощью Office Store обновления и усовершенствования автоматически развертываются для пользователей.</span><span class="sxs-lookup"><span data-stu-id="d6def-134">With the Office Store option, updates and enhancements are automatically deployed to users.</span></span>

5. <span data-ttu-id="d6def-135">На следующей странице выберите **Все**, **Определенные пользователи или группы** или **Только я**, чтобы указать пользователей, для которых развертывается надстройка.</span><span class="sxs-lookup"><span data-stu-id="d6def-135">On the next page, select **Everyone**, **Specific users/groups**, or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="d6def-136">Используйте поле поиска для поиска конкретных пользователей или групп.</span><span class="sxs-lookup"><span data-stu-id="d6def-136">Use the Search box to find specific users or groups.</span></span> <br/>

    > [!NOTE]
    > <span data-ttu-id="d6def-137">Чтобы узнать о других состояниях, применимых к надстройок, [см.](./manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="d6def-137">To learn about other states that apply to an add-in, see [Add-in states](./manage-addins-in-the-admin-center.md).</span></span>
  
6. <span data-ttu-id="d6def-138">Нажмите **Развернуть**.</span><span class="sxs-lookup"><span data-stu-id="d6def-138">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="d6def-139">При развертывании надстройки появляется зеленый тик.</span><span class="sxs-lookup"><span data-stu-id="d6def-139">A green tick appears when the add-in is deployed.</span></span> <span data-ttu-id="d6def-140">Следуйте инструкциям на странице, чтобы проверить надстройок.</span><span class="sxs-lookup"><span data-stu-id="d6def-140">Follow the on-page instructions to test the add-in.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d6def-141">Пользователям может потребоваться Office для просмотра значка дополнения на ленте приложения.</span><span class="sxs-lookup"><span data-stu-id="d6def-141">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="d6def-142">Outlook надстройки могут занять до 24 часов, чтобы появиться на лентах приложений.</span><span class="sxs-lookup"><span data-stu-id="d6def-142">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span>

8. <span data-ttu-id="d6def-143">После завершения, выберите **Следующий**.</span><span class="sxs-lookup"><span data-stu-id="d6def-143">When finished, select **Next**.</span></span> <span data-ttu-id="d6def-144">Если вы развернуты только для себя, вы можете выбрать **Изменение, который имеет доступ к надстройок для развертывания** для большего времени пользователей.</span><span class="sxs-lookup"><span data-stu-id="d6def-144">If you've deployed to just yourself, you can select **Change who has access to add-in** to deploy to more users.</span></span>

    <span data-ttu-id="d6def-145">Если вы развернули надстройу другим членам организации, следуйте инструкциям, чтобы объявить о развертывании надстройок.</span><span class="sxs-lookup"><span data-stu-id="d6def-145">If you've deployed the add-in to other members of your organization, follow the instructions to announce the deployment of the add-in.</span></span> <br/>
  
    <span data-ttu-id="d6def-146">Это хорошая практика, чтобы информировать пользователей и групп, что развернутое дополнение доступно.</span><span class="sxs-lookup"><span data-stu-id="d6def-146">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="d6def-147">Рассмотрите возможность отправки электронной почты, в которую описывается, когда и как использовать надстройки.</span><span class="sxs-lookup"><span data-stu-id="d6def-147">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="d6def-148">Включите или ссылку на содержимое справки или часто задаваемые вопросы, которые могут помочь пользователям, если у них есть проблемы с надстройки.</span><span class="sxs-lookup"><span data-stu-id="d6def-148">Include or link to Help content or FAQs that might help users if they have problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="d6def-149">Рекомендации при назначении надстройки пользователям и группам</span><span class="sxs-lookup"><span data-stu-id="d6def-149">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="d6def-150">Глобальные администраторы Exchange администраторы могут назначить надстройки всем или конкретным пользователям и группам.</span><span class="sxs-lookup"><span data-stu-id="d6def-150">Global admins and Exchange admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="d6def-151">Каждый вариант имеет ряд особенностей.</span><span class="sxs-lookup"><span data-stu-id="d6def-151">Each option has implications:</span></span>
  
- <span data-ttu-id="d6def-152">**Все** Эта опция присваивает надстройки каждому пользователю в организации.</span><span class="sxs-lookup"><span data-stu-id="d6def-152">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="d6def-153">Используйте этот вариант осторожно и только для тех надстроек, которые действительно применяются во всей организации.</span><span class="sxs-lookup"><span data-stu-id="d6def-153">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span>

- <span data-ttu-id="d6def-154">**Пользователи** Если вы назначаете надстройу отдельному пользователю, а затем развертываете надстройу новому пользователю, необходимо сначала добавить нового пользователя.</span><span class="sxs-lookup"><span data-stu-id="d6def-154">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span>

- <span data-ttu-id="d6def-155">**Группы** При назначении надстройок группе пользователям, добавленным в группу, автоматически назначается надстройа.</span><span class="sxs-lookup"><span data-stu-id="d6def-155">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="d6def-156">Когда пользователь удаляется из группы, пользователь теряет доступ к надстройки.</span><span class="sxs-lookup"><span data-stu-id="d6def-156">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="d6def-157">В любом случае никаких дополнительных действий от администратора не требуется.</span><span class="sxs-lookup"><span data-stu-id="d6def-157">In either case, no additional action is required from the admin.</span></span>

- <span data-ttu-id="d6def-158">**Только я** Если вы назначаете надстройу только себе, надстройа назначается только вашей учетной записи, которая идеально подходит для тестирования надстройок.</span><span class="sxs-lookup"><span data-stu-id="d6def-158">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span>

<span data-ttu-id="d6def-159">Правильный вариант для организации зависит от конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d6def-159">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="d6def-160">Тем не менее, мы рекомендуем делать задания с помощью групп.</span><span class="sxs-lookup"><span data-stu-id="d6def-160">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="d6def-161">Как администратору может быть проще управлять надстройки, используя группы и контролируя членство в этих группах, а не назначать отдельных пользователей каждый раз.</span><span class="sxs-lookup"><span data-stu-id="d6def-161">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="d6def-162">В некоторых ситуациях можно ограничить доступ к небольшому набору пользователей, делая задания конкретным пользователям, назначая пользователей вручную.</span><span class="sxs-lookup"><span data-stu-id="d6def-162">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span>
  
## <a name="more-about-office-add-ins-security"></a><span data-ttu-id="d6def-163">Подробнее Office безопасности дополнительных надстройок</span><span class="sxs-lookup"><span data-stu-id="d6def-163">More about Office add-ins security</span></span>

<span data-ttu-id="d6def-p117">Надстройки Office включают XML-файл манифеста, содержащий метаданные и, что главное, указывающий на веб-приложение, которое содержит весь код и алгоритмы. У разных настроек разные возможности. Например, надстройки могут:</span><span class="sxs-lookup"><span data-stu-id="d6def-p117">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
  
- <span data-ttu-id="d6def-167">Выводить данные.</span><span class="sxs-lookup"><span data-stu-id="d6def-167">Display data.</span></span>

- <span data-ttu-id="d6def-168">Читать документ пользователя для предоставления контекстных услуг.</span><span class="sxs-lookup"><span data-stu-id="d6def-168">Read a user's document to provide contextual services.</span></span>

- <span data-ttu-id="d6def-169">Считывать данные из документа пользователя и записывать их в него для предоставления значений.</span><span class="sxs-lookup"><span data-stu-id="d6def-169">Read and write data to and from a user's document to provide value to that user.</span></span>

<span data-ttu-id="d6def-170">Дополнительные сведения о типах и возможностях надстроек Office см. в статье [Общие сведения о платформе надстроек Office](/office/dev/add-ins/overview/office-add-ins) (на английском языке). Особое внимание обратите на раздел "Структура надстройки Office".</span><span class="sxs-lookup"><span data-stu-id="d6def-170">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="d6def-p118">Для взаимодействия с документом пользователя надстройке необходимо объявить нужные ей разрешения в манифесте. Пятиуровневая модель разрешений на доступ API JavaScript обеспечивает конфиденциальность и безопасность для надстроек области задач. Большинство надстроек в Магазине Office относятся к уровню ReadWriteDocument, а почти все из них поддерживают по крайней мере уровень ReadDocument. Дополнительные сведения об уровнях разрешений см. в статье [Запрос разрешений на использование API в контенте и в надстройках области задач](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span><span class="sxs-lookup"><span data-stu-id="d6def-p118">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span>
  
<span data-ttu-id="d6def-p119">При обновлении манифеста обычно изменения связаны со значком и текстом надстройки. Иногда изменяются сами ее команды. Однако разрешения надстройки не изменяются. Веб-приложение, где выполняется весь код и алгоритм надстроек, может измениться в любое время.</span><span class="sxs-lookup"><span data-stu-id="d6def-p119">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="d6def-178">Надстройки обновляются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d6def-178">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="d6def-p120">**Бизнес-надстройки**: так как в этом случае администратор добавил манифест вручную, ему потребуется добавить новый файл манифеста, чтобы применить изменения метаданных. При следующем запуске соответствующего приложения Office надстройка будут обновлена. Веб-приложение может изменяться в любое время.</span><span class="sxs-lookup"><span data-stu-id="d6def-p120">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d6def-182">Администратору не нужно удалять lob Add-in для выполнения обновления.</span><span class="sxs-lookup"><span data-stu-id="d6def-182">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="d6def-183">В разделе Дополнительные встрой администратор может просто нажать на lob Add-in и **выбрать кнопку обновления** в правом нижнем углу.</span><span class="sxs-lookup"><span data-stu-id="d6def-183">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="d6def-184">Обновление будет работать только в том случае, если версия нового дополнения больше, чем у существующего дополнения.</span><span class="sxs-lookup"><span data-stu-id="d6def-184">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>

- <span data-ttu-id="d6def-p122">**Надстройка из Магазина Office**: если надстройка, которую администратор выбрал из Магазина Office, изменилась, она будет обновлена с помощью функции централизованного развертывания при следующем запуске соответствующего приложения Office. Веб-приложение может изменяться в любое время.</span><span class="sxs-lookup"><span data-stu-id="d6def-p122">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="d6def-188">См. также:</span><span class="sxs-lookup"><span data-stu-id="d6def-188">Related content</span></span>

<span data-ttu-id="d6def-189">[Управление надстройки в центре администратора (статья)](manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="d6def-189">[Manage add-ins in the admin center](manage-addins-in-the-admin-center.md) (article)</span></span>

<span data-ttu-id="d6def-190">[Создайте надстройное дополнение к первому панели задач Word](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) (статья)</span><span class="sxs-lookup"><span data-stu-id="d6def-190">[Build your first Word task pane add-in](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) (article)</span></span>

<span data-ttu-id="d6def-191">[Несовершеннолетние и приобретение надстройок из магазина](minors-and-acquiring-addins-from-the-store.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="d6def-191">[Minors and acquiring add-ins from the store](minors-and-acquiring-addins-from-the-store.md) (article)</span></span>
  
<span data-ttu-id="d6def-192">[Используйте централизованные смеся PowerShell развертывания для управления надстройками](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="d6def-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (article)</span></span>
  
<span data-ttu-id="d6def-193">[Устранение неполадок: Пользователь, не видя надстройки](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (статья)</span><span class="sxs-lookup"><span data-stu-id="d6def-193">[Troubleshoot: User not seeing add-ins](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (article)</span></span>