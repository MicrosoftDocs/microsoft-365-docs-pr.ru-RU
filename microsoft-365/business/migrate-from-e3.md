---
title: Миграция в Microsoft 365 Бизнес из Office 365 E3
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
description: Узнайте, как переместить бизнес в Microsoft 365 Бизнес Премиум из Office 365 E3.
ms.openlocfilehash: f2b7962918186f4a1063c5a66596135c2972ec71
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51750007"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Перенос из Office 365 E3 в Microsoft 365 Бизнес Премиум

Microsoft 365 Business Premium имеет все необходимое для малого бизнеса, сочетая лучшие в своем классе облачные приложения с простым управлением устройствами и безопасностью. Если у вас в настоящее время есть подписка на Office 365 E3, но не более 300 сотрудников, рассмотрите возможность перехода на Microsoft 365 Business Premium для дополнительных функций безопасности.

Миграция проста: сначала переключаются лицензии, и все данные и сведения о пользователях в текущей подписке сохраняются. После переноса необходимо настроить функции, добавленные в Microsoft 365 Business Premium.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Различия между Office 365 E3 и Microsoft 365 Бизнес Премиум

В этой таблице показаны различия между Microsoft 365 Бизнес Премиум и Office 365 E3.

| Функция    | Поддержка в Microsoft 365 Бизнес Премиум    | Поддержка в Office 365 E3 | 
|:-------|:-----|:-----|
| **Локальная среда**        | | | 
| Приложения Office<sup>1</sup>    | Приложения Microsoft 365 для бизнеса    | Приложения Microsoft 365 для предприятий | 
| **Приложения облачной производительности**        | | | 
| Exchange Online и Outlook    | Ограничение хранения 50 ГБ на почтовый ящик и неограниченное архивация на базе Exchange Online    | Ограничение на хранение 100 ГБ на почтовый ящик и неограниченные архивация на базе Exchange Online | 
| Teams    | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | ![Включено с Office 365 E3](../media/check-mark.png) | 
| OneDrive для бизнеса    | Ограничение хранения 1 ТБ на пользователя    | Без ограничений | 
| Yammer, SharePoint Online, Planner, Stream    | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | ![Включено с Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | ![Включено с Office 365 E3](../media/check-mark.png) | 
| MileIQ    | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | | 
| **Защита от угроз**        | | | 
| Defender для Office 365 (план 1) | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | Не включено, но может быть добавлено в | 
| **управление удостоверениями;**        | | | 
| Сброс пароля самообслуживления для гибридных учетных записей Azure Active Directory (Azure AD), многофакторной проверки подлинности Azure AD (MFA), условного доступа, списания паролей для идентификаторов локального доступа|     ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    |  | 
| **Управление устройствами и приложениями**        | | |
| Microsoft Intune, Windows AutoPilot|     ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    |  |
| Активация совместно используемого компьютера|     ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | ![Включено с Office 365 E3](../media/check-mark.png)| 
| Обновление прав на Windows 10 Pro с лицензий Win 7/8.1 Pro|     ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    || 
| **Защита информации**        | | |
|Защита от потери данных в Office 365|    ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)|![Включено с Office 365 E3](../media/check-mark.png)|
|План защиты информации Azure 1, правоприменительство BitLocker|![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)||
|План защиты информации Azure 1, метки конфиденциальности|![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)||
|**Лицензия клиентского доступа (права CAL)**|||
|Корпоративный пакет CAL (Exchange, SharePoint, Skype)||![Включено с Office 365 E3](../media/check-mark.png)|

<sup>1</sup> Версия Microsoft 365 Бизнес Премиум приложений Office не включает активацию тома с помощью групповой политики, телеметрии приложений, элементов управления обновлениями, сравнения электронных таблиц и запросов или бизнес-аналитики.

## <a name="migration"></a>Миграция

Чтобы перенести подписку, [](../commerce/subscriptions/change-plans-manually.md) см. инструкции по смене планов вручную, если вы хотите переместить несколько человек в Microsoft 365 Business Premium. Вы также можете [обновить](../commerce/subscriptions/upgrade-to-different-plan.md)всех автоматически или работать с партнером, чтобы переместить подписку на E3 и лицензии на подписку Microsoft 365 Бизнес Премиум.
В следующих разделах описываются изменения, которые необходимо внести, если таковые есть, и то, что можно сделать после миграции.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Конфигурация и данные подписки на Office 365 E3
Вам не нужно вносить изменения в текущую подписку или данные перед миграцией, включающие:

- Конфигурация подписки, например записи DNS и доменные имена.
- Учетные записи пользователей и групп и параметры проверки подлинности, такие как многофакторная проверка подлинности или политики условного доступа.
- Конфигурации служб производительности и их данные, такие как teams, почтовые ящики Exchange Online, сайты SharePoint Online, папки OneDrive для бизнеса и записные книжки OneNote.
- Приложения Office будут масштабироваться автоматически. Современное лицензирование Office 365 проверяет назначение лицензии пользователя каждые 72 часа и преобразует приложения Office в версию, которая соответствует подписке пользователя.

### <a name="windows-10"></a>Windows 10

Если windows еще не в обновлении Windows Pro Creator, обновите их [до Обновления создателей Windows Pro.](upgrade-to-windows-pro-creators-update.md)

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Настройка политик для защиты пользовательских устройств и файлов

> [!NOTE]
> Если вы настроили политики и устройства MDM Office 365, эти устройства будут перечислены на странице **Устройства** в центре администрирования Microsoft 365. Все политики, которые вы создали, будут показываться в списке классических политик на портале [Intune.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)

После присвоения лицензий Microsoft 365 Business Premium можно начать защищать устройства и файлы пользователей.

Если вы обновили всех в вашей организации до Microsoft 365 Business Premium, вы увидите мастера настройки на домашней странице и сможете выполнять настройку [Microsoft 365 Business Premium](set-up.md) в действиях мастера настройки для защиты файлов и мобильных устройств.

Вы также можете выполнить эти действия на странице Устройства:
  
1. В центре администрирования в левом nav перейдите к **политикам устройств.** \> 
    
2. На странице **Политики устройства** выберите **Добавить**.
    
3. В области **Добавить политику** удайте политику имя, а затем выберите тип **политики** из отсея. 
    
     Можно настроить политики приложений для защиты файлов на устройствах Android и iPhone, а также Windows 10, а также настроить политики конфигурации устройств для устройств Windows 10, которые принадлежат компании. Подробные сведения см. в следующих ссылках:
    
  - [Настройка параметров защиты приложений для устройств с Android и iOS](app-protection-settings-for-android-and-ios.md)
    
  - [Настройка параметров защиты приложений для устройств с Windows 10](protection-settings-for-windows-10-devices.md)
    
  - [Настройка параметров защиты устройств для пк с Windows 10](protection-settings-for-windows-10-pcs.md)
  
4. После того как вы настроите политики, вы и ваши сотрудники сможете настроить устройства:
    
  - Настройка [устройств Windows для пользователей Microsoft 365 Business Premium](set-up-windows-devices.md) для действий для устройств Windows. 
    
  - Настройка [мобильных устройств для пользователей Microsoft 365 Business Premium](set-up-mobile-devices.md) для действий для android-телефонов и iPhone. 
  
### <a name="mailbox-size"></a>Размер почтового ящика

Microsoft 365 Business Premium имеет ограничение хранилища на 50 ГБ, так как использует Exchange Online Plan 1. При миграции в Microsoft 365 Business Premium, если количество пользователей превышает 50 ГБ хранилища почтовых ящиков, рекомендуется назначить этому пользователю план Exchange Online Plan 2 и удалить план Exchange Online Plan 1, так как назначение обоих нецелесообразны.


### <a name="threat-protection"></a>Защита от угроз

После миграции в Microsoft 365 Бизнес Премиум у вас есть Defender для Office 365. Обзор [см. в обзоре Microsoft Defender для Office 365.](../security/office-365-security/defender-for-office-365.md) Чтобы настроить, см. [в](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)этой ссылке настройка безопасных ссылок, [](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)настройка безопасных вложений и настройка защиты от фишинга в Defender для Office [365.](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)

### <a name="sensitivity-labels"></a>Метки конфиденциальности

Чтобы начать использовать метки чувствительности, [см.](../compliance/sensitivity-labels.md) обзор меток чувствительности и создание и управление видео [меток чувствительности.](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)
