---
title: Автоматизация лицензирования и членства в группах для тестовой среды Microsoft 365 для предприятий
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
description: Настройте лицензирование на основе групп и динамическое членство в группах в тестовой среде Microsoft 365 для предприятий.
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487580"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="9576d-103">Автоматизация лицензирования и членства в группах для тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="9576d-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="9576d-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для корпоративных тестовых сред.*</span><span class="sxs-lookup"><span data-stu-id="9576d-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="9576d-105">Лицензирование на основе групп автоматически назначает или удаляет лицензии для учетной записи пользователя на основе членства в группе.</span><span class="sxs-lookup"><span data-stu-id="9576d-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="9576d-106">Динамическое членство в группах добавляет или удаляет участников группы на основе свойств учетной записи пользователя, например **"Отдел"** или **"Страна".**</span><span class="sxs-lookup"><span data-stu-id="9576d-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="9576d-107">В этой статье по шагам вы можете с демонстрацией добавления и удаления участников группы в тестовой среде Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="9576d-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="9576d-108">Настройка автоматического лицензирования и динамического членства в группах в тестовой среде Microsoft 365 для предприятий состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="9576d-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="9576d-109">Этап 1. Создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="9576d-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="9576d-110">Этап 2. Настройка и тестирование динамического членства в группах и автоматического лицензирования</span><span class="sxs-lookup"><span data-stu-id="9576d-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="9576d-112">Чтобы получить визуальную карту со всеми статьями в руководстве по лаборатории тестирования Microsoft 365 для предприятий, перейдите в стек руководств по лаборатории тестирования [Microsoft 365 для предприятий.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="9576d-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="9576d-113">Этап 1. Создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="9576d-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="9576d-114">Если вы хотите протестировать только автоматическое лицензирование и членство в группах облегченным способом с минимальными требованиями, следуйте инструкциям в базовой конфигурации [lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="9576d-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="9576d-115">Если вы хотите протестировать автоматическое лицензирование и членство в группах в имитированном предприятии, следуйте инструкциям по сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="9576d-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9576d-116">Для тестирования автоматического лицензирования и членства в группах не требуется тестовая среда имитации предприятия, которая включает имитированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="9576d-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="9576d-117">Он предоставляется здесь в качестве варианта, чтобы вы могли протестировать автоматическое лицензирование и членство в группах и поэкспериментировать с ним в типичной для организации среде.</span><span class="sxs-lookup"><span data-stu-id="9576d-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="9576d-118">Этап 2. Настройка и тестирование динамического членства в группах и автоматического лицензирования</span><span class="sxs-lookup"><span data-stu-id="9576d-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="9576d-119">Сначала создайте группу Sales и добавьте динамическое правило членства в  группах, чтобы учетные записи пользователей, для которого установлено имя **"Отдел** продаж", автоматически присоединялись к группе "Продажи".</span><span class="sxs-lookup"><span data-stu-id="9576d-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="9576d-120">В частном экземпляре браузера войте в Центр администрирования [Microsoft 365](https://admin.microsoft.com) с помощью учетной записи глобального администратора вашей подписки на лабораторию тестирования Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="9576d-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="9576d-121">На отдельной вкладке браузера перейдите на портал Azure по ссылке [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="9576d-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="9576d-122">На портале Azure **введите группы в** поле поиска и выберите **"Группы".**</span><span class="sxs-lookup"><span data-stu-id="9576d-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="9576d-123">В области **"Все группы"** выберите **"Новая группа".**</span><span class="sxs-lookup"><span data-stu-id="9576d-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="9576d-124">В **типе группы** выберите **Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="9576d-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="9576d-125">In **Group name**, enter **Sales**.</span><span class="sxs-lookup"><span data-stu-id="9576d-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="9576d-126">В **типе членства выберите** **динамического пользователя.**</span><span class="sxs-lookup"><span data-stu-id="9576d-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="9576d-127">Выберите **динамических участников пользователя.**</span><span class="sxs-lookup"><span data-stu-id="9576d-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="9576d-128">В области **правил динамического** членства:</span><span class="sxs-lookup"><span data-stu-id="9576d-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="9576d-129">Выберите **свойство** отдела.</span><span class="sxs-lookup"><span data-stu-id="9576d-129">Select the **department** property.</span></span>
   - <span data-ttu-id="9576d-130">Выберите оператор **"Равно".**</span><span class="sxs-lookup"><span data-stu-id="9576d-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="9576d-131">В поле **"Значение"** введите **"Продажи".**</span><span class="sxs-lookup"><span data-stu-id="9576d-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="9576d-132">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9576d-132">Select **Save**.</span></span>
11. <span data-ttu-id="9576d-133">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9576d-133">Select **Create**.</span></span>

<span data-ttu-id="9576d-134">Затем настройте группу продаж, чтобы участникам автоматически была назначена лицензия Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="9576d-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="9576d-135">Выберите **группу** "Продажи", а затем выберите **"Лицензии".**</span><span class="sxs-lookup"><span data-stu-id="9576d-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="9576d-136">В области **назначений лицензий "Обновление"** выберите **Microsoft 365 E5** и выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="9576d-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="9576d-137">Закройте вкладку портала Azure в браузере.</span><span class="sxs-lookup"><span data-stu-id="9576d-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="9576d-138">Затем протестировать динамическое членство в группах и автоматическое лицензирование для учетной записи User 4:</span><span class="sxs-lookup"><span data-stu-id="9576d-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="9576d-139">На **вкладке Microsoft Office "Главная"** в браузере выберите **"Администратор".**</span><span class="sxs-lookup"><span data-stu-id="9576d-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="9576d-140">На **вкладке Центра администрирования Microsoft 365** выберите **активных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="9576d-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="9576d-141">На странице **"Активные пользователи"** выберите **учетную запись "Пользователь 4".**</span><span class="sxs-lookup"><span data-stu-id="9576d-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="9576d-142">В области **"Пользователь 4"** выберите **"Изменить** для **лицензий на продукты".**</span><span class="sxs-lookup"><span data-stu-id="9576d-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="9576d-143">В области **лицензий** на продукты отключите лицензию **Microsoft 365 E5** и выберите **"Сохранить**  >  **закрыть".**</span><span class="sxs-lookup"><span data-stu-id="9576d-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="9576d-144">В свойствах учетной записи User 4 убедитесь, что лицензии на продукты не назначены, а членство в группах не назначено.</span><span class="sxs-lookup"><span data-stu-id="9576d-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="9576d-145">Для **контактных данных** выберите **"Изменить"**.</span><span class="sxs-lookup"><span data-stu-id="9576d-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="9576d-146">В области **"Изменение контактных данных"** выберите **"Контактные данные".**</span><span class="sxs-lookup"><span data-stu-id="9576d-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="9576d-147">В поле **"Отдел"** **введите "Продажи"** и выберите **"Сохранить**  >  **закрыть".**</span><span class="sxs-lookup"><span data-stu-id="9576d-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="9576d-148">Подождите несколько минут, а затем  периодически выберите значок "Обновить" в правом верхнем правом верхнем конце области учетных записей User 4.</span><span class="sxs-lookup"><span data-stu-id="9576d-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="9576d-149">Со временем вы увидите:</span><span class="sxs-lookup"><span data-stu-id="9576d-149">In time, you should see the:</span></span>

- <span data-ttu-id="9576d-150">**Свойство членства в** группах, обновленное с помощью **группы "Продажи".**</span><span class="sxs-lookup"><span data-stu-id="9576d-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="9576d-151">**Свойство лицензий на** продукты, обновленное с помощью **лицензии Microsoft 365 E5.**</span><span class="sxs-lookup"><span data-stu-id="9576d-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="9576d-152">См. эти статьи, чтобы развернуть динамическое членство в группах и автоматическое лицензирование в рабочей области:</span><span class="sxs-lookup"><span data-stu-id="9576d-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="9576d-153">Лицензирование на основе групп в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9576d-153">Group-based licensing in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="9576d-154">Динамические группы в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9576d-154">Dynamic groups in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="9576d-155">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="9576d-155">Next step</span></span>

<span data-ttu-id="9576d-156">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="9576d-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9576d-157">См. также</span><span class="sxs-lookup"><span data-stu-id="9576d-157">See also</span></span>

[<span data-ttu-id="9576d-158">План удостоверений</span><span class="sxs-lookup"><span data-stu-id="9576d-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="9576d-159">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="9576d-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="9576d-160">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="9576d-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="9576d-161">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="9576d-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
