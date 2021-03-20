---
title: Сведения о параметрах профиля AutoPilot
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Профили AutoPilot помогают управлять установкой Windows на устройствах пользователей. Профили содержат по умолчанию и необязательные параметры, такие как пропустить установку Кортаны.
ms.openlocfilehash: be10e0e1c8c96ce05aab8526d2010313662ed5f2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913385"
---
# <a name="about-autopilot-profile-settings"></a>Сведения о параметрах профиля AutoPilot

## <a name="autopilot-profile-settings"></a>Параметры профилей AutoPilot

Вы можете использовать профили АвтоПилота для управления установкой Windows на устройствах пользователей. Эти профили содержат описанные ниже параметры.
  
 **Автоматически задаваемы функции по умолчанию AutoPilot:**
  
|**Параметр**|**Описание**|
|:-----|:-----|
|Пропустить регистрацию Кортаны, OneDrive и OEM  <br/> |Пропускает установку потребительских приложений, таких как Кортана и личный OneDrive. Пользователь устройства может установить их позже, если пользователь является локальным администратором на устройстве. Первоначальная регистрация производителя пропущена, так как устройство будет управляться Microsoft 365 Бизнес Премиум.  <br/> |
|Интерфейс входа с фирменной символикой компании  <br/> |Если в вашей компании есть страница Добавить брендинг вашей компании на страницу [Вход в Microsoft 365,](../admin/setup/customize-sign-in-page.md)пользователь устройства получит этот опыт при входе.  <br/> |
|Автоматическая регистрация в службе управления мобильными устройствами с использованием настроенных учетных записей AAD  <br/> |Идентификатор пользователя будет управляться Azure Active Directory, и пользователи во время входа в Windows и Microsoft 365 с учетными данными Microsoft 365 Бизнес Премиум.  <br/> |
   
 **Дополнительные параметры**
  
|**Параметр**|**Описание**|
|:-----|:-----|
|Пропустить параметры конфиденциальности (по умолчанию выключен)  <br/> |Если для этого параметра установить значение **Вкл.**, пользователь устройства не увидит условия лицензии для устройства и Windows при первом входе.  <br/> |
|Не разрешать пользователю становиться локальным администратором  <br/> |Если для этого параметра установить значение **Вкл.**, пользователь устройства не сможет устанавливать личные приложения, такие как Кортана.<br/> |
