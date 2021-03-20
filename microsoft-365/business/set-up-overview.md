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
description: 'Узнайте о шагах настройки для Microsoft 365 Business Premium: от подписки до добавления домена и пользователей до настройки политик безопасности и других.'
ms.openlocfilehash: 9d92aefb3b5666bb7c2fd2e13c9a00f074f107a7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912497"
---
# <a name="overview-of-setup"></a>Обзор настройки

Просмотрите короткое видео о настройке Microsoft 365 Бизнес Премиум.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Если это видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

Большинство действий по настройке можно сделать в управляемой настройке, но другие параметры также перечислены.

## <a name="step-1-add-your-domain-and-users"></a>Действие 1. Добавление домена и пользователей

   - **[Добавьте домен](set-up.md#add-your-domain-to-personalize-sign-in)** (если вы приобрели домен в ходе [регистрации](sign-up.md), то это действие уже выполнено.)

   - **Добавление пользователей**. Добавить пользователей можно тремя способами:
        - В [управляемой настройке](set-up.md#add-users-in-the-wizard).
        - Воспользуйтесь синхронизацией каталогов, чтобы [добавить пользователей с помощью Azure AD Connect ](../enterprise/set-up-directory-synchronization.md), если у вас есть локальная служба каталогов Active Directory.
        - Кроме того, вы сможете [добавить пользователей позже](../admin/add-users/add-users.md) в Центре администрирования.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Действие 2. Настройка политик безопасности и настройка устройств 

  - Настройка [политик устройств с](set-up.md#protect-your-organization) помощью управляемой установки. 
  - Кроме того, вы сможете добавлять новых пользователей или редактировать их в [Центре администрирования](view-policies-and-devices.md) и на [портале Intune](/intune/tutorial-walkthrough-intune-portal).
  - Мастер установки также настроит основные параметры защиты от угроз и защиты от потери данных.
  
  Помимо параметров безопасности, в мастере установки вы можете повысить уровень безопасности, добавив следующие параметры:

- **Защита от вредоносных программ в электронной почте**
- **Защита от фишинга в Defender для Office 365**
- **Архивация на базе Exchange Online**
- **Azure Information Protection (план 1**)

Чтобы начать работу, [см. в этой ленте повышение](increase-threat-protection.md) защиты от угроз и [настройка функций соответствия](set-up-compliance.md)требованиям.

См. [также топ-10 способов](/office365/admin/security-and-compliance/secure-your-business-data) обеспечения безопасности microsoft 365 Бизнес Премиум для дорожной карты лучших методов безопасности.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Действие 3. Настройка устройств с Windows 10 и управление ими

После завершения управляемой установки необходимо защитить все компьютеры Windows 10 в организации.
  
- Windows 10 Pro [](pre-requisites-for-data-protection.md) является обязательным условием для Microsoft 365 Бизнес Премиум, но если у вас есть Windows 7 Pro, Windows 8 Pro или Windows 8.1 Pro, ваша подписка дает право на обновление до [Windows 10 Pro](./upgrade-to-windows-pro-creators-update.md).
- Чтобы настроить политики для устройств с Windows 10, выполните действия, описанные в разделе [защита компьютеров с Windows 10](secure-win-10-pcs.md).

При присоединении устройства с Windows 10 к Azure AD применяются политики, установленные для компьютеров с Windows 10. Дополнительные сведения см. в [сайте Настройка устройств Windows для пользователей Microsoft 365.](set-up-windows-devices.md)

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Шаг 4. Установка приложений Microsoft 365 для бизнеса
- Вы можете автоматически установить Office на устройствах с Windows с помощью[мастера установки](set-up.md#deploy-office-365-client-apps).
- Разрешите пользователям [устанавливать приложения Office](/office365/admin/setup/install-applications) для Windows и устройств.
     
## <a name="advanced"></a>Дополнительно
- **Использование Autopilot для настройки новых устройств**
            
     Вы можете воспользоваться [Windows Autopilot](add-autopilot-devices-and-profile.md)для автоматической предварительной настройки **новых** устройств с Windows 10 для пользователя, но возможно, что будет проще найти [партнера](https://www.microsoft.com/solution-providers/search), который сделает это за вас. Кроме того, вы можете перейти в [магазин Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) и попросить эксперта по облачным технологиям настроить приобретаемые вами новые устройства.

- **Доступ к локальным ресурсам**

     - Если в организации используется локальный Windows Server Active Directory, можно настроить Microsoft 365 Business Premium для защиты устройств Windows 10, сохраняя при этом доступ к локальным ресурсам, которые требуют локальной проверки подлинности. Выполните действия в Включить устройства Windows 10, которые будут управляться [microsoft 365 Business Premium,](manage-windows-devices.md) чтобы настроить это. Это предпочтительный способ, а устройства в этом состоянии называются устройствами с гибридным присоединением к Azure AD.

    - Если в вашем бизнесе имеется локальный каталог Active Directory, содержащий некоторые локальные ресурсы (например, акции файлов и принтеры), вы можете предоставить устройствам Azure AD-присоединенные доступ к этим ресурсам, следуя следующим шагам: доступ к локальным ресурсам с устройства Azure AD в [Microsoft 365 Business Premium.](access-resources.md)

## <a name="see-also"></a>См. также

[Обучающие видеоролики по Microsoft 365 для бизнеса](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)