---
title: Центр администрирования Exchange в автономной службе EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Узнайте об интерфейсе управления веб-сайтами в автономных системах Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ec9dcbccbee734ea7c475b1ac0a5f9a92a0b401b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286961"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="d3c20-103">Центр администрирования Exchange в автономной службе EOP</span><span class="sxs-lookup"><span data-stu-id="d3c20-103">Exchange admin center in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d3c20-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="d3c20-104">**Applies to**</span></span>
-  [<span data-ttu-id="d3c20-105">Автономный exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d3c20-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="d3c20-106">Центр администрирования Exchange (EAC) — это веб-консоль управления для автономных служб Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="d3c20-106">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="d3c20-107">Ищете версию этой темы для Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="d3c20-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="d3c20-108">См. [Центр администрирования Exchange в Exchange Online.](https://docs.microsoft.com/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="d3c20-108">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="d3c20-109">Открытие EAC в EOP</span><span class="sxs-lookup"><span data-stu-id="d3c20-109">Open the EAC in EOP</span></span>

<span data-ttu-id="d3c20-110">Клиенты автономных EOP могут получить доступ к EAC с помощью следующих методов:</span><span class="sxs-lookup"><span data-stu-id="d3c20-110">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="d3c20-111">**Из Центра администрирования Microsoft 365:**</span><span class="sxs-lookup"><span data-stu-id="d3c20-111">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="d3c20-112">Go to <https://admin.microsoft.com> and click Show **all**.</span><span class="sxs-lookup"><span data-stu-id="d3c20-112">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Щелкните "Показать все" в Центре администрирования Microsoft 365](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="d3c20-114">В разделе **"Центры администрирования"** щелкните **"Все центры администрирования".**</span><span class="sxs-lookup"><span data-stu-id="d3c20-114">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Щелкните все центры администрирования в Центре администрирования Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="d3c20-116">На странице **"Все центры администрирования"** щелкните **Exchange Online Protection.**</span><span class="sxs-lookup"><span data-stu-id="d3c20-116">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="d3c20-117">Перейдите непосредственно по этой `https://admin.protection.outlook.com/ecp/` теме.</span><span class="sxs-lookup"><span data-stu-id="d3c20-117">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="d3c20-118">Общие элементы пользовательского интерфейса в EAC в EOP</span><span class="sxs-lookup"><span data-stu-id="d3c20-118">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="d3c20-119">В этом разделе рассматриваются элементы интерфейса пользователя в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="d3c20-119">This section describes the user interface elements that are found in the EAC.</span></span>

![Центр администрирования Exchange в Exchange Online Protection](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="d3c20-121">Панель "Функции"</span><span class="sxs-lookup"><span data-stu-id="d3c20-121">Feature Pane</span></span>

<span data-ttu-id="d3c20-p102">Это первый уровень навигации для большинства заданий, выполняемых в Центре администрирования Exchange. Панель функций состоит из областей функций.</span><span class="sxs-lookup"><span data-stu-id="d3c20-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="d3c20-124">**Получатели:** здесь вы будете просматривать группы и внешние контакты.</span><span class="sxs-lookup"><span data-stu-id="d3c20-124">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="d3c20-125">**Разрешения :** здесь вы будете управлять ролями администраторов.</span><span class="sxs-lookup"><span data-stu-id="d3c20-125">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="d3c20-126">**Управление соответствием** требованиям: здесь вы найдете отчет о группе ролей администраторов и журнал аудита администратора.</span><span class="sxs-lookup"><span data-stu-id="d3c20-126">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="d3c20-127">**Защита**: здесь можно управлять политиками защиты от вредоносных программ, политикой фильтрации подключений по умолчанию и DKIM.</span><span class="sxs-lookup"><span data-stu-id="d3c20-127">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d3c20-128">В Центре безопасности & и соответствия требованиям следует управлять политиками защиты от вредоносных программ и политикой фильтрации подключений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d3c20-128">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="d3c20-129">Дополнительные сведения см. в настройках политик для борьбы с вредоносными [программами в EOP](configure-anti-malware-policies.md) и настройке фильтрации подключений [в EOP.](configure-the-connection-filter-policy.md)</span><span class="sxs-lookup"><span data-stu-id="d3c20-129">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="d3c20-130">**Поток почты**: здесь вы сможете управлять правилами потока почты (также известными как правила транспорта), принятыми доменами и соединитетелями, а также где можно запускать трассировку сообщений.</span><span class="sxs-lookup"><span data-stu-id="d3c20-130">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="d3c20-131">**Гибридная** конфигурация: здесь [](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)можно запустить мастер гибридной конфигурации, а также установить модуль [Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="d3c20-131">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="d3c20-132">Вкладки</span><span class="sxs-lookup"><span data-stu-id="d3c20-132">Tabs</span></span>

<span data-ttu-id="d3c20-133">Вкладки  это второй уровень навигации.</span><span class="sxs-lookup"><span data-stu-id="d3c20-133">The tabs are your second level of navigation.</span></span> <span data-ttu-id="d3c20-134">Каждый из компонентов содержит различные вкладки, на каждой из которых будет представлена функция.</span><span class="sxs-lookup"><span data-stu-id="d3c20-134">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="d3c20-135">Панель инструментов</span><span class="sxs-lookup"><span data-stu-id="d3c20-135">Toolbar</span></span>

<span data-ttu-id="d3c20-p105">При выборе большинства вкладок отображается панель инструментов. Панель инструментов содержит значки, которые выполняют определенное действие. Значки и их действия описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d3c20-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="d3c20-139">Значок</span><span class="sxs-lookup"><span data-stu-id="d3c20-139">Icon</span></span>|<span data-ttu-id="d3c20-140">Имя</span><span class="sxs-lookup"><span data-stu-id="d3c20-140">Name</span></span>|<span data-ttu-id="d3c20-141">Action</span><span class="sxs-lookup"><span data-stu-id="d3c20-141">Action</span></span>|
|---|---|---|
|![Значок добавления](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="d3c20-143">"Добавить", "Создать"</span><span class="sxs-lookup"><span data-stu-id="d3c20-143">Add, New</span></span>|<span data-ttu-id="d3c20-p106">Используйте этот значок для создания нового объекта. Некоторые из этих значков имеют стрелку вниз, щелкнув которую, можно отобразить дополнительные объекты, которые можно создать.</span><span class="sxs-lookup"><span data-stu-id="d3c20-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Значок редактирования](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="d3c20-147">Изменить</span><span class="sxs-lookup"><span data-stu-id="d3c20-147">Edit</span></span>|<span data-ttu-id="d3c20-148">Используйте этот значок для редактирования объекта.</span><span class="sxs-lookup"><span data-stu-id="d3c20-148">Use this icon to edit an object.</span></span>|
|![Значок удаления](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="d3c20-150">Удаление</span><span class="sxs-lookup"><span data-stu-id="d3c20-150">Delete</span></span>|<span data-ttu-id="d3c20-p107">Используйте этот значок для удаления объекта. У некоторых значков удаления есть стрелка вниз, которая позволяет отобразить дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="d3c20-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![значок поиска](../../media/ITPro-EAC-.gif)|<span data-ttu-id="d3c20-154">Поиск</span><span class="sxs-lookup"><span data-stu-id="d3c20-154">Search</span></span>|<span data-ttu-id="d3c20-155">Этот значок позволяет открыть поле поиска, в котором можно ввести фразу поиска для объекта, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="d3c20-155">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Значок обновления](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="d3c20-157">Обновить</span><span class="sxs-lookup"><span data-stu-id="d3c20-157">Refresh</span></span>|<span data-ttu-id="d3c20-158">Используйте этот значок, чтобы обновить представление списка.</span><span class="sxs-lookup"><span data-stu-id="d3c20-158">Use this icon to refresh the list view.</span></span>|
|![Значок дополнительных параметров](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="d3c20-160">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="d3c20-160">More options</span></span>|<span data-ttu-id="d3c20-p108">Используйте этот значок для просмотра дополнительных действий, которые можно выполнить для объектов этой вкладки. Например, при нажатии этого значка в области **Получатели \> Пользователи** отображается параметр для выполнения **расширенного поиска**.  </span><span class="sxs-lookup"><span data-stu-id="d3c20-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Значок "Стрелка вверх"](../../media/ITPro-EAC-UpArrowIcon.gif)![Значок "Стрелка вниз"](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="d3c20-165">Стрелка вверх и стрелка вниз</span><span class="sxs-lookup"><span data-stu-id="d3c20-165">Up arrow and down arrow</span></span>|<span data-ttu-id="d3c20-166">Используйте эти значки для изменения приоритета объекта.</span><span class="sxs-lookup"><span data-stu-id="d3c20-166">Use these icons to move an object's priority up or down.</span></span>|
|![Значок "Удалить"](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="d3c20-168">Удалить</span><span class="sxs-lookup"><span data-stu-id="d3c20-168">Remove</span></span>|<span data-ttu-id="d3c20-169">Используйте этот значок, чтобы удалять объекты из списка.</span><span class="sxs-lookup"><span data-stu-id="d3c20-169">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="d3c20-170">Представление списка</span><span class="sxs-lookup"><span data-stu-id="d3c20-170">List View</span></span>

<span data-ttu-id="d3c20-p109">При выборе вкладки в большинстве случаев отображается представление списка. Лимит просмотра в Центре администрирования Exchange составляет около 10 000 объектов. Кроме того, включено постраничное разделение, так что вы можете листать страницы результатов.</span><span class="sxs-lookup"><span data-stu-id="d3c20-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="d3c20-174">Область сведений</span><span class="sxs-lookup"><span data-stu-id="d3c20-174">Details Pane</span></span>

<span data-ttu-id="d3c20-p110">При выборе объекта в представлении списка информация об этом объекте отображается в области сведений. В некоторых случаях область сведений включает задачи управления.</span><span class="sxs-lookup"><span data-stu-id="d3c20-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="d3c20-177">Иконка "Я" и справка</span><span class="sxs-lookup"><span data-stu-id="d3c20-177">Me tile and Help</span></span>

<span data-ttu-id="d3c20-178">Плитка **Я** позволяет выйти из Центра администрирования Exchange и войти в него как другой пользователь.</span><span class="sxs-lookup"><span data-stu-id="d3c20-178">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="d3c20-179">В **выпадаемом** меню "Значок справки" ![ можно сделать следующие ](../../media/ITPro-EAC-HelpIcon.gif) действия:</span><span class="sxs-lookup"><span data-stu-id="d3c20-179">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can do the following actions:</span></span>

- <span data-ttu-id="d3c20-180">**Справка:** ![ щелкните значок ](../../media/ITPro-EAC-HelpIcon.gif) справки, чтобы просмотреть содержимое справки в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d3c20-180">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>
- <span data-ttu-id="d3c20-181">**Обратная** связь: оставьте отзыв.</span><span class="sxs-lookup"><span data-stu-id="d3c20-181">**Feedback**: Leave feedback.</span></span>
- <span data-ttu-id="d3c20-182">**Сообщество:** зайдите на форумы сообщества, чтобы найти ответы на них.</span><span class="sxs-lookup"><span data-stu-id="d3c20-182">**Community**: Post a question for find answers in the community forums.</span></span>
- <span data-ttu-id="d3c20-183">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span><span class="sxs-lookup"><span data-stu-id="d3c20-183">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="d3c20-184">Вы можете отключить пузырьок справки или включить его, если он отключен.</span><span class="sxs-lookup"><span data-stu-id="d3c20-184">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>
- <span data-ttu-id="d3c20-185">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span><span class="sxs-lookup"><span data-stu-id="d3c20-185">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="d3c20-186">Поддерживаемые веб-браузеры</span><span class="sxs-lookup"><span data-stu-id="d3c20-186">Supported Browsers</span></span>

<span data-ttu-id="d3c20-187">Для лучшего использования EAC рекомендуется всегда использовать новейшие браузеры, клиенты Office и приложения.</span><span class="sxs-lookup"><span data-stu-id="d3c20-187">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="d3c20-188">We also recommend that you install software updates when they become available.</span><span class="sxs-lookup"><span data-stu-id="d3c20-188">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="d3c20-189">Дополнительные сведения о поддерживаемых браузерах и системных требованиях для службы см. в требованиях к [системе для Office.](https://products.office.com/office-system-requirements)</span><span class="sxs-lookup"><span data-stu-id="d3c20-189">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="d3c20-190">Поддерживаемые языки</span><span class="sxs-lookup"><span data-stu-id="d3c20-190">Supported languages</span></span>

<span data-ttu-id="d3c20-191">Следующие языки поддерживаются и доступны для EAC в автономных EOP.</span><span class="sxs-lookup"><span data-stu-id="d3c20-191">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="d3c20-192">Амхарский</span><span class="sxs-lookup"><span data-stu-id="d3c20-192">Amharic</span></span>
- <span data-ttu-id="d3c20-193">Арабский</span><span class="sxs-lookup"><span data-stu-id="d3c20-193">Arabic</span></span>
- <span data-ttu-id="d3c20-194">Баскский (Basque)</span><span class="sxs-lookup"><span data-stu-id="d3c20-194">Basque (Basque)</span></span>
- <span data-ttu-id="d3c20-195">Бенгальский (Индия)</span><span class="sxs-lookup"><span data-stu-id="d3c20-195">Bengali (India)</span></span>
- <span data-ttu-id="d3c20-196">Болгарский</span><span class="sxs-lookup"><span data-stu-id="d3c20-196">Bulgarian</span></span>
- <span data-ttu-id="d3c20-197">Каталонский</span><span class="sxs-lookup"><span data-stu-id="d3c20-197">Catalan</span></span>
- <span data-ttu-id="d3c20-198">китайский (упрощенное письмо);</span><span class="sxs-lookup"><span data-stu-id="d3c20-198">Chinese (Simplified)</span></span>
- <span data-ttu-id="d3c20-199">китайский (традиционный);</span><span class="sxs-lookup"><span data-stu-id="d3c20-199">Chinese (Traditional)</span></span>
- <span data-ttu-id="d3c20-200">хорватский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-200">Croatian</span></span>
- <span data-ttu-id="d3c20-201">чешский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-201">Czech</span></span>
- <span data-ttu-id="d3c20-202">датский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-202">Danish</span></span>
- <span data-ttu-id="d3c20-203">голландский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-203">Dutch</span></span>
- <span data-ttu-id="d3c20-204">английский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-204">English</span></span>
- <span data-ttu-id="d3c20-205">эстонский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-205">Estonian</span></span>
- <span data-ttu-id="d3c20-206">Филиппинский (Филиппины)</span><span class="sxs-lookup"><span data-stu-id="d3c20-206">Filipino (Philippines)</span></span>
- <span data-ttu-id="d3c20-207">финский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-207">Finnish</span></span>
- <span data-ttu-id="d3c20-208">французский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-208">French</span></span>
- <span data-ttu-id="d3c20-209">Галисийский</span><span class="sxs-lookup"><span data-stu-id="d3c20-209">Galician</span></span>
- <span data-ttu-id="d3c20-210">немецкий;</span><span class="sxs-lookup"><span data-stu-id="d3c20-210">German</span></span>
- <span data-ttu-id="d3c20-211">греческий;</span><span class="sxs-lookup"><span data-stu-id="d3c20-211">Greek</span></span>
- <span data-ttu-id="d3c20-212">Гуджарати</span><span class="sxs-lookup"><span data-stu-id="d3c20-212">Gujarati</span></span>
- <span data-ttu-id="d3c20-213">иврит;</span><span class="sxs-lookup"><span data-stu-id="d3c20-213">Hebrew</span></span>
- <span data-ttu-id="d3c20-214">хинди;</span><span class="sxs-lookup"><span data-stu-id="d3c20-214">Hindi</span></span>
- <span data-ttu-id="d3c20-215">венгерский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-215">Hungarian</span></span>
- <span data-ttu-id="d3c20-216">Исландский</span><span class="sxs-lookup"><span data-stu-id="d3c20-216">Icelandic</span></span>
- <span data-ttu-id="d3c20-217">индонезийский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-217">Indonesian</span></span>
- <span data-ttu-id="d3c20-218">итальянский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-218">Italian</span></span>
- <span data-ttu-id="d3c20-219">японский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-219">Japanese</span></span>
- <span data-ttu-id="d3c20-220">Каннада</span><span class="sxs-lookup"><span data-stu-id="d3c20-220">Kannada</span></span>
- <span data-ttu-id="d3c20-221">Казахский</span><span class="sxs-lookup"><span data-stu-id="d3c20-221">Kazakh</span></span>
- <span data-ttu-id="d3c20-222">Суахили</span><span class="sxs-lookup"><span data-stu-id="d3c20-222">Kiswahili</span></span>
- <span data-ttu-id="d3c20-223">корейский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-223">Korean</span></span>
- <span data-ttu-id="d3c20-224">латышский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-224">Latvian</span></span>
- <span data-ttu-id="d3c20-225">литовский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-225">Lithuanian</span></span>
- <span data-ttu-id="d3c20-226">Малайский (Бруней-Даруссалам)</span><span class="sxs-lookup"><span data-stu-id="d3c20-226">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="d3c20-227">Малайский (Малайзия)</span><span class="sxs-lookup"><span data-stu-id="d3c20-227">Malay (Malaysia)</span></span>
- <span data-ttu-id="d3c20-228">Малаялам</span><span class="sxs-lookup"><span data-stu-id="d3c20-228">Malayalam</span></span>
- <span data-ttu-id="d3c20-229">Маратхи</span><span class="sxs-lookup"><span data-stu-id="d3c20-229">Marathi</span></span>
- <span data-ttu-id="d3c20-230">Норвежский (букмол)</span><span class="sxs-lookup"><span data-stu-id="d3c20-230">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="d3c20-231">Норвежский (нюнорск)</span><span class="sxs-lookup"><span data-stu-id="d3c20-231">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="d3c20-232">Ория</span><span class="sxs-lookup"><span data-stu-id="d3c20-232">Oriya</span></span>
- <span data-ttu-id="d3c20-233">Персидский</span><span class="sxs-lookup"><span data-stu-id="d3c20-233">Persian</span></span>
- <span data-ttu-id="d3c20-234">польский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-234">Polish</span></span>
- <span data-ttu-id="d3c20-235">португальский (Бразилия);</span><span class="sxs-lookup"><span data-stu-id="d3c20-235">Portuguese (Brazil)</span></span>
- <span data-ttu-id="d3c20-236">португальский (Португалия);</span><span class="sxs-lookup"><span data-stu-id="d3c20-236">Portuguese (Portugal)</span></span>
- <span data-ttu-id="d3c20-237">румынский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-237">Romanian</span></span>
- <span data-ttu-id="d3c20-238">русский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-238">Russian</span></span>
- <span data-ttu-id="d3c20-239">Сербскохорватский (кириллица, Сербия)</span><span class="sxs-lookup"><span data-stu-id="d3c20-239">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="d3c20-240">сербский (латиница);</span><span class="sxs-lookup"><span data-stu-id="d3c20-240">Serbian (Latin)</span></span>
- <span data-ttu-id="d3c20-241">словацкий;</span><span class="sxs-lookup"><span data-stu-id="d3c20-241">Slovak</span></span>
- <span data-ttu-id="d3c20-242">словенский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-242">Slovenian</span></span>
- <span data-ttu-id="d3c20-243">испанский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-243">Spanish</span></span>
- <span data-ttu-id="d3c20-244">шведский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-244">Swedish</span></span>
- <span data-ttu-id="d3c20-245">Тамильский</span><span class="sxs-lookup"><span data-stu-id="d3c20-245">Tamil</span></span>
- <span data-ttu-id="d3c20-246">Телугу</span><span class="sxs-lookup"><span data-stu-id="d3c20-246">Telugu</span></span>
- <span data-ttu-id="d3c20-247">тайский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-247">Thai</span></span>
- <span data-ttu-id="d3c20-248">турецкий;</span><span class="sxs-lookup"><span data-stu-id="d3c20-248">Turkish</span></span>
- <span data-ttu-id="d3c20-249">украинский;</span><span class="sxs-lookup"><span data-stu-id="d3c20-249">Ukrainian</span></span>
- <span data-ttu-id="d3c20-250">Урду</span><span class="sxs-lookup"><span data-stu-id="d3c20-250">Urdu</span></span>
- <span data-ttu-id="d3c20-251">Вьетнамский</span><span class="sxs-lookup"><span data-stu-id="d3c20-251">Vietnamese</span></span>
- <span data-ttu-id="d3c20-252">Валлийский</span><span class="sxs-lookup"><span data-stu-id="d3c20-252">Welsh</span></span>
