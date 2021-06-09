---
title: Зависимость от имени адресов устройств
description: Удаление зависимости от имен устройств или запрос исключения
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
ms.openlocfilehash: 8c82acb5306e3add7c41fd4e6f7e313782d47574
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893987"
---
# <a name="address-device-name-dependency"></a><span data-ttu-id="1196d-103">Зависимость от имени адресов устройств</span><span class="sxs-lookup"><span data-stu-id="1196d-103">Address device name dependency</span></span>

<span data-ttu-id="1196d-104">компьютеры, управляемые Майкрософт применяется стандартизированный формат имен при регистрации устройств и автоматически переименовывать устройства, если имя изменено позже.</span><span class="sxs-lookup"><span data-stu-id="1196d-104">Microsoft Managed Desktop applies a standardized name format when devices are enrolled and will automatically rename devices if the name is changed later.</span></span> <span data-ttu-id="1196d-105">Дополнительные сведения см. в [сайте Device names.](../service-description/device-names.md)</span><span class="sxs-lookup"><span data-stu-id="1196d-105">For more info, see [Device names](../service-description/device-names.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1196d-106">Если среда зависит от определенных имен устройств (например, для поддержки определенной конфигурации сети), необходимо изучить варианты удаления этой зависимости перед регистрацией в компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1196d-106">If your environment depends on specific device names (for example, to support a particular network configuration), you should investigate options to remove that dependency before enrolling in Microsoft Managed Desktop.</span></span> <span data-ttu-id="1196d-107">Если необходимо сохранить зависимость от имени, можно отправить запрос через портал [Admin,](../working-with-managed-desktop/admin-support.md) чтобы отключить функцию переименования и использовать нужный формат имен.</span><span class="sxs-lookup"><span data-stu-id="1196d-107">If you must keep the name dependency, you can submit a request through the [Admin portal](../working-with-managed-desktop/admin-support.md) to disable the renaming function and use your desired name format.</span></span>