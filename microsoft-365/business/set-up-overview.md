---
title: Обзор установки
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Узнайте о шагах установки для Microsoft 365 бизнес премиум, от подписки до добавления домена и пользователей до настройки политик безопасности и других.
ms.openlocfilehash: 008a5c51698589667acc0d01649f67dab33b4c58
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245071"
---
# <a name="overview-of-setup"></a>Обзор настройки

Просмотрите короткое видео о Microsoft 365 бизнес премиум настройке.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Если это видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](../business-video/index.yml).

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

См. [также топ-10](/office365/admin/security-and-compliance/secure-your-business-data) способов обеспечения безопасности Microsoft 365 бизнес премиум на дорожную карту лучших методов безопасности.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Действие 3. Настройка устройств с Windows 10 и управление ими

После завершения управляемой установки необходимо защитить все компьютеры Windows 10 организации.
  
- Windows 10 Pro является обязательным [](pre-requisites-for-data-protection.md) условием для Microsoft 365 бизнес премиум, но если у вас есть Windows 7 Pro, Windows 8 Профессиональная или Windows 8.1 Профессиональная, подписка дает вам право на обновление до [Windows 10 Pro](./upgrade-to-windows-pro-creators-update.md).
- Чтобы настроить политики для устройств с Windows 10, выполните действия, описанные в разделе [защита компьютеров с Windows 10](secure-win-10-pcs.md).

При присоединении устройства с Windows 10 к Azure AD применяются политики, установленные для компьютеров с Windows 10. Дополнительные сведения см. в [Windows устройств для Microsoft 365 пользователей.](set-up-windows-devices.md)

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Шаг 4. Установка Приложения Microsoft 365 для бизнеса
- Вы можете автоматически установить Office на устройствах с Windows с помощью[мастера установки](set-up.md#deploy-office-365-client-apps).
- Разрешите пользователям [устанавливать приложения Office](/office365/admin/setup/install-applications) для Windows и устройств.
     
## <a name="advanced"></a>Дополнительно
- **Использование Autopilot для настройки новых устройств**
            
     Вы можете воспользоваться [Windows Autopilot](add-autopilot-devices-and-profile.md)для автоматической предварительной настройки **новых** устройств с Windows 10 для пользователя, но возможно, что будет проще найти [партнера](https://www.microsoft.com/solution-providers/search), который сделает это за вас. Кроме того, вы можете перейти в [магазин Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) и попросить эксперта по облачным технологиям настроить приобретаемые вами новые устройства.

- **Доступ к локальным ресурсам**

     - Если в организации используется Windows Server Active Directory, можно настроить Microsoft 365 бизнес премиум для защиты Windows 10 устройств, сохраняя при этом доступ к локальным ресурсам, которые требуют локальной проверки подлинности. Выполните действия в включить устройства с [Windows 10,](manage-windows-devices.md) которые будут управляться Microsoft 365 бизнес премиум, чтобы настроить это. Это предпочтительный способ, а устройства в этом состоянии называются устройствами с гибридным присоединением к Azure AD.

    - Если в вашем предприятии имеется локальный каталог Active Directory, содержащий некоторые локальные ресурсы (например, пакеты файлов и принтеры), вы можете предоставить устройствам Azure AD-присоединенные доступ к этим ресурсам, следуя следующим шагам: доступ к локальным ресурсам с устройства [Azure AD](access-resources.md)в Microsoft 365 бизнес премиум .

## <a name="related-content"></a>См. также:

[Microsoft 365 для видео обучения бизнесу](../business-video/index.yml) (страница ссылки)