---
title: Взаимодействие с пользователем в среде с поддержкой нескольких регионов
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Сведения о взаимодействии с пользователем SharePoint, OneDrive и Exchange в среде с поддержкой нескольких регионов для Microsoft 365.
ms.openlocfilehash: 4e752581f4ca692f9fecc5019f8e34543ebf7067
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362382"
---
# <a name="user-experience-in-a-multi-geo-environment"></a><span data-ttu-id="a4e52-103">Взаимодействие с пользователем в среде с поддержкой нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="a4e52-103">User experience in a multi-geo environment</span></span>

<span data-ttu-id="a4e52-104">Ниже показано, что увидят пользователи в конфигурации OneDrive с поддержкой нескольких регионов.</span><span class="sxs-lookup"><span data-stu-id="a4e52-104">Here's what your users will see in a OneDrive Multi-Geo configuration:</span></span>

## <a name="exchange-mailbox"></a><span data-ttu-id="a4e52-105">Почтовый ящик Exchange</span><span class="sxs-lookup"><span data-stu-id="a4e52-105">Exchange mailbox</span></span>

<span data-ttu-id="a4e52-106">Почтовый ящик Exchange пользователя подготавливается в его предпочтительном расположении данных (PDL) и автоматически перемещается, если PDL изменяется.</span><span class="sxs-lookup"><span data-stu-id="a4e52-106">A user's Exchange mailbox is provisioned to their preferred data location, and is automatically relocated if their PDL changes.</span></span> <span data-ttu-id="a4e52-107">Обычно пользователи могут использовать Outlook и Outlook в Интернете без изменения пользовательского интерфейса в среде с поддержкой нескольких регионов.</span><span class="sxs-lookup"><span data-stu-id="a4e52-107">Users can use Outlook and Outlook on the web normally with no change in user experience in a multi-geo environment.</span></span>

## <a name="hub-sites"></a><span data-ttu-id="a4e52-108">Центральные сайты</span><span class="sxs-lookup"><span data-stu-id="a4e52-108">Hub sites</span></span>

<span data-ttu-id="a4e52-109">Центральные сайты SharePoint расширяют возможности обнаружения и взаимодействия с контентом для сотрудников, создавая полное и согласованное представление проектов, отделов и регионов.</span><span class="sxs-lookup"><span data-stu-id="a4e52-109">SharePoint Hub sites enhances the discovery and engagement with content for employees, while creating a complete and consistent representation of projects, departments or regions.</span></span> <span data-ttu-id="a4e52-110">В среде с поддержкой нескольких регионов сайты из периферийных расположений можно легко связать с центральным сайтом, независимо от его географического расположения.</span><span class="sxs-lookup"><span data-stu-id="a4e52-110">In a multi-geo environment, sites from satellite locations can easily be associated with a hub site regardless the hub site's geo location.</span></span> <span data-ttu-id="a4e52-111">Пользователи могут искать и получать результаты на центральном сайте с помощью единого интерфейса поиска, независимо от географического расположения сайта.</span><span class="sxs-lookup"><span data-stu-id="a4e52-111">Users can search and get results across the hub through a single search experience, regardless of the geo location of the sites.</span></span>

## <a name="microsoft-365-app-launcher"></a><span data-ttu-id="a4e52-112">Средство запуска приложений Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a4e52-112">Microsoft 365 app launcher</span></span>

<span data-ttu-id="a4e52-113">Средство запуска приложений поддерживает несколько регионов и будет выполнять перенаправление для каждой плитки в соответствующее географическое расположение рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="a4e52-113">The app launcher is multi-geo aware and will direct each tile to the appropriate geo location of the workload.</span></span> <span data-ttu-id="a4e52-114">Плитки SharePoint и OneDrive направляют пользователя в расположение, соответствующее подготовленному географическому расположению пользователя.</span><span class="sxs-lookup"><span data-stu-id="a4e52-114">The SharePoint and OneDrive tiles will point the user to the location corresponding to the user's provisioned geo location.</span></span> <span data-ttu-id="a4e52-115">Это означает, что если у пользователя есть сайт OneDrive в центральном расположении, плитка SharePoint направляет его на домашнюю страницу SharePoint в центральном расположении, но сайт группы будет подготовлен в расположении, соответствующем его PDL.</span><span class="sxs-lookup"><span data-stu-id="a4e52-115">This means that is the user has a OneDrive in the central location, their SharePoint tile will point them to SP Home in the central location but their group site will be provisioned in the location corresponding to their PDL.</span></span> 

## <a name="office-applications"></a><span data-ttu-id="a4e52-116">Приложения Office</span><span class="sxs-lookup"><span data-stu-id="a4e52-116">Office applications</span></span>

<span data-ttu-id="a4e52-117">Office приложения, такие как Word, Excel и PowerPoint, будут автоматически обнаруживать правильные OneDrive геолокации для каждого пользователя при входе в систему.</span><span class="sxs-lookup"><span data-stu-id="a4e52-117">Office applications such as Word, Excel, and PowerPoint will automatically detect the correct OneDrive geo-location for each user when they log in.</span></span> <span data-ttu-id="a4e52-118">Пользователям не нужно вводить специальный URL-адрес для OneDrive с учетом региона.</span><span class="sxs-lookup"><span data-stu-id="a4e52-118">Users do not need to enter the geo-specific URL for their OneDrive or SharePoint sites.</span></span>

## <a name="onedrive-sync-app"></a><span data-ttu-id="a4e52-119">приложение синхронизации OneDrive приложение</span><span class="sxs-lookup"><span data-stu-id="a4e52-119">OneDrive sync app</span></span>

<span data-ttu-id="a4e52-120">Приложение приложение синхронизации OneDrive (версия 17.3.6943.0625 и более поздней версии) автоматически определяет правильное расположение OneDrive гео для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a4e52-120">The OneDrive sync app (version 17.3.6943.0625 and later) will automatically detect the correct OneDrive geo location for the user.</span></span> <span data-ttu-id="a4e52-121">Поддержка приложения sync включает возможность синхронизации сайтов на основе групп независимо от их географического расположения.</span><span class="sxs-lookup"><span data-stu-id="a4e52-121">Sync app support includes the ability to sync groups-based sites regardless of their geo location.</span></span> <span data-ttu-id="a4e52-122">Обратите внимание, что клиент синхронизации Groove не поддерживается для сред с несколькими регионами.</span><span class="sxs-lookup"><span data-stu-id="a4e52-122">Note that the Groove sync client is not supported for multi-geo.</span></span> 

## <a name="onedrive-location"></a><span data-ttu-id="a4e52-123">OneDrive расположение</span><span class="sxs-lookup"><span data-stu-id="a4e52-123">OneDrive location</span></span>

<span data-ttu-id="a4e52-124">Пользователи будут иметь свои OneDrive в предпочтительном расположении данных.</span><span class="sxs-lookup"><span data-stu-id="a4e52-124">Users will have their OneDrive provisioned in their preferred data location.</span></span> <span data-ttu-id="a4e52-125">Если пользователь переходит на URL OneDrive с неправильным геолокационным расположением (например, закладки из предыдущего географического расположения), он автоматически перенаправляется на OneDrive в соответствующем географическом расположении.</span><span class="sxs-lookup"><span data-stu-id="a4e52-125">If a user navigates to a OneDrive URL that contains an incorrect geo location (such as a bookmark from a previous geo location), they are automatically redirected to the OneDrive in the appropriate geo location.</span></span>

## <a name="onedrive-ios-and-android"></a><span data-ttu-id="a4e52-126">OneDrive для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="a4e52-126">OneDrive iOS and Android</span></span> 

<span data-ttu-id="a4e52-p107">Мобильные приложения OneDrive для iOS и Android будут отображать ваши файлы OneDrive и файлы, к которым вам предоставлен доступ, независимо от их географического расположения. Выполнив поиск из мобильных приложений OneDrive, вы увидите релевантные результаты из всех географических расположений. Скачайте последние версии этих приложений.</span><span class="sxs-lookup"><span data-stu-id="a4e52-p107">The OneDrive iOS and Android mobile apps will show you your OneDrive files and files shared with you regardless of their geo location. Search from the OneDrive mobile apps will show relevant results from all geo locations. Please download the latest version of these apps.</span></span>

<span data-ttu-id="a4e52-130">Дополнительные сведения см. в статьях [Работа с OneDrive в iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) и [Использование OneDrive на устройстве с Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36).</span><span class="sxs-lookup"><span data-stu-id="a4e52-130">See Use [OneDrive on iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) and [Use OneDrive for Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) for more information.</span></span>

## <a name="onedrive-mobile-client"></a><span data-ttu-id="a4e52-131">Мобильный клиент OneDrive</span><span class="sxs-lookup"><span data-stu-id="a4e52-131">OneDrive Mobile Client</span></span> 

<span data-ttu-id="a4e52-132">Мобильный клиент OneDrive поддерживает несколько регионов и отображает соответствующие данные и результаты из всех географических расположений.</span><span class="sxs-lookup"><span data-stu-id="a4e52-132">The OneDrive Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="search"></a><span data-ttu-id="a4e52-133">Поиск</span><span class="sxs-lookup"><span data-stu-id="a4e52-133">Search</span></span>

<span data-ttu-id="a4e52-134">Каждое географическое расположение имеет свой индекс поиска и Центр поиска.</span><span class="sxs-lookup"><span data-stu-id="a4e52-134">Each geo location has its own search index and Search Center.</span></span> <span data-ttu-id="a4e52-135">При поиске пользователя запрос отправляется во все географические расположения, а возвращаемые результаты сливаются, а затем ранжются, чтобы пользователь получил унифицированные результаты.</span><span class="sxs-lookup"><span data-stu-id="a4e52-135">When a user searches, the query is sent to all the geo locations, and the returned results are merged and then ranked so the user gets unified results.</span></span> <span data-ttu-id="a4e52-136">Пользователи получают результаты из всех географических расположений независимо от их собственного географического расположения.</span><span class="sxs-lookup"><span data-stu-id="a4e52-136">Users get results from all geo locations regardless of their own geo location.</span></span> <span data-ttu-id="a4e52-137">См. [в рубке Настройка поиска OneDrive с поддержкой нескольких регионов](configure-search-for-multi-geo.md) для определенных особеннок.</span><span class="sxs-lookup"><span data-stu-id="a4e52-137">See [Configure Search for OneDrive Multi-Geo](configure-search-for-multi-geo.md) for specifics.</span></span>

<span data-ttu-id="a4e52-138">Поддерживаемые клиенты поиска:</span><span class="sxs-lookup"><span data-stu-id="a4e52-138">The following search clients are supported:</span></span>

-   <span data-ttu-id="a4e52-139">OneDrive</span><span class="sxs-lookup"><span data-stu-id="a4e52-139">OneDrive</span></span>

-   <span data-ttu-id="a4e52-140">Delve;</span><span class="sxs-lookup"><span data-stu-id="a4e52-140">Delve</span></span>

-   <span data-ttu-id="a4e52-141">домашняя страница SharePoint;</span><span class="sxs-lookup"><span data-stu-id="a4e52-141">SharePoint Home</span></span>

-   <span data-ttu-id="a4e52-142">центр поиска;</span><span class="sxs-lookup"><span data-stu-id="a4e52-142">The Search Center</span></span>

-   <span data-ttu-id="a4e52-143">специальные поисковые приложения, которые используют API поиска SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a4e52-143">Custom search applications that use the SharePoint Search API</span></span>

## <a name="sharepoint-home"></a><span data-ttu-id="a4e52-144">Домашняя страница SharePoint</span><span class="sxs-lookup"><span data-stu-id="a4e52-144">SharePoint Home</span></span> 

<span data-ttu-id="a4e52-145">В SharePoint с поддержкой нескольких регионов ваш SharePoint находится в расположении, где находится пользователь, как определяется его OneDrive расположения.</span><span class="sxs-lookup"><span data-stu-id="a4e52-145">In SharePoint Multi-Geo your SharePoint home is hosted in the location where the user resides as determined by their OneDrive location.</span></span> <span data-ttu-id="a4e52-146">Например: если у пользователя есть сайт OneDrive, размещенный в периферийном европейском расположении, его домашняя страница SharePoint будет отображаться в Европе.</span><span class="sxs-lookup"><span data-stu-id="a4e52-146">For example: if the user has their OneDrive hosted in an European satellite location, their SharePoint Home will be rendered from Europe.</span></span> <span data-ttu-id="a4e52-147">Домашняя страница SharePoint содержит весь контент, относящийся к пользователю, независимо от его географического расположения.</span><span class="sxs-lookup"><span data-stu-id="a4e52-147">SharePoint home includes all content relevant to the user regardless of its geo location.</span></span> 

<span data-ttu-id="a4e52-148">**Отслеживаемые сайты, новости с сайтов, последние сайты, часто посещаемые сайты и рекомендуемые сайты**</span><span class="sxs-lookup"><span data-stu-id="a4e52-148">**Followed Sites, News from Sites, Recent Sites, Frequent Sites, and Suggested sites**</span></span>

<span data-ttu-id="a4e52-149">Все эти компоненты отображаются для пользователей независимо от географического расположения, где размещен контент, если у пользователя есть разрешения для указанного контента.</span><span class="sxs-lookup"><span data-stu-id="a4e52-149">All of these components will show up for the user regardless of the geo location where the content is hosted, so long as the user has permissions to said content.</span></span> 

<span data-ttu-id="a4e52-150">**Важные ссылки**</span><span class="sxs-lookup"><span data-stu-id="a4e52-150">**Features Links**</span></span>

<span data-ttu-id="a4e52-151">Администраторы могут настраивать важные ссылки на домашней странице SharePoint в соответствии с каждым географическим расположением.</span><span class="sxs-lookup"><span data-stu-id="a4e52-151">Admins may configure Featured links in SharePoint home as appropriate to each geo location.</span></span> <span data-ttu-id="a4e52-152">Это позволяет администратору выделять на домашней странице SharePoint для каждого региона ссылки, относящиеся к пользователям в этом регионе.</span><span class="sxs-lookup"><span data-stu-id="a4e52-152">This allows the admin to feature in the SP Home for each region the links that are appropriate for users in the region.</span></span> 

## <a name="sharepoint-mobile-client"></a><span data-ttu-id="a4e52-153">Мобильный клиент SharePoint</span><span class="sxs-lookup"><span data-stu-id="a4e52-153">SharePoint Mobile Client</span></span> 

<span data-ttu-id="a4e52-154">Мобильный клиент SharePoint поддерживает несколько регионов и отображает соответствующие данные и результаты из всех географических расположений.</span><span class="sxs-lookup"><span data-stu-id="a4e52-154">The SharePoint Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="sharing"></a><span data-ttu-id="a4e52-155">Общий доступ</span><span class="sxs-lookup"><span data-stu-id="a4e52-155">Sharing</span></span>

<span data-ttu-id="a4e52-156">Интерфейс выбора людей отображает всех пользователей, независимо от их географического расположения.</span><span class="sxs-lookup"><span data-stu-id="a4e52-156">The People Picker experience shows all users regardless of their geo location.</span></span> <span data-ttu-id="a4e52-157">Это позволяет пользователю предоставлять общий доступ другим пользователям в одном географическом расположении или в любом другом географическом расположении клиента.</span><span class="sxs-lookup"><span data-stu-id="a4e52-157">This allows a user to share with another user in their same geo or in any other of your tenant's geo locations.</span></span> <span data-ttu-id="a4e52-158">Содержимое из разных географических расположений будет показываться в представлении **Общий** со мной в OneDrive пользователя и может быть доступны с помощью единого Sign-On независимо от того, в какой геолокации он расположен.</span><span class="sxs-lookup"><span data-stu-id="a4e52-158">Content from different geo locations will show up in the **Shared with Me** view in the user's OneDrive and can be accessed with Single Sign-On experience regardless of which geo location it is hosted in.</span></span>

## <a name="teams-experience"></a><span data-ttu-id="a4e52-159">Работа в Teams</span><span class="sxs-lookup"><span data-stu-id="a4e52-159">Teams Experience</span></span>

<span data-ttu-id="a4e52-160">Teams — это многосерийная служба.</span><span class="sxs-lookup"><span data-stu-id="a4e52-160">Teams is a multi-geo service.</span></span> <span data-ttu-id="a4e52-161">Файлы OneDrive, а также недавно просмотренные файлы отображаются независимо от географического расположения пользователя.</span><span class="sxs-lookup"><span data-stu-id="a4e52-161">OneDrive files and recently viewed files are shown regardless of the user's geo location.</span></span> <span data-ttu-id="a4e52-162">@упоминания доступны для пользователей из всех географических расположений.</span><span class="sxs-lookup"><span data-stu-id="a4e52-162">@ mentions work with users from all geo-locations.</span></span>

## <a name="user-profiles"></a><span data-ttu-id="a4e52-163">Профили пользователей</span><span class="sxs-lookup"><span data-stu-id="a4e52-163">User profiles</span></span>

<span data-ttu-id="a4e52-p113">Управление данными профиля пользователя выполняется в географическом расположении пользователя. При выборе пользователя вы будете перенаправлены в его соответствующее географическое расположение, где увидите полные сведения профиля.</span><span class="sxs-lookup"><span data-stu-id="a4e52-p113">User profile information is mastered in the user's geo location. When selecting a user, you will be directed to the appropriate geo location for the user, where you will see their full profile details.</span></span>

<span data-ttu-id="a4e52-166">Если служба Delve выключена, отобразится классический интерфейс профиля в SharePoint без поддержки нескольких регионов.</span><span class="sxs-lookup"><span data-stu-id="a4e52-166">If Delve is turned off, you will see the classic profile experience in SharePoint, which is not multi-geo aware.</span></span>


