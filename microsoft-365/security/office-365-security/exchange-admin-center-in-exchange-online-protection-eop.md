---
title: Центр администрирования Exchange в Exchange Online Protection
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
description: "Центр администрирования Exchange \x97 это веб-консоль управления для Microsoft Exchange Online Protection."
ms.openlocfilehash: 3c83e87e6fa88e8fbcc0f16a0043707a9c9ec93a
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441576"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a><span data-ttu-id="3315e-103">Центр администрирования Exchange в Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3315e-103">Exchange admin center in Exchange Online Protection</span></span>

<span data-ttu-id="3315e-104">Центр администрирования Exchange  это веб-консоль управления для Microsoft Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="3315e-104">The Exchange admin center (EAC) is the web-based management console for Microsoft Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="3315e-105">Ищете версию этой статьи в Exchange Server?</span><span class="sxs-lookup"><span data-stu-id="3315e-105">Looking for the Exchange Server version of this topic?</span></span> <span data-ttu-id="3315e-106">Обратитесь к [центру администрирования Exchange в exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx).</span><span class="sxs-lookup"><span data-stu-id="3315e-106">See [Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx).</span></span>

<span data-ttu-id="3315e-107">Ищете версию этой статьи для Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="3315e-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="3315e-108">Обратитесь к [центру администрирования Exchange в Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="3315e-108">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="accessing-the-eac"></a><span data-ttu-id="3315e-109">Вход в Центр администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="3315e-109">Accessing the EAC</span></span>

<span data-ttu-id="3315e-110">В большинстве случаев клиенты EOP будут получать доступ к центру администрирования Exchange через центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3315e-110">In most cases, EOP customers will access the EAC through the Microsoft 365 admin center.</span></span> <span data-ttu-id="3315e-111">Ссылка на Exchange Online Protection расположена в раскрывающемся меню на плитке **Администратор**, находящейся рядом с плиткой **Я**.</span><span class="sxs-lookup"><span data-stu-id="3315e-111">You can find a link to EOP in the drop-down menu in the **Admin** tile, which is next to the **Me** tile.</span></span> <span data-ttu-id="3315e-112">Чтобы перейти в Центр администрирования Exchange, щелкните плитку **Администратор** и в раскрывающемся меню выберите **Exchange Online Protection**.</span><span class="sxs-lookup"><span data-stu-id="3315e-112">Click the **Admin** tile and select **Exchange Online Protection** from the drop down menu to be taken to the EAC.</span></span>

<span data-ttu-id="3315e-p104">Перейти к странице входа в Центр администрирования Exchange можно также непосредственно по URL-адресу: `https://admin.protection.outlook.com/ecp/<companydomain>`. Например, `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`. После того как вы укажете свои учетные данные пользователя, вы перейдете непосредственно в Центр администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="3315e-p104">You can also access the EAC sign in page directly via the following URL: `https://admin.protection.outlook.com/ecp/<companydomain>`. For example, `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`. After specifying your user credentials you will be taken directly into the EAC.</span></span>

## <a name="common-user-interface-elements-in-the-eac"></a><span data-ttu-id="3315e-116">Общие элементы пользовательского интерфейса в Центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="3315e-116">Common user interface elements in the EAC</span></span>

<span data-ttu-id="3315e-117">В этом разделе рассматриваются элементы интерфейса пользователя в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="3315e-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP — Админцентер](../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="3315e-119">Панель "Функции"</span><span class="sxs-lookup"><span data-stu-id="3315e-119">Feature Pane</span></span>

<span data-ttu-id="3315e-p105">Это первый уровень навигации для большинства заданий, выполняемых в Центре администрирования Exchange. Панель функций состоит из областей функций.</span><span class="sxs-lookup"><span data-stu-id="3315e-p105">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

1. <span data-ttu-id="3315e-122">**Получатели**: в этой области отображаются внутренние пользователи и внешние контакты.</span><span class="sxs-lookup"><span data-stu-id="3315e-122">**Recipients**: This is where you'll view internal users and external contacts.</span></span>

2. <span data-ttu-id="3315e-123">**Разрешения**: здесь вы будете управлять ролями администраторов.</span><span class="sxs-lookup"><span data-stu-id="3315e-123">**Permissions**: This where you'll manage administrator roles.</span></span>

3. <span data-ttu-id="3315e-124">**Управление соответствием**: в этой области находятся журналы аудита и отчеты, например отчет о группе ролей администраторов.</span><span class="sxs-lookup"><span data-stu-id="3315e-124">**Compliance Management**: This is where you'll find audit logs and reports, such as the administrator role group report.</span></span>

4. <span data-ttu-id="3315e-125">**Защита**: здесь вы можете управлять защитой от вредоносных программ и нежелательной почты для вашей организации, а также управлять сообщениями в карантине.</span><span class="sxs-lookup"><span data-stu-id="3315e-125">**Protection**: This is where you'll manage anti-malware and anti-spam protection for your organization, as well as manage messages in quarantine.</span></span>

5. <span data-ttu-id="3315e-126">**Поток обработки почты**: в этой области можно управлять правилами, обслуживаемыми доменами и соединителями, а также выполнять трассировку сообщений.</span><span class="sxs-lookup"><span data-stu-id="3315e-126">**Mail Flow**: This is where you'll manage rules, accepted domains, and connectors, as well as where you'll go to perform message trace.</span></span>

### <a name="tabs"></a><span data-ttu-id="3315e-127">Вкладки</span><span class="sxs-lookup"><span data-stu-id="3315e-127">Tabs</span></span>

<span data-ttu-id="3315e-128">Вкладки  это второй уровень навигации.</span><span class="sxs-lookup"><span data-stu-id="3315e-128">The tabs are your second level of navigation.</span></span> <span data-ttu-id="3315e-129">Каждый из компонентов содержит различные вкладки, на каждой из которых будет представлена функция.</span><span class="sxs-lookup"><span data-stu-id="3315e-129">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="3315e-130">Панель инструментов</span><span class="sxs-lookup"><span data-stu-id="3315e-130">Toolbar</span></span>

<span data-ttu-id="3315e-p107">При выборе большинства вкладок отображается панель инструментов. Панель инструментов содержит значки, которые выполняют определенное действие. Значки и их действия описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="3315e-p107">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

|<span data-ttu-id="3315e-134">**Значок**</span><span class="sxs-lookup"><span data-stu-id="3315e-134">**Icon**</span></span>|<span data-ttu-id="3315e-135">**Имя**</span><span class="sxs-lookup"><span data-stu-id="3315e-135">**Name**</span></span>|<span data-ttu-id="3315e-136">**Действие**</span><span class="sxs-lookup"><span data-stu-id="3315e-136">**Action**</span></span>|
|:-----|:-----|:-----|
|![Значок добавления](../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="3315e-138">"Добавить", "Создать"</span><span class="sxs-lookup"><span data-stu-id="3315e-138">Add, New</span></span>|<span data-ttu-id="3315e-p108">Используйте этот значок для создания нового объекта. Некоторые из этих значков имеют стрелку вниз, щелкнув которую, можно отобразить дополнительные объекты, которые можно создать.</span><span class="sxs-lookup"><span data-stu-id="3315e-p108">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Значок редактирования](../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="3315e-142">Изменить</span><span class="sxs-lookup"><span data-stu-id="3315e-142">Edit</span></span>|<span data-ttu-id="3315e-143">Используйте этот значок для редактирования объекта.</span><span class="sxs-lookup"><span data-stu-id="3315e-143">Use this icon to edit an object.</span></span>|
|![Значок удаления](../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="3315e-145">Удаление</span><span class="sxs-lookup"><span data-stu-id="3315e-145">Delete</span></span>|<span data-ttu-id="3315e-p109">Используйте этот значок для удаления объекта. У некоторых значков удаления есть стрелка вниз, которая позволяет отобразить дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="3315e-p109">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![значок поиска](../media/ITPro-EAC-.gif)|<span data-ttu-id="3315e-149">Поиск</span><span class="sxs-lookup"><span data-stu-id="3315e-149">Search</span></span>|<span data-ttu-id="3315e-150">Этот значок позволяет открыть поле поиска, в котором можно ввести фразу поиска для объекта, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="3315e-150">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Значок обновления](../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="3315e-152">Обновить</span><span class="sxs-lookup"><span data-stu-id="3315e-152">Refresh</span></span>|<span data-ttu-id="3315e-153">Используйте этот значок, чтобы обновить представление списка.</span><span class="sxs-lookup"><span data-stu-id="3315e-153">Use this icon to refresh the list view.</span></span>|
|![Значок дополнительных параметров](../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="3315e-155">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="3315e-155">More options</span></span>|<span data-ttu-id="3315e-p110">Используйте этот значок для просмотра дополнительных действий, которые можно выполнить для объектов этой вкладки. Например, при нажатии этого значка в области **Получатели \> Пользователи** отображается параметр для выполнения **расширенного поиска**.  </span><span class="sxs-lookup"><span data-stu-id="3315e-p110">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Значок "Стрелка вверх"](../media/ITPro-EAC-UpArrowIcon.gif)![Значок "Стрелка вниз"](../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="3315e-160">Стрелка вверх и стрелка вниз</span><span class="sxs-lookup"><span data-stu-id="3315e-160">Up arrow and down arrow</span></span>|<span data-ttu-id="3315e-161">Используйте эти значки для изменения приоритета объекта.</span><span class="sxs-lookup"><span data-stu-id="3315e-161">Use these icons to move an object's priority up or down.</span></span>|
|![Значок "Удалить"](../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="3315e-163">Удалить</span><span class="sxs-lookup"><span data-stu-id="3315e-163">Remove</span></span>|<span data-ttu-id="3315e-164">Используйте этот значок, чтобы удалять объекты из списка.</span><span class="sxs-lookup"><span data-stu-id="3315e-164">Use this icon to remove objects from a list.</span></span>|

### <a name="list-view"></a><span data-ttu-id="3315e-165">Представление списка</span><span class="sxs-lookup"><span data-stu-id="3315e-165">List View</span></span>

<span data-ttu-id="3315e-p111">При выборе вкладки в большинстве случаев отображается представление списка. Лимит просмотра в Центре администрирования Exchange составляет около 10 000 объектов. Кроме того, включено постраничное разделение, так что вы можете листать страницы результатов.</span><span class="sxs-lookup"><span data-stu-id="3315e-p111">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="3315e-169">Область сведений</span><span class="sxs-lookup"><span data-stu-id="3315e-169">Details Pane</span></span>

<span data-ttu-id="3315e-p112">При выборе объекта в представлении списка информация об этом объекте отображается в области сведений. В некоторых случаях область сведений включает задачи управления.</span><span class="sxs-lookup"><span data-stu-id="3315e-p112">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="3315e-172">Иконка "Я" и справка</span><span class="sxs-lookup"><span data-stu-id="3315e-172">Me tile and Help</span></span>

<span data-ttu-id="3315e-p113">Плитка **Я** позволяет выйти из Центра администрирования Exchange и войти в него как другой пользователь. При помощи раскрывающегося меню справки **Справка**![Значок справки](../media/ITPro-EAC-HelpIcon.gif) можно выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3315e-p113">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

1. <span data-ttu-id="3315e-175">**Справка**: щелкните ![значок](../media/ITPro-EAC-HelpIcon.gif) справки, чтобы просмотреть содержимое справки в Интернете.</span><span class="sxs-lookup"><span data-stu-id="3315e-175">**Help**: Click ![Help Icon](../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

2. <span data-ttu-id="3315e-176">**Отключить всплывающее**окно справки: при создании или редактировании объекта всплывающая справка отображается в контекстной справке для полей.</span><span class="sxs-lookup"><span data-stu-id="3315e-176">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="3315e-177">Вы можете отключить подменю справки или включить его, если оно отключено.</span><span class="sxs-lookup"><span data-stu-id="3315e-177">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

3. <span data-ttu-id="3315e-178">**Авторские права**: щелкните эту ссылку, чтобы прочитать уведомление об авторских правах для Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="3315e-178">**Copyright**: Click this link to read the copyright notice for Exchange Online Protection.</span></span>

4. <span data-ttu-id="3315e-179">**Конфиденциальность**: щелкните, чтобы прочитать политику конфиденциальности для Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="3315e-179">**Privacy**: Click to read the privacy policy for Exchange Online Protection.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="3315e-180">Поддерживаемые веб-браузеры</span><span class="sxs-lookup"><span data-stu-id="3315e-180">Supported Browsers</span></span>

<span data-ttu-id="3315e-p115">Чтобы работа с Центром администрирования Exchange (EAC) была максимально продуктивной, рекомендуется всегда использовать только последние версии браузеров, клиентов Office и приложений. Мы также рекомендуем устанавливать обновления по мере их доступности. Для получения дополнительных сведений о поддерживаемых браузерах и системных требованиях для службы см. раздел [Требования к системе для Office 365](https://go.microsoft.com/fwlink/p/?LinkID=402699).</span><span class="sxs-lookup"><span data-stu-id="3315e-p115">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps. We also recommend that you install software updates when they become available. For more information about the supported browsers and system requirements for the service, see [Office 365 System Requirements](https://go.microsoft.com/fwlink/p/?LinkID=402699).</span></span>

## <a name="supported-languages-in-eop"></a><span data-ttu-id="3315e-184">Поддерживаемые в EOP языки</span><span class="sxs-lookup"><span data-stu-id="3315e-184">Supported languages in EOP</span></span>

<span data-ttu-id="3315e-185">Для Exchange Online Protection доступны и поддерживаются следующие языки.</span><span class="sxs-lookup"><span data-stu-id="3315e-185">The following languages are supported and available for Exchange Online Protection.</span></span>

- <span data-ttu-id="3315e-186">Амхарский</span><span class="sxs-lookup"><span data-stu-id="3315e-186">Amharic</span></span>

- <span data-ttu-id="3315e-187">Арабский</span><span class="sxs-lookup"><span data-stu-id="3315e-187">Arabic</span></span>

- <span data-ttu-id="3315e-188">Баскский (Basque)</span><span class="sxs-lookup"><span data-stu-id="3315e-188">Basque (Basque)</span></span>

- <span data-ttu-id="3315e-189">Бенгальский (Индия)</span><span class="sxs-lookup"><span data-stu-id="3315e-189">Bengali (India)</span></span>

- <span data-ttu-id="3315e-190">Болгарский</span><span class="sxs-lookup"><span data-stu-id="3315e-190">Bulgarian</span></span>

- <span data-ttu-id="3315e-191">Каталонский</span><span class="sxs-lookup"><span data-stu-id="3315e-191">Catalan</span></span>

- <span data-ttu-id="3315e-192">китайский (упрощенное письмо);</span><span class="sxs-lookup"><span data-stu-id="3315e-192">Chinese (Simplified)</span></span>

- <span data-ttu-id="3315e-193">китайский (традиционный);</span><span class="sxs-lookup"><span data-stu-id="3315e-193">Chinese (Traditional)</span></span>

- <span data-ttu-id="3315e-194">хорватский;</span><span class="sxs-lookup"><span data-stu-id="3315e-194">Croatian</span></span>

- <span data-ttu-id="3315e-195">чешский;</span><span class="sxs-lookup"><span data-stu-id="3315e-195">Czech</span></span>

- <span data-ttu-id="3315e-196">датский;</span><span class="sxs-lookup"><span data-stu-id="3315e-196">Danish</span></span>

- <span data-ttu-id="3315e-197">голландский;</span><span class="sxs-lookup"><span data-stu-id="3315e-197">Dutch</span></span>

- <span data-ttu-id="3315e-198">голландский;</span><span class="sxs-lookup"><span data-stu-id="3315e-198">Dutch</span></span>

- <span data-ttu-id="3315e-199">английский;</span><span class="sxs-lookup"><span data-stu-id="3315e-199">English</span></span>

- <span data-ttu-id="3315e-200">эстонский;</span><span class="sxs-lookup"><span data-stu-id="3315e-200">Estonian</span></span>

- <span data-ttu-id="3315e-201">Филиппинский (Филиппины)</span><span class="sxs-lookup"><span data-stu-id="3315e-201">Filipino (Philippines)</span></span>

- <span data-ttu-id="3315e-202">финский;</span><span class="sxs-lookup"><span data-stu-id="3315e-202">Finnish</span></span>

- <span data-ttu-id="3315e-203">французский;</span><span class="sxs-lookup"><span data-stu-id="3315e-203">French</span></span>

- <span data-ttu-id="3315e-204">Галисийский</span><span class="sxs-lookup"><span data-stu-id="3315e-204">Galician</span></span>

- <span data-ttu-id="3315e-205">немецкий;</span><span class="sxs-lookup"><span data-stu-id="3315e-205">German</span></span>

- <span data-ttu-id="3315e-206">греческий;</span><span class="sxs-lookup"><span data-stu-id="3315e-206">Greek</span></span>

- <span data-ttu-id="3315e-207">Гуджарати</span><span class="sxs-lookup"><span data-stu-id="3315e-207">Gujarati</span></span>

- <span data-ttu-id="3315e-208">иврит;</span><span class="sxs-lookup"><span data-stu-id="3315e-208">Hebrew</span></span>

- <span data-ttu-id="3315e-209">хинди;</span><span class="sxs-lookup"><span data-stu-id="3315e-209">Hindi</span></span>

- <span data-ttu-id="3315e-210">венгерский;</span><span class="sxs-lookup"><span data-stu-id="3315e-210">Hungarian</span></span>

- <span data-ttu-id="3315e-211">Исландский</span><span class="sxs-lookup"><span data-stu-id="3315e-211">Icelandic</span></span>

- <span data-ttu-id="3315e-212">индонезийский;</span><span class="sxs-lookup"><span data-stu-id="3315e-212">Indonesian</span></span>

- <span data-ttu-id="3315e-213">итальянский;</span><span class="sxs-lookup"><span data-stu-id="3315e-213">Italian</span></span>

- <span data-ttu-id="3315e-214">японский;</span><span class="sxs-lookup"><span data-stu-id="3315e-214">Japanese</span></span>

- <span data-ttu-id="3315e-215">Каннада</span><span class="sxs-lookup"><span data-stu-id="3315e-215">Kannada</span></span>

- <span data-ttu-id="3315e-216">Казахский</span><span class="sxs-lookup"><span data-stu-id="3315e-216">Kazakh</span></span>

- <span data-ttu-id="3315e-217">Суахили</span><span class="sxs-lookup"><span data-stu-id="3315e-217">Kiswahili</span></span>

- <span data-ttu-id="3315e-218">корейский;</span><span class="sxs-lookup"><span data-stu-id="3315e-218">Korean</span></span>

- <span data-ttu-id="3315e-219">латышский;</span><span class="sxs-lookup"><span data-stu-id="3315e-219">Latvian</span></span>

- <span data-ttu-id="3315e-220">литовский;</span><span class="sxs-lookup"><span data-stu-id="3315e-220">Lithuanian</span></span>

- <span data-ttu-id="3315e-221">Малайский (Бруней-Даруссалам)</span><span class="sxs-lookup"><span data-stu-id="3315e-221">Malay (Brunei Darussalam)</span></span>

- <span data-ttu-id="3315e-222">Малайский (Малайзия)</span><span class="sxs-lookup"><span data-stu-id="3315e-222">Malay (Malaysia)</span></span>

- <span data-ttu-id="3315e-223">Малаялам</span><span class="sxs-lookup"><span data-stu-id="3315e-223">Malayalam</span></span>

- <span data-ttu-id="3315e-224">Маратхи</span><span class="sxs-lookup"><span data-stu-id="3315e-224">Marathi</span></span>

- <span data-ttu-id="3315e-225">Норвежский (букмол)</span><span class="sxs-lookup"><span data-stu-id="3315e-225">Norwegian (Bokmål)</span></span>

- <span data-ttu-id="3315e-226">Норвежский (нюнорск)</span><span class="sxs-lookup"><span data-stu-id="3315e-226">Norwegian (Nynorsk)</span></span>

- <span data-ttu-id="3315e-227">Ория</span><span class="sxs-lookup"><span data-stu-id="3315e-227">Oriya</span></span>

- <span data-ttu-id="3315e-228">Персидский</span><span class="sxs-lookup"><span data-stu-id="3315e-228">Persian</span></span>

- <span data-ttu-id="3315e-229">польский;</span><span class="sxs-lookup"><span data-stu-id="3315e-229">Polish</span></span>

- <span data-ttu-id="3315e-230">португальский (Бразилия);</span><span class="sxs-lookup"><span data-stu-id="3315e-230">Portuguese (Brazil)</span></span>

- <span data-ttu-id="3315e-231">португальский (Португалия);</span><span class="sxs-lookup"><span data-stu-id="3315e-231">Portuguese (Portugal)</span></span>

- <span data-ttu-id="3315e-232">румынский;</span><span class="sxs-lookup"><span data-stu-id="3315e-232">Romanian</span></span>

- <span data-ttu-id="3315e-233">русский;</span><span class="sxs-lookup"><span data-stu-id="3315e-233">Russian</span></span>

- <span data-ttu-id="3315e-234">Сербскохорватский (кириллица, Сербия)</span><span class="sxs-lookup"><span data-stu-id="3315e-234">Serbian (Cyrillic, Serbia)</span></span>

- <span data-ttu-id="3315e-235">сербский (латиница);</span><span class="sxs-lookup"><span data-stu-id="3315e-235">Serbian (Latin)</span></span>

- <span data-ttu-id="3315e-236">словацкий;</span><span class="sxs-lookup"><span data-stu-id="3315e-236">Slovak</span></span>

- <span data-ttu-id="3315e-237">словенский;</span><span class="sxs-lookup"><span data-stu-id="3315e-237">Slovenian</span></span>

- <span data-ttu-id="3315e-238">испанский;</span><span class="sxs-lookup"><span data-stu-id="3315e-238">Spanish</span></span>

- <span data-ttu-id="3315e-239">шведский;</span><span class="sxs-lookup"><span data-stu-id="3315e-239">Swedish</span></span>

- <span data-ttu-id="3315e-240">Тамильский</span><span class="sxs-lookup"><span data-stu-id="3315e-240">Tamil</span></span>

- <span data-ttu-id="3315e-241">Телугу</span><span class="sxs-lookup"><span data-stu-id="3315e-241">Telugu</span></span>

- <span data-ttu-id="3315e-242">тайский;</span><span class="sxs-lookup"><span data-stu-id="3315e-242">Thai</span></span>

- <span data-ttu-id="3315e-243">турецкий;</span><span class="sxs-lookup"><span data-stu-id="3315e-243">Turkish</span></span>

- <span data-ttu-id="3315e-244">украинский;</span><span class="sxs-lookup"><span data-stu-id="3315e-244">Ukrainian</span></span>

- <span data-ttu-id="3315e-245">Урду</span><span class="sxs-lookup"><span data-stu-id="3315e-245">Urdu</span></span>

- <span data-ttu-id="3315e-246">Вьетнамский</span><span class="sxs-lookup"><span data-stu-id="3315e-246">Vietnamese</span></span>

- <span data-ttu-id="3315e-247">Валлийский</span><span class="sxs-lookup"><span data-stu-id="3315e-247">Welsh</span></span>


