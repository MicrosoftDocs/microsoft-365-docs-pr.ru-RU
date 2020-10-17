---
title: Автоматизация лицензирования и участия в группах для тестовой среды Microsoft 365 для предприятий
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
description: Настройте лицензирование на основе групп и членство в динамической группе в тестовой среде Microsoft 365 для предприятия.
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487580"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="f6e6b-103">Автоматизация лицензирования и участия в группах для тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="f6e6b-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="f6e6b-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*</span><span class="sxs-lookup"><span data-stu-id="f6e6b-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="f6e6b-105">Лицензирование на основе групп автоматически назначает или удаляет лицензии для учетной записи пользователя в соответствии с членством в группе.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="f6e6b-106">Членство в динамической группе добавляет или удаляет членов группы на основе свойств учетной записи пользователя, например **отдела** или **страны**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="f6e6b-107">В этой статье описывается, как добавлять и удалять членов группы в тестовой среде Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="f6e6b-108">Настройка автоматического лицензирования и участия в динамической группе для тестовой среды Microsoft 365 для предприятий состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="f6e6b-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="f6e6b-109">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="f6e6b-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="f6e6b-110">Этап 2: Настройка и тестирование членства в динамических группах и автоматическое лицензирование</span><span class="sxs-lookup"><span data-stu-id="f6e6b-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="f6e6b-112">Для отображения всех статей, посвященных руководству по лаборатории тестирования Microsoft 365 для предприятий, перейдите к разделу [руководство по лаборатории тестирования microsoft 365 для предприятия](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="f6e6b-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="f6e6b-113">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="f6e6b-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="f6e6b-114">Если требуется только протестировать автоматизированное лицензирование и членство в группах в упрощенном виде с минимальными требованиями, следуйте инструкциям, приведенным в разделе [облегченная базовая конфигурация](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="f6e6b-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="f6e6b-115">Если вы хотите протестировать автоматизированное лицензирование и членство в группах на имитируемой предприятии, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f6e6b-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f6e6b-116">Для тестирования автоматического лицензирования и членства в группах не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="f6e6b-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="f6e6b-117">Он предоставляется в качестве варианта, чтобы можно было протестировать автоматизированное членство и членство в группах и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="f6e6b-118">Этап 2: Настройка и тестирование членства в динамических группах и автоматическое лицензирование</span><span class="sxs-lookup"><span data-stu-id="f6e6b-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="f6e6b-119">Сначала создайте группу Sales и добавьте правило членства в динамической группе, чтобы учетные записи пользователей с **подразделением** " **продажи** " автоматически присоединяются к группе "продажи".</span><span class="sxs-lookup"><span data-stu-id="f6e6b-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="f6e6b-120">В частном экземпляре Интернет-браузера Войдите в [центр администрирования microsoft 365](https://admin.microsoft.com) , используя учетную запись глобального администратора для подписки на тестовую лаборатория Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="f6e6b-121">На отдельной вкладке браузера перейдите на портал Azure по адресу [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="f6e6b-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="f6e6b-122">На портале Azure введите **группы** в поле поиска, а затем выберите **группы**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="f6e6b-123">в области **все группы** выберите пункт **создать группу**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="f6e6b-124">В списке **Тип группы**выберите **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="f6e6b-125">В поле **имя группы**введите **Sales**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="f6e6b-126">В списке **тип участия**выберите **динамический пользователь**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="f6e6b-127">Выберите **элемент динамические пользователи**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="f6e6b-128">В области **динамические правила членства** :</span><span class="sxs-lookup"><span data-stu-id="f6e6b-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="f6e6b-129">Выберите свойство **Department** .</span><span class="sxs-lookup"><span data-stu-id="f6e6b-129">Select the **department** property.</span></span>
   - <span data-ttu-id="f6e6b-130">Выберите оператор **Equals (равно** ).</span><span class="sxs-lookup"><span data-stu-id="f6e6b-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="f6e6b-131">В поле **значение** введите **Sales**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="f6e6b-132">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-132">Select **Save**.</span></span>
11. <span data-ttu-id="f6e6b-133">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-133">Select **Create**.</span></span>

<span data-ttu-id="f6e6b-134">Затем настройте группу продаж таким образом, чтобы участникам автоматически присвоено право на использование Microsoft 365 в качестве лицензии.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="f6e6b-135">Выберите группу **Sales (продажи** ), а затем выберите **Licenses (лицензии**).</span><span class="sxs-lookup"><span data-stu-id="f6e6b-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="f6e6b-136">В области **Обновление назначений лицензий** выберите **Microsoft 365**а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="f6e6b-137">В браузере закройте вкладку портал Azure.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="f6e6b-138">После этого проверьте членство в динамической группе и автоматическое лицензирование для учетной записи User 4:</span><span class="sxs-lookup"><span data-stu-id="f6e6b-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="f6e6b-139">На вкладке **Домашняя страница Microsoft Office** в браузере выберите элемент **Администратор**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="f6e6b-140">На вкладке **центра администрирования Microsoft 365** выберите пункт **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="f6e6b-141">На странице **Активные пользователи** выберите учетную запись **пользователя 4** .</span><span class="sxs-lookup"><span data-stu-id="f6e6b-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="f6e6b-142">В области **пользователь 4** выберите **изменить** для пункта **лицензии на продукты**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="f6e6b-143">В области **лицензии на продукты** отключите лицензию **Microsoft 365** , а затем нажмите кнопку **сохранить**  >  **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="f6e6b-144">В свойствах учетной записи пользователя 4 Убедитесь, что лицензии на продукты не назначены и членство в группах отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="f6e6b-145">Для **получения контактной информации**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="f6e6b-146">В области **изменение сведений о контакте** выберите **Контактная информация**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="f6e6b-147">В поле **Отдел** введите **Sales**, а затем нажмите кнопку **сохранить**  >  **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="f6e6b-148">Подождите несколько минут, а затем периодически нажмите значок **обновления** в правом верхнем углу панели учетных записей пользователя 4.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="f6e6b-149">В течение этого времени вы должны увидеть:</span><span class="sxs-lookup"><span data-stu-id="f6e6b-149">In time, you should see the:</span></span>

- <span data-ttu-id="f6e6b-150">Свойство **членства в группах** Обновлено в группе " **продажи** ".</span><span class="sxs-lookup"><span data-stu-id="f6e6b-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="f6e6b-151">Свойство **Licenses (лицензии продукта** ), обновленное с помощью лицензии **Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="f6e6b-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="f6e6b-152">В этих статьях представлены сведения о развертывании динамических членов групп и автоматических лицензирований в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="f6e6b-153">Лицензирование на основе групп в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f6e6b-153">Group-based licensing in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="f6e6b-154">Динамические группы в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f6e6b-154">Dynamic groups in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="f6e6b-155">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="f6e6b-155">Next step</span></span>

<span data-ttu-id="f6e6b-156">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="f6e6b-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6e6b-157">См. также</span><span class="sxs-lookup"><span data-stu-id="f6e6b-157">See also</span></span>

[<span data-ttu-id="f6e6b-158">Схема удостоверений</span><span class="sxs-lookup"><span data-stu-id="f6e6b-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="f6e6b-159">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="f6e6b-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f6e6b-160">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="f6e6b-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="f6e6b-161">Microsoft 365 для корпоративных документов</span><span class="sxs-lookup"><span data-stu-id="f6e6b-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
