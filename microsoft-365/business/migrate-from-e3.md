---
title: Переход на Microsoft 365 бизнес из Office 365 E3
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Узнайте, как перейти с Office 365 E3 на Microsoft 365 бизнес премиум.
ms.openlocfilehash: eebf78c24ed4bfd1a4fc2d843f37aebbe3d35e31
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558265"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Переход с Office 365 E3 на Microsoft 365 бизнес премиум 

Microsoft 365 бизнес премиум имеет все необходимое для малого бизнеса, сочетая лучшие в своем классе облачные приложения для повышения производительности с простым управлением устройствами и безопасностью. Если у вас есть подписка на Office 365 E3, но не более 300 сотрудников, рассмотрите возможность перехода на Microsoft 365 бизнес премиум для дополнительных функций безопасности.

Миграция проста: сначала вы переключаетсяе лицензии, а все данные и сведения о пользователях в текущей подписке сохраняются. После миграции вам потребуется настроить функции, добавленные в Microsoft 365 бизнес премиум.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Различия между Office 365 E3 и Microsoft 365 бизнес премиум

В этой таблице показаны различия между Microsoft 365 бизнес премиум и Office 365 E3.

| Возможность    | Поддержка в Microsoft 365 бизнес премиум    | Поддержка в Office 365 E3 | 
|:-------|:-----|:-----|
| **Локальная среда**        | | | 
| Приложения Office<sup>1</sup>    | Приложения Microsoft 365 для бизнеса    | Приложения Microsoft 365 для предприятий | 
| **Облачные приложения для повышения производительности**        | | | 
| Exchange Online и Outlook    | Ограничение на объем хранилища 50 ГБ на почтовый ящик и неограниченное архивация на базе Exchange Online    | Ограничение в 100 ГБ на почтовый ящик и неограниченное архивация на базе Exchange Online | 
| Teams    | ![Входит в состав Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Office 365 E3](../media/check-mark.png) | 
| OneDrive для бизнеса    | Ограничение на объем хранилища 1 ТБ на пользователя    | Без ограничений | 
| Yammer, SharePoint Online, Планировщик, Stream    | ![Входит в состав Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Входит в состав Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Office 365 E3](../media/check-mark.png) | 
| Диспетчер клиентов Outlook, MileIQ    | ![Входит в состав Microsoft 365 бизнес премиум](../media/check-mark.png)    | | 
| **Защита от угроз**        | | | 
| Защитник для Office 365 (план 1) | ![Входит в состав Microsoft 365 бизнес премиум](../media/check-mark.png)    | Не включено, но может быть добавлено в | 
| **управление удостоверениями;**        | | | 
| Самостоятельный сброс паролей для гибридных учетных записей Azure Active Directory (Azure AD), многофакторная проверка подлинности Azure AD (MFA), условный доступ, возврат паролей для локального удостоверения|     ![Входит в состав Microsoft 365 бизнес премиум](../media/check-mark.png)    |  | 
| **Управление устройствами и приложениями**        | | |
| Microsoft Intune, Windows AutoPilot|     ![Входит в состав Microsoft 365 бизнес премиум](../media/check-mark.png)    |  |
| Активация совместно используемого компьютера|     ![Входит в состав Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Office 365 E3](../media/check-mark.png)| 
| Права на обновление до Windows 10 Pro с лицензий Win 7/8.1 Pro|     ![Входит в состав Microsoft 365 бизнес премиум](../media/check-mark.png)    || 
| **Защита информации**        | | |
|Защита от потери данных в Office 365|    ![Входит в состав Microsoft 365 бизнес премиум](../media/check-mark.png)|![Включено в Office 365 E3](../media/check-mark.png)|
|Azure Information Protection (план 1), использование Bitlocker|![Входит в состав Microsoft 365 бизнес премиум](../media/check-mark.png)||
|Azure Information Protection (план 1), метки конфиденциальности|![Входит в состав Microsoft 365 бизнес премиум](../media/check-mark.png)||
|**Лицензия клиентского доступа (cal rights)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![Включено в Office 365 E3](../media/check-mark.png)|

<sup>1</sup> Версия Приложений Office для Microsoft 365 бизнес премиум не включает активацию томов с помощью групповой политики, телеметрии приложений, элементов управления обновлениями, сравнения электронных таблиц и запросов, а также бизнес-аналитики.

## <a name="migration"></a>Миграция

Инструкции по переносу [](../commerce/subscriptions/change-plans-manually.md) подписки см. в руководстве по изменению планов вручную, если вы хотите переместить только несколько человек в Microsoft 365 бизнес премиум. Вы также [можете](../commerce/subscriptions/upgrade-to-different-plan.md)автоматически обновить всех пользователей или вместе с партнером перенести подписку и лицензии E3 на подписку Microsoft 365 бизнес премиум.
В следующих разделах описаны изменения, которые необходимо внести (если они есть) и что можно сделать после миграции.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Конфигурация и данные подписки На Office 365 E3
Перед миграцией не нужно вносить какие-либо изменения в текущую подписку или данные, в том числе:

- Конфигурация подписки, например записи DNS и доменные имена.
- Учетные записи пользователей и групп и параметры проверки подлинности, такие как многофакторная проверка подлинности или политики условного доступа.
- Конфигурации служб повышения производительности и их данные, такие как Teams, почтовые ящики Exchange Online, сайты SharePoint Online, папки OneDrive для бизнеса и записные книжки OneNote.
- Приложения Office будут масштабироваться автоматически. Современное лицензирование Office 365 проверяет назначение лицензии пользователя каждые 72 часа и преобразует приложения Office в версию, которая соответствует подписке пользователя.

### <a name="windows-10"></a>Windows 10

Если windows еще не обновлена windows Pro Creator, обновите их [до Windows Pro Creators Update.](upgrade-to-windows-pro-creators-update.md)

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Настройка политик для защиты пользовательских устройств и файлов

> [!NOTE]
> Если вы настроили политики и устройства MDM Office 365, эти устройства будут перечислены на странице "Устройства" в Центре администрирования Microsoft 365.  Все политики, которые вы настроили, будут отсылаться в список классических политик на [портале Intune.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)

После присвоения лицензий Microsoft 365 бизнес премиум вы можете начать защищать устройства и файлы пользователей.

Если вы обновили всех пользователей в организации до Microsoft 365 бизнес премиум, мастер установки будет отыгрыт на домашней странице и сможете выполнять действия по настройке [Microsoft 365 бизнес премиум](set-up.md) в мастере настройки для защиты файлов и мобильных устройств.

Вы также можете выполнить эти действия на странице "Устройства":
  
1. В Центре администрирования в левой области найдите **"Политики** \> **устройств".**
    
2. На странице **"Политики устройств"** выберите **"Добавить".**
    
3. В области **"Добавление** политики" приведите для политики имя, а затем выберите тип **политики** в выпадаемом окке. 
    
     Вы можете настроить политики приложений для защиты файлов на устройствах с Android и iPhone, а также Windows 10, а также настроить политики конфигурации устройств для устройств с Windows 10, которые принадлежат компании. Подробные сведения см. по следующим ссылкам:
    
  - [Настройка параметров защиты приложений для устройств с Android и iOS](app-protection-settings-for-android-and-ios.md)
    
  - [Настройка параметров защиты приложений для устройств с Windows 10](protection-settings-for-windows-10-devices.md)
    
  - [Настройка параметров защиты устройств для компьютеров с Windows 10](protection-settings-for-windows-10-pcs.md)
  
4. После того как вы настроите политики, вы и ваши сотрудники сможете настроить устройства:
    
  - Действия для устройств с Windows см. в подсети "Настройка устройств с Windows для [пользователей Microsoft 365 бизнес премиум".](set-up-windows-devices.md) 
    
  - Дополнительные действия для телефонов с Android и iPhone см. в подсети "Настройка мобильных устройств для [пользователей Microsoft 365](set-up-mobile-devices.md) бизнес премиум". 
  
### <a name="mailbox-size"></a>Размер почтового ящика

Microsoft 365 бизнес премиум имеет ограничение хранилища в 50 ГБ, так как использует Exchange Online (план 1). При переходе на Microsoft 365 бизнес премиум, если какой-либо из пользователей превышает 50 ГБ хранилища почтовых ящиков, рекомендуется назначить этому пользователю Exchange Online (план 2) и удалить Exchange Online (план 1), так как невозможно назначить и то, и другое.


### <a name="threat-protection"></a>Защита от угроз

После перехода на Microsoft 365 бизнес премиум у вас есть Защитник для Office 365. Обзор см. в Microsoft Defender для [Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) To set up, see [set up Safe Links,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa) [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).

### <a name="sensitivity-labels"></a>Метки конфиденциальности

Чтобы начать использовать метки [](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) конфиденциальности, см. обзор меток конфиденциальности, а также видео о создании меток [конфиденциальности и управлении ими.](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)
