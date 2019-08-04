---
title: Обзор настройки
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Обзор процедуры настройки для Microsoft 365 Business.
ms.openlocfilehash: ae7ed0aab36a6e759e0f0c1fbc3d3183273a284e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074409"
---
# <a name="overview-of-setup"></a>Обзор программы установки

Большинство этапов настройки можно выполнить в мастере установки, но Кроме того, указаны другие параметры.


## <a name="step-1-add-your-domain-and-users"></a>Шаг 1: Добавление домена и пользователей

   - **[Добавление домена](set-up.md#add-your-domain-to-personalize-sign-in)** (если вы приобрели свой домен во время [регистрации](sign-up.md), этот шаг уже выполнен.)

    - **Добавление пользователей**. Это можно сделать одним из трех способов:
        - В [мастере](set-up.md#add-users-in-the-wizard).
        - Используйте синхронизацию службы каталогов для [добавления пользователей с помощью Azure AD Connect,](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) если у вас есть локальная служба Active Directory.
        - Вы также можете [Добавить пользователей позже](add-users-m365b.md) в центре администрирования.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Шаг 2: Настройка политик безопасности и настройка устройств 

  - Используйте [Мастер установки](set-up.md#set-up-security-policies-and-device-configurations) для настройки политик устройств и безопасности. 
  - Вы также можете добавить дополнительные или изменить их позже в [центре администрирования](view-policies-and-devices.md) и [портале Intune](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).
  - В дополнение к параметрам безопасности в мастере установки вы можете повысить уровень безопасности, добавив следующие параметры:

      - **Защита от вредоносных программ электронной почты**
      - **Безопасные ссылки расширенной защиты от угроз (ATP)**
      - **Безопасные вложения ATP**
      - **Защита от фишинга ATP**
      - **Архивация на базе Exchange Online**
      - **Data Loss Prevention (DLP)**
      - **Azure Information Protection (Plan1**)

          Чтобы приступить к работе, [Настройте дополнительные политики безопасности](set-up-advanced-security.md).

        Кроме того, вы можете ознакомиться с десятью рекомендациями по обеспечению безопасности [Microsoft 365 для бизнеса](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) в плане рекомендаций по обеспечению безопасности.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Шаг 3: Настройка устройств с Windows 10 и управление ими

   Когда вы присоединяете устройство Windows 10 к Azure AD, политики, которые вы настроили в [шаге 2](#step-2-set-up-security-policies-and-configure-devices) , будут применены к нему.

   - Windows 10 профессиональная — это [Предварительный компонент](pre-requisites-for-data-protection.md) для Microsoft 365 Business, но если у вас есть Windows 7 Профессиональная, Windows 8 Профессиональная или Windows 8,1 Pro, ваша подписка дает вам возможность [выполнить обновление до Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
    - Используйте [Мастер установки](set-up.md#set-up-security-policies-and-device-configurations) для настройки политик для устройств с Windows 10.

## <a name="stes-4-install-office-365-business"></a>Стес 4: установка Office 365 для бизнеса
- Вы можете автоматически установить Office на устройствах с Windows с помощью [мастера установки](set-up.md#deploy-office-365-client-apps).
- Автоматическая [Установка Office](auto-install-or-uninstall-office.md) из центра администрирования.
- Разрешите пользователям [устанавливать приложения Office](https://docs.microsoft.com/office365/admin/setup/install-applications) для Windows и устройств.
     
## <a name="advanced"></a>Дополнительно
- **Использование автопилота для настройки новых устройств**
            
     Вы можете использовать [автопилот Windows](add-autopilot-devices-and-profile.md) для автоматической предварительной настройки **новых** устройств с Windows 10 для пользователя, но вам может быть проще получить [партнера](https://www.microsoft.com/solution-providers/search) , который может сделать это. Вы также можете перейти в [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) и попросить специалиста по облачным технологиям настроить новые устройства, которые вы приобрели.

- **Доступ к локальным ресурсам**

     - Если ваша организация использует локальную службу Windows Server Active Directory, вы можете настроить Microsoft 365 бизнес для защиты устройств с Windows 10, сохраняя доступ к локальным ресурсам, требующим локальной проверки подлинности. Выполните действия, описанные в разделе " [Включение устройств, присоединенных к домену" с Windows 10 для управления в Microsoft 365 Business](manage-windows-devices.md) , чтобы настроить. Это предпочитаемый метод и устройства в этом состоянии называются гибридными подключенными устройствами Azure AD.

    - Если в вашей организации есть локальная служба Active Directory, содержащая некоторые локальные ресурсы (например, файловые ресурсы и принтеры), вы можете предоставить подключенным устройствам Azure AD доступ к этим ресурсам, выполнив действия, описанные здесь: [доступ к локальным ресурсам из Подключенное к Azure AD устройство в Microsoft 365 Business](access-resources.md).

  