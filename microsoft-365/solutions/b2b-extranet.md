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
description: Узнайте, как создать сайт экстрасети B2B или команду с управляемыми гостями из организации-партнера.
ms.openlocfilehash: f9b8d9326f302233ed85c9d168fdf6f343dc6cbf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904760"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="9298b-103">Создание экстрасети B2B с управляемыми гостями</span><span class="sxs-lookup"><span data-stu-id="9298b-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="9298b-104">Управление правами [на использование Azure Active Directory](/azure/active-directory/governance/entitlement-management-overview) можно использовать для создания экстрасети B2B для совместной работы с организацией-партнером, использующей Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9298b-104">You can use [Azure Active Directory Entitlement Management](/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="9298b-105">Это позволяет пользователям самостоятельно зарегистрироваться на сайте экстрасети или в команде и получать доступ через рабочий процесс утверждения.</span><span class="sxs-lookup"><span data-stu-id="9298b-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="9298b-106">С помощью этого метода обмена ресурсами для совместной работы организация-партнер может помочь поддерживать и утверждать гостей на их конце, уменьшая нагрузку на ИТ-отдел и позволяя тем, кто наиболее знаком с соглашением о сотрудничестве, управлять доступом пользователей.</span><span class="sxs-lookup"><span data-stu-id="9298b-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guests on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="9298b-107">В этой статье пошаговая статья посвящена созданию пакета ресурсов (в данном случае сайта или группы), которые можно делиться с организацией-партнером с помощью модели регистрации доступа к самообслуживке.</span><span class="sxs-lookup"><span data-stu-id="9298b-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="9298b-108">Перед началом создайте сайт или команду, которые вы хотите поделиться с организацией-партнером и включить его для общего доступа к гостю.</span><span class="sxs-lookup"><span data-stu-id="9298b-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="9298b-109">Дополнительные [сведения см. в](collaborate-in-site.md) совместной работе с гостями на сайте или в совместной работе с гостями [в группе.](collaborate-as-team.md)</span><span class="sxs-lookup"><span data-stu-id="9298b-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="9298b-110">Кроме того, рекомендуется [](create-secure-guest-sharing-environment.md) просмотреть создание безопасной среды обмена гостями для получения сведений об особенностях безопасности и соответствия требованиям, которые можно использовать для поддержания политик управления при совместном сотрудничестве с гостями.</span><span class="sxs-lookup"><span data-stu-id="9298b-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="license-requirements"></a><span data-ttu-id="9298b-111">Требования лицензирования</span><span class="sxs-lookup"><span data-stu-id="9298b-111">License requirements</span></span>

<span data-ttu-id="9298b-112">Для использования этой функции требуется лицензия Azure AD Premium P2.</span><span class="sxs-lookup"><span data-stu-id="9298b-112">Using this feature requires an Azure AD Premium P2 license.</span></span> 

<span data-ttu-id="9298b-113">Специализированные облака, такие как Azure Germany и Azure China 21Vianet, в настоящее время недоступны для использования.</span><span class="sxs-lookup"><span data-stu-id="9298b-113">Specialized clouds, such as Azure Germany and Azure China 21Vianet, are not currently available for use.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="9298b-114">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="9298b-114">Video demonstration</span></span>

<span data-ttu-id="9298b-115">Это видео демонстрирует процедуры, охватываемых в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9298b-115">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="9298b-116">Подключение организации-партнера</span><span class="sxs-lookup"><span data-stu-id="9298b-116">Connect the partner organization</span></span>

<span data-ttu-id="9298b-117">Чтобы пригласить гостей из организации-партнера, необходимо добавить домен партнера в качестве связанной организации в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9298b-117">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="9298b-118">Добавление подключенной организации</span><span class="sxs-lookup"><span data-stu-id="9298b-118">To add a connected organization</span></span>
1. <span data-ttu-id="9298b-119">В [Azure Active Directory](https://aad.portal.azure.com)нажмите **кнопку Управление удостоверением**.</span><span class="sxs-lookup"><span data-stu-id="9298b-119">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="9298b-120">Щелкните **Подключенные организации**.</span><span class="sxs-lookup"><span data-stu-id="9298b-120">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="9298b-121">Щелкните **Добавить подключенную организацию**.</span><span class="sxs-lookup"><span data-stu-id="9298b-121">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="9298b-122">Введите имя и описание организации, а затем нажмите **кнопку Далее: Домен Directory +**.</span><span class="sxs-lookup"><span data-stu-id="9298b-122">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="9298b-123">Нажмите **кнопку Добавить каталог + домен**.</span><span class="sxs-lookup"><span data-stu-id="9298b-123">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="9298b-124">Введите домен для организации, которую необходимо подключить, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9298b-124">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="9298b-125">Нажмите **кнопку Подключиться,** а затем **нажмите кнопку Далее: Спонсоры**.</span><span class="sxs-lookup"><span data-stu-id="9298b-125">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="9298b-126">Добавьте людей из вашей организации или организации, к которым вы подключаете, чтобы утвердить доступ для гостей.</span><span class="sxs-lookup"><span data-stu-id="9298b-126">Add people from your organization or the organization that you're connecting to who you want to approve access for guests.</span></span>
10. <span data-ttu-id="9298b-127">Щелкните **Далее: проверка и создание**.</span><span class="sxs-lookup"><span data-stu-id="9298b-127">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="9298b-128">Просмотрите выбранные параметры и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9298b-128">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Снимок экрана страницы подключенных организаций в Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="9298b-130">Выбор ресурсов для обмена</span><span class="sxs-lookup"><span data-stu-id="9298b-130">Choose the resources to share</span></span>

<span data-ttu-id="9298b-131">Первым шагом в выборе ресурсов для совместной работы с организацией-партнером является создание каталога, который будет содержать их.</span><span class="sxs-lookup"><span data-stu-id="9298b-131">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="9298b-132">Создание каталога</span><span class="sxs-lookup"><span data-stu-id="9298b-132">To create a catalog</span></span>
1. <span data-ttu-id="9298b-133">В [Azure Active Directory](https://aad.portal.azure.com)нажмите **кнопку Управление удостоверением**.</span><span class="sxs-lookup"><span data-stu-id="9298b-133">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="9298b-134">Щелкните **Каталоги**.</span><span class="sxs-lookup"><span data-stu-id="9298b-134">Click **Catalogs**.</span></span>
3. <span data-ttu-id="9298b-135">Нажмите **кнопку Новый каталог**.</span><span class="sxs-lookup"><span data-stu-id="9298b-135">Click **New catalog**.</span></span>
4. <span data-ttu-id="9298b-136">Введите имя и описание для  каталога  и убедитесь, что включено и включено для внешних **пользователей,** оба за набором да .</span><span class="sxs-lookup"><span data-stu-id="9298b-136">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="9298b-137">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9298b-137">Click **Create**.</span></span>

   ![Снимок экрана страницы каталогов в Azure Active Directory Identity Governance](../media/identity-governance-catalogs.png)

<span data-ttu-id="9298b-139">После создания каталога добавьте сайт SharePoint или команду, которые вы хотите поделиться с организацией-партнером.</span><span class="sxs-lookup"><span data-stu-id="9298b-139">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="9298b-140">Добавление ресурсов в каталог</span><span class="sxs-lookup"><span data-stu-id="9298b-140">To add resources to a catalog</span></span>
1. <span data-ttu-id="9298b-141">В Azure AD Identity Governance щелкните **Каталоги,** а затем щелкните каталог, в котором необходимо добавить ресурсы.</span><span class="sxs-lookup"><span data-stu-id="9298b-141">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="9298b-142">Щелкните **Ресурсы** и нажмите **кнопку Добавить ресурсы**.</span><span class="sxs-lookup"><span data-stu-id="9298b-142">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="9298b-143">Выберите группы или сайты SharePoint, которые необходимо включить в свою экстрасеть, а затем нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9298b-143">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Снимок экрана страницы ресурсов каталога в Azure Active Directory Identity Governance](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="9298b-145">После определения ресурсов, которыми вы хотите поделиться, следующим шагом является создание пакета доступа, который определяет тип доступа, который предоставляется пользователям-партнерам, и процесс утверждения для новых пользователей-партнеров, запрашивающих доступ.</span><span class="sxs-lookup"><span data-stu-id="9298b-145">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="9298b-146">Создание пакета доступа</span><span class="sxs-lookup"><span data-stu-id="9298b-146">To create an access package</span></span>
1. <span data-ttu-id="9298b-147">В Azure AD Identity Governance щелкните **Каталоги,** а затем щелкните каталог, в котором необходимо создать пакет доступа.</span><span class="sxs-lookup"><span data-stu-id="9298b-147">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="9298b-148">Щелкните **пакеты Access** и нажмите **кнопку Новый пакет доступа.**</span><span class="sxs-lookup"><span data-stu-id="9298b-148">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="9298b-149">Введите имя и описание пакета доступа, а затем нажмите **кнопку Далее: Роли ресурса**.</span><span class="sxs-lookup"><span data-stu-id="9298b-149">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="9298b-150">Выберите ресурсы из каталога, которые необходимо использовать для экстрасети.</span><span class="sxs-lookup"><span data-stu-id="9298b-150">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="9298b-151">Для каждого ресурса в столбце **Роль** выберите роль пользователя, которую вы хотите предоставить гостям, которые используют экстрасети.</span><span class="sxs-lookup"><span data-stu-id="9298b-151">For each resource, in the **Role** column, choose the user role you want to grant to the guests who use the extranet.</span></span>
6. <span data-ttu-id="9298b-152">Нажмите **кнопку Далее: Запросы**.</span><span class="sxs-lookup"><span data-stu-id="9298b-152">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="9298b-153">В **статье Пользователи, которые могут запрашивать доступ,** выберите **Для пользователей, не в каталоге**.</span><span class="sxs-lookup"><span data-stu-id="9298b-153">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="9298b-154">Убедитесь, что выбран параметр **"Конкретные подключенные** организации", а затем нажмите **кнопку Добавить каталоги.**</span><span class="sxs-lookup"><span data-stu-id="9298b-154">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="9298b-155">Выберите подключенную организацию, которую вы добавили ранее, и нажмите кнопку **Выберите**</span><span class="sxs-lookup"><span data-stu-id="9298b-155">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="9298b-156">В **соответствии с утверждением** выберите **Да** для **утверждения.**</span><span class="sxs-lookup"><span data-stu-id="9298b-156">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="9298b-157">В **первом утверждении** выберите один из спонсоров, которые вы добавили ранее, или выберите конкретного пользователя.</span><span class="sxs-lookup"><span data-stu-id="9298b-157">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="9298b-158">Нажмите **кнопку Добавить откат** и выберите одобрение отката.</span><span class="sxs-lookup"><span data-stu-id="9298b-158">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="9298b-159">В **статье Включить** выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="9298b-159">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="9298b-160">Нажмите **кнопку Далее: жизненный цикл**.</span><span class="sxs-lookup"><span data-stu-id="9298b-160">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="9298b-161">Выберите параметры проверки истечения срока действия и доступа, которые необходимо использовать, а затем нажмите **кнопку Далее: Обзор + Создание**.</span><span class="sxs-lookup"><span data-stu-id="9298b-161">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="9298b-162">Просмотрите параметры и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9298b-162">Review your settings, and then click **Create**.</span></span>

    ![Снимок экрана экрана пакетов доступа в Azure Active Directory Identity Governance](../media/identity-governance-access-packages.png)

<span data-ttu-id="9298b-164">Если вы в партнерстве с крупной организацией, возможно, захотите скрыть пакет доступа.</span><span class="sxs-lookup"><span data-stu-id="9298b-164">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="9298b-165">Если пакет скрыт, пользователи в организации-партнере не увидят пакет на портале *My Access.*</span><span class="sxs-lookup"><span data-stu-id="9298b-165">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="9298b-166">Вместо этого им необходимо отправить прямую ссылку для регистрации пакета.</span><span class="sxs-lookup"><span data-stu-id="9298b-166">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="9298b-167">Сокрытие пакета доступа может уменьшить количество ненадлежащих запросов на доступ, а также помочь сохранить доступные пакеты доступа, организованные на портале организации-партнера.</span><span class="sxs-lookup"><span data-stu-id="9298b-167">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="9298b-168">Настройка пакета доступа к скрытому</span><span class="sxs-lookup"><span data-stu-id="9298b-168">To set an access package to hidden</span></span>
1. <span data-ttu-id="9298b-169">В Azure AD Identity Governance щелкните **пакеты Access** и нажмите кнопку пакет доступа.</span><span class="sxs-lookup"><span data-stu-id="9298b-169">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="9298b-170">На странице **Обзор** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="9298b-170">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="9298b-171">В **статье Свойства** выберите **Да** для **скрытых** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9298b-171">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![Снимок экрана свойства пакета редактирования доступа](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="9298b-173">Приглашение пользователей-партнеров</span><span class="sxs-lookup"><span data-stu-id="9298b-173">Invite partner users</span></span>

<span data-ttu-id="9298b-174">Если пакет доступа установлен скрытым, необходимо отправить прямую ссылку в организацию-партнер, чтобы они могли запрашивать доступ к вашему сайту или команде.</span><span class="sxs-lookup"><span data-stu-id="9298b-174">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="9298b-175">Поиск ссылки портала доступа</span><span class="sxs-lookup"><span data-stu-id="9298b-175">To find the access portal link</span></span>
1. <span data-ttu-id="9298b-176">В Azure AD Identity Governance щелкните **пакеты Access** и нажмите кнопку пакет доступа.</span><span class="sxs-lookup"><span data-stu-id="9298b-176">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="9298b-177">На странице **Обзор** щелкните **Скопируйте ссылку на буфер обмена** для ссылки **портала "Мой доступ".**</span><span class="sxs-lookup"><span data-stu-id="9298b-177">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Снимок экрана свойств пакета доступа со ссылкой на портал доступа](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="9298b-179">После скопив ссылку, вы можете поделиться ссылкой со своим контактом в организации-партнере, и они могут отправить ее пользователям в их команде совместной работы.</span><span class="sxs-lookup"><span data-stu-id="9298b-179">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="9298b-180">См. также</span><span class="sxs-lookup"><span data-stu-id="9298b-180">See Also</span></span>

[<span data-ttu-id="9298b-181">Создание безопасной среды гостевого общего доступа</span><span class="sxs-lookup"><span data-stu-id="9298b-181">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)