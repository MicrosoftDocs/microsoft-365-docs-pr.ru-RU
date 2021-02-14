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
description: Профили AutoPilot помогают управлять установкой Windows на устройствах пользователей. Профили содержат параметры по умолчанию и необязательные параметры, например пропустить установку Кортаны.
ms.openlocfilehash: 100de5e9548f901008d3ae154ac5a237ef265ffb
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401041"
---
# <a name="about-autopilot-profile-settings"></a>Сведения о параметрах профиля AutoPilot

## <a name="autopilot-profile-settings"></a>Параметры профиля AutoPilot

Профили AutoPilot можно использовать для управления установкой Windows на устройствах пользователей. Эти профили содержат описанные ниже параметры.
  
 **Функции AutoPilot по умолчанию (необходимые), которые устанавливаются автоматически:**
  
|**Параметр**|**Описание**|
|:-----|:-----|
|Пропуск регистрации Кортаны, OneDrive и OEM  <br/> |Пропускает установку потребительских приложений, таких как Кортана и личный OneDrive. Пользователь устройства может установить их позже, если пользователь является локальным администратором на устройстве. Первоначальная регистрация изготовителя пропускается, так как устройство будет управляться Microsoft 365 бизнес премиум.  <br/> |
|Интерфейс входа с фирменной символикой компании  <br/> |Если в вашей компании есть страница "Добавление фирменой марки вашей компании на страницу "Вход в [Microsoft 365",](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page)пользователь устройства получит такой опыт при входе.  <br/> |
|Автоматическая регистрация в службе управления мобильными устройствами с использованием настроенных учетных записей AAD  <br/> |Удостоверение пользователя будет управляться Службой Azure Active Directory, и пользователи во время входа в Windows и Microsoft 365 будут использовать свои учетные данные Microsoft 365 бизнес премиум.  <br/> |
   
 **Дополнительные параметры**
  
|**Параметр**|**Описание**|
|:-----|:-----|
|Пропустить параметры конфиденциальности (по умолчанию выключен)  <br/> |Если для этого параметра установить значение **Вкл.**, пользователь устройства не увидит условия лицензии для устройства и Windows при первом входе.  <br/> |
|Не разрешать пользователю становиться локальным администратором  <br/> |Если для этого параметра установить значение **Вкл.**, пользователь устройства не сможет устанавливать личные приложения, такие как Кортана.<br/> |
   
