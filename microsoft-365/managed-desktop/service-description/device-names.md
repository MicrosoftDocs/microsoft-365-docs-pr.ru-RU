---
title: Имена устройств
description: Управление microsoft Managed Desktop именами устройств
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
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893981"
---
# <a name="device-names"></a><span data-ttu-id="41583-103">Имена устройств</span><span class="sxs-lookup"><span data-stu-id="41583-103">Device names</span></span>

<span data-ttu-id="41583-104">Microsoft Managed Desktop использует Автопилот Windows, Azure Active Directory и Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="41583-104">Microsoft Managed Desktop uses Windows Autopilot, Azure Active Directory, and Microsoft Intune.</span></span> <span data-ttu-id="41583-105">Для бесперебойной совместной работы этих служб устройствам требуются согласованные стандартизированные имена.</span><span class="sxs-lookup"><span data-stu-id="41583-105">For these services to work together seamlessly, devices need consistent, standardized names.</span></span> <span data-ttu-id="41583-106">Microsoft Managed Desktop применяет стандартизированный формат имен (формы *MMD-%RAND11)* при регистрации устройств.</span><span class="sxs-lookup"><span data-stu-id="41583-106">Microsoft Managed Desktop applies a standardized name format (of the form *MMD-%RAND11*) when devices are enrolled.</span></span> <span data-ttu-id="41583-107">Автопилот Windows назначает эти имена.</span><span class="sxs-lookup"><span data-stu-id="41583-107">Windows Autopilot assigns these names.</span></span> <span data-ttu-id="41583-108">Дополнительные сведения об автопилоте см. в странице [First-run experience with Autopilot и на странице Состояние регистрации.](../get-started/esp-first-run.md)</span><span class="sxs-lookup"><span data-stu-id="41583-108">For more information about Autopilot, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

## <a name="automated-name-changes"></a><span data-ttu-id="41583-109">Автоматические изменения имени</span><span class="sxs-lookup"><span data-stu-id="41583-109">Automated name changes</span></span>

<span data-ttu-id="41583-110">Если устройство будет переименовано позже, microsoft Managed Desktop автоматически переименует его в новое имя в стандартизированном формате.</span><span class="sxs-lookup"><span data-stu-id="41583-110">If a device gets renamed later, Microsoft Managed Desktop will automatically rename it to a new name in the standardized format.</span></span> <span data-ttu-id="41583-111">Этот процесс происходит каждые четыре часа.</span><span class="sxs-lookup"><span data-stu-id="41583-111">This process occurs every four hours.</span></span> <span data-ttu-id="41583-112">Изменение имени происходит при следующем перезапуске устройства пользователем.</span><span class="sxs-lookup"><span data-stu-id="41583-112">The name change takes place the next time the user restarts the device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41583-113">Если среда зависит от определенных имен устройств (например, для поддержки определенной конфигурации сети), необходимо изучить варианты удаления этой зависимости перед регистрацией в Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="41583-113">If your environment depends on specific device names (for example, to support a particular network configuration), you should investigate options to remove that dependency before enrolling in Microsoft Managed Desktop.</span></span> <span data-ttu-id="41583-114">Если необходимо сохранить зависимость от имени, можно отправить запрос через портал [Admin,](../working-with-managed-desktop/admin-support.md) чтобы отключить функцию переименования и использовать нужный формат имен.</span><span class="sxs-lookup"><span data-stu-id="41583-114">If you must keep the name dependency, you can submit a request through the [Admin portal](../working-with-managed-desktop/admin-support.md) to disable the renaming function and use your desired name format.</span></span>