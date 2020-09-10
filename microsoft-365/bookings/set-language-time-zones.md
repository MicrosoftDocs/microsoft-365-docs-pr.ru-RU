---
title: Настройка языка и часовых поясов в Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 94af3e22-aca6-4e91-8b91-1cd5a02a9ea8
description: Измените параметры языка и часового пояса в книгах Майкрософт. Если резервирования создаются в неправильное время, могут быть настроены резервирования для неправильного часового пояса.
ms.openlocfilehash: 07e5dde2a896610ee079063943aff24ec69ba721
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "47420017"
---
# <a name="set-language-and-time-zones-in-microsoft-bookings"></a><span data-ttu-id="69dcc-104">Настройка языка и часовых поясов в Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="69dcc-104">Set language and time zones in Microsoft Bookings</span></span>

<span data-ttu-id="69dcc-105">Если вы используете резервирование Microsoft и создание резервирований выполняется в неправильное время, может потребоваться изменить параметры часового пояса.</span><span class="sxs-lookup"><span data-stu-id="69dcc-105">If you are using Microsoft Bookings and bookings are created at the wrong time, then your time zone settings might need to be changed.</span></span> <span data-ttu-id="69dcc-106">Аналогично, если некоторые резервирования относятся к неправильному языку, может потребоваться изменить языковые параметры.</span><span class="sxs-lookup"><span data-stu-id="69dcc-106">Likewise, if some bookings are in the wrong language, you might need to change your language settings.</span></span>

<span data-ttu-id="69dcc-107">Существует два отдельных параметра языка и часового пояса для резервирований.</span><span class="sxs-lookup"><span data-stu-id="69dcc-107">There are two separate language and time zone settings for Bookings.</span></span> <span data-ttu-id="69dcc-108">Первый параметр определяет язык и часовой пояс календаря резервирования и задается с помощью Outlook в Интернете для личного календаря пользователя, вошедшего в систему.</span><span class="sxs-lookup"><span data-stu-id="69dcc-108">The first setting controls the language and time zone of the booking calendar and is set using the Outlook on the web settings for the personal calendar of the logged-in user.</span></span> <span data-ttu-id="69dcc-109">Второй параметр влияет на страницу самообслуживания резервирования, используемую клиентами, и задается с помощью страницы "региональные параметры", которая управляет языком и часовым поясами только для этой страницы.</span><span class="sxs-lookup"><span data-stu-id="69dcc-109">The second setting affects the self-service booking page that your customers use and is set using a "regional settings" page that controls language and time zone only for that page.</span></span>

> [!NOTE]
> <span data-ttu-id="69dcc-110">Для клиентов, у которых есть подписки Microsoft 365 бизнес Standard, Microsoft 365 a3 или Microsoft 365 A5, резервирование включается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="69dcc-110">Bookings is turned on by default for customers who have the Microsoft 365 Business Standard, Microsoft 365 A3, or Microsoft 365 A5 subscriptions.</span></span> <span data-ttu-id="69dcc-111">Кроме того, они доступны пользователям Office 365 корпоративный E3 и Office 365 корпоративный, но по умолчанию она отключена.</span><span class="sxs-lookup"><span data-stu-id="69dcc-111">Bookings is also available to customers who have Office 365 Enterprise E3 and Office 365 Enterprise E5, but it is turned off by default.</span></span> <span data-ttu-id="69dcc-112">Чтобы приступить к работе, ознакомьтесь [со статьей получение доступа к книгам Майкрософт](get-access.md).</span><span class="sxs-lookup"><span data-stu-id="69dcc-112">To get started, see [Get access to Microsoft Bookings](get-access.md).</span></span> <span data-ttu-id="69dcc-113">Чтобы включить или отключить резервирование, ознакомьтесь со статьей [Включение или отключение учета для Организации](turn-bookings-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="69dcc-113">To turn Bookings on or off, see [Turn Bookings on or off for your organization](turn-bookings-on-or-off.md).</span></span>

## <a name="setting-language-and-time-zone-for-a-booking-calendar"></a><span data-ttu-id="69dcc-114">Настройка языка и часового пояса для календаря резервирования</span><span class="sxs-lookup"><span data-stu-id="69dcc-114">Setting language and time zone for a booking calendar</span></span>

<span data-ttu-id="69dcc-115">В календаре резервирования используются параметры языка и часового пояса пользователя, вошедшего в систему.</span><span class="sxs-lookup"><span data-stu-id="69dcc-115">The booking calendar uses the logged-in user’s language and time zone settings.</span></span> <span data-ttu-id="69dcc-116">Например, если в часовом поясе вошедшего пользователя задано стандартное восточное время (EST), календарь резервирования будет показывать время начала и окончания текущей встречи в средстве EST.</span><span class="sxs-lookup"><span data-stu-id="69dcc-116">For example, If the logged-in user’s time zone is set to Eastern Standard Time (EST), then the booking calendar will show existing appointment start and end times in EST.</span></span> <span data-ttu-id="69dcc-117">Этот часовой пояс был изначально установлен при создании веб-учетных записей пользователей Microsoft 365 и Outlook.</span><span class="sxs-lookup"><span data-stu-id="69dcc-117">This time zone was originally set when the user’s Microsoft 365 and Outlook on the web accounts were created.</span></span>

<span data-ttu-id="69dcc-118">Чтобы задать язык и часовой пояс для календаря резервирования, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="69dcc-118">To set the language and time zone for the booking calendar:</span></span>

1. <span data-ttu-id="69dcc-119">Войдите в Microsoft 365 и выберите плитку Outlook на целевой странице (как показано на снимке экрана ниже) или в средстве запуска приложений Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="69dcc-119">Log into Microsoft 365 and select the Outlook tile on the landing page (as shown in the screenshot below) or in the Microsoft 365 App Launcher.</span></span>

   ![Изображение плитки Outlook на целевой странице Microsoft 365](../media/bookings-outlook-tile.png)

1. <span data-ttu-id="69dcc-121">После открытия Outlook нажмите **значок шестеренки** в верхнем правом углу экрана, чтобы открыть личные параметры и параметры учетной записи, а затем выполните поиск по запросу "часовой пояс" в поле поиска на панели **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="69dcc-121">After Outlook opens, select the **gear icon** in the upper, right-hand corner of the screen to open your personal and account settings, then search for “time zone” in the **Settings** panel search box.</span></span> <span data-ttu-id="69dcc-122">В области параметров вы увидите текущие значения языка и часового пояса для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="69dcc-122">The panel will update to show your current personal language and time zone settings for this account.</span></span> <span data-ttu-id="69dcc-123">Как было отмечено ранее, эти значения используются также в календаре резервирования.</span><span class="sxs-lookup"><span data-stu-id="69dcc-123">As noted above, this setting also controls the language and time zone of the booking calendar.</span></span>

1. <span data-ttu-id="69dcc-124">Измените язык или часовой пояс, щелкнув стрелку раскрывающегося списка в поле **язык или текущий часовой пояс** и выбрав нужный параметр.</span><span class="sxs-lookup"><span data-stu-id="69dcc-124">Change the language or time zone by selecting the drop-down arrow in the **Language or Current time zone** box and choosing the desired setting.</span></span>

1. <span data-ttu-id="69dcc-125">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69dcc-125">Click **Save**.</span></span> <span data-ttu-id="69dcc-126">Панель параметров закрывается, Outlook на веб-сайте перезапускается, и применяются новые параметры языка и часового пояса.</span><span class="sxs-lookup"><span data-stu-id="69dcc-126">The Settings panel closes, Outlook on the web restarts, and the new language and time zone settings are applied.</span></span>

## <a name="setting-the-language-and-time-zone-for-the-booking-page"></a><span data-ttu-id="69dcc-127">Настройка языка и часового пояса для страницы резервирования</span><span class="sxs-lookup"><span data-stu-id="69dcc-127">Setting the language and time zone for the booking page</span></span>

1. <span data-ttu-id="69dcc-128">В Microsoft 365 выберите средство запуска приложений, а затем выберите пункт **резервирования**.</span><span class="sxs-lookup"><span data-stu-id="69dcc-128">In Microsoft 365, select the app launcher, and then select **Bookings**.</span></span>

1. <span data-ttu-id="69dcc-129">В области навигации выберите пункт **резервирование страницы** и выберите пункт **изменить параметры языка и часового пояса**.</span><span class="sxs-lookup"><span data-stu-id="69dcc-129">In the navigation pane, select **Booking page** and select **Change language and time zone settings**.</span></span>

   ![Снимок экрана: изменение ссылки на параметры языка и часового пояса](../media/bookings-region-language-timezone-settings.png)

1. <span data-ttu-id="69dcc-131">Выберите язык и текущий часовой пояс и нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="69dcc-131">Select your language and current time zone and choose OK.</span></span>

   ![Снимок экрана: параметры языка и часового пояса](../media/bookings-region-timezone-settings.png)
