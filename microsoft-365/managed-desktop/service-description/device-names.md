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
# <a name="device-names"></a>Имена устройств

Microsoft Managed Desktop использует Автопилот Windows, Azure Active Directory и Microsoft Intune. Для бесперебойной совместной работы этих служб устройствам требуются согласованные стандартизированные имена. Microsoft Managed Desktop применяет стандартизированный формат имен (формы *MMD-%RAND11)* при регистрации устройств. Автопилот Windows назначает эти имена. Дополнительные сведения об автопилоте см. в странице [First-run experience with Autopilot и на странице Состояние регистрации.](../get-started/esp-first-run.md)

## <a name="automated-name-changes"></a>Автоматические изменения имени

Если устройство будет переименовано позже, microsoft Managed Desktop автоматически переименует его в новое имя в стандартизированном формате. Этот процесс происходит каждые четыре часа. Изменение имени происходит при следующем перезапуске устройства пользователем.

> [!IMPORTANT]
> Если среда зависит от определенных имен устройств (например, для поддержки определенной конфигурации сети), необходимо изучить варианты удаления этой зависимости перед регистрацией в Microsoft Managed Desktop. Если необходимо сохранить зависимость от имени, можно отправить запрос через портал [Admin,](../working-with-managed-desktop/admin-support.md) чтобы отключить функцию переименования и использовать нужный формат имен.