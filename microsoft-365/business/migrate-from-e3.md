---
title: Миграция в Microsoft 365 бизнес из Office 365 E3
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
description: Если у вас Office 365 E3 подписка, но не более 300 сотрудников, подумайте о переходе на Microsoft 365 бизнес премиум.
ms.openlocfilehash: c1b4da07b3bf28cce1a48424ab45cde6ea54d367
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394178"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Перенос с Office 365 E3 на Microsoft 365 бизнес премиум

Microsoft 365 бизнес премиум имеет все необходимое для вашего малого бизнеса, сочетая лучшие в своем классе приложения с облачной производительностью с простым управлением устройствами и безопасностью. Если у вас в настоящее время Office 365 E3 подписка, но не более 300 сотрудников, рассмотрите возможность Microsoft 365 бизнес премиум дополнительных функций безопасности.

Миграция проста: сначала переключаются лицензии, и все данные и сведения о пользователях в текущей подписке сохраняются. После переноса необходимо настроить функции, добавленные в Microsoft 365 бизнес премиум.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Различия между Office 365 E3 и Microsoft 365 бизнес премиум

В этой таблице показаны различия между Microsoft 365 бизнес премиум и Office 365 E3.

| Функция    | Поддержка в Microsoft 365 бизнес премиум    | Поддержка в Office 365 E3 |
|:-------|:-----|:-----|
| **Локальная архитектура**        | | |
| Office приложения<sup>1</sup>    | Приложения Microsoft 365 для бизнеса    | Приложения Microsoft 365 для предприятий |
| **Приложения облачной производительности**        | | |
| Exchange Online и Outlook    | Ограничение хранения 50 ГБ на почтовый ящик и неограниченное Exchange Online Archiving    | Ограничение хранения 100 ГБ на почтовый ящик и неограниченное Exchange Online Archiving |
| Teams    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Office 365 E3](../media/check-mark.png) | 
| OneDrive для бизнеса    | Ограничение хранения 1 ТБ на пользователя    | Без ограничений | 
| Yammer, SharePoint Online, Planner, Stream    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Office 365 E3](../media/check-mark.png) |
| **Защита от угроз**        | | |
| Defender для Office 365 (план 1) | ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | Не включено, но может быть добавлено в |
| **управление удостоверениями;**        | | |
| Сброс пароля самообслуживления для гибридных учетных записей Azure Active Directory (Azure AD), многофакторной проверки подлинности Azure AD (MFA), условного доступа, списания паролей для идентификаторов локального доступа|     ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    |  |
| **Управление устройствами и приложениями**        | | |
| Microsoft Intune, Windows AutoPilot|     ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    |  |
| Активация совместно используемого компьютера|     ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    | ![Включено в Office 365 E3](../media/check-mark.png)| 
| Обновление прав на Windows 10 Pro из лицензий Win 7/8.1 Pro|     ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)    ||
| **Защита информации**        | | |
|Защита от потери данных в Office 365|    ![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)|![Включено в Office 365 E3](../media/check-mark.png)|
|План защиты информации Azure 1, правоприменительство BitLocker|![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)||
|План защиты информации Azure 1, метки конфиденциальности|![Включено в Microsoft 365 бизнес премиум](../media/check-mark.png)||
|**Лицензия клиентского доступа (права CAL)**|||
|Enterprise Cal Suite (Exchange, SharePoint, Skype)||![Включено в Office 365 E3](../media/check-mark.png)|

<sup>1</sup> Microsoft 365 бизнес премиум версии Office не включает активацию тома с помощью групповой политики, телеметрии приложений, элементов управления обновлениями, сравнения электронных таблиц и запросов или бизнес-аналитики.

## <a name="migration"></a>Миграция

Чтобы перенести подписку, см. в инструкциях [Поменяйте](../commerce/subscriptions/change-plans-manually.md) планы вручную, если вы хотите переместить несколько Microsoft 365 бизнес премиум. Вы также можете [обновить](../commerce/subscriptions/upgrade-to-different-plan.md)всех автоматически или работать с партнером, чтобы переместить подписку на E3 и лицензии на Microsoft 365 бизнес премиум подписку.
В следующих разделах описываются изменения, которые необходимо внести, если таковые есть, и то, что можно сделать после миграции.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 E3 конфигурации подписки и данных
Вам не нужно вносить изменения в текущую подписку или данные перед миграцией, включающие:

- Конфигурация подписки, например записи DNS и доменные имена.
- Учетные записи пользователей и групп и параметры проверки подлинности, такие как многофакторная проверка подлинности или политики условного доступа.
- Конфигурации служб производительности и их данные, такие как Teams, Exchange Online почтовые ящики, сайты SharePoint Online, OneDrive для бизнеса папок и OneNote блокноты.
- Office приложения будут масштабироваться автоматически. Office 365 лицензирование проверяет назначение лицензии пользователя каждые 72 часа и преобразует Office приложения в версию, которая соответствует подписке пользователя.

### <a name="windows-10"></a>Windows 10

Если ваши Windows еще не Windows Pro обновления Создателя, обновите их до [Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Настройка политик для защиты пользовательских устройств и файлов

> [!NOTE]
> Если вы настроили Office 365 MDM-политики и устройства, эти устройства будут перечислены на странице **Устройства** в Центр администрирования Microsoft 365. Все политики, которые вы создали, будут показываться в списке классических политик на портале [Intune.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)

После присвоения лицензий Microsoft 365 бизнес премиум вы можете начать защищать устройства и файлы пользователей.

Если вы обновили все Microsoft 365 бизнес премиум организации, вы увидите мастера настройки на домашней странице [](set-up.md) и сможете следовать за настройками Microsoft 365 бизнес премиум в действиях мастера установки для защиты файлов и мобильных устройств.

Вы также можете выполнить эти действия на странице Устройства:
  
1. В центре администрирования в левом nav перейдите к **политикам устройств.** \> 

2. На странице **Политики устройства** выберите **Добавить**.

3. В области **Добавить политику** удайте политику имя, а затем выберите тип **политики** из отсея.

     Можно настроить политики приложений для защиты файлов на устройствах Android и iPhone, а также Windows 10, а также настроить политики конфигурации устройств для устройств, Windows 10 устройств. Подробные сведения см. в следующих ссылках:

  - [Настройка параметров защиты приложений для устройств с Android и iOS](app-protection-settings-for-android-and-ios.md)

  - [Настройка параметров защиты приложений для устройств с Windows 10](protection-settings-for-windows-10-devices.md)

  - [Установите параметры защиты устройств для Windows 10 ПК](protection-settings-for-windows-10-pcs.md)
  
4. После того как вы настроите политики, вы и ваши сотрудники сможете настроить устройства:

  - См. [в Windows устройств для Microsoft 365 бизнес премиум для](set-up-windows-devices.md) действий для Windows устройств. 

  - Настройка [мобильных устройств для Microsoft 365 бизнес премиум для](set-up-mobile-devices.md) действий для android-телефонов и iPhone. 
  
### <a name="mailbox-size"></a>Размер почтового ящика

Microsoft 365 бизнес премиум имеет ограничение хранилища в 50 ГБ, так как Exchange Online 1. При переносе в Microsoft 365 бизнес премиум, если объем хранилища почтовых ящиков превышает 50 ГБ, рекомендуется назначить этому пользователю Exchange Online Plan 2 и удалить Exchange Online Plan 1, так как назначение обоих нецелесообразны.

### <a name="threat-protection"></a>Защита от угроз

После переноса в Microsoft 365 бизнес премиум у вас есть Defender для Office 365. Обзор [см. в Office 365](../security/office-365-security/defender-for-office-365.md) Microsoft Defender. Чтобы настроить, см. в Сейф [ссылки,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa) [Сейф](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)вложения и настройка защиты от фишинга в [Defender для Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).

### <a name="sensitivity-labels"></a>Метки конфиденциальности

Чтобы начать использовать метки чувствительности, [см.](../compliance/sensitivity-labels.md) обзор меток чувствительности и создание и управление видео [меток чувствительности.](../business-video/create-sensitivity-labels.md)

## <a name="related-content"></a>См. также:

[Изменение планов вручную](../commerce/subscriptions/change-plans-manually.md) (статья)\
[Обновление Windows устройств до Windows 10 Pro](upgrade-to-windows-pro-creators-update.md) (видео)\
[Установите параметры защиты приложений для устройств Android или iOS](app-protection-settings-for-android-and-ios.md) (статья)\
[Установка или изменение параметров](protection-settings-for-windows-10-devices.md) защиты приложений для Windows 10 устройств (статья)\
[]

