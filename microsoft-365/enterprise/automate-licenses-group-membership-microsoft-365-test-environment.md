---
title: Автоматизировать лицензирования и групповых членство для тестовой среды Microsoft 365 для предприятия
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Настройка группы лицензирования и членство в группах динамических в тестовой среде Microsoft 365 для предприятия.
ms.openlocfilehash: 45a78af202f2d9ab029683aae4d95ed9a3370b08
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870827"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="fe69e-103">Автоматизировать лицензирования и групповых членство для тестовой среды Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="fe69e-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="fe69e-p101">Группа лицензирования автоматически назначает или удаление лицензий для учетной записи пользователя на основе членства в группах. Членство в группах динамических добавляет или удаляет участникам группы в зависимости от свойств учетной записи пользователя, например, отдела или страны. В этой статье действия по демонстрации из них в тестовой среде Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="fe69e-p101">Group-based licensing automatically assigns or removes licenses for a user account based on group membership. Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country. This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="fe69e-107">Существует два этапа по настройке членство в группах auto лицензирования и динамических в тестовой среде Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="fe69e-107">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="fe69e-108">Создание тестовой среды Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="fe69e-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="fe69e-109">Настройки и тестирования динамических группах и автоматическое лицензирование.</span><span class="sxs-lookup"><span data-stu-id="fe69e-109">Configure and test dynamic group membership and automatic licensing.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="fe69e-111">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="fe69e-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="fe69e-112">Этап 1: Создание масштабирование тестовой среды Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="fe69e-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="fe69e-113">Если необходимо проверить автоматизированных лицензирования и членство в группах в облегченный путь с минимальным требованиям, следуйте инструкциям в [упрощенной базовой конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="fe69e-113">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="fe69e-114">Если вы хотите проверить автоматизированных лицензирования и членство в группах в имитации enterprise, следуйте инструкциям в [сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="fe69e-114">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe69e-p102">Тестирование автоматизирована лицензирования и членства в группе не требуется тестовой среды имитации предприятия, включающая имитации интрасети, подключенных к Интернету и синхронизации каталогов для леса Windows Server AD. Предоставляется здесь как вариант, чтобы проверка автоматической лицензирования и членство в группах и экспериментировать с его в среде, которая представляет типичное организации.</span><span class="sxs-lookup"><span data-stu-id="fe69e-p102">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="fe69e-117">Этап 2: Настройки и тестирования динамических группах и автоматическое Лицензирование</span><span class="sxs-lookup"><span data-stu-id="fe69e-117">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="fe69e-118">Во-первых создается новая группа продаж и Добавление правила членства динамическую группу, чтобы учетные записи пользователей с отделом, задайте значение продаж, автоматически добавляются в группу.</span><span class="sxs-lookup"><span data-stu-id="fe69e-118">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="fe69e-119">С помощью закрытого экземпляра веб-браузер, войдите в портал Office по [https://office.com](https://office.com) с учетной записью глобального администратора Office 365 E5 пробной подписки.</span><span class="sxs-lookup"><span data-stu-id="fe69e-119">Using a private instance of your Internet browser, sign in to the Office portal at [https://office.com](https://office.com) with the global administrator account of your Office 365 E5 trial subscription.</span></span>
2. <span data-ttu-id="fe69e-120">На отдельной вкладке браузера перейдите на портале Azure по [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="fe69e-120">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="fe69e-121">На портале Azure последовательно выберите **Azure Active Directory > Пользователи и группы > Все группы**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-121">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="fe69e-122">На blade **все группы** нажмите кнопку **Создать группу**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-122">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="fe69e-123">В **группе тип**выберите **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-123">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="fe69e-124">В поле **имя группы**введите **продажи**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-124">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="fe69e-125">В поле **типа участия**выберите **динамических пользователя** .</span><span class="sxs-lookup"><span data-stu-id="fe69e-125">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="fe69e-126">Выберите **Добавить динамический запрос**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-126">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="fe69e-127">В поле **Место добавления пользователей** выберите **Отдел**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-127">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="fe69e-128">В следующем поле выберите **Равно**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-128">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="fe69e-129">В следующем поле введите **продажи**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-129">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="fe69e-130">Выберите **Добавить запрос** > **Создать**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-130">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="fe69e-131">Закройте blade-серверы \*\*и **групп — все группы** \*\* .</span><span class="sxs-lookup"><span data-stu-id="fe69e-131">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="fe69e-132">Далее следует настроить группы продаж, чтобы участники автоматически назначаются Office 365 E5 и мобильных устройств предприятия + лицензий E5 безопасности.</span><span class="sxs-lookup"><span data-stu-id="fe69e-132">Next, you configure the Sales group so that members are automatically assigned Office 365 E5 and Enterprise Mobility + Security E5 licenses.</span></span>

1. <span data-ttu-id="fe69e-133">На blade **Обзор** для Azure Active Directory, щелкните **лицензий > всех продуктов**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-133">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="fe69e-134">В списке выберите **Enterprise Mobility + Security E5** и **Office 365 корпоративный E5** и нажмите **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-134">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="fe69e-135">На blade **Назначение лицензии** нажмите кнопку **пользователи и группы**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-135">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="fe69e-136">В списке группы выберите группу **продаж** .</span><span class="sxs-lookup"><span data-stu-id="fe69e-136">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="fe69e-137">Выберите **Выбрать** > **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-137">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="fe69e-138">Закройте вкладку портала Azure в браузере.</span><span class="sxs-lookup"><span data-stu-id="fe69e-138">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="fe69e-139">Рассмотрим процедуру тестирования динамических группах и автоматическое Лицензирование для учетной записи пользователя 4.</span><span class="sxs-lookup"><span data-stu-id="fe69e-139">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="fe69e-140">В браузере откройте вкладку **Microsoft Office для дома** и щелкните **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-140">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="fe69e-141">На вкладке **центра администрирования Office** щелкните **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-141">From the **Office Admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="fe69e-142">На странице **активных пользователей** выберите учетную запись **пользователя 4** .</span><span class="sxs-lookup"><span data-stu-id="fe69e-142">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="fe69e-143">В области **пользователя 4** выберите **Изменить** для **лицензий на продукт**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-143">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="fe69e-144">В области **лицензий на продукт** включить **мобильности Enterprise + E5 безопасности** и лицензий на **Office 365 корпоративный E5** отключить и нажмите кнопку **Сохранить > Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-144">On the **Product licenses** pane, turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses off, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="fe69e-145">В окне свойств учетной записи пользователя 4 убедитесь, что были назначены лицензии не продукта и нет нет членов группы.</span><span class="sxs-lookup"><span data-stu-id="fe69e-145">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="fe69e-146">Нажмите кнопку **Изменить** сведения **контакта**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-146">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="fe69e-147">В области **Изменение контактная информация** щелкните **Контактные данные**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-147">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="fe69e-148">Введите в поле **отдела** **продаж**и нажмите кнопку **Сохранить > Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="fe69e-148">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="fe69e-149">Подождите несколько минут и периодически щелкните значок обновления в правом верхнем углу области учетной записи пользователя 4.</span><span class="sxs-lookup"><span data-stu-id="fe69e-149">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="fe69e-150">На время должны отображаться:</span><span class="sxs-lookup"><span data-stu-id="fe69e-150">In time you should see the:</span></span>

- <span data-ttu-id="fe69e-151">Свойство **членство в группах** , добавлены в группу **продаж** .</span><span class="sxs-lookup"><span data-stu-id="fe69e-151">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="fe69e-152">Обновлено с лицензии **Enterprise мобильности + E5 безопасности** и **Office 365 корпоративный E5** свойство **лицензий на продукт** .</span><span class="sxs-lookup"><span data-stu-id="fe69e-152">**Product licenses** property updated with the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses.</span></span>

<span data-ttu-id="fe69e-153">Просмотрите следующие действия на этапе Identity сведения и ссылки на развертывание динамических группах и автоматическое Лицензирование в рабочей среде:</span><span class="sxs-lookup"><span data-stu-id="fe69e-153">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="fe69e-154">Настройка автоматического лицензирования</span><span class="sxs-lookup"><span data-stu-id="fe69e-154">Set up automatic licensing</span></span>](identity-group-based-licensing.md)
- [<span data-ttu-id="fe69e-155">Настройка динамического членства в группах</span><span class="sxs-lookup"><span data-stu-id="fe69e-155">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md)

## <a name="next-step"></a><span data-ttu-id="fe69e-156">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="fe69e-156">Next step</span></span>

<span data-ttu-id="fe69e-157">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="fe69e-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe69e-158">См. также</span><span class="sxs-lookup"><span data-stu-id="fe69e-158">See also</span></span>

[<span data-ttu-id="fe69e-159">Шаг 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="fe69e-159">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="fe69e-160">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="fe69e-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="fe69e-161">Развертывание Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="fe69e-161">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="fe69e-162">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="fe69e-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
