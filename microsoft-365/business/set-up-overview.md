---
title: Обзор установки
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Обзор действий по установке Microsoft 365 бизнес.
ms.openlocfilehash: 4aca617015cceb85ca35c8d8ada7b83d1416d959
ms.sourcegitcommit: 178ecb21cacdeaf440f3df2fe6e539e9127fcf15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2019
ms.locfileid: "40850811"
---
# <a name="overview-of-setup"></a>Обзор установки

Посмотрите короткое видео о Microsoft 365 бизнес-установки.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Если вы нашли это видео, изучите [полную серию обучающих материалов для малых предприятий и новых в Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

Большинство действий по установке можно выполнить с помощью мастера установки, но есть и другие варианты.

## <a name="step-1-add-your-domain-and-users"></a>Действие 1. Добавление домена и пользователей

   - **[Добавьте домен](set-up.md#add-your-domain-to-personalize-sign-in)** (если вы приобрели домен в ходе[регистрации](sign-up.md), то это действие уже выполнено.)

    - **Добавление пользователей**. Добавить пользователей можно тремя способами:
        - В этом [мастере](set-up.md#add-users-in-the-wizard).
        - Воспользуйтесь синхронизацией каталогов, чтобы [добавить пользователей с помощью Azure AD Connect ](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization), если у вас есть локальная служба каталогов Active Directory.
        - Кроме того, вы сможете [добавить пользователей позже](add-users-m365b.md) в Центре администрирования.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Действие 2. Настройка политик безопасности и настройка устройств 

  - Чтобы настроить политики устройств, воспользуйтесь этим [мастером установки](set-up.md#protect-your-organization). 
  - Кроме того, вы сможете добавлять новых пользователей или редактировать их в [Центре администрирования](view-policies-and-devices.md) и на [портале Intune](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).
  - Мастер установки также настроит основные параметры защиты от угроз и защиты от потери данных.
  
  Помимо параметров безопасности, в мастере установки вы можете повысить уровень безопасности, добавив следующие параметры:

- **Защита от вредоносных программ в электронной почте**
- **Защита от фишинга ATP**
- **Архивация на базе Exchange Online**
- **Azure Information Protection (план 1**)

Чтобы приступить к работе, ознакомьтесь со статьей [Настройка расширенных политик безопасности](set-up-advanced-security.md).

См. также[10 основных способов защиты Microsoft 365 бизнес](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data), где содержится план рекомендаций в области безопасности.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Действие 3. Настройка устройств с Windows 10 и управление ими

После запуска мастера установки рекомендуется обеспечить защиту всех компьютеров с Windwos 10 в вашей организации.
  
- Windows 10 Профессиональная является[необходимым компонентом](pre-requisites-for-data-protection.md) для Microsoft 365 бизнес, но если у вас есть подписка на Windows 7 Профессиональная, Windows 8 Профессиональная или Windows 8.1 Профессиональная, вы можете [перейти на Windows 10 Профессиональная](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
- Чтобы настроить политики для устройств с Windows 10, выполните действия, описанные в разделе [защита компьютеров с Windows 10](secure-win-10-pcs.md).

При присоединении устройства с Windows 10 к Azure AD применяются политики, установленные для компьютеров с Windows 10. Для получения дополнительной информации см. [Настройка устройств с Windows для пользователей Microsoft 365 бизнес](set-up-windows-devices.md).

## <a name="step-4-install-office-365-business"></a>Действие 4. Установка Office 365 бизнес
- Вы можете автоматически установить Office на устройствах с Windows с помощью[мастера установки](set-up.md#deploy-office-365-client-apps).
- Разрешите пользователям [устанавливать приложения Office](https://docs.microsoft.com/office365/admin/setup/install-applications) для Windows и устройств.
     
## <a name="advanced"></a>Дополнительно
- **Использование Autopilot для настройки новых устройств**
            
     Вы можете воспользоваться[Windows Autopilot](add-autopilot-devices-and-profile.md)для автоматической предварительной настройки **новых** устройств с Windows 10 для пользователя, но возможно, что будет проще найти [партнера](https://www.microsoft.com/solution-providers/search), который сделает это за вас. Кроме того, вы можете перейти в [магазин Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) и попросить эксперта по облачным технологиям настроить приобретаемые вами новые устройства.

- **Доступ к локальным ресурсам**

     - Если в вашей организации используется локальная версия Windows Server Active Directory, вы можете настроить Microsoft 365 бизнес для защиты устройств с Windows 10, сохранив при этом доступ к локальным ресурсам, для которых требуется локальная проверка подлинности. Для такой настройки выполните действия, перечисленные в разделе [Разрешение Microsoft 365 бизнес управлять устройствами с Windows 10, присоединенными к домену](manage-windows-devices.md). Это предпочтительный способ, а устройства в этом состоянии называются устройствами с гибридным присоединением к Azure AD.

    - Если в вашей организации есть локальная служба каталогов Active Directory, содержащая определенные локальные ресурсы (например, общие папки и принтеры), вы можете предоставить устройствам, присоединенным к Azure AD, доступ к этим ресурсам, выполнив действия, описанные в разделе [Доступ к локальным ресурсам с устройства, присоединенного к Azure AD, в Microsoft 365 бизнес](access-resources.md).

## <a name="see-also"></a>См. также

[учебные видео по Microsoft 365 бизнес](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
