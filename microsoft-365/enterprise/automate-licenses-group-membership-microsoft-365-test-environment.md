---
title: Автоматизация лицензирования и участия в группах для тестовой среды Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Настройте лицензирование на основе групп и членство в динамической группе в тестовой среде Microsoft 365 Enterprise.
ms.openlocfilehash: fe6380d94919556904a1fb1ac0624fac3496fe30
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673255"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="bf029-103">Автоматизация лицензирования и участия в группах для тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="bf029-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="bf029-104">*Это руководство по лаборатории тестирования можно использовать только для тестовых сред Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="bf029-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="bf029-105">Лицензирование на основе групп автоматически назначает или удаляет лицензии для учетной записи пользователя в соответствии с членством в группе.</span><span class="sxs-lookup"><span data-stu-id="bf029-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="bf029-106">Членство в динамической группе добавляет или удаляет членов группы на основе свойств учетной записи пользователя, например отдела или страны.</span><span class="sxs-lookup"><span data-stu-id="bf029-106">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="bf029-107">В этой статье описывается демонстрация обеих сред в тестовой среде Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bf029-107">This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="bf029-108">Настройка автоматического лицензирования и участия в динамической группе в тестовой среде Microsoft 365 Enterprise состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="bf029-108">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="bf029-109">Создайте среду тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="bf029-109">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="bf029-110">Настройка и проверка членства в динамических группах и автоматическое лицензирование.</span><span class="sxs-lookup"><span data-stu-id="bf029-110">Configure and test dynamic group membership and automatic licensing.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="bf029-112">Щелкните [здесь](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="bf029-112">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="bf029-113">Этап 1. Создание собственной тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="bf029-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="bf029-114">Если вы хотите просто протестировать автоматизированное лицензирование и членство в группах в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="bf029-114">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="bf029-115">Если вы хотите протестировать автоматизированное лицензирование и членство в группах на имитируемой предприятии, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="bf029-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf029-116">Для тестирования автоматического лицензирования и членства в группах не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="bf029-116">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="bf029-117">Он предоставляется в качестве параметра, чтобы можно было протестировать автоматизированное членство и членство в группах и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="bf029-117">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="bf029-118">Этап 2: Настройка и тестирование членства в динамических группах и автоматическое лицензирование</span><span class="sxs-lookup"><span data-stu-id="bf029-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="bf029-119">Сначала необходимо создать новую группу продаж и добавить правило членства в динамической группе, чтобы учетные записи пользователей с подразделением "продажи" автоматически добавлялись в группу "продажи".</span><span class="sxs-lookup"><span data-stu-id="bf029-119">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="bf029-120">Используя частный экземпляр Интернет-браузера, войдите на портал Office 365 [https://portal.office.com](https://portal.office.com) с учетной записью глобального администратора подписки на тестовую лаборатория Office 365.</span><span class="sxs-lookup"><span data-stu-id="bf029-120">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Office 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="bf029-121">На отдельной вкладке браузера перейдите на портал Azure по адресу [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="bf029-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="bf029-122">На портале Azure последовательно выберите **Azure Active Directory > Пользователи и группы > Все группы**.</span><span class="sxs-lookup"><span data-stu-id="bf029-122">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="bf029-123">В колонке **все группы** нажмите кнопку **создать группу**.</span><span class="sxs-lookup"><span data-stu-id="bf029-123">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="bf029-124">В списке **Тип группы**выберите **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="bf029-124">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="bf029-125">В списке **имя группы**введите **Sales**.</span><span class="sxs-lookup"><span data-stu-id="bf029-125">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="bf029-126">В списке **тип участия**выберите **динамический пользователь** .</span><span class="sxs-lookup"><span data-stu-id="bf029-126">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="bf029-127">Выберите **Добавить динамический запрос**.</span><span class="sxs-lookup"><span data-stu-id="bf029-127">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="bf029-128">В поле **Место добавления пользователей** выберите **Отдел**.</span><span class="sxs-lookup"><span data-stu-id="bf029-128">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="bf029-129">В следующем поле выберите **Равно**.</span><span class="sxs-lookup"><span data-stu-id="bf029-129">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="bf029-130">В следующем поле введите **Sales**.</span><span class="sxs-lookup"><span data-stu-id="bf029-130">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="bf029-131">Выберите **Добавить запрос** > **Создать**.</span><span class="sxs-lookup"><span data-stu-id="bf029-131">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="bf029-132">Закройте **группы** и **группы — все** лопасти групп.</span><span class="sxs-lookup"><span data-stu-id="bf029-132">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="bf029-133">После этого настройте группу продаж таким образом, чтобы членам автоматически присвоены лицензии Office 365 и Office для мобильных устройств + Security.</span><span class="sxs-lookup"><span data-stu-id="bf029-133">Next, you configure the Sales group so that members are automatically assigned Office 365 E5 and Enterprise Mobility + Security E5 licenses.</span></span>

1. <span data-ttu-id="bf029-134">В колонке **Обзор** в статье Azure Active Directory щелкните **Licenses > All Products**.</span><span class="sxs-lookup"><span data-stu-id="bf029-134">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="bf029-135">В списке выберите **Enterprise Mobility + Security E5** и **Office 365 корпоративный E5** и нажмите **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="bf029-135">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="bf029-136">В колонке **Назначение лицензии** щелкните **Пользователи и группы**.</span><span class="sxs-lookup"><span data-stu-id="bf029-136">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="bf029-137">В списке групп выберите группу **продаж** .</span><span class="sxs-lookup"><span data-stu-id="bf029-137">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="bf029-138">Выберите **Выбрать** > **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="bf029-138">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="bf029-139">Закройте вкладку портала Azure в браузере.</span><span class="sxs-lookup"><span data-stu-id="bf029-139">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="bf029-140">Далее вы протестируете сведения о членстве в динамических группах и автоматическом лицензировании для учетной записи User 4.</span><span class="sxs-lookup"><span data-stu-id="bf029-140">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="bf029-141">На вкладке **Домашняя страница Microsoft Office** в браузере щелкните элемент **Администратор**.</span><span class="sxs-lookup"><span data-stu-id="bf029-141">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="bf029-142">На вкладке **центра администрирования Microsoft 365** щелкните **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="bf029-142">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="bf029-143">На странице **Активные пользователи** выберите учетную запись **пользователя 4** .</span><span class="sxs-lookup"><span data-stu-id="bf029-143">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="bf029-144">В области **пользователь 4** щелкните **изменить** для параметра **лицензии на продукты**.</span><span class="sxs-lookup"><span data-stu-id="bf029-144">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="bf029-145">В области **лицензии на продукты** выключите **Enterprise Mobility + Security** двор и лицензии **Office 365 корпоративный** , а затем нажмите кнопку **сохранить > закрыть**.</span><span class="sxs-lookup"><span data-stu-id="bf029-145">On the **Product licenses** pane, turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses off, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="bf029-146">В свойствах учетной записи пользователя 4 Убедитесь, что лицензии на продукты не назначены и членство в группах отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bf029-146">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="bf029-147">Нажмите кнопку **изменить** для **получения сведений о контакте**.</span><span class="sxs-lookup"><span data-stu-id="bf029-147">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="bf029-148">В области **изменение сведений о контакте** щелкните **Контактная информация**.</span><span class="sxs-lookup"><span data-stu-id="bf029-148">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="bf029-149">В поле **Отдел** введите **Sales**, а затем нажмите кнопку **сохранить > закрыть**.</span><span class="sxs-lookup"><span data-stu-id="bf029-149">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="bf029-150">Подождите несколько минут, а затем периодически щелкайте значок обновления в правом верхнем углу области учетной записи пользователя 4.</span><span class="sxs-lookup"><span data-stu-id="bf029-150">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="bf029-151">В момент времени вы увидите:</span><span class="sxs-lookup"><span data-stu-id="bf029-151">In time you should see the:</span></span>

- <span data-ttu-id="bf029-152">Свойство **членства в группах** Обновлено в группе " **продажи** ".</span><span class="sxs-lookup"><span data-stu-id="bf029-152">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="bf029-153">**Лицензия на продукты** обновлена с помощью лицензий **Enterprise Mobility + Security** , а также лицензий **Office 365 корпоративный** .</span><span class="sxs-lookup"><span data-stu-id="bf029-153">**Product licenses** property updated with the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses.</span></span>

<span data-ttu-id="bf029-154">На этапе идентификации вы можете ознакомиться со сведениями и ссылками, чтобы развернуть членство в динамической группе и автоматическое лицензирование в рабочей среде:</span><span class="sxs-lookup"><span data-stu-id="bf029-154">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="bf029-155">Настройка автоматического лицензирования</span><span class="sxs-lookup"><span data-stu-id="bf029-155">Set up automatic licensing</span></span>](identity-use-group-management.md#identity-group-license)
- [<span data-ttu-id="bf029-156">Настройка динамического членства в группах</span><span class="sxs-lookup"><span data-stu-id="bf029-156">Set up dynamic group membership</span></span>](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a><span data-ttu-id="bf029-157">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="bf029-157">Next step</span></span>

<span data-ttu-id="bf029-158">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="bf029-158">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf029-159">См. также</span><span class="sxs-lookup"><span data-stu-id="bf029-159">See also</span></span>

[<span data-ttu-id="bf029-160">Шаг 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="bf029-160">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="bf029-161">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="bf029-161">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="bf029-162">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="bf029-162">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="bf029-163">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="bf029-163">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
