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
description: Узнайте о интерфейсе управления веб-сайтом в автономных exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab834d14673370a39e148aefa568591ff4c50b8f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916998"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="2c610-103">Центр администрирования Exchange в автономной службе EOP</span><span class="sxs-lookup"><span data-stu-id="2c610-103">Exchange admin center in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2c610-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="2c610-104">**Applies to**</span></span>
-  [<span data-ttu-id="2c610-105">Автономный exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2c610-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="2c610-106">Центр администрирования Exchange (EAC) — это веб-консоль управления для автономных служб Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="2c610-106">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="2c610-107">Ищете версию Exchange Online этой темы?</span><span class="sxs-lookup"><span data-stu-id="2c610-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="2c610-108">См. [центр администрирования Exchange в Exchange Online.](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="2c610-108">See [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="2c610-109">Откройте EAC в EOP</span><span class="sxs-lookup"><span data-stu-id="2c610-109">Open the EAC in EOP</span></span>

<span data-ttu-id="2c610-110">Автономные клиенты EOP могут получить доступ к EAC с помощью следующих методов:</span><span class="sxs-lookup"><span data-stu-id="2c610-110">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="2c610-111">**Из центра администрирования Microsoft 365:**</span><span class="sxs-lookup"><span data-stu-id="2c610-111">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="2c610-112">Перейдите и <https://admin.microsoft.com> нажмите **кнопку Показать все**.</span><span class="sxs-lookup"><span data-stu-id="2c610-112">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Щелкните Показать все в центре администрирования Microsoft 365](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="2c610-114">В разделе **Центры администрирования,** который отображается, щелкните **Все центры администрирования**.</span><span class="sxs-lookup"><span data-stu-id="2c610-114">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Щелкните все центры администрирования в центре администрирования Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="2c610-116">На странице **Все центры администрирования,** которая появляется, нажмите **Exchange Online Protection**.</span><span class="sxs-lookup"><span data-stu-id="2c610-116">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="2c610-117">Перейдите непосредственно к `https://admin.protection.outlook.com/ecp/` .</span><span class="sxs-lookup"><span data-stu-id="2c610-117">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="2c610-118">Общие элементы пользовательского интерфейса в EAC в EOP</span><span class="sxs-lookup"><span data-stu-id="2c610-118">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="2c610-119">В этом разделе рассматриваются элементы интерфейса пользователя в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="2c610-119">This section describes the user interface elements that are found in the EAC.</span></span>

![Центр администрирования Exchange в Exchange Online Protection](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="2c610-121">Панель "Функции"</span><span class="sxs-lookup"><span data-stu-id="2c610-121">Feature Pane</span></span>

<span data-ttu-id="2c610-p102">Это первый уровень навигации для большинства заданий, выполняемых в Центре администрирования Exchange. Панель функций состоит из областей функций.</span><span class="sxs-lookup"><span data-stu-id="2c610-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="2c610-124">**Получатели.** Здесь будут просматриваться группы и внешние контакты.</span><span class="sxs-lookup"><span data-stu-id="2c610-124">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="2c610-125">**Разрешения.** Здесь вы будете управлять ролями администратора.</span><span class="sxs-lookup"><span data-stu-id="2c610-125">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="2c610-126">**Управление соответствием** требованиям. Здесь вы найдете отчет группы ролей администратора и отчет журнала аудита администратора.</span><span class="sxs-lookup"><span data-stu-id="2c610-126">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="2c610-127">**Защита.** Здесь можно управлять политиками защиты от вредоносных программ, политикой фильтра подключений по умолчанию и DKIM.</span><span class="sxs-lookup"><span data-stu-id="2c610-127">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2c610-128">Вы должны управлять политиками защиты от вредоносных программ и политикой фильтрации подключений по умолчанию в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="2c610-128">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="2c610-129">Дополнительные сведения см. в [перенастройке](configure-anti-malware-policies.md) политик по борьбе с вредоносными программами в EOP и настройке фильтрации подключений [в EOP.](configure-the-connection-filter-policy.md)</span><span class="sxs-lookup"><span data-stu-id="2c610-129">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="2c610-130">**Поток** почты. Здесь вы будете управлять правилами потока почты (также известными как правила транспорта), принятыми доменами и соединитетелями, а также с возможностью запуска трассировки сообщений.</span><span class="sxs-lookup"><span data-stu-id="2c610-130">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="2c610-131">**Гибрид.** Здесь можно запустить мастер гибридной конфигурации [и](/Exchange/hybrid-configuration-wizard)установить модуль [PowerShell Exchange Online.](/powershell/exchange/mfa-connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="2c610-131">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="2c610-132">Вкладки</span><span class="sxs-lookup"><span data-stu-id="2c610-132">Tabs</span></span>

<span data-ttu-id="2c610-133">Вкладки  это второй уровень навигации.</span><span class="sxs-lookup"><span data-stu-id="2c610-133">The tabs are your second level of navigation.</span></span> <span data-ttu-id="2c610-134">Каждый из компонентов содержит различные вкладки, на каждой из которых будет представлена функция.</span><span class="sxs-lookup"><span data-stu-id="2c610-134">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="2c610-135">Панель инструментов</span><span class="sxs-lookup"><span data-stu-id="2c610-135">Toolbar</span></span>

<span data-ttu-id="2c610-p105">При выборе большинства вкладок отображается панель инструментов. Панель инструментов содержит значки, которые выполняют определенное действие. Значки и их действия описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="2c610-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="2c610-139">Значок</span><span class="sxs-lookup"><span data-stu-id="2c610-139">Icon</span></span>|<span data-ttu-id="2c610-140">Имя</span><span class="sxs-lookup"><span data-stu-id="2c610-140">Name</span></span>|<span data-ttu-id="2c610-141">Action</span><span class="sxs-lookup"><span data-stu-id="2c610-141">Action</span></span>|
|---|---|---|
|![Значок добавления](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="2c610-143">"Добавить", "Создать"</span><span class="sxs-lookup"><span data-stu-id="2c610-143">Add, New</span></span>|<span data-ttu-id="2c610-p106">Используйте этот значок для создания нового объекта. Некоторые из этих значков имеют стрелку вниз, щелкнув которую, можно отобразить дополнительные объекты, которые можно создать.</span><span class="sxs-lookup"><span data-stu-id="2c610-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Значок редактирования](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="2c610-147">Изменить</span><span class="sxs-lookup"><span data-stu-id="2c610-147">Edit</span></span>|<span data-ttu-id="2c610-148">Используйте этот значок для редактирования объекта.</span><span class="sxs-lookup"><span data-stu-id="2c610-148">Use this icon to edit an object.</span></span>|
|![Значок удаления](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="2c610-150">Удаление</span><span class="sxs-lookup"><span data-stu-id="2c610-150">Delete</span></span>|<span data-ttu-id="2c610-p107">Используйте этот значок для удаления объекта. У некоторых значков удаления есть стрелка вниз, которая позволяет отобразить дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="2c610-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![значок поиска](../../media/ITPro-EAC-.gif)|<span data-ttu-id="2c610-154">Поиск</span><span class="sxs-lookup"><span data-stu-id="2c610-154">Search</span></span>|<span data-ttu-id="2c610-155">Этот значок позволяет открыть поле поиска, в котором можно ввести фразу поиска для объекта, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="2c610-155">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Значок обновления](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="2c610-157">Обновить</span><span class="sxs-lookup"><span data-stu-id="2c610-157">Refresh</span></span>|<span data-ttu-id="2c610-158">Используйте этот значок, чтобы обновить представление списка.</span><span class="sxs-lookup"><span data-stu-id="2c610-158">Use this icon to refresh the list view.</span></span>|
|![Значок дополнительных параметров](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="2c610-160">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="2c610-160">More options</span></span>|<span data-ttu-id="2c610-p108">Используйте этот значок для просмотра дополнительных действий, которые можно выполнить для объектов этой вкладки. Например, при нажатии этого значка в области **Получатели \> Пользователи** отображается параметр для выполнения **расширенного поиска**.  </span><span class="sxs-lookup"><span data-stu-id="2c610-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Значок "Стрелка вверх"](../../media/ITPro-EAC-UpArrowIcon.gif)![Значок "Стрелка вниз"](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="2c610-165">Стрелка вверх и стрелка вниз</span><span class="sxs-lookup"><span data-stu-id="2c610-165">Up arrow and down arrow</span></span>|<span data-ttu-id="2c610-166">Используйте эти значки для изменения приоритета объекта.</span><span class="sxs-lookup"><span data-stu-id="2c610-166">Use these icons to move an object's priority up or down.</span></span>|
|![Значок "Удалить"](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="2c610-168">Удалить</span><span class="sxs-lookup"><span data-stu-id="2c610-168">Remove</span></span>|<span data-ttu-id="2c610-169">Используйте этот значок, чтобы удалять объекты из списка.</span><span class="sxs-lookup"><span data-stu-id="2c610-169">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="2c610-170">Представление списка</span><span class="sxs-lookup"><span data-stu-id="2c610-170">List View</span></span>

<span data-ttu-id="2c610-p109">При выборе вкладки в большинстве случаев отображается представление списка. Лимит просмотра в Центре администрирования Exchange составляет около 10 000 объектов. Кроме того, включено постраничное разделение, так что вы можете листать страницы результатов.</span><span class="sxs-lookup"><span data-stu-id="2c610-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="2c610-174">Область сведений</span><span class="sxs-lookup"><span data-stu-id="2c610-174">Details Pane</span></span>

<span data-ttu-id="2c610-p110">При выборе объекта в представлении списка информация об этом объекте отображается в области сведений. В некоторых случаях область сведений включает задачи управления.</span><span class="sxs-lookup"><span data-stu-id="2c610-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="2c610-177">Иконка "Я" и справка</span><span class="sxs-lookup"><span data-stu-id="2c610-177">Me tile and Help</span></span>

<span data-ttu-id="2c610-178">Плитка **Я** позволяет выйти из Центра администрирования Exchange и войти в него как другой пользователь.</span><span class="sxs-lookup"><span data-stu-id="2c610-178">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="2c610-179">Из выпадаемого меню Значок справки можно сделать ![ ](../../media/ITPro-EAC-HelpIcon.gif) следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2c610-179">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can do the following actions:</span></span>

- <span data-ttu-id="2c610-180">**Справка.** ![ Щелкните значок ](../../media/ITPro-EAC-HelpIcon.gif) справки, чтобы просмотреть содержимое справки в Интернете.</span><span class="sxs-lookup"><span data-stu-id="2c610-180">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>
- <span data-ttu-id="2c610-181">**Обратная** связь. Оставьте отзывы.</span><span class="sxs-lookup"><span data-stu-id="2c610-181">**Feedback**: Leave feedback.</span></span>
- <span data-ttu-id="2c610-182">**Сообщество**. Публикация вопроса для поиска ответов на форумах сообщества.</span><span class="sxs-lookup"><span data-stu-id="2c610-182">**Community**: Post a question for find answers in the community forums.</span></span>
- <span data-ttu-id="2c610-183">**Отключение пузыря справки.** Пузырь справки отображает контекстную справку для полей при создании или редактировании объекта.</span><span class="sxs-lookup"><span data-stu-id="2c610-183">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="2c610-184">Вы можете отключить пузырь справки или включить его, если он отключен.</span><span class="sxs-lookup"><span data-stu-id="2c610-184">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>
- <span data-ttu-id="2c610-185">**Показать командный журнал:** открывается новое окно, которое отображает эквивалентные команды PowerShell, основанные на том, что вы настроили в EAC.</span><span class="sxs-lookup"><span data-stu-id="2c610-185">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="2c610-186">Поддерживаемые веб-браузеры</span><span class="sxs-lookup"><span data-stu-id="2c610-186">Supported Browsers</span></span>

<span data-ttu-id="2c610-187">Для наилучшего использования EAC рекомендуется всегда использовать новейшие браузеры, клиенты Office и приложения.</span><span class="sxs-lookup"><span data-stu-id="2c610-187">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="2c610-188">We also recommend that you install software updates when they become available.</span><span class="sxs-lookup"><span data-stu-id="2c610-188">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="2c610-189">Дополнительные сведения о поддерживаемых браузерах и системных требованиях к службе см. в сведениях [System requirements for Office.](https://products.office.com/office-system-requirements)</span><span class="sxs-lookup"><span data-stu-id="2c610-189">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="2c610-190">Поддерживаемые языки</span><span class="sxs-lookup"><span data-stu-id="2c610-190">Supported languages</span></span>

<span data-ttu-id="2c610-191">Следующие языки поддерживаются и доступны для EAC в автономных EOP.</span><span class="sxs-lookup"><span data-stu-id="2c610-191">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="2c610-192">Амхарский</span><span class="sxs-lookup"><span data-stu-id="2c610-192">Amharic</span></span>
- <span data-ttu-id="2c610-193">Арабский</span><span class="sxs-lookup"><span data-stu-id="2c610-193">Arabic</span></span>
- <span data-ttu-id="2c610-194">Баскский (Basque)</span><span class="sxs-lookup"><span data-stu-id="2c610-194">Basque (Basque)</span></span>
- <span data-ttu-id="2c610-195">Бенгальский (Индия)</span><span class="sxs-lookup"><span data-stu-id="2c610-195">Bengali (India)</span></span>
- <span data-ttu-id="2c610-196">Болгарский</span><span class="sxs-lookup"><span data-stu-id="2c610-196">Bulgarian</span></span>
- <span data-ttu-id="2c610-197">Каталонский</span><span class="sxs-lookup"><span data-stu-id="2c610-197">Catalan</span></span>
- <span data-ttu-id="2c610-198">китайский (упрощенное письмо);</span><span class="sxs-lookup"><span data-stu-id="2c610-198">Chinese (Simplified)</span></span>
- <span data-ttu-id="2c610-199">китайский (традиционный);</span><span class="sxs-lookup"><span data-stu-id="2c610-199">Chinese (Traditional)</span></span>
- <span data-ttu-id="2c610-200">хорватский;</span><span class="sxs-lookup"><span data-stu-id="2c610-200">Croatian</span></span>
- <span data-ttu-id="2c610-201">чешский;</span><span class="sxs-lookup"><span data-stu-id="2c610-201">Czech</span></span>
- <span data-ttu-id="2c610-202">датский;</span><span class="sxs-lookup"><span data-stu-id="2c610-202">Danish</span></span>
- <span data-ttu-id="2c610-203">голландский;</span><span class="sxs-lookup"><span data-stu-id="2c610-203">Dutch</span></span>
- <span data-ttu-id="2c610-204">английский;</span><span class="sxs-lookup"><span data-stu-id="2c610-204">English</span></span>
- <span data-ttu-id="2c610-205">эстонский;</span><span class="sxs-lookup"><span data-stu-id="2c610-205">Estonian</span></span>
- <span data-ttu-id="2c610-206">Филиппинский (Филиппины)</span><span class="sxs-lookup"><span data-stu-id="2c610-206">Filipino (Philippines)</span></span>
- <span data-ttu-id="2c610-207">финский;</span><span class="sxs-lookup"><span data-stu-id="2c610-207">Finnish</span></span>
- <span data-ttu-id="2c610-208">французский;</span><span class="sxs-lookup"><span data-stu-id="2c610-208">French</span></span>
- <span data-ttu-id="2c610-209">Галисийский</span><span class="sxs-lookup"><span data-stu-id="2c610-209">Galician</span></span>
- <span data-ttu-id="2c610-210">немецкий;</span><span class="sxs-lookup"><span data-stu-id="2c610-210">German</span></span>
- <span data-ttu-id="2c610-211">греческий;</span><span class="sxs-lookup"><span data-stu-id="2c610-211">Greek</span></span>
- <span data-ttu-id="2c610-212">Гуджарати</span><span class="sxs-lookup"><span data-stu-id="2c610-212">Gujarati</span></span>
- <span data-ttu-id="2c610-213">иврит;</span><span class="sxs-lookup"><span data-stu-id="2c610-213">Hebrew</span></span>
- <span data-ttu-id="2c610-214">хинди;</span><span class="sxs-lookup"><span data-stu-id="2c610-214">Hindi</span></span>
- <span data-ttu-id="2c610-215">венгерский;</span><span class="sxs-lookup"><span data-stu-id="2c610-215">Hungarian</span></span>
- <span data-ttu-id="2c610-216">Исландский</span><span class="sxs-lookup"><span data-stu-id="2c610-216">Icelandic</span></span>
- <span data-ttu-id="2c610-217">индонезийский;</span><span class="sxs-lookup"><span data-stu-id="2c610-217">Indonesian</span></span>
- <span data-ttu-id="2c610-218">итальянский;</span><span class="sxs-lookup"><span data-stu-id="2c610-218">Italian</span></span>
- <span data-ttu-id="2c610-219">японский;</span><span class="sxs-lookup"><span data-stu-id="2c610-219">Japanese</span></span>
- <span data-ttu-id="2c610-220">Каннада</span><span class="sxs-lookup"><span data-stu-id="2c610-220">Kannada</span></span>
- <span data-ttu-id="2c610-221">Казахский</span><span class="sxs-lookup"><span data-stu-id="2c610-221">Kazakh</span></span>
- <span data-ttu-id="2c610-222">Суахили</span><span class="sxs-lookup"><span data-stu-id="2c610-222">Kiswahili</span></span>
- <span data-ttu-id="2c610-223">корейский;</span><span class="sxs-lookup"><span data-stu-id="2c610-223">Korean</span></span>
- <span data-ttu-id="2c610-224">латышский;</span><span class="sxs-lookup"><span data-stu-id="2c610-224">Latvian</span></span>
- <span data-ttu-id="2c610-225">литовский;</span><span class="sxs-lookup"><span data-stu-id="2c610-225">Lithuanian</span></span>
- <span data-ttu-id="2c610-226">Малайский (Бруней-Даруссалам)</span><span class="sxs-lookup"><span data-stu-id="2c610-226">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="2c610-227">Малайский (Малайзия)</span><span class="sxs-lookup"><span data-stu-id="2c610-227">Malay (Malaysia)</span></span>
- <span data-ttu-id="2c610-228">Малаялам</span><span class="sxs-lookup"><span data-stu-id="2c610-228">Malayalam</span></span>
- <span data-ttu-id="2c610-229">Маратхи</span><span class="sxs-lookup"><span data-stu-id="2c610-229">Marathi</span></span>
- <span data-ttu-id="2c610-230">Норвежский (букмол)</span><span class="sxs-lookup"><span data-stu-id="2c610-230">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="2c610-231">Норвежский (нюнорск)</span><span class="sxs-lookup"><span data-stu-id="2c610-231">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="2c610-232">Ория</span><span class="sxs-lookup"><span data-stu-id="2c610-232">Oriya</span></span>
- <span data-ttu-id="2c610-233">Персидский</span><span class="sxs-lookup"><span data-stu-id="2c610-233">Persian</span></span>
- <span data-ttu-id="2c610-234">польский;</span><span class="sxs-lookup"><span data-stu-id="2c610-234">Polish</span></span>
- <span data-ttu-id="2c610-235">португальский (Бразилия);</span><span class="sxs-lookup"><span data-stu-id="2c610-235">Portuguese (Brazil)</span></span>
- <span data-ttu-id="2c610-236">португальский (Португалия);</span><span class="sxs-lookup"><span data-stu-id="2c610-236">Portuguese (Portugal)</span></span>
- <span data-ttu-id="2c610-237">румынский;</span><span class="sxs-lookup"><span data-stu-id="2c610-237">Romanian</span></span>
- <span data-ttu-id="2c610-238">русский;</span><span class="sxs-lookup"><span data-stu-id="2c610-238">Russian</span></span>
- <span data-ttu-id="2c610-239">Сербскохорватский (кириллица, Сербия)</span><span class="sxs-lookup"><span data-stu-id="2c610-239">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="2c610-240">сербский (латиница);</span><span class="sxs-lookup"><span data-stu-id="2c610-240">Serbian (Latin)</span></span>
- <span data-ttu-id="2c610-241">словацкий;</span><span class="sxs-lookup"><span data-stu-id="2c610-241">Slovak</span></span>
- <span data-ttu-id="2c610-242">словенский;</span><span class="sxs-lookup"><span data-stu-id="2c610-242">Slovenian</span></span>
- <span data-ttu-id="2c610-243">испанский;</span><span class="sxs-lookup"><span data-stu-id="2c610-243">Spanish</span></span>
- <span data-ttu-id="2c610-244">шведский;</span><span class="sxs-lookup"><span data-stu-id="2c610-244">Swedish</span></span>
- <span data-ttu-id="2c610-245">Тамильский</span><span class="sxs-lookup"><span data-stu-id="2c610-245">Tamil</span></span>
- <span data-ttu-id="2c610-246">Телугу</span><span class="sxs-lookup"><span data-stu-id="2c610-246">Telugu</span></span>
- <span data-ttu-id="2c610-247">тайский;</span><span class="sxs-lookup"><span data-stu-id="2c610-247">Thai</span></span>
- <span data-ttu-id="2c610-248">турецкий;</span><span class="sxs-lookup"><span data-stu-id="2c610-248">Turkish</span></span>
- <span data-ttu-id="2c610-249">украинский;</span><span class="sxs-lookup"><span data-stu-id="2c610-249">Ukrainian</span></span>
- <span data-ttu-id="2c610-250">Урду</span><span class="sxs-lookup"><span data-stu-id="2c610-250">Urdu</span></span>
- <span data-ttu-id="2c610-251">Вьетнамский</span><span class="sxs-lookup"><span data-stu-id="2c610-251">Vietnamese</span></span>
- <span data-ttu-id="2c610-252">Валлийский</span><span class="sxs-lookup"><span data-stu-id="2c610-252">Welsh</span></span>