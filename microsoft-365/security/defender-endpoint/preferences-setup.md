---
title: Настройка Центр безопасности в Microsoft Defender параметров
description: Используйте страницу параметров для настройки общих параметров, разрешений, apis и правил.
keywords: параметры, общие параметры, разрешения, apis, правила
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5869e8406158eb6d6b2f48b3083cb9011bb3951d
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604349"
---
# <a name="configure-microsoft-defender-security-center-settings"></a><span data-ttu-id="1e0e5-104">Настройка Центр безопасности в Microsoft Defender параметров</span><span class="sxs-lookup"><span data-stu-id="1e0e5-104">Configure Microsoft Defender Security Center settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1e0e5-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1e0e5-105">**Applies to:**</span></span>
- [<span data-ttu-id="1e0e5-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1e0e5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1e0e5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e0e5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1e0e5-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="1e0e5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1e0e5-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-prefsettings-abovefoldlink)

<span data-ttu-id="1e0e5-110">Используйте меню **Параметры,** чтобы изменить общие параметры, расширенные функции, включить функцию предварительного просмотра, уведомления электронной почты и настраиваемую функцию разведки угроз.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-110">Use the **Settings** menu to modify general settings, advanced features, enable the preview experience, email notifications, and the custom threat intelligence feature.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1e0e5-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="1e0e5-111">In this section</span></span>

<span data-ttu-id="1e0e5-112">Статья</span><span class="sxs-lookup"><span data-stu-id="1e0e5-112">Topic</span></span> | <span data-ttu-id="1e0e5-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1e0e5-113">Description</span></span>
:---|:---
<span data-ttu-id="1e0e5-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1e0e5-114">General settings</span></span> | <span data-ttu-id="1e0e5-115">Измените общие параметры, которые ранее определялись как часть процесса работы с бортовой установкой.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-115">Modify your general settings that were previously defined as part of the onboarding process.</span></span>
<span data-ttu-id="1e0e5-116">Разрешения</span><span class="sxs-lookup"><span data-stu-id="1e0e5-116">Permissions</span></span> | <span data-ttu-id="1e0e5-117">Управление доступом к порталу с помощью RBAC, а также групп устройств.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-117">Manage portal access using RBAC as well as device groups.</span></span>
<span data-ttu-id="1e0e5-118">Интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="1e0e5-118">APIs</span></span> | <span data-ttu-id="1e0e5-119">Включение интеграции intel и SIEM угроз.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-119">Enable the threat intel and SIEM integration.</span></span>
<span data-ttu-id="1e0e5-120">Правила</span><span class="sxs-lookup"><span data-stu-id="1e0e5-120">Rules</span></span> | <span data-ttu-id="1e0e5-121">Настройка правил подавления и параметров автоматизации.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-121">Configure suppressions rules and automation settings.</span></span>
<span data-ttu-id="1e0e5-122">Управление устройствами</span><span class="sxs-lookup"><span data-stu-id="1e0e5-122">Device management</span></span> | <span data-ttu-id="1e0e5-123">На борту и вне устройствах.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-123">Onboard and offboard devices.</span></span>
<span data-ttu-id="1e0e5-124">Сетевые оценки</span><span class="sxs-lookup"><span data-stu-id="1e0e5-124">Network assessments</span></span> | <span data-ttu-id="1e0e5-125">Выберите устройства, которые будут регулярно проверяться и добавляться в инвентарь устройств.</span><span class="sxs-lookup"><span data-stu-id="1e0e5-125">Choose devices to be scanned regularly and added to the device inventory.</span></span>
