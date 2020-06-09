---
title: Центр администрирования Exchange в автономном EOP
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
description: Сведения об интерфейсе веб-управления в автономной службе Exchange Online Protection (EOP).
ms.openlocfilehash: 777597489e54c642220cb42f0c686b675101897f
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617002"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="7ba1e-103">Центр администрирования Exchange в автономном EOP</span><span class="sxs-lookup"><span data-stu-id="7ba1e-103">Exchange admin center in standalone EOP</span></span>

<span data-ttu-id="7ba1e-104">Центр администрирования Exchange — это веб-консоль управления для отдельной Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="7ba1e-104">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="7ba1e-105">Ищете версию этой статьи для Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="7ba1e-105">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="7ba1e-106">Обратитесь к [центру администрирования Exchange в Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="7ba1e-106">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="7ba1e-107">Открытие центра администрирования Exchange в EOP</span><span class="sxs-lookup"><span data-stu-id="7ba1e-107">Open the EAC in EOP</span></span>

<span data-ttu-id="7ba1e-108">Автономные клиенты EOP могут получать доступ к центру администрирования Exchange с помощью следующих методов:</span><span class="sxs-lookup"><span data-stu-id="7ba1e-108">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="7ba1e-109">**В центре администрирования Microsoft 365**:</span><span class="sxs-lookup"><span data-stu-id="7ba1e-109">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="7ba1e-110">Перейдите к разделу <https://admin.microsoft.com> и выберите команду **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-110">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Щелкните Показать все в центре администрирования Microsoft 365](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="7ba1e-112">В открывшемся разделе **центры администрирования** выберите **все центры администрирования**.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-112">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Выберите пункт все центры администрирования в центре администрирования Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="7ba1e-114">На открывшейся странице **все центры администрирования** выберите **Exchange Online Protection**.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-114">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="7ba1e-115">Перейдите непосредственно к `https://admin.protection.outlook.com/ecp/` .</span><span class="sxs-lookup"><span data-stu-id="7ba1e-115">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="7ba1e-116">Общие элементы пользовательского интерфейса в центре администрирования Exchange в EOP</span><span class="sxs-lookup"><span data-stu-id="7ba1e-116">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="7ba1e-117">В этом разделе рассматриваются элементы интерфейса пользователя в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP — Админцентер](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="7ba1e-119">Панель "Функции"</span><span class="sxs-lookup"><span data-stu-id="7ba1e-119">Feature Pane</span></span>

<span data-ttu-id="7ba1e-p102">Это первый уровень навигации для большинства заданий, выполняемых в Центре администрирования Exchange. Панель функций состоит из областей функций.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="7ba1e-122">**Получатели**: в этой области отображаются группы и внешние контакты.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-122">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="7ba1e-123">**Разрешения**: здесь вы будете управлять ролями администраторов.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-123">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="7ba1e-124">**Управление соответствием**: здесь вы найдете отчет группы ролей администраторов и отчет по журналу аудита действий администратора.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-124">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="7ba1e-125">**Protection**: в этой области можно управлять политиками защиты от вредоносных программ, политикой фильтрации подключений по умолчанию и DKIM.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-125">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="7ba1e-126">Следует управлять политиками защиты от вредоносных программ и политикой фильтрации подключений по умолчанию в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-126">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="7ba1e-127">Дополнительную информацию можно узнать [в статье Настройка политик защиты от вредоносных программ в EOP](configure-anti-malware-policies.md) и [Настройка ФИЛЬТРАЦИИ подключений в EOP](configure-the-connection-filter-policy.md).</span><span class="sxs-lookup"><span data-stu-id="7ba1e-127">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="7ba1e-128">**Поток обработки почты**: здесь вы будете управлять правилами потока обработки почты (также называемыми правилами транспорта), обслуживаемыми доменами и соединителями, а также с местом, где можно запустить трассировку сообщений.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-128">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="7ba1e-129">**Гибридная**среда: в этой области можно запустить [Мастер гибридной конфигурации](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), а также установить [модуль PowerShell для Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7ba1e-129">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="7ba1e-130">Вкладки</span><span class="sxs-lookup"><span data-stu-id="7ba1e-130">Tabs</span></span>

<span data-ttu-id="7ba1e-131">Вкладки  это второй уровень навигации.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-131">The tabs are your second level of navigation.</span></span> <span data-ttu-id="7ba1e-132">Каждый из компонентов содержит различные вкладки, на каждой из которых будет представлена функция.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-132">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="7ba1e-133">Панель инструментов</span><span class="sxs-lookup"><span data-stu-id="7ba1e-133">Toolbar</span></span>

<span data-ttu-id="7ba1e-p105">При выборе большинства вкладок отображается панель инструментов. Панель инструментов содержит значки, которые выполняют определенное действие. Значки и их действия описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

||||
|---|---|---|
|<span data-ttu-id="7ba1e-137">**Значок**</span><span class="sxs-lookup"><span data-stu-id="7ba1e-137">**Icon**</span></span>|<span data-ttu-id="7ba1e-138">**Имя**</span><span class="sxs-lookup"><span data-stu-id="7ba1e-138">**Name**</span></span>|<span data-ttu-id="7ba1e-139">**Действие**</span><span class="sxs-lookup"><span data-stu-id="7ba1e-139">**Action**</span></span>|
|![Значок добавления](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="7ba1e-141">"Добавить", "Создать"</span><span class="sxs-lookup"><span data-stu-id="7ba1e-141">Add, New</span></span>|<span data-ttu-id="7ba1e-p106">Используйте этот значок для создания нового объекта. Некоторые из этих значков имеют стрелку вниз, щелкнув которую, можно отобразить дополнительные объекты, которые можно создать.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Значок редактирования](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="7ba1e-145">Изменить</span><span class="sxs-lookup"><span data-stu-id="7ba1e-145">Edit</span></span>|<span data-ttu-id="7ba1e-146">Используйте этот значок для редактирования объекта.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-146">Use this icon to edit an object.</span></span>|
|![Значок удаления](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="7ba1e-148">Удаление</span><span class="sxs-lookup"><span data-stu-id="7ba1e-148">Delete</span></span>|<span data-ttu-id="7ba1e-p107">Используйте этот значок для удаления объекта. У некоторых значков удаления есть стрелка вниз, которая позволяет отобразить дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![значок поиска](../../media/ITPro-EAC-.gif)|<span data-ttu-id="7ba1e-152">Поиск</span><span class="sxs-lookup"><span data-stu-id="7ba1e-152">Search</span></span>|<span data-ttu-id="7ba1e-153">Этот значок позволяет открыть поле поиска, в котором можно ввести фразу поиска для объекта, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-153">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Значок обновления](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="7ba1e-155">Обновить</span><span class="sxs-lookup"><span data-stu-id="7ba1e-155">Refresh</span></span>|<span data-ttu-id="7ba1e-156">Используйте этот значок, чтобы обновить представление списка.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-156">Use this icon to refresh the list view.</span></span>|
|![Значок дополнительных параметров](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="7ba1e-158">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="7ba1e-158">More options</span></span>|<span data-ttu-id="7ba1e-p108">Используйте этот значок для просмотра дополнительных действий, которые можно выполнить для объектов этой вкладки. Например, при нажатии этого значка в области **Получатели \> Пользователи** отображается параметр для выполнения **расширенного поиска**.  </span><span class="sxs-lookup"><span data-stu-id="7ba1e-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Значок "Стрелка вверх"](../../media/ITPro-EAC-UpArrowIcon.gif)![Значок "Стрелка вниз"](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="7ba1e-163">Стрелка вверх и стрелка вниз</span><span class="sxs-lookup"><span data-stu-id="7ba1e-163">Up arrow and down arrow</span></span>|<span data-ttu-id="7ba1e-164">Используйте эти значки для изменения приоритета объекта.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-164">Use these icons to move an object's priority up or down.</span></span>|
|![Значок "Удалить"](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="7ba1e-166">Удалить</span><span class="sxs-lookup"><span data-stu-id="7ba1e-166">Remove</span></span>|<span data-ttu-id="7ba1e-167">Используйте этот значок, чтобы удалять объекты из списка.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-167">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="7ba1e-168">Представление списка</span><span class="sxs-lookup"><span data-stu-id="7ba1e-168">List View</span></span>

<span data-ttu-id="7ba1e-p109">При выборе вкладки в большинстве случаев отображается представление списка. Лимит просмотра в Центре администрирования Exchange составляет около 10 000 объектов. Кроме того, включено постраничное разделение, так что вы можете листать страницы результатов.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="7ba1e-172">Область сведений</span><span class="sxs-lookup"><span data-stu-id="7ba1e-172">Details Pane</span></span>

<span data-ttu-id="7ba1e-p110">При выборе объекта в представлении списка информация об этом объекте отображается в области сведений. В некоторых случаях область сведений включает задачи управления.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="7ba1e-175">Иконка "Я" и справка</span><span class="sxs-lookup"><span data-stu-id="7ba1e-175">Me tile and Help</span></span>

<span data-ttu-id="7ba1e-p111">Плитка **Я** позволяет выйти из Центра администрирования Exchange и войти в него как другой пользователь. При помощи раскрывающегося меню справки **Справка**![Значок справки](../../media/ITPro-EAC-HelpIcon.gif) можно выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7ba1e-p111">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

- <span data-ttu-id="7ba1e-178">**Справка**: щелкните ![ значок справки, ](../../media/ITPro-EAC-HelpIcon.gif) чтобы просмотреть содержимое справки в Интернете.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-178">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

- <span data-ttu-id="7ba1e-179">**Обратная связь**: Оставьте отзыв.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-179">**Feedback**: Leave feedback.</span></span>

- <span data-ttu-id="7ba1e-180">**Сообщество**: опубликуйте вопрос для поиска ответов на форумах сообщества.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-180">**Community**: Post a question for find answers in the community forums.</span></span>

- <span data-ttu-id="7ba1e-181">**Отключить всплывающее**окно справки: при создании или редактировании объекта всплывающая справка отображается в контекстной справке для полей.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-181">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="7ba1e-182">Вы можете отключить подменю справки или включить его, если оно отключено.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-182">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

- <span data-ttu-id="7ba1e-183">**Показать ведение журнала команды**: откроется новое окно с эквивалентными командами PowerShell в зависимости от того, что было настроено в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-183">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="7ba1e-184">Поддерживаемые веб-браузеры</span><span class="sxs-lookup"><span data-stu-id="7ba1e-184">Supported Browsers</span></span>

<span data-ttu-id="7ba1e-185">Для оптимальной работы с центром администрирования Exchange рекомендуется всегда использовать новейшие браузеры, клиенты Office и приложения.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-185">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="7ba1e-186">We also recommend that you install software updates when they become available.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-186">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="7ba1e-187">Дополнительные сведения о поддерживаемых браузерах и требованиях к системе для службы приведены в разделе [требования к системе для Office](https://products.office.com/office-system-requirements).</span><span class="sxs-lookup"><span data-stu-id="7ba1e-187">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="7ba1e-188">Поддерживаемые языки</span><span class="sxs-lookup"><span data-stu-id="7ba1e-188">Supported languages</span></span>

<span data-ttu-id="7ba1e-189">Следующие языки поддерживаются и доступны для центра администрирования Exchange в автономной EOP.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-189">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="7ba1e-190">Амхарский</span><span class="sxs-lookup"><span data-stu-id="7ba1e-190">Amharic</span></span>

- <span data-ttu-id="7ba1e-191">Арабский</span><span class="sxs-lookup"><span data-stu-id="7ba1e-191">Arabic</span></span>

- <span data-ttu-id="7ba1e-192">Баскский (Basque)</span><span class="sxs-lookup"><span data-stu-id="7ba1e-192">Basque (Basque)</span></span>

- <span data-ttu-id="7ba1e-193">Бенгальский (Индия)</span><span class="sxs-lookup"><span data-stu-id="7ba1e-193">Bengali (India)</span></span>

- <span data-ttu-id="7ba1e-194">Болгарский</span><span class="sxs-lookup"><span data-stu-id="7ba1e-194">Bulgarian</span></span>

- <span data-ttu-id="7ba1e-195">Каталонский</span><span class="sxs-lookup"><span data-stu-id="7ba1e-195">Catalan</span></span>

- <span data-ttu-id="7ba1e-196">китайский (упрощенное письмо);</span><span class="sxs-lookup"><span data-stu-id="7ba1e-196">Chinese (Simplified)</span></span>

- <span data-ttu-id="7ba1e-197">китайский (традиционный);</span><span class="sxs-lookup"><span data-stu-id="7ba1e-197">Chinese (Traditional)</span></span>

- <span data-ttu-id="7ba1e-198">хорватский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-198">Croatian</span></span>

- <span data-ttu-id="7ba1e-199">чешский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-199">Czech</span></span>

- <span data-ttu-id="7ba1e-200">датский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-200">Danish</span></span>

- <span data-ttu-id="7ba1e-201">голландский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-201">Dutch</span></span>

- <span data-ttu-id="7ba1e-202">голландский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-202">Dutch</span></span>

- <span data-ttu-id="7ba1e-203">английский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-203">English</span></span>

- <span data-ttu-id="7ba1e-204">эстонский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-204">Estonian</span></span>

- <span data-ttu-id="7ba1e-205">Филиппинский (Филиппины)</span><span class="sxs-lookup"><span data-stu-id="7ba1e-205">Filipino (Philippines)</span></span>

- <span data-ttu-id="7ba1e-206">финский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-206">Finnish</span></span>

- <span data-ttu-id="7ba1e-207">французский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-207">French</span></span>

- <span data-ttu-id="7ba1e-208">Галисийский</span><span class="sxs-lookup"><span data-stu-id="7ba1e-208">Galician</span></span>

- <span data-ttu-id="7ba1e-209">немецкий;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-209">German</span></span>

- <span data-ttu-id="7ba1e-210">греческий;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-210">Greek</span></span>

- <span data-ttu-id="7ba1e-211">Гуджарати</span><span class="sxs-lookup"><span data-stu-id="7ba1e-211">Gujarati</span></span>

- <span data-ttu-id="7ba1e-212">иврит;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-212">Hebrew</span></span>

- <span data-ttu-id="7ba1e-213">хинди;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-213">Hindi</span></span>

- <span data-ttu-id="7ba1e-214">венгерский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-214">Hungarian</span></span>

- <span data-ttu-id="7ba1e-215">Исландский</span><span class="sxs-lookup"><span data-stu-id="7ba1e-215">Icelandic</span></span>

- <span data-ttu-id="7ba1e-216">индонезийский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-216">Indonesian</span></span>

- <span data-ttu-id="7ba1e-217">итальянский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-217">Italian</span></span>

- <span data-ttu-id="7ba1e-218">японский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-218">Japanese</span></span>

- <span data-ttu-id="7ba1e-219">Каннада</span><span class="sxs-lookup"><span data-stu-id="7ba1e-219">Kannada</span></span>

- <span data-ttu-id="7ba1e-220">Казахский</span><span class="sxs-lookup"><span data-stu-id="7ba1e-220">Kazakh</span></span>

- <span data-ttu-id="7ba1e-221">Суахили</span><span class="sxs-lookup"><span data-stu-id="7ba1e-221">Kiswahili</span></span>

- <span data-ttu-id="7ba1e-222">корейский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-222">Korean</span></span>

- <span data-ttu-id="7ba1e-223">латышский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-223">Latvian</span></span>

- <span data-ttu-id="7ba1e-224">литовский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-224">Lithuanian</span></span>

- <span data-ttu-id="7ba1e-225">Малайский (Бруней-Даруссалам)</span><span class="sxs-lookup"><span data-stu-id="7ba1e-225">Malay (Brunei Darussalam)</span></span>

- <span data-ttu-id="7ba1e-226">Малайский (Малайзия)</span><span class="sxs-lookup"><span data-stu-id="7ba1e-226">Malay (Malaysia)</span></span>

- <span data-ttu-id="7ba1e-227">Малаялам</span><span class="sxs-lookup"><span data-stu-id="7ba1e-227">Malayalam</span></span>

- <span data-ttu-id="7ba1e-228">Маратхи</span><span class="sxs-lookup"><span data-stu-id="7ba1e-228">Marathi</span></span>

- <span data-ttu-id="7ba1e-229">Норвежский (букмол)</span><span class="sxs-lookup"><span data-stu-id="7ba1e-229">Norwegian (Bokmål)</span></span>

- <span data-ttu-id="7ba1e-230">Норвежский (нюнорск)</span><span class="sxs-lookup"><span data-stu-id="7ba1e-230">Norwegian (Nynorsk)</span></span>

- <span data-ttu-id="7ba1e-231">Ория</span><span class="sxs-lookup"><span data-stu-id="7ba1e-231">Oriya</span></span>

- <span data-ttu-id="7ba1e-232">Персидский</span><span class="sxs-lookup"><span data-stu-id="7ba1e-232">Persian</span></span>

- <span data-ttu-id="7ba1e-233">польский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-233">Polish</span></span>

- <span data-ttu-id="7ba1e-234">португальский (Бразилия);</span><span class="sxs-lookup"><span data-stu-id="7ba1e-234">Portuguese (Brazil)</span></span>

- <span data-ttu-id="7ba1e-235">португальский (Португалия);</span><span class="sxs-lookup"><span data-stu-id="7ba1e-235">Portuguese (Portugal)</span></span>

- <span data-ttu-id="7ba1e-236">румынский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-236">Romanian</span></span>

- <span data-ttu-id="7ba1e-237">русский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-237">Russian</span></span>

- <span data-ttu-id="7ba1e-238">Сербскохорватский (кириллица, Сербия)</span><span class="sxs-lookup"><span data-stu-id="7ba1e-238">Serbian (Cyrillic, Serbia)</span></span>

- <span data-ttu-id="7ba1e-239">сербский (латиница);</span><span class="sxs-lookup"><span data-stu-id="7ba1e-239">Serbian (Latin)</span></span>

- <span data-ttu-id="7ba1e-240">словацкий;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-240">Slovak</span></span>

- <span data-ttu-id="7ba1e-241">словенский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-241">Slovenian</span></span>

- <span data-ttu-id="7ba1e-242">испанский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-242">Spanish</span></span>

- <span data-ttu-id="7ba1e-243">шведский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-243">Swedish</span></span>

- <span data-ttu-id="7ba1e-244">Тамильский</span><span class="sxs-lookup"><span data-stu-id="7ba1e-244">Tamil</span></span>

- <span data-ttu-id="7ba1e-245">Телугу</span><span class="sxs-lookup"><span data-stu-id="7ba1e-245">Telugu</span></span>

- <span data-ttu-id="7ba1e-246">тайский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-246">Thai</span></span>

- <span data-ttu-id="7ba1e-247">турецкий;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-247">Turkish</span></span>

- <span data-ttu-id="7ba1e-248">украинский;</span><span class="sxs-lookup"><span data-stu-id="7ba1e-248">Ukrainian</span></span>

- <span data-ttu-id="7ba1e-249">Урду</span><span class="sxs-lookup"><span data-stu-id="7ba1e-249">Urdu</span></span>

- <span data-ttu-id="7ba1e-250">Вьетнамский</span><span class="sxs-lookup"><span data-stu-id="7ba1e-250">Vietnamese</span></span>

- <span data-ttu-id="7ba1e-251">Валлийский</span><span class="sxs-lookup"><span data-stu-id="7ba1e-251">Welsh</span></span>
