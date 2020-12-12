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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Узнайте об интерфейсе управления веб-сайтами в автономных системах Exchange Online Protection (EOP).
ms.openlocfilehash: fc76ecd6dafcf9453a0c6de14917c96c950f8370
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659670"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="a3a48-103">Центр администрирования Exchange в автономной службе EOP</span><span class="sxs-lookup"><span data-stu-id="a3a48-103">Exchange admin center in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a3a48-104">Центр администрирования Exchange (EAC) — это веб-консоль управления для автономных служб Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="a3a48-104">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="a3a48-105">Ищете версию этой темы для Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="a3a48-105">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="a3a48-106">См. [Центр администрирования Exchange в Exchange Online.](https://docs.microsoft.com/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="a3a48-106">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="a3a48-107">Открытие EAC в EOP</span><span class="sxs-lookup"><span data-stu-id="a3a48-107">Open the EAC in EOP</span></span>

<span data-ttu-id="a3a48-108">Клиенты автономных EOP могут получить доступ к EAC с помощью следующих методов:</span><span class="sxs-lookup"><span data-stu-id="a3a48-108">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="a3a48-109">**Из Центра администрирования Microsoft 365:**</span><span class="sxs-lookup"><span data-stu-id="a3a48-109">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="a3a48-110">Go to <https://admin.microsoft.com> and click Show **all**.</span><span class="sxs-lookup"><span data-stu-id="a3a48-110">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Щелкните "Показать все" в Центре администрирования Microsoft 365](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="a3a48-112">В разделе **"Центры администрирования"** щелкните **"Все центры администрирования".**</span><span class="sxs-lookup"><span data-stu-id="a3a48-112">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Щелкните все центры администрирования в Центре администрирования Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="a3a48-114">На странице **"Все центры администрирования"** щелкните **Exchange Online Protection.**</span><span class="sxs-lookup"><span data-stu-id="a3a48-114">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="a3a48-115">Перейдите непосредственно по этой `https://admin.protection.outlook.com/ecp/` теме.</span><span class="sxs-lookup"><span data-stu-id="a3a48-115">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="a3a48-116">Общие элементы пользовательского интерфейса в EAC в EOP</span><span class="sxs-lookup"><span data-stu-id="a3a48-116">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="a3a48-117">В этом разделе рассматриваются элементы интерфейса пользователя в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="a3a48-117">This section describes the user interface elements that are found in the EAC.</span></span>

![Центр администрирования Exchange в Exchange Online Protection](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="a3a48-119">Панель "Функции"</span><span class="sxs-lookup"><span data-stu-id="a3a48-119">Feature Pane</span></span>

<span data-ttu-id="a3a48-p102">Это первый уровень навигации для большинства заданий, выполняемых в Центре администрирования Exchange. Панель функций состоит из областей функций.</span><span class="sxs-lookup"><span data-stu-id="a3a48-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="a3a48-122">**Получатели:** здесь вы будете просматривать группы и внешние контакты.</span><span class="sxs-lookup"><span data-stu-id="a3a48-122">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="a3a48-123">**Разрешения :** здесь вы будете управлять ролями администраторов.</span><span class="sxs-lookup"><span data-stu-id="a3a48-123">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="a3a48-124">**Управление соответствием** требованиям : здесь вы найдете отчет о группе ролей администраторов и журнал аудита администратора.</span><span class="sxs-lookup"><span data-stu-id="a3a48-124">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="a3a48-125">**Защита**: здесь можно управлять политиками защиты от вредоносных программ, политикой фильтрации подключений по умолчанию и DKIM.</span><span class="sxs-lookup"><span data-stu-id="a3a48-125">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a3a48-126">В Центре безопасности & и соответствия требованиям следует управлять политиками защиты от вредоносных программ и политикой фильтрации подключений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a3a48-126">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="a3a48-127">Дополнительные сведения см. в сведениях о настройке политик борьбы с вредоносными [программами в EOP](configure-anti-malware-policies.md) и настройке фильтрации подключений [в EOP.](configure-the-connection-filter-policy.md)</span><span class="sxs-lookup"><span data-stu-id="a3a48-127">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="a3a48-128">**Поток почты**: здесь вы сможете управлять правилами потока почты (также известными как правила транспорта), принятыми доменами и соединитетелями, а также где можно запускать трассировку сообщений.</span><span class="sxs-lookup"><span data-stu-id="a3a48-128">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="a3a48-129">**Гибридная** конфигурация: здесь можно запустить мастер гибридной конфигурации [и](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)установить модуль Exchange [Online PowerShell.](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="a3a48-129">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="a3a48-130">Вкладки</span><span class="sxs-lookup"><span data-stu-id="a3a48-130">Tabs</span></span>

<span data-ttu-id="a3a48-131">Вкладки  это второй уровень навигации.</span><span class="sxs-lookup"><span data-stu-id="a3a48-131">The tabs are your second level of navigation.</span></span> <span data-ttu-id="a3a48-132">Каждый из компонентов содержит различные вкладки, на каждой из которых будет представлена функция.</span><span class="sxs-lookup"><span data-stu-id="a3a48-132">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="a3a48-133">Панель инструментов</span><span class="sxs-lookup"><span data-stu-id="a3a48-133">Toolbar</span></span>

<span data-ttu-id="a3a48-p105">При выборе большинства вкладок отображается панель инструментов. Панель инструментов содержит значки, которые выполняют определенное действие. Значки и их действия описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a3a48-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="a3a48-137">Значок</span><span class="sxs-lookup"><span data-stu-id="a3a48-137">Icon</span></span>|<span data-ttu-id="a3a48-138">Имя</span><span class="sxs-lookup"><span data-stu-id="a3a48-138">Name</span></span>|<span data-ttu-id="a3a48-139">Action</span><span class="sxs-lookup"><span data-stu-id="a3a48-139">Action</span></span>|
|---|---|---|
|![Значок добавления](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="a3a48-141">"Добавить", "Создать"</span><span class="sxs-lookup"><span data-stu-id="a3a48-141">Add, New</span></span>|<span data-ttu-id="a3a48-p106">Используйте этот значок для создания нового объекта. Некоторые из этих значков имеют стрелку вниз, щелкнув которую, можно отобразить дополнительные объекты, которые можно создать.</span><span class="sxs-lookup"><span data-stu-id="a3a48-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Значок редактирования](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="a3a48-145">Изменить</span><span class="sxs-lookup"><span data-stu-id="a3a48-145">Edit</span></span>|<span data-ttu-id="a3a48-146">Используйте этот значок для редактирования объекта.</span><span class="sxs-lookup"><span data-stu-id="a3a48-146">Use this icon to edit an object.</span></span>|
|![Значок удаления](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="a3a48-148">Удаление</span><span class="sxs-lookup"><span data-stu-id="a3a48-148">Delete</span></span>|<span data-ttu-id="a3a48-p107">Используйте этот значок для удаления объекта. У некоторых значков удаления есть стрелка вниз, которая позволяет отобразить дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="a3a48-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![значок поиска](../../media/ITPro-EAC-.gif)|<span data-ttu-id="a3a48-152">Поиск</span><span class="sxs-lookup"><span data-stu-id="a3a48-152">Search</span></span>|<span data-ttu-id="a3a48-153">Этот значок позволяет открыть поле поиска, в котором можно ввести фразу поиска для объекта, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="a3a48-153">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Значок обновления](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="a3a48-155">Обновить</span><span class="sxs-lookup"><span data-stu-id="a3a48-155">Refresh</span></span>|<span data-ttu-id="a3a48-156">Используйте этот значок, чтобы обновить представление списка.</span><span class="sxs-lookup"><span data-stu-id="a3a48-156">Use this icon to refresh the list view.</span></span>|
|![Значок дополнительных параметров](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="a3a48-158">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="a3a48-158">More options</span></span>|<span data-ttu-id="a3a48-p108">Используйте этот значок для просмотра дополнительных действий, которые можно выполнить для объектов этой вкладки. Например, при нажатии этого значка в области **Получатели \> Пользователи** отображается параметр для выполнения **расширенного поиска**.  </span><span class="sxs-lookup"><span data-stu-id="a3a48-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Значок "Стрелка вверх"](../../media/ITPro-EAC-UpArrowIcon.gif)![Значок "Стрелка вниз"](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="a3a48-163">Стрелка вверх и стрелка вниз</span><span class="sxs-lookup"><span data-stu-id="a3a48-163">Up arrow and down arrow</span></span>|<span data-ttu-id="a3a48-164">Используйте эти значки для изменения приоритета объекта.</span><span class="sxs-lookup"><span data-stu-id="a3a48-164">Use these icons to move an object's priority up or down.</span></span>|
|![Значок "Удалить"](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="a3a48-166">Удалить</span><span class="sxs-lookup"><span data-stu-id="a3a48-166">Remove</span></span>|<span data-ttu-id="a3a48-167">Используйте этот значок, чтобы удалять объекты из списка.</span><span class="sxs-lookup"><span data-stu-id="a3a48-167">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="a3a48-168">Представление списка</span><span class="sxs-lookup"><span data-stu-id="a3a48-168">List View</span></span>

<span data-ttu-id="a3a48-p109">При выборе вкладки в большинстве случаев отображается представление списка. Лимит просмотра в Центре администрирования Exchange составляет около 10 000 объектов. Кроме того, включено постраничное разделение, так что вы можете листать страницы результатов.</span><span class="sxs-lookup"><span data-stu-id="a3a48-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="a3a48-172">Область сведений</span><span class="sxs-lookup"><span data-stu-id="a3a48-172">Details Pane</span></span>

<span data-ttu-id="a3a48-p110">При выборе объекта в представлении списка информация об этом объекте отображается в области сведений. В некоторых случаях область сведений включает задачи управления.</span><span class="sxs-lookup"><span data-stu-id="a3a48-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="a3a48-175">Иконка "Я" и справка</span><span class="sxs-lookup"><span data-stu-id="a3a48-175">Me tile and Help</span></span>

<span data-ttu-id="a3a48-176">Плитка **Я** позволяет выйти из Центра администрирования Exchange и войти в него как другой пользователь.</span><span class="sxs-lookup"><span data-stu-id="a3a48-176">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="a3a48-177">В **выпадаемом** меню "Значок справки" ![ можно сделать следующие ](../../media/ITPro-EAC-HelpIcon.gif) действия:</span><span class="sxs-lookup"><span data-stu-id="a3a48-177">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can do the following actions:</span></span>

- <span data-ttu-id="a3a48-178">**Справка:** ![ щелкните значок ](../../media/ITPro-EAC-HelpIcon.gif) справки, чтобы просмотреть содержимое справки в Интернете.</span><span class="sxs-lookup"><span data-stu-id="a3a48-178">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>
- <span data-ttu-id="a3a48-179">**Обратная** связь: оставьте отзыв.</span><span class="sxs-lookup"><span data-stu-id="a3a48-179">**Feedback**: Leave feedback.</span></span>
- <span data-ttu-id="a3a48-180">**Сообщество:** зайдите на форумы сообщества, чтобы найти ответы на них.</span><span class="sxs-lookup"><span data-stu-id="a3a48-180">**Community**: Post a question for find answers in the community forums.</span></span>
- <span data-ttu-id="a3a48-181">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span><span class="sxs-lookup"><span data-stu-id="a3a48-181">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="a3a48-182">Вы можете отключить пузырьок справки или включить его, если он отключен.</span><span class="sxs-lookup"><span data-stu-id="a3a48-182">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>
- <span data-ttu-id="a3a48-183">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span><span class="sxs-lookup"><span data-stu-id="a3a48-183">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="a3a48-184">Поддерживаемые веб-браузеры</span><span class="sxs-lookup"><span data-stu-id="a3a48-184">Supported Browsers</span></span>

<span data-ttu-id="a3a48-185">Для лучшего использования EAC рекомендуется всегда использовать новейшие браузеры, клиенты Office и приложения.</span><span class="sxs-lookup"><span data-stu-id="a3a48-185">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="a3a48-186">We also recommend that you install software updates when they become available.</span><span class="sxs-lookup"><span data-stu-id="a3a48-186">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="a3a48-187">Дополнительные сведения о поддерживаемых браузерах и системных требованиях для службы см. в требованиях к [системе для Office.](https://products.office.com/office-system-requirements)</span><span class="sxs-lookup"><span data-stu-id="a3a48-187">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="a3a48-188">Поддерживаемые языки</span><span class="sxs-lookup"><span data-stu-id="a3a48-188">Supported languages</span></span>

<span data-ttu-id="a3a48-189">Следующие языки поддерживаются и доступны для EAC в автономных EOP.</span><span class="sxs-lookup"><span data-stu-id="a3a48-189">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="a3a48-190">Амхарский</span><span class="sxs-lookup"><span data-stu-id="a3a48-190">Amharic</span></span>
- <span data-ttu-id="a3a48-191">Арабский</span><span class="sxs-lookup"><span data-stu-id="a3a48-191">Arabic</span></span>
- <span data-ttu-id="a3a48-192">Баскский (Basque)</span><span class="sxs-lookup"><span data-stu-id="a3a48-192">Basque (Basque)</span></span>
- <span data-ttu-id="a3a48-193">Бенгальский (Индия)</span><span class="sxs-lookup"><span data-stu-id="a3a48-193">Bengali (India)</span></span>
- <span data-ttu-id="a3a48-194">Болгарский</span><span class="sxs-lookup"><span data-stu-id="a3a48-194">Bulgarian</span></span>
- <span data-ttu-id="a3a48-195">Каталонский</span><span class="sxs-lookup"><span data-stu-id="a3a48-195">Catalan</span></span>
- <span data-ttu-id="a3a48-196">китайский (упрощенное письмо);</span><span class="sxs-lookup"><span data-stu-id="a3a48-196">Chinese (Simplified)</span></span>
- <span data-ttu-id="a3a48-197">китайский (традиционный);</span><span class="sxs-lookup"><span data-stu-id="a3a48-197">Chinese (Traditional)</span></span>
- <span data-ttu-id="a3a48-198">хорватский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-198">Croatian</span></span>
- <span data-ttu-id="a3a48-199">чешский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-199">Czech</span></span>
- <span data-ttu-id="a3a48-200">датский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-200">Danish</span></span>
- <span data-ttu-id="a3a48-201">голландский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-201">Dutch</span></span>
- <span data-ttu-id="a3a48-202">английский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-202">English</span></span>
- <span data-ttu-id="a3a48-203">эстонский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-203">Estonian</span></span>
- <span data-ttu-id="a3a48-204">Филиппинский (Филиппины)</span><span class="sxs-lookup"><span data-stu-id="a3a48-204">Filipino (Philippines)</span></span>
- <span data-ttu-id="a3a48-205">финский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-205">Finnish</span></span>
- <span data-ttu-id="a3a48-206">французский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-206">French</span></span>
- <span data-ttu-id="a3a48-207">Галисийский</span><span class="sxs-lookup"><span data-stu-id="a3a48-207">Galician</span></span>
- <span data-ttu-id="a3a48-208">немецкий;</span><span class="sxs-lookup"><span data-stu-id="a3a48-208">German</span></span>
- <span data-ttu-id="a3a48-209">греческий;</span><span class="sxs-lookup"><span data-stu-id="a3a48-209">Greek</span></span>
- <span data-ttu-id="a3a48-210">Гуджарати</span><span class="sxs-lookup"><span data-stu-id="a3a48-210">Gujarati</span></span>
- <span data-ttu-id="a3a48-211">иврит;</span><span class="sxs-lookup"><span data-stu-id="a3a48-211">Hebrew</span></span>
- <span data-ttu-id="a3a48-212">хинди;</span><span class="sxs-lookup"><span data-stu-id="a3a48-212">Hindi</span></span>
- <span data-ttu-id="a3a48-213">венгерский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-213">Hungarian</span></span>
- <span data-ttu-id="a3a48-214">Исландский</span><span class="sxs-lookup"><span data-stu-id="a3a48-214">Icelandic</span></span>
- <span data-ttu-id="a3a48-215">индонезийский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-215">Indonesian</span></span>
- <span data-ttu-id="a3a48-216">итальянский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-216">Italian</span></span>
- <span data-ttu-id="a3a48-217">японский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-217">Japanese</span></span>
- <span data-ttu-id="a3a48-218">Каннада</span><span class="sxs-lookup"><span data-stu-id="a3a48-218">Kannada</span></span>
- <span data-ttu-id="a3a48-219">Казахский</span><span class="sxs-lookup"><span data-stu-id="a3a48-219">Kazakh</span></span>
- <span data-ttu-id="a3a48-220">Суахили</span><span class="sxs-lookup"><span data-stu-id="a3a48-220">Kiswahili</span></span>
- <span data-ttu-id="a3a48-221">корейский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-221">Korean</span></span>
- <span data-ttu-id="a3a48-222">латышский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-222">Latvian</span></span>
- <span data-ttu-id="a3a48-223">литовский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-223">Lithuanian</span></span>
- <span data-ttu-id="a3a48-224">Малайский (Бруней-Даруссалам)</span><span class="sxs-lookup"><span data-stu-id="a3a48-224">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="a3a48-225">Малайский (Малайзия)</span><span class="sxs-lookup"><span data-stu-id="a3a48-225">Malay (Malaysia)</span></span>
- <span data-ttu-id="a3a48-226">Малаялам</span><span class="sxs-lookup"><span data-stu-id="a3a48-226">Malayalam</span></span>
- <span data-ttu-id="a3a48-227">Маратхи</span><span class="sxs-lookup"><span data-stu-id="a3a48-227">Marathi</span></span>
- <span data-ttu-id="a3a48-228">Норвежский (букмол)</span><span class="sxs-lookup"><span data-stu-id="a3a48-228">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="a3a48-229">Норвежский (нюнорск)</span><span class="sxs-lookup"><span data-stu-id="a3a48-229">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="a3a48-230">Ория</span><span class="sxs-lookup"><span data-stu-id="a3a48-230">Oriya</span></span>
- <span data-ttu-id="a3a48-231">Персидский</span><span class="sxs-lookup"><span data-stu-id="a3a48-231">Persian</span></span>
- <span data-ttu-id="a3a48-232">польский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-232">Polish</span></span>
- <span data-ttu-id="a3a48-233">португальский (Бразилия);</span><span class="sxs-lookup"><span data-stu-id="a3a48-233">Portuguese (Brazil)</span></span>
- <span data-ttu-id="a3a48-234">португальский (Португалия);</span><span class="sxs-lookup"><span data-stu-id="a3a48-234">Portuguese (Portugal)</span></span>
- <span data-ttu-id="a3a48-235">румынский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-235">Romanian</span></span>
- <span data-ttu-id="a3a48-236">русский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-236">Russian</span></span>
- <span data-ttu-id="a3a48-237">Сербскохорватский (кириллица, Сербия)</span><span class="sxs-lookup"><span data-stu-id="a3a48-237">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="a3a48-238">сербский (латиница);</span><span class="sxs-lookup"><span data-stu-id="a3a48-238">Serbian (Latin)</span></span>
- <span data-ttu-id="a3a48-239">словацкий;</span><span class="sxs-lookup"><span data-stu-id="a3a48-239">Slovak</span></span>
- <span data-ttu-id="a3a48-240">словенский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-240">Slovenian</span></span>
- <span data-ttu-id="a3a48-241">испанский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-241">Spanish</span></span>
- <span data-ttu-id="a3a48-242">шведский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-242">Swedish</span></span>
- <span data-ttu-id="a3a48-243">Тамильский</span><span class="sxs-lookup"><span data-stu-id="a3a48-243">Tamil</span></span>
- <span data-ttu-id="a3a48-244">Телугу</span><span class="sxs-lookup"><span data-stu-id="a3a48-244">Telugu</span></span>
- <span data-ttu-id="a3a48-245">тайский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-245">Thai</span></span>
- <span data-ttu-id="a3a48-246">турецкий;</span><span class="sxs-lookup"><span data-stu-id="a3a48-246">Turkish</span></span>
- <span data-ttu-id="a3a48-247">украинский;</span><span class="sxs-lookup"><span data-stu-id="a3a48-247">Ukrainian</span></span>
- <span data-ttu-id="a3a48-248">Урду</span><span class="sxs-lookup"><span data-stu-id="a3a48-248">Urdu</span></span>
- <span data-ttu-id="a3a48-249">Вьетнамский</span><span class="sxs-lookup"><span data-stu-id="a3a48-249">Vietnamese</span></span>
- <span data-ttu-id="a3a48-250">Валлийский</span><span class="sxs-lookup"><span data-stu-id="a3a48-250">Welsh</span></span>
