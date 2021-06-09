---
title: Автоматизация лицензирования и членства в группе для Microsoft 365 для тестовой среды предприятия
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Настройка группового лицензирования и динамического членства в группе в Microsoft 365 для корпоративной тестовой среды.
ms.openlocfilehash: 26840e2884202a0fa9c4bb563f3d7c653482ef87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905372"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="2739e-103">Автоматизация лицензирования и членства в группе для Microsoft 365 для тестовой среды предприятия</span><span class="sxs-lookup"><span data-stu-id="2739e-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="2739e-104">*Это руководство по тестовой лаборатории можно использовать только для Microsoft 365 для корпоративных тестовых сред.*</span><span class="sxs-lookup"><span data-stu-id="2739e-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="2739e-105">Групповое лицензирование автоматически назначает или удаляет лицензии для учетной записи пользователя на основе членства в группе.</span><span class="sxs-lookup"><span data-stu-id="2739e-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="2739e-106">Динамическое членство в группе добавляет или удаляет членов в группу на основе свойств учетных записей пользователей, таких как **Department** или **Country.**</span><span class="sxs-lookup"><span data-stu-id="2739e-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="2739e-107">В этой статье понаб- ется демонстрация добавления и удаления членов группы в Microsoft 365 для корпоративной тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="2739e-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="2739e-108">Настройка автоматического лицензирования и динамического членства в группе Microsoft 365 для корпоративной тестовой среды включает в себя два этапа:</span><span class="sxs-lookup"><span data-stu-id="2739e-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="2739e-109">Этап 1. Создание Microsoft 365 для корпоративной тестовой среды</span><span class="sxs-lookup"><span data-stu-id="2739e-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="2739e-110">Этап 2. Настройка и тестирование динамического членства в группе и автоматического лицензирования</span><span class="sxs-lookup"><span data-stu-id="2739e-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="2739e-112">Чтобы получить визуальную карту для всех статей в стеке руководства по Microsoft 365 для корпоративной лаборатории тестирования, перейдите Microsoft 365 для корпоративного руководства по [лаборатории тестирования.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="2739e-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="2739e-113">Этап 1. Создание Microsoft 365 для корпоративной тестовой среды</span><span class="sxs-lookup"><span data-stu-id="2739e-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="2739e-114">Если вы хотите проверить автоматическое лицензирование и членство в группе в легком режиме с минимальными требованиями, следуйте инструкциям в базовой конфигурации [Lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="2739e-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="2739e-115">Если вы хотите протестировать автоматическое лицензирование и членство в группе в смоделированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="2739e-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2739e-116">Для тестирования автоматического лицензирования и членства в группах не требуется смоделированная тестовая среда предприятия, которая включает смоделированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса служб домена Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="2739e-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="2739e-117">Он предоставляется здесь в качестве параметра, чтобы можно было протестировать автоматическое лицензирование и членство в группе и поэкспериментировать с ним в среде, которая представляет собой типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="2739e-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="2739e-118">Этап 2. Настройка и тестирование динамического членства в группе и автоматического лицензирования</span><span class="sxs-lookup"><span data-stu-id="2739e-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="2739e-119">Сначала создайте новую группу с именем Sales и добавьте правило  динамического  членства в группе, чтобы учетные записи пользователей с набором Отдела продаж автоматически присоединялись к группе продаж.</span><span class="sxs-lookup"><span data-stu-id="2739e-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="2739e-120">В частном экземпляре вашего интернет-браузера [вопишитесь](https://admin.microsoft.com) в центр администрирования Microsoft 365 с глобальной учетной записью администратора вашей Microsoft 365 E5 тестовой лаборатории.</span><span class="sxs-lookup"><span data-stu-id="2739e-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="2739e-121">На отдельной вкладке браузера перейдите на портал Azure по [https://portal.azure.com](https://portal.azure.com) ссылке .</span><span class="sxs-lookup"><span data-stu-id="2739e-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="2739e-122">На портале Azure введите **группы** в поле поиска и выберите **Группы.**</span><span class="sxs-lookup"><span data-stu-id="2739e-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="2739e-123">в области **Все группы** выберите **Новую группу**.</span><span class="sxs-lookup"><span data-stu-id="2739e-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="2739e-124">В **типе группы** выберите **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="2739e-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="2739e-125">В **названии группы** введите **Sales**.</span><span class="sxs-lookup"><span data-stu-id="2739e-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="2739e-126">В **типе Membership** выберите **динамического пользователя**.</span><span class="sxs-lookup"><span data-stu-id="2739e-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="2739e-127">Выберите **динамических пользователей**.</span><span class="sxs-lookup"><span data-stu-id="2739e-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="2739e-128">В области **динамических правил членства:**</span><span class="sxs-lookup"><span data-stu-id="2739e-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="2739e-129">Выберите **свойство отдела.**</span><span class="sxs-lookup"><span data-stu-id="2739e-129">Select the **department** property.</span></span>
   - <span data-ttu-id="2739e-130">Выберите **оператора Equals.**</span><span class="sxs-lookup"><span data-stu-id="2739e-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="2739e-131">В поле **Значение** введите **Sales**.</span><span class="sxs-lookup"><span data-stu-id="2739e-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="2739e-132">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2739e-132">Select **Save**.</span></span>
11. <span data-ttu-id="2739e-133">Выберите пункт **Создать**.</span><span class="sxs-lookup"><span data-stu-id="2739e-133">Select **Create**.</span></span>

<span data-ttu-id="2739e-134">Затем настройте группу Продаж, чтобы участникам автоматически была назначена Microsoft 365 E5 лицензия.</span><span class="sxs-lookup"><span data-stu-id="2739e-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="2739e-135">Выберите **группу Продаж,** а затем выберите **Лицензии.**</span><span class="sxs-lookup"><span data-stu-id="2739e-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="2739e-136">В области **назначений лицензии** Update выберите **Microsoft 365 E5** и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2739e-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="2739e-137">В браузере закройте вкладку портала Azure.</span><span class="sxs-lookup"><span data-stu-id="2739e-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="2739e-138">Далее проверьте динамическое членство в группе и автоматическое лицензирование на учетной записи Пользователя 4:</span><span class="sxs-lookup"><span data-stu-id="2739e-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="2739e-139">На **вкладке Microsoft Office в** браузере выберите **Администратор**.</span><span class="sxs-lookup"><span data-stu-id="2739e-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="2739e-140">На **вкладке Microsoft 365 центра администрирования** выберите **активных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="2739e-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="2739e-141">На странице **Активные пользователи** выберите учетную запись **Пользователя 4.**</span><span class="sxs-lookup"><span data-stu-id="2739e-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="2739e-142">На области **User 4** выберите **Изменить** для **лицензий на продукт.**</span><span class="sxs-lookup"><span data-stu-id="2739e-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="2739e-143">На области **лицензий** продукта отключите лицензию Microsoft 365 E5, а затем выберите **сохранить**   >  **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2739e-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="2739e-144">В свойствах учетной записи User 4 убедитесь, что лицензии на продукты не назначены и нет членства в группе.</span><span class="sxs-lookup"><span data-stu-id="2739e-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="2739e-145">Сведения **о контактах** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="2739e-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="2739e-146">В области **Сведений об изменениях контактов** выберите **контактную информацию.**</span><span class="sxs-lookup"><span data-stu-id="2739e-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="2739e-147">В поле **Department** введите **sales** и выберите **Сохранить**  >  **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2739e-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="2739e-148">Подождите несколько минут, а затем периодически выберите значок **Обновления** в правом верхнем справа области учетной записи Пользователя 4.</span><span class="sxs-lookup"><span data-stu-id="2739e-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="2739e-149">Со временем вы увидите:</span><span class="sxs-lookup"><span data-stu-id="2739e-149">In time, you should see the:</span></span>

- <span data-ttu-id="2739e-150">**Свойство членства в** группах, обновленное группой **Продаж.**</span><span class="sxs-lookup"><span data-stu-id="2739e-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="2739e-151">**Свойство лицензий** на продукты, обновленное с **Microsoft 365 E5** лицензией.</span><span class="sxs-lookup"><span data-stu-id="2739e-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="2739e-152">См. в этих статьях развертывание динамического членства в группе и автоматического лицензирования в производстве:</span><span class="sxs-lookup"><span data-stu-id="2739e-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="2739e-153">Лицензирование на основе групп в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2739e-153">Group-based licensing in Azure Active Directory</span></span>](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="2739e-154">Динамические группы в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2739e-154">Dynamic groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="2739e-155">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="2739e-155">Next step</span></span>

<span data-ttu-id="2739e-156">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="2739e-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="2739e-157">См. также</span><span class="sxs-lookup"><span data-stu-id="2739e-157">See also</span></span>

[<span data-ttu-id="2739e-158">Дорожная карта удостоверений</span><span class="sxs-lookup"><span data-stu-id="2739e-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="2739e-159">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="2739e-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2739e-160">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="2739e-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2739e-161">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="2739e-161">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)