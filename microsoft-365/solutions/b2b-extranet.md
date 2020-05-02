---
title: Создание экстрасети B2B с управляемыми гостями
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
ms.custom:
- M365solutions
localization_priority: Normal
f1.keywords: NOCSH
description: Узнайте, как создать сайт или группу экстрасети B2B с управляемыми гостевыми пользователями из партнерской организации.
ms.openlocfilehash: 3a1faab90907daf9c48ec02c51eb272187fb0fde
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/01/2020
ms.locfileid: "44001707"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="913c6-103">Создание экстрасети B2B с управляемыми гостями</span><span class="sxs-lookup"><span data-stu-id="913c6-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="913c6-104">С помощью [управления обслуживанием Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) вы можете создать экстрасеть B2B для совместной работы с партнерской организацией, в которой используется Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="913c6-104">You can use [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="913c6-105">Это позволяет пользователям самостоятельно регистрироваться на сайте или группе экстрасети и получать доступ с помощью рабочего процесса утверждения.</span><span class="sxs-lookup"><span data-stu-id="913c6-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="913c6-106">С помощью этого метода совместного использования ресурсов для совместной работы Партнерская организация может способствовать обслуживанию и утверждению гостевых пользователей, уменьшая нагрузку на ИТ-отдел и предоставляя им все, кто знаком с соглашением о совместной работе для управления доступом пользователей.</span><span class="sxs-lookup"><span data-stu-id="913c6-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guest users on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="913c6-107">В этой статье описано, как создать пакет ресурсов (в данном случае, на сайте или в группе), который можно предоставить партнерской организации через модель регистрации самостоятельного доступа.</span><span class="sxs-lookup"><span data-stu-id="913c6-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="913c6-108">Прежде чем приступать к работе, создайте сайт или рабочую группу, к которой вы хотите предоставить доступ партнерской организации, и включите ее для общего доступа гостей.</span><span class="sxs-lookup"><span data-stu-id="913c6-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="913c6-109">Для получения дополнительных сведений ознакомьтесь со статьей [Совместная работа с гостями на сайте](collaborate-in-site.md) или [Совместная работа с гостями в группе](collaborate-as-team.md) .</span><span class="sxs-lookup"><span data-stu-id="913c6-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="913c6-110">Кроме того, рекомендуется ознакомиться со сведениями о том, [как создать безопасную среду общего доступа](create-secure-guest-sharing-environment.md) , чтобы получить сведения о функциях обеспечения безопасности и соответствия требованиям, которые можно использовать для поддержки политик управления при совместной работе с гостями.</span><span class="sxs-lookup"><span data-stu-id="913c6-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="connect-the-partner-organization"></a><span data-ttu-id="913c6-111">Подключение партнерской организации</span><span class="sxs-lookup"><span data-stu-id="913c6-111">Connect the partner organization</span></span>

<span data-ttu-id="913c6-112">Чтобы пригласить гостей из партнерской организации, необходимо добавить домен партнера в качестве подключенной Организации в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="913c6-112">In order to invite guests from a partner organization, you need to add the the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="913c6-113">Добавление подключенной Организации</span><span class="sxs-lookup"><span data-stu-id="913c6-113">To add a connected organization</span></span>
1. <span data-ttu-id="913c6-114">В [Azure Active Directory](https://aad.portal.azure.com)щелкните **Управление удостоверениями**.</span><span class="sxs-lookup"><span data-stu-id="913c6-114">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="913c6-115">Щелкните элемент **подключенные Организации**.</span><span class="sxs-lookup"><span data-stu-id="913c6-115">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="913c6-116">Щелкните **Добавить подключенную организацию**.</span><span class="sxs-lookup"><span data-stu-id="913c6-116">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="913c6-117">Введите имя и описание организации, а затем нажмите кнопку **Далее: Каталог и домен**.</span><span class="sxs-lookup"><span data-stu-id="913c6-117">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="913c6-118">Нажмите кнопку **Добавить каталог + домен**.</span><span class="sxs-lookup"><span data-stu-id="913c6-118">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="913c6-119">Введите домен для Организации, к которой требуется подключиться, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="913c6-119">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="913c6-120">Нажмите кнопку **подключить**, а затем нажмите кнопку **Далее: Спонсоры**.</span><span class="sxs-lookup"><span data-stu-id="913c6-120">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="913c6-121">Добавьте людей из вашей организации или организации, к которой вы подключаетесь, к которым вы хотите утвердить доступ для гостей.</span><span class="sxs-lookup"><span data-stu-id="913c6-121">Add people from your organization or the organization that you're connecting to who you want to approve access for guest users.</span></span>
10. <span data-ttu-id="913c6-122">Нажмите кнопку **Далее: Проверка + создать**.</span><span class="sxs-lookup"><span data-stu-id="913c6-122">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="913c6-123">Просмотрите выбранные параметры и нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="913c6-123">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Снимок экрана со страницей "подключенные организации" в Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="913c6-125">Выбор ресурсов для совместного использования</span><span class="sxs-lookup"><span data-stu-id="913c6-125">Choose the resources to share</span></span>

<span data-ttu-id="913c6-126">Первый шаг в выборе ресурсов для совместного использования с партнерской организацией состоит в создании каталога, в котором они должны содержаться.</span><span class="sxs-lookup"><span data-stu-id="913c6-126">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="913c6-127">Создание каталога</span><span class="sxs-lookup"><span data-stu-id="913c6-127">To create a catalog</span></span>
1. <span data-ttu-id="913c6-128">В [Azure Active Directory](https://aad.portal.azure.com)щелкните **Управление удостоверениями**.</span><span class="sxs-lookup"><span data-stu-id="913c6-128">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="913c6-129">Щелкните **каталоги**.</span><span class="sxs-lookup"><span data-stu-id="913c6-129">Click **Catalogs**.</span></span>
3. <span data-ttu-id="913c6-130">Нажмите кнопку **создать каталог**.</span><span class="sxs-lookup"><span data-stu-id="913c6-130">Click **New catalog**.</span></span>
4. <span data-ttu-id="913c6-131">Введите имя и описание каталога и **Убедитесь, что** для **внешних пользователей** задано значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="913c6-131">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="913c6-132">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="913c6-132">Click **Create**.</span></span>

   ![Снимок экрана: страница каталогов в управлении удостоверениями Azure Active Directory](../media/identity-governance-catalogs.png)

<span data-ttu-id="913c6-134">После создания каталога вы добавляете сайт или группу SharePoint, к которым вы хотите предоставить доступ партнерской организации.</span><span class="sxs-lookup"><span data-stu-id="913c6-134">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="913c6-135">Добавление ресурсов в каталог</span><span class="sxs-lookup"><span data-stu-id="913c6-135">To add resources to a catalog</span></span>
1. <span data-ttu-id="913c6-136">В разделе Управление удостоверениями Azure AD щелкните **каталоги**, а затем выберите каталог, в который требуется добавить ресурсы.</span><span class="sxs-lookup"><span data-stu-id="913c6-136">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="913c6-137">Щелкните **ресурсы** , а затем — **Добавить ресурсы**.</span><span class="sxs-lookup"><span data-stu-id="913c6-137">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="913c6-138">Выберите сайты Teams или SharePoint, которые вы хотите включить в экстрасеть, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="913c6-138">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Снимок экрана: страница ресурсов каталога в управлении удостоверениями Azure Active Directory](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="913c6-140">После определения ресурсов, к которым вы хотите предоставить общий доступ, следующим шагом является создание пакета Access, который определяет тип доступа, предоставленный пользователям-партнерам, и процесс утверждения для новых партнеров-пользователей, запрашивающих доступ.</span><span class="sxs-lookup"><span data-stu-id="913c6-140">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="913c6-141">Создание пакета Access</span><span class="sxs-lookup"><span data-stu-id="913c6-141">To create an access package</span></span>
1. <span data-ttu-id="913c6-142">В разделе Управление удостоверениями Azure AD щелкните **каталоги**, а затем выберите каталог, в котором нужно создать пакет Access.</span><span class="sxs-lookup"><span data-stu-id="913c6-142">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="913c6-143">Щелкните **пакеты Access**, а затем — **новый пакет Access**.</span><span class="sxs-lookup"><span data-stu-id="913c6-143">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="913c6-144">Введите имя и описание для пакета Access, а затем нажмите кнопку **Далее: роли ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="913c6-144">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="913c6-145">Выберите ресурсы из каталога, который вы хотите использовать для экстрасети.</span><span class="sxs-lookup"><span data-stu-id="913c6-145">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="913c6-146">Для каждого ресурса в столбце **роль** выберите роль пользователя, которую необходимо предоставить гостям, использующим экстрасеть.</span><span class="sxs-lookup"><span data-stu-id="913c6-146">For each resource, in the **Role** column, choose the user role you want to grant to the guest users who use the extranet.</span></span>
6. <span data-ttu-id="913c6-147">Нажмите кнопку **Далее: запросы**.</span><span class="sxs-lookup"><span data-stu-id="913c6-147">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="913c6-148">В разделе **Пользователи, которые могут запрашивать доступ**, выберите для пользователей, не находящихся **в вашем каталоге**.</span><span class="sxs-lookup"><span data-stu-id="913c6-148">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="913c6-149">Убедитесь, что выбран параметр **конкретные подключенные Организации** , а затем нажмите кнопку **Добавить каталоги**.</span><span class="sxs-lookup"><span data-stu-id="913c6-149">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="913c6-150">Выберите добавленную ранее подключенную организацию и нажмите кнопку **выбрать**</span><span class="sxs-lookup"><span data-stu-id="913c6-150">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="913c6-151">В разделе **утверждение**выберите **Да** для параметра **требуется утверждение**.</span><span class="sxs-lookup"><span data-stu-id="913c6-151">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="913c6-152">В разделе **первый утверждающий**выберите одного из спонсоров, добавленных ранее, или выберите определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="913c6-152">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="913c6-153">Нажмите кнопку **добавить резервную** копию и выберите резервный утверждающий.</span><span class="sxs-lookup"><span data-stu-id="913c6-153">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="913c6-154">В разделе **включить**нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="913c6-154">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="913c6-155">Нажмите кнопку **Далее: жизненный цикл**.</span><span class="sxs-lookup"><span data-stu-id="913c6-155">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="913c6-156">Выберите нужные параметры проверки истечения срока действия и проверки доступа, а затем нажмите кнопку **Далее: Проверка и создание**.</span><span class="sxs-lookup"><span data-stu-id="913c6-156">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="913c6-157">Проверьте параметры и нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="913c6-157">Review your settings, and then click **Create**.</span></span>

    ![Снимок экрана с экраном пакетов доступа в управлении удостоверениями Azure Active Directory](../media/identity-governance-access-packages.png)

<span data-ttu-id="913c6-159">Если вы собираетесь с большой организацией, вам может потребоваться скрыть пакет Access.</span><span class="sxs-lookup"><span data-stu-id="913c6-159">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="913c6-160">Если пакет скрыт, пользователи в партнерской организации не увидят пакет на своем портале *доступа* .</span><span class="sxs-lookup"><span data-stu-id="913c6-160">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="913c6-161">Вместо этого им необходимо отправить прямую ссылку для регистрации пакета.</span><span class="sxs-lookup"><span data-stu-id="913c6-161">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="913c6-162">Скрытие пакета Access может уменьшить количество неуместных запросов на доступ, а также обеспечить доступ к пакетам Access, организованным на портал партнерской организации.</span><span class="sxs-lookup"><span data-stu-id="913c6-162">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="913c6-163">Установка скрытого пакета доступа</span><span class="sxs-lookup"><span data-stu-id="913c6-163">To set an access package to hidden</span></span>
1. <span data-ttu-id="913c6-164">В управлении удостоверениями Azure AD щелкните **пакеты Access**, а затем щелкните пакет Access.</span><span class="sxs-lookup"><span data-stu-id="913c6-164">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="913c6-165">На странице **Обзор** щелкните **изменить**.</span><span class="sxs-lookup"><span data-stu-id="913c6-165">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="913c6-166">В разделе **Свойства**выберите пункт **Да** для параметра **скрытый**и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="913c6-166">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![Снимок экрана: экран свойств пакета редактирования](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="913c6-168">Приглашение партнеров для пользователей</span><span class="sxs-lookup"><span data-stu-id="913c6-168">Invite partner users</span></span>

<span data-ttu-id="913c6-169">Если вы установили скрытый пакет доступа, необходимо отправить прямую ссылку на партнерскую организацию, чтобы она могла запрашивать доступ к сайту или группе.</span><span class="sxs-lookup"><span data-stu-id="913c6-169">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="913c6-170">Поиск ссылки на портал доступа</span><span class="sxs-lookup"><span data-stu-id="913c6-170">To find the access portal link</span></span>
1. <span data-ttu-id="913c6-171">В управлении удостоверениями Azure AD щелкните **пакеты Access**, а затем щелкните пакет Access.</span><span class="sxs-lookup"><span data-stu-id="913c6-171">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="913c6-172">На странице **Обзор** щелкните ссылку **Копировать в буфер обмена, чтобы** **перейти по ссылке портал My Access**.</span><span class="sxs-lookup"><span data-stu-id="913c6-172">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Снимок экрана: свойства пакета Access с ссылкой на портал доступа](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="913c6-174">После того как вы скопировали ссылку, вы можете поделиться ею с контактом в партнерской организации и отправить его пользователям в своей группе совместной работы.</span><span class="sxs-lookup"><span data-stu-id="913c6-174">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="913c6-175">См. также</span><span class="sxs-lookup"><span data-stu-id="913c6-175">See Also</span></span>

[<span data-ttu-id="913c6-176">Создание безопасной среды гостевого общего доступа</span><span class="sxs-lookup"><span data-stu-id="913c6-176">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

