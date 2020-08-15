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
ms.openlocfilehash: a25a47b81ce8c119e7aeb44660af32bb9cafb08a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685562"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7cc72-103">Автоматизация лицензирования и участия в группах для тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="7cc72-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7cc72-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*</span><span class="sxs-lookup"><span data-stu-id="7cc72-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="7cc72-105">Лицензирование на основе групп автоматически назначает или удаляет лицензии для учетной записи пользователя в соответствии с членством в группе.</span><span class="sxs-lookup"><span data-stu-id="7cc72-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="7cc72-106">Членство в динамической группе добавляет или удаляет членов группы на основе свойств учетной записи пользователя, например отдела или страны.</span><span class="sxs-lookup"><span data-stu-id="7cc72-106">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="7cc72-107">В этой статье описывается демонстрация как в среде тестирования Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="7cc72-107">This article steps you through a demonstration of both in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="7cc72-108">Настройка автоматического лицензирования и участия в динамической группе в среде тестирования Microsoft 365 для предприятия состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="7cc72-108">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment:</span></span>

1. <span data-ttu-id="7cc72-109">Создайте тестовую среду Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="7cc72-109">Create the Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="7cc72-110">Настройка и проверка членства в динамических группах и автоматическое лицензирование.</span><span class="sxs-lookup"><span data-stu-id="7cc72-110">Configure and test dynamic group membership and automatic licensing.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="7cc72-112">Щелкните [здесь](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 для крупных предприятий.</span><span class="sxs-lookup"><span data-stu-id="7cc72-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7cc72-113">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="7cc72-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7cc72-114">Если вы хотите просто протестировать автоматизированное лицензирование и членство в группах в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="7cc72-114">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="7cc72-115">Если вы хотите протестировать автоматизированное лицензирование и членство в группах на имитируемой предприятии, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7cc72-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7cc72-116">Для тестирования автоматического лицензирования и членства в группах не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="7cc72-116">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="7cc72-117">Он предоставляется в качестве параметра, чтобы можно было протестировать автоматизированное членство и членство в группах и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="7cc72-117">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="7cc72-118">Этап 2: Настройка и тестирование членства в динамических группах и автоматическое лицензирование</span><span class="sxs-lookup"><span data-stu-id="7cc72-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="7cc72-119">Сначала необходимо создать новую группу продаж и добавить правило членства в динамической группе, чтобы учетные записи пользователей с подразделением "продажи" автоматически добавлялись в группу "продажи".</span><span class="sxs-lookup"><span data-stu-id="7cc72-119">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="7cc72-120">Используя частный экземпляр Интернет-браузера, войдите в [центр администрирования microsoft 365](https://admin.microsoft.com) , используя учетную запись глобального администратора подписки на тестовую лаборатория Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7cc72-120">Using a private instance of your Internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="7cc72-121">На отдельной вкладке браузера перейдите на портал Azure по адресу [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="7cc72-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="7cc72-122">На портале Azure введите **группы** в поле поиска, а затем нажмите кнопку **группы**.</span><span class="sxs-lookup"><span data-stu-id="7cc72-122">In the Azure portal, type **groups** in the search box, and then click **Groups**.</span></span>
4. <span data-ttu-id="7cc72-123">в области " **все группы** " нажмите кнопку **создать группу**.</span><span class="sxs-lookup"><span data-stu-id="7cc72-123">in the **All groups** pane, click **New group**.</span></span>
5. <span data-ttu-id="7cc72-124">В списке **Тип группы**выберите **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="7cc72-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="7cc72-125">В списке **имя группы**введите **Sales**.</span><span class="sxs-lookup"><span data-stu-id="7cc72-125">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="7cc72-126">В списке **тип участия**выберите **динамический пользователь**.</span><span class="sxs-lookup"><span data-stu-id="7cc72-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="7cc72-127">Щелкните элемент **динамические пользователи**.</span><span class="sxs-lookup"><span data-stu-id="7cc72-127">Click **Dynamic user members**.</span></span>
9. <span data-ttu-id="7cc72-128">В области **динамические правила членства** :</span><span class="sxs-lookup"><span data-stu-id="7cc72-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="7cc72-129">Выберите свойство **Department** .</span><span class="sxs-lookup"><span data-stu-id="7cc72-129">Select the **department** property.</span></span>
   - <span data-ttu-id="7cc72-130">Выберите оператор **Equals (равно** ).</span><span class="sxs-lookup"><span data-stu-id="7cc72-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="7cc72-131">Введите **стоимость** **продаж** .</span><span class="sxs-lookup"><span data-stu-id="7cc72-131">Type **Sales** in **Value**.</span></span>
10. <span data-ttu-id="7cc72-132">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7cc72-132">Click **Save**.</span></span>
11. <span data-ttu-id="7cc72-133">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7cc72-133">Click **Create**.</span></span>

<span data-ttu-id="7cc72-134">После этого настройте группу продаж таким образом, чтобы членам автоматически присвоено значение лицензия Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7cc72-134">Next, you configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="7cc72-135">Щелкните группу **Sales (продажи** ), а затем щелкните **Licenses (лицензии**).</span><span class="sxs-lookup"><span data-stu-id="7cc72-135">Click the **Sales** group, and then click **Licenses**.</span></span>
2. <span data-ttu-id="7cc72-136">В области **Обновление назначений лицензий** выберите **Microsoft 365**а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7cc72-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then click **Save**.</span></span>
3. <span data-ttu-id="7cc72-137">Закройте вкладку портала Azure в браузере.</span><span class="sxs-lookup"><span data-stu-id="7cc72-137">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="7cc72-138">Далее вы протестируете сведения о членстве в динамических группах и автоматическом лицензировании для учетной записи User 4.</span><span class="sxs-lookup"><span data-stu-id="7cc72-138">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="7cc72-139">На вкладке **Домашняя страница Microsoft Office** в браузере щелкните элемент **Администратор**.</span><span class="sxs-lookup"><span data-stu-id="7cc72-139">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="7cc72-140">На вкладке **центра администрирования Microsoft 365** щелкните **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="7cc72-140">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="7cc72-141">На странице **Активные пользователи** выберите учетную запись **пользователя 4** .</span><span class="sxs-lookup"><span data-stu-id="7cc72-141">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="7cc72-142">В области **пользователь 4** щелкните **изменить** для параметра **лицензии на продукты**.</span><span class="sxs-lookup"><span data-stu-id="7cc72-142">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="7cc72-143">В области **лицензии на продукты** отключите лицензию **Microsoft 365** , а затем нажмите кнопку **сохранить > закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7cc72-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="7cc72-144">В свойствах учетной записи пользователя 4 Убедитесь, что лицензии на продукты не назначены и членство в группах отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7cc72-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="7cc72-145">Нажмите кнопку **изменить** для **получения сведений о контакте**.</span><span class="sxs-lookup"><span data-stu-id="7cc72-145">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="7cc72-146">В области **изменение сведений о контакте** щелкните **Контактная информация**.</span><span class="sxs-lookup"><span data-stu-id="7cc72-146">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="7cc72-147">В поле **Отдел** введите **Sales**, а затем нажмите кнопку **сохранить > закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7cc72-147">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="7cc72-148">Подождите несколько минут, а затем периодически щелкайте значок обновления в правом верхнем углу области учетной записи пользователя 4.</span><span class="sxs-lookup"><span data-stu-id="7cc72-148">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="7cc72-149">В момент времени вы увидите:</span><span class="sxs-lookup"><span data-stu-id="7cc72-149">In time you should see the:</span></span>

- <span data-ttu-id="7cc72-150">Свойство **членства в группах** Обновлено в группе " **продажи** ".</span><span class="sxs-lookup"><span data-stu-id="7cc72-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="7cc72-151">Свойство **Licenses (лицензии продукта** ), обновленное с помощью лицензии **Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="7cc72-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="7cc72-152">В этих статьях представлены сведения о развертывании динамических членов групп и автоматических лицензирований в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="7cc72-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- <span data-ttu-id="7cc72-153">ССЫЛКА ПОДЛЕЖИТ ОПРЕДЕЛЕНИЮ</span><span class="sxs-lookup"><span data-stu-id="7cc72-153">LINK TBD</span></span>
- <span data-ttu-id="7cc72-154">ССЫЛКА ПОДЛЕЖИТ ОПРЕДЕЛЕНИЮ</span><span class="sxs-lookup"><span data-stu-id="7cc72-154">LINK TBD</span></span>

## <a name="next-step"></a><span data-ttu-id="7cc72-155">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="7cc72-155">Next step</span></span>

<span data-ttu-id="7cc72-156">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="7cc72-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7cc72-157">См. также</span><span class="sxs-lookup"><span data-stu-id="7cc72-157">See also</span></span>

[<span data-ttu-id="7cc72-158">Схема удостоверений</span><span class="sxs-lookup"><span data-stu-id="7cc72-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="7cc72-159">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="7cc72-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7cc72-160">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="7cc72-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7cc72-161">Microsoft 365 для корпоративных документов</span><span class="sxs-lookup"><span data-stu-id="7cc72-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
