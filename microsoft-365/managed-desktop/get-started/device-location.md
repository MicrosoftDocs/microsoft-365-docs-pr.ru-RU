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
# <a name="windows-10-location-service"></a>Служба расположения Windows 10

Устройства в Microsoft Managed Desktop регистрируются с помощью Автопилота Windows. Этот процесс позволяет управлять ими с помощью Azure Active Directory и Microsoft Intune. По умолчанию служба расположения Windows 10 отключена, если устройство включено впервые, если эта функция не включена в параметрах Конфиденциальность во время "неявного опыта". Эти параметры скрыты во время регистрации автопилота в Microsoft Managed Desktop. Дополнительные сведения о настройках автопилота см. в странице [First-run experience with Autopilot и на странице Состояние регистрации.](esp-first-run.md)

По этой причине устройства Microsoft Managed Desktop не могут получить расположение своих устройств, что ограничивает возможности некоторых функций Windows, например часовых поясов. Дополнительные сведения о службе расположения Windows 10 см. в [службе расположения и конфиденциальности Windows 10.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)

Чтобы участвовать в Microsoft Managed Desktop, не нужно использовать службу расположения, но пользовательский доступ будет ограничен. Например, устройства не смогут автоматически определять часовой пояс, когда пользователи работают в другом часовом поясе.

## <a name="enable-the-location-service"></a>Включить службу расположения

Вы можете либо использовать службу расположения при регистрации устройств в службу Microsoft Managed Desktop, либо вы можете включить или отключить службу после регистрации.

### <a name="opt-in-during-enrollment"></a>Выбор во время регистрации

Вы можете включить службу расположения службы управляемых настольных компьютеров Майкрософт. Во время последовательности регистрации вам будет предложено выбрать, хотите ли вы разрешить включить службу расположения Windows 10 на устройствах.

### <a name="control-the-location-service-after-enrollment"></a>Управление службой расположения после регистрации

Служба расположения может быть включена (или отключена) в [](../working-with-managed-desktop/admin-support.md) любое время, подав запрос на поддержку на [портале Admin.](access-admin-portal.md)

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a>Как Microsoft Managed Desktop настраивает службу расположения Windows 10

Если вы решите использовать службу расположения, мы используем минимальные параметры, необходимые без влияния на конфиденциальность пользователей. Дополнительные сведения см. в [службе расположения и конфиденциальности Windows 10.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)

Microsoft Managed Desktop позволяет **параметру конфиденциальности расположения** в **настройках Windows** разрешить **доступ к расположению на этом устройстве.** Пользовательский интерфейс выглядит так:

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Параметры расположения в настройках Windows":::

> [!NOTE]
> Если вы решите использовать службу расположения, это относится только к самой операционной системе Windows. Приложения не могут использовать службы расположения. Каждый пользователь может выбрать, разрешить ли приложениям доступ к их расположению.