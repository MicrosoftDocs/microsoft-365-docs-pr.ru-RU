---
title: Обзор установки
f1.keywords:
- NOCSH
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 'Узнайте, как настроить Microsoft 365 бизнес премиум: от подписки до добавления домена и пользователей, настройки политик безопасности и других.'
ms.openlocfilehash: 46370166a9d5e8c9308b8947513e631c159f0b86
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842137"
---
# <a name="overview-of-setup"></a>Обзор установки

Посмотрите короткое видео о настройке Microsoft 365 бизнес премиум.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Если это видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

Большинство действий по настройке можно сделать в управляемой настройке, но другие параметры также перечислены.

## <a name="step-1-add-your-domain-and-users"></a>Действие 1. Добавление домена и пользователей

   - **[Добавьте домен](set-up.md#add-your-domain-to-personalize-sign-in)** (если вы приобрели домен в ходе [регистрации](sign-up.md), то это действие уже выполнено.)

   - **Добавление пользователей**. Добавить пользователей можно тремя способами:
        - В [управляемой настройке.](set-up.md#add-users-in-the-wizard)
        - Воспользуйтесь синхронизацией каталогов, чтобы [добавить пользователей с помощью Azure AD Connect ](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization), если у вас есть локальная служба каталогов Active Directory.
        - Кроме того, вы сможете [добавить пользователей позже](add-users-m365b.md) в Центре администрирования.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Действие 2. Настройка политик безопасности и настройка устройств 

  - Используйте [управляемую настройку](set-up.md#protect-your-organization) для настройки политик устройств. 
  - Кроме того, вы сможете добавлять новых пользователей или редактировать их в [Центре администрирования](view-policies-and-devices.md) и на [портале Intune](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).
  - Мастер установки также настроит основные параметры защиты от угроз и защиты от потери данных.
  
  Помимо параметров безопасности, в мастере установки вы можете повысить уровень безопасности, добавив следующие параметры:

- **Защита от вредоносных программ в электронной почте**
- **Защита от фишинга в Защитнике office 365**
- **Архивация на базе Exchange Online**
- **Azure Information Protection (план 1**)

To get started, see [increase threat protection](increase-threat-protection.md) and set up compliance [features](set-up-compliance.md).

См. также 10 лучших способов защиты [Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) бизнес премиум.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Действие 3. Настройка устройств с Windows 10 и управление ими

После выполнения управляемой настройки необходимо защитить все компьютеры с Windows 10 в организации.
  
- Windows 10 Pro [](pre-requisites-for-data-protection.md) является необходимым условием для Microsoft 365 бизнес премиум, но если у вас есть Windows 7 Pro, Windows 8 Pro или Windows 8.1 Pro, ваша подписка дает право на обновление до [Windows 10 Pro.](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)
- Чтобы настроить политики для устройств с Windows 10, выполните действия, описанные в разделе [защита компьютеров с Windows 10](secure-win-10-pcs.md).

При присоединении устройства с Windows 10 к Azure AD применяются политики, установленные для компьютеров с Windows 10. Дополнительные сведения [см. в подсети "Настройка устройств с Windows для пользователей Microsoft 365".](set-up-windows-devices.md)

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Шаг 4. Установка приложений Microsoft 365 для бизнеса
- Вы можете автоматически установить Office на устройствах с Windows с помощью[мастера установки](set-up.md#deploy-office-365-client-apps).
- Разрешите пользователям [устанавливать приложения Office](https://docs.microsoft.com/office365/admin/setup/install-applications) для Windows и устройств.
     
## <a name="advanced"></a>Дополнительно
- **Использование Autopilot для настройки новых устройств**
            
     Вы можете воспользоваться [Windows Autopilot](add-autopilot-devices-and-profile.md)для автоматической предварительной настройки **новых** устройств с Windows 10 для пользователя, но возможно, что будет проще найти [партнера](https://www.microsoft.com/solution-providers/search), который сделает это за вас. Кроме того, вы можете перейти в [магазин Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) и попросить эксперта по облачным технологиям настроить приобретаемые вами новые устройства.

- **Доступ к локальным ресурсам**

     - Если в вашей организации используется локальная служба Windows Server Active Directory, вы можете настроить Microsoft 365 бизнес премиум для защиты устройств с Windows 10, сохранив при этом доступ к локальным ресурсам, которые требуют локальной проверки подлинности. Чтобы настроить эту возможность, выполните действия, которые необходимо предпринять, чтобы включить управление устройствами с Windows 10, которые присоединились к домену, [с помощью Microsoft 365 бизнес премиум.](manage-windows-devices.md) Это предпочтительный способ, а устройства в этом состоянии называются устройствами с гибридным присоединением к Azure AD.

    - Если в вашей компании есть локальная служба Active Directory, которая содержит некоторые локальные ресурсы (например, файловые ресурсы и принтеры), вы можете предоставить устройствам, присоединенным к Azure AD, доступ к этим ресурсам, следуя указанным ниже шагам: доступ к локальным ресурсам с устройства, присоединенного к [Azure AD, в Microsoft 365 бизнес премиум.](access-resources.md)

## <a name="see-also"></a>См. также

[Обучающие видеоролики по Microsoft 365 для бизнеса](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
