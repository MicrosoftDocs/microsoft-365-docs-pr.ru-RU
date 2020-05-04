---
title: Отображение и скрытие новых функций с помощью управления новыми возможностями
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
description: 'Определите, какие компоненты и сведения о содержимом: будут отображаться или скрыты от конечных пользователей в разделе "новые возможности управления Office для настольных приложений Office".'
ms.openlocfilehash: 7399da493f8e6878a92dc13d92482d7ddece0ba3
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011703"
---
# <a name="show-or-hide-new-features-using-whats-new-management"></a><span data-ttu-id="99dc8-103">Отображение и скрытие новых функций с помощью управления новыми возможностями</span><span class="sxs-lookup"><span data-stu-id="99dc8-103">Show or hide new features using What's New Management</span></span>

<span data-ttu-id="99dc8-104">Управление новыми возможностями Office для Win 32 позволяет Организации решать, какие функции будут отображаться у конечных пользователей в классическом приложении Office или скрыты от них.</span><span class="sxs-lookup"><span data-stu-id="99dc8-104">Office What's New Management for Win 32 allows your organization to decide which features are shown to or hidden from end users in the Office desktop app.</span></span> <span data-ttu-id="99dc8-105">Каждый выпуск Office включает в себя новые и улучшенные функции, а предварительный просмотр контента позволяет просматривать новые материалы для каждой версии и канала, а также включать или отключать отображение нового контента для каждого компонента конечным пользователям.</span><span class="sxs-lookup"><span data-stu-id="99dc8-105">Each release of Office includes new and improved features, and the content preview allows you to view new content for each release version and channel, and choose whether to hide or show What's new content for each feature to end users.</span></span> 

<span data-ttu-id="99dc8-106">В разделе новые возможности настольных приложений Office выделяется проверенный список новых функций, выпускаемых для этого приложения, с кратким описанием и часто изображением или видеороликом, созданным командой, которые помогают клиентам узнать, как использовать эту функцию.</span><span class="sxs-lookup"><span data-stu-id="99dc8-106">The What's new content in the Office desktop apps highlights a curated list of new features being released for that application, with a short description, and often a picture or a video created by the team releasing the feature to help customers learn how to use the feature.</span></span> 

<span data-ttu-id="99dc8-107">Управление новыми возможности Office доступно в центре администрирования Microsoft 365 и через [службу настройки клиентов](https://config.office.com).</span><span class="sxs-lookup"><span data-stu-id="99dc8-107">Office What's New management is available in the Microsoft 365 admin center and through the [Client Configuration Service](https://config.office.com).</span></span>

> [!NOTE]
> <span data-ttu-id="99dc8-108">Роли администратора глобального администратора и приложения Office управляют новым содержимым, которое пользователи видят в своих приложениях Office.</span><span class="sxs-lookup"><span data-stu-id="99dc8-108">Global admin and Office Apps admin roles manage the What's new content that users see in their Office apps.</span></span>

##  <a name="show-or-hide-new-features"></a><span data-ttu-id="99dc8-109">Отображение и скрытие новых компонентов</span><span class="sxs-lookup"><span data-stu-id="99dc8-109">Show or hide new features</span></span> 

<span data-ttu-id="99dc8-110">Администраторы могут предварительно просмотреть содержимое канала "что нового" и управлять его выпуском с помощью Office "новые возможности управления".</span><span class="sxs-lookup"><span data-stu-id="99dc8-110">Admins can preview the What's new content for a channel, and manage the release of the content using Office What's New Management.</span></span>

1. <span data-ttu-id="99dc8-111">В центре администрирования Microsoft 365 в разделе **Параметры**выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="99dc8-111">In the Microsoft 365 admin center, under **Settings**, choose **Settings**.</span></span>

2. <span data-ttu-id="99dc8-112">На вкладке **службы** выберите пункт **управление новыми действиями в Office**.</span><span class="sxs-lookup"><span data-stu-id="99dc8-112">On the **Services** tab, choose **Office What's New Management**.</span></span>

3. <span data-ttu-id="99dc8-113">Выберите один или несколько компонентов для просмотра имени компонента, краткого описания, приложения и версии выпуска для каждой функции в раскрывающейся панели.</span><span class="sxs-lookup"><span data-stu-id="99dc8-113">Select one or more features to view the feature name, a short description, the application, and the release version for each feature on the flyout panel.</span></span>

4. <span data-ttu-id="99dc8-114">Выберите **Скрыть от пользователей** или **Показать для пользователей**.</span><span class="sxs-lookup"><span data-stu-id="99dc8-114">Choose **Hide from users** or **Show to users**.</span></span>  

    <span data-ttu-id="99dc8-115">Состояние, **отображаемое по умолчанию** , указывает, что по умолчанию сведения о компонентах отображаются по умолчанию до тех пор, пока администратор не настроит состояние компонента как **скрытое** или **Отображаемое**.</span><span class="sxs-lookup"><span data-stu-id="99dc8-115">The status **Shown by default** indicates feature information is shown by default to users until the admin sets the status for a feature to **Hidden** or **Shown**.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="99dc8-116">Если функция доступна в нескольких приложениях Office, то при установке скрытого объявления функции скрываются во всех приложениях Office.</span><span class="sxs-lookup"><span data-stu-id="99dc8-116">If a feature is available in multiple Office apps, setting the feature to hidden hides the feature announcement in all of the Office apps.</span></span>

<span data-ttu-id="99dc8-117">Новые возможности отображаются в Office новые возможности управления на основе этого расписания:</span><span class="sxs-lookup"><span data-stu-id="99dc8-117">New features appear in Office What's New Management based on this schedule:</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="99dc8-118">**Канал**</span><span class="sxs-lookup"><span data-stu-id="99dc8-118">**Channel**</span></span> <br/> |<span data-ttu-id="99dc8-119">**В окне "предварительный просмотр управления"**</span><span class="sxs-lookup"><span data-stu-id="99dc8-119">**In management preview**</span></span> <br/> |<span data-ttu-id="99dc8-120">**Выполнение действий**</span><span class="sxs-lookup"><span data-stu-id="99dc8-120">**Take action**</span></span> <br/> |
|<span data-ttu-id="99dc8-121">**Monthly**</span><span class="sxs-lookup"><span data-stu-id="99dc8-121">**Monthly**</span></span> <br/> |<span data-ttu-id="99dc8-122">15 месяца</span><span class="sxs-lookup"><span data-stu-id="99dc8-122">15th of the month</span></span>  <br/> |<span data-ttu-id="99dc8-123">1-3 недель до ежемесячного выпуска</span><span class="sxs-lookup"><span data-stu-id="99dc8-123">1 - 3 weeks before the monthly release</span></span> <br/> |
|<span data-ttu-id="99dc8-124">**Половина года (Целевая)**</span><span class="sxs-lookup"><span data-stu-id="99dc8-124">**Semi-annual (Targeted)**</span></span> <br/> |<span data-ttu-id="99dc8-125">1 сентября и 1 марта</span><span class="sxs-lookup"><span data-stu-id="99dc8-125">Sept 1 and March 1</span></span> <br/> | <span data-ttu-id="99dc8-126">2 недели перед основным выпуском, в котором переносятся новые функции</span><span class="sxs-lookup"><span data-stu-id="99dc8-126">2 weeks before the major release that brings new features</span></span>
|<span data-ttu-id="99dc8-127">**Половина года**</span><span class="sxs-lookup"><span data-stu-id="99dc8-127">**Semi-annual**</span></span> <br/> |<span data-ttu-id="99dc8-128">1 января и 1 июля</span><span class="sxs-lookup"><span data-stu-id="99dc8-128">Jan 1 and July 1</span></span> <br/> | <span data-ttu-id="99dc8-129">2 недели перед основным выпуском, в котором переносятся новые функции</span><span class="sxs-lookup"><span data-stu-id="99dc8-129">2 weeks before the major release that brings new features</span></span><br/> |

<span data-ttu-id="99dc8-130">Для получения дополнительных сведений о расписаниях обновления каналов ознакомьтесь с разработкой [журнала обновлений для приложений Microsoft 365 (в порядке даты)](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date).</span><span class="sxs-lookup"><span data-stu-id="99dc8-130">For more information about channel update schedules, see [Update history for Microsoft 365 Apps (listed by date)](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date).</span></span>

## <a name="related-articles"></a><span data-ttu-id="99dc8-131">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="99dc8-131">Related articles</span></span>

[<span data-ttu-id="99dc8-132">Новые возможности управления в Office теперь доступны в целом</span><span class="sxs-lookup"><span data-stu-id="99dc8-132">Office What's New management is now generally available</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)