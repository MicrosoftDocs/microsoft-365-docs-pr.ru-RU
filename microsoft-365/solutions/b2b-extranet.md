---
title: Создание экстрасети B2B с управляемыми гостями
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: Узнайте, как создать сайт или команду экстрасети B2B с управляемыми гостями из партнерской организации.
ms.openlocfilehash: cfb7cc4310cb83f9ce7761c95f021724b7d75faf
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613600"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="482dc-103">Создание экстрасети B2B с управляемыми гостями</span><span class="sxs-lookup"><span data-stu-id="482dc-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="482dc-104">Вы можете использовать [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) для создания экстрасети B2B для совместной работы с партнерской организацией, использующей Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="482dc-104">You can use [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="482dc-105">Это позволяет пользователям самостоятельно зарегистрироваться на сайте экстрасети или в группе и получить доступ через рабочий процесс утверждения.</span><span class="sxs-lookup"><span data-stu-id="482dc-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="482dc-106">С помощью этого метода общего доступа к ресурсам для совместной работы партнерская организация может помочь поддерживать и утверждать гостей на их стороне, снижая нагрузку на ИТ-отдел и позволяя пользователям, знакомым с соглашением о совместной работе, управлять доступом пользователей.</span><span class="sxs-lookup"><span data-stu-id="482dc-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guests on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="482dc-107">В этой статье пошаговая статья посвящена созданию пакета ресурсов (в данном случае это сайт или группа), которые можно использовать совместно с партнерской организацией с помощью модели регистрации для самостоятельного доступа.</span><span class="sxs-lookup"><span data-stu-id="482dc-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="482dc-108">Перед началом создайте сайт или команду, которые вы хотите поделиться с партнерской организацией, и в качестве гостевого общего доступа.</span><span class="sxs-lookup"><span data-stu-id="482dc-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="482dc-109">Дополнительные [сведения см.](collaborate-in-site.md) в [](collaborate-as-team.md) совместной работе с гостями на сайте или совместной работе с гостями в команде.</span><span class="sxs-lookup"><span data-stu-id="482dc-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="482dc-110">Также рекомендуется просмотреть [](create-secure-guest-sharing-environment.md) статью "Создание безопасной среды гостевого общего доступа" для получения сведений о функции безопасности и соответствия требованиям, которые можно использовать для поддержки политик управления при совместной работы с гостями.</span><span class="sxs-lookup"><span data-stu-id="482dc-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="license-requirements"></a><span data-ttu-id="482dc-111">Требования лицензирования</span><span class="sxs-lookup"><span data-stu-id="482dc-111">License requirements</span></span>

<span data-ttu-id="482dc-112">Для использования этой функции требуется лицензия Azure AD Premium P2.</span><span class="sxs-lookup"><span data-stu-id="482dc-112">Using this feature requires an Azure AD Premium P2 license.</span></span> 

<span data-ttu-id="482dc-113">Специализированные облака, такие как Azure Germany и Azure China 21Vianet, в настоящее время недоступны для использования.</span><span class="sxs-lookup"><span data-stu-id="482dc-113">Specialized clouds, such as Azure Germany and Azure China 21Vianet, are not currently available for use.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="482dc-114">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="482dc-114">Video demonstration</span></span>

<span data-ttu-id="482dc-115">В этом видео демонстрируются процедуры, охватываемых в этой статье.</span><span class="sxs-lookup"><span data-stu-id="482dc-115">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="482dc-116">Подключение партнерской организации</span><span class="sxs-lookup"><span data-stu-id="482dc-116">Connect the partner organization</span></span>

<span data-ttu-id="482dc-117">Чтобы пригласить гостей из партнерской организации, необходимо добавить домен партнера как подключенную организацию в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="482dc-117">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="482dc-118">Добавление подключенной организации</span><span class="sxs-lookup"><span data-stu-id="482dc-118">To add a connected organization</span></span>
1. <span data-ttu-id="482dc-119">В [Azure Active Directory щелкните](https://aad.portal.azure.com) **"Управление удостоверением".**</span><span class="sxs-lookup"><span data-stu-id="482dc-119">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="482dc-120">Щелкните **"Подключенные организации".**</span><span class="sxs-lookup"><span data-stu-id="482dc-120">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="482dc-121">Нажмите **кнопку "Добавить подключенную организацию".**</span><span class="sxs-lookup"><span data-stu-id="482dc-121">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="482dc-122">Введите имя и описание организации, а затем нажмите кнопку **"Далее: каталог + домен".**</span><span class="sxs-lookup"><span data-stu-id="482dc-122">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="482dc-123">Нажмите **кнопку "Добавить каталог+ домен".**</span><span class="sxs-lookup"><span data-stu-id="482dc-123">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="482dc-124">Введите домен для организации, которую нужно подключить, и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="482dc-124">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="482dc-125">Нажмите **кнопку "Подключиться",** а затем нажмите **кнопку "Далее: спонсоры".**</span><span class="sxs-lookup"><span data-stu-id="482dc-125">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="482dc-126">Добавьте людей из вашей организации или организации, к которым вы подключаете тех, к кому вы хотите утвердить доступ для гостей.</span><span class="sxs-lookup"><span data-stu-id="482dc-126">Add people from your organization or the organization that you're connecting to who you want to approve access for guests.</span></span>
10. <span data-ttu-id="482dc-127">Нажмите **кнопку "Далее": просмотр и создание.**</span><span class="sxs-lookup"><span data-stu-id="482dc-127">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="482dc-128">Просмотрите выбранные параметры и нажмите кнопку **"Создать".**</span><span class="sxs-lookup"><span data-stu-id="482dc-128">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Снимок экрана: страница подключенных организаций в Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="482dc-130">Выбор ресурсов для обмена</span><span class="sxs-lookup"><span data-stu-id="482dc-130">Choose the resources to share</span></span>

<span data-ttu-id="482dc-131">Первым шагом при выборе ресурсов для обмена с партнерской организацией является создание каталога, в котором они будут содержаться.</span><span class="sxs-lookup"><span data-stu-id="482dc-131">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="482dc-132">Создание каталога</span><span class="sxs-lookup"><span data-stu-id="482dc-132">To create a catalog</span></span>
1. <span data-ttu-id="482dc-133">В [Azure Active Directory щелкните](https://aad.portal.azure.com) **"Управление удостоверением".**</span><span class="sxs-lookup"><span data-stu-id="482dc-133">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="482dc-134">Щелкните **каталоги.**</span><span class="sxs-lookup"><span data-stu-id="482dc-134">Click **Catalogs**.</span></span>
3. <span data-ttu-id="482dc-135">Щелкните **"Новый каталог"**.</span><span class="sxs-lookup"><span data-stu-id="482dc-135">Click **New catalog**.</span></span>
4. <span data-ttu-id="482dc-136">Введите имя и описание каталога,  а также убедитесь, что для обоих этих ок есть "Да" и "Включено" для **внешних пользователей.** </span><span class="sxs-lookup"><span data-stu-id="482dc-136">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="482dc-137">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="482dc-137">Click **Create**.</span></span>

   ![Снимок экрана: страница каталогов в службе управления удостоверениями Azure Active Directory](../media/identity-governance-catalogs.png)

<span data-ttu-id="482dc-139">После создания каталога добавьте сайт или команду SharePoint, которые вы хотите поделиться с партнерской организацией.</span><span class="sxs-lookup"><span data-stu-id="482dc-139">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="482dc-140">Добавление ресурсов в каталог</span><span class="sxs-lookup"><span data-stu-id="482dc-140">To add resources to a catalog</span></span>
1. <span data-ttu-id="482dc-141">В средстве управления удостоверениями Azure AD щелкните **"Каталоги",** а затем выберите каталог, в который требуется добавить ресурсы.</span><span class="sxs-lookup"><span data-stu-id="482dc-141">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="482dc-142">Щелкните **"Ресурсы"** и выберите **"Добавить ресурсы".**</span><span class="sxs-lookup"><span data-stu-id="482dc-142">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="482dc-143">Выберите группы или сайты SharePoint, которые вы хотите включить в экстрасеть, и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="482dc-143">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Снимок экрана: страница ресурсов каталога в службе управления удостоверением Azure Active Directory](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="482dc-145">После определения ресурсов, к которым вы хотите предоставить доступ, необходимо создать пакет доступа, который определяет тип доступа, который предоставляется пользователям-партнерам, и процесс утверждения новых пользователей партнеров, запрашивающих доступ.</span><span class="sxs-lookup"><span data-stu-id="482dc-145">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="482dc-146">Создание пакета доступа</span><span class="sxs-lookup"><span data-stu-id="482dc-146">To create an access package</span></span>
1. <span data-ttu-id="482dc-147">В службе управления удостоверениями Azure AD щелкните **"Каталоги",** а затем выберите каталог, в котором требуется создать пакет доступа.</span><span class="sxs-lookup"><span data-stu-id="482dc-147">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="482dc-148">Щелкните **пакеты Access** и выберите **"Новый пакет доступа".**</span><span class="sxs-lookup"><span data-stu-id="482dc-148">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="482dc-149">Введите имя и описание пакета доступа и нажмите кнопку **"Далее: роли ресурсов".**</span><span class="sxs-lookup"><span data-stu-id="482dc-149">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="482dc-150">Выберите ресурсы из каталога, который вы хотите использовать для экстрасети.</span><span class="sxs-lookup"><span data-stu-id="482dc-150">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="482dc-151">Для каждого ресурса в столбце **"Роль"** выберите роль пользователя, которую вы хотите предоставить гостям, которые используют экстрасеть.</span><span class="sxs-lookup"><span data-stu-id="482dc-151">For each resource, in the **Role** column, choose the user role you want to grant to the guests who use the extranet.</span></span>
6. <span data-ttu-id="482dc-152">Нажмите **кнопку "Далее": запросы.**</span><span class="sxs-lookup"><span data-stu-id="482dc-152">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="482dc-153">Under **Users who can request access**, choose For users not in your **directory**.</span><span class="sxs-lookup"><span data-stu-id="482dc-153">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="482dc-154">Убедитесь, что выбран **параметр "Определенные подключенные** организации" и нажмите кнопку **"Добавить каталоги".**</span><span class="sxs-lookup"><span data-stu-id="482dc-154">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="482dc-155">Выберите подключенную организацию, которую вы добавили ранее, и нажмите кнопку **"Выбрать"**</span><span class="sxs-lookup"><span data-stu-id="482dc-155">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="482dc-156">В **области "Утверждение"** выберите **"Да** для **утверждения".**</span><span class="sxs-lookup"><span data-stu-id="482dc-156">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="482dc-157">В **области "Первый автор"** выберите одного из спонсоров, добавленных ранее, или выберите определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="482dc-157">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="482dc-158">Нажмите **кнопку "Добавить откат"** и выберите утвержденного.</span><span class="sxs-lookup"><span data-stu-id="482dc-158">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="482dc-159">В **области "Включить"** выберите **"Да".**</span><span class="sxs-lookup"><span data-stu-id="482dc-159">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="482dc-160">Нажмите **кнопку "Далее": жизненный цикл.**</span><span class="sxs-lookup"><span data-stu-id="482dc-160">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="482dc-161">Выберите параметры срока действия и проверки доступа, которые вы хотите использовать, а затем нажмите кнопку **"Далее: Просмотр+ Создать"**.</span><span class="sxs-lookup"><span data-stu-id="482dc-161">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="482dc-162">Просмотрите параметры и нажмите кнопку **"Создать".**</span><span class="sxs-lookup"><span data-stu-id="482dc-162">Review your settings, and then click **Create**.</span></span>

    ![Снимок экрана: экран пакетов доступа в службе управления удостоверениями Azure Active Directory](../media/identity-governance-access-packages.png)

<span data-ttu-id="482dc-164">Если вы сотрудничают с крупной организацией, вам может потребоваться скрыть пакет доступа.</span><span class="sxs-lookup"><span data-stu-id="482dc-164">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="482dc-165">Если пакет скрыт, пользователи партнерской организации не увидят пакет на своем портале *My Access.*</span><span class="sxs-lookup"><span data-stu-id="482dc-165">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="482dc-166">Вместо этого им необходимо отправить прямую ссылку для регистрации в пакете.</span><span class="sxs-lookup"><span data-stu-id="482dc-166">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="482dc-167">Скрытие пакета доступа может уменьшить количество недопустимых запросов на доступ, а также помочь организовать доступные пакеты доступа на портале партнерской организации.</span><span class="sxs-lookup"><span data-stu-id="482dc-167">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="482dc-168">Настройка скрытого пакета доступа</span><span class="sxs-lookup"><span data-stu-id="482dc-168">To set an access package to hidden</span></span>
1. <span data-ttu-id="482dc-169">В службе управления удостоверениями Azure AD щелкните **пакеты Access** и выберите пакет доступа.</span><span class="sxs-lookup"><span data-stu-id="482dc-169">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="482dc-170">На странице **"Обзор"** нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="482dc-170">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="482dc-171">В **области "Свойства"** выберите **"Да** **для скрытого"** и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="482dc-171">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![Снимок экрана со свойствами пакета правки доступа](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="482dc-173">Приглашение партнеров</span><span class="sxs-lookup"><span data-stu-id="482dc-173">Invite partner users</span></span>

<span data-ttu-id="482dc-174">Если пакет доступа скрыт, необходимо отправить прямую ссылку партнерской организации, чтобы они могли запросить доступ к сайту или команде.</span><span class="sxs-lookup"><span data-stu-id="482dc-174">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="482dc-175">Поиск ссылки на портал доступа</span><span class="sxs-lookup"><span data-stu-id="482dc-175">To find the access portal link</span></span>
1. <span data-ttu-id="482dc-176">В службе управления удостоверениями Azure AD щелкните **пакеты Access** и выберите пакет доступа.</span><span class="sxs-lookup"><span data-stu-id="482dc-176">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="482dc-177">На странице **"Обзор"** **щелкните ссылку "Копировать в буфер** обмена" для ссылки **портала "Мой доступ".**</span><span class="sxs-lookup"><span data-stu-id="482dc-177">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Снимок экрана: свойства пакета доступа со ссылкой на портал доступа](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="482dc-179">После копирования ссылки вы можете поделиться ссылкой со своим контактом в партнерской организации, и они смогут отправить ее пользователям в своей группе совместной работы.</span><span class="sxs-lookup"><span data-stu-id="482dc-179">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="482dc-180">См. также</span><span class="sxs-lookup"><span data-stu-id="482dc-180">See Also</span></span>

[<span data-ttu-id="482dc-181">Создание безопасной среды гостевого общего доступа</span><span class="sxs-lookup"><span data-stu-id="482dc-181">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)
