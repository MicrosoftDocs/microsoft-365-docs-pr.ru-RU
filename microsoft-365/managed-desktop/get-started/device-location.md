---
title: Служба расположения Windows 10
description: Как включить службы расположения Windows для устройств
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929525"
---
# <a name="windows-10-location-service"></a><span data-ttu-id="c7d3c-104">Служба расположения Windows 10</span><span class="sxs-lookup"><span data-stu-id="c7d3c-104">Windows 10 location service</span></span>

<span data-ttu-id="c7d3c-105">Устройства в Microsoft Managed Desktop регистрируются с помощью Автопилота Windows.</span><span class="sxs-lookup"><span data-stu-id="c7d3c-105">Devices in Microsoft Managed Desktop are registered by using Windows Autopilot.</span></span> <span data-ttu-id="c7d3c-106">Этот процесс позволяет управлять ими с помощью Azure Active Directory и Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="c7d3c-106">This process lets us manage them with Azure Active Directory and Microsoft Intune.</span></span> <span data-ttu-id="c7d3c-107">По умолчанию служба расположения Windows 10 отключена, если устройство включено впервые, если эта функция не включена в параметрах Конфиденциальность во время "неявного опыта".</span><span class="sxs-lookup"><span data-stu-id="c7d3c-107">By default, the Windows 10 location service is disabled when a device is turned on for the first time unless this feature is enabled in the Privacy settings during the "out of box experience."</span></span> <span data-ttu-id="c7d3c-108">Эти параметры скрыты во время регистрации автопилота в Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="c7d3c-108">These settings are hidden during Autopilot enrollment in Microsoft Managed Desktop.</span></span> <span data-ttu-id="c7d3c-109">Дополнительные сведения о настройках автопилота см. в странице [First-run experience with Autopilot и на странице Состояние регистрации.](esp-first-run.md)</span><span class="sxs-lookup"><span data-stu-id="c7d3c-109">For more information about how Autopilot is set up, see [First-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md).</span></span>

<span data-ttu-id="c7d3c-110">По этой причине устройства Microsoft Managed Desktop не могут получить расположение своих устройств, что ограничивает возможности некоторых функций Windows, например часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="c7d3c-110">For this reason, Microsoft Managed Desktop devices can't obtain their device location, which limits the functionality of several Windows features, such as time zones.</span></span> <span data-ttu-id="c7d3c-111">Дополнительные сведения о службе расположения Windows 10 см. в [службе расположения и конфиденциальности Windows 10.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)</span><span class="sxs-lookup"><span data-stu-id="c7d3c-111">For more information about the Windows 10 location service, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="c7d3c-112">Чтобы участвовать в Microsoft Managed Desktop, не нужно использовать службу расположения, но пользовательский доступ будет ограничен.</span><span class="sxs-lookup"><span data-stu-id="c7d3c-112">You don't have to use the location service in order to participate in Microsoft Managed Desktop, but the user experience will be restricted.</span></span> <span data-ttu-id="c7d3c-113">Например, устройства не смогут автоматически определять часовой пояс, когда пользователи работают в другом часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="c7d3c-113">For example, devices won't be able to automatically determine the time zone they're in when your users work in a different time zone.</span></span>

## <a name="enable-the-location-service"></a><span data-ttu-id="c7d3c-114">Включить службу расположения</span><span class="sxs-lookup"><span data-stu-id="c7d3c-114">Enable the location service</span></span>

<span data-ttu-id="c7d3c-115">Вы можете либо использовать службу расположения при регистрации устройств в службу Microsoft Managed Desktop, либо вы можете включить или отключить службу после регистрации.</span><span class="sxs-lookup"><span data-stu-id="c7d3c-115">You can either opt in to using the location service when you enroll devices into the Microsoft Managed Desktop service or you can turn the service on or off after enrollment.</span></span>

### <a name="opt-in-during-enrollment"></a><span data-ttu-id="c7d3c-116">Выбор во время регистрации</span><span class="sxs-lookup"><span data-stu-id="c7d3c-116">Opt in during enrollment</span></span>

<span data-ttu-id="c7d3c-117">Вы можете включить службу расположения службы управляемых настольных компьютеров Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c7d3c-117">You can have the Microsoft Managed Desktop service enable the location service.</span></span> <span data-ttu-id="c7d3c-118">Во время последовательности регистрации вам будет предложено выбрать, хотите ли вы разрешить включить службу расположения Windows 10 на устройствах.</span><span class="sxs-lookup"><span data-stu-id="c7d3c-118">During the enrollment sequence, you'll be asked to select whether you want to allow the Windows 10 location service to be enabled on devices.</span></span>

### <a name="control-the-location-service-after-enrollment"></a><span data-ttu-id="c7d3c-119">Управление службой расположения после регистрации</span><span class="sxs-lookup"><span data-stu-id="c7d3c-119">Control the location service after enrollment</span></span>

<span data-ttu-id="c7d3c-120">Служба расположения может быть включена (или отключена) в [](../working-with-managed-desktop/admin-support.md) любое время, подав запрос на поддержку на [портале Admin.](access-admin-portal.md)</span><span class="sxs-lookup"><span data-stu-id="c7d3c-120">You can have the location service turned on (or off) at any time by submitting a [support request](../working-with-managed-desktop/admin-support.md) through the [Admin portal](access-admin-portal.md).</span></span>

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a><span data-ttu-id="c7d3c-121">Как Microsoft Managed Desktop настраивает службу расположения Windows 10</span><span class="sxs-lookup"><span data-stu-id="c7d3c-121">How Microsoft Managed Desktop configures the Windows 10 location service</span></span>

<span data-ttu-id="c7d3c-122">Если вы решите использовать службу расположения, мы используем минимальные параметры, необходимые без влияния на конфиденциальность пользователей.</span><span class="sxs-lookup"><span data-stu-id="c7d3c-122">If you opt in to using the location service, we use the minimum settings necessary without affecting users' privacy.</span></span> <span data-ttu-id="c7d3c-123">Дополнительные сведения см. в [службе расположения и конфиденциальности Windows 10.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)</span><span class="sxs-lookup"><span data-stu-id="c7d3c-123">For more information, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="c7d3c-124">Microsoft Managed Desktop позволяет **параметру конфиденциальности расположения** в **настройках Windows** разрешить **доступ к расположению на этом устройстве.**</span><span class="sxs-lookup"><span data-stu-id="c7d3c-124">Microsoft Managed Desktop enables the **Location privacy** setting in **Windows settings** to **Allow access to location on this device**.</span></span> <span data-ttu-id="c7d3c-125">Пользовательский интерфейс выглядит так:</span><span class="sxs-lookup"><span data-stu-id="c7d3c-125">The user interface looks like this:</span></span>

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Параметры расположения в настройках Windows":::

> [!NOTE]
> <span data-ttu-id="c7d3c-127">Если вы решите использовать службу расположения, это относится только к самой операционной системе Windows.</span><span class="sxs-lookup"><span data-stu-id="c7d3c-127">If you opt in to using the location service, this applies only to the Windows operating system itself.</span></span> <span data-ttu-id="c7d3c-128">Приложения не могут использовать службы расположения.</span><span class="sxs-lookup"><span data-stu-id="c7d3c-128">Apps are not allowed to use location services.</span></span> <span data-ttu-id="c7d3c-129">Каждый пользователь может выбрать, разрешить ли приложениям доступ к их расположению.</span><span class="sxs-lookup"><span data-stu-id="c7d3c-129">Each user can choose whether to allow apps to access their location.</span></span>