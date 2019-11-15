---
title: Переход на Microsoft 365 Business из Office 365 E3
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
search.appverid:
- BCS160
- MET150
description: Узнайте, как перенести бизнес в Microsoft 365 Business из Office 365 E3.
ms.openlocfilehash: f624ee7ef7c00ac4d1fe413500d0cd081a156748
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640580"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a>Переход с Office 365 E3 на Microsoft 365 Бизнес 

Microsoft 365 Business имеет все необходимое для малого бизнеса, объединяя лучшие облачные приложения для продуктивной работы с использованием простого управления устройствами и обеспечения безопасности. Если у вас уже есть подписка на Office 365 E3, но не более 300 сотрудников, попробуйте перейти на Microsoft 365 Business для получения дополнительных функций безопасности.

Миграция проста: сначала можно сменить лицензии и все данные, а также сведения о пользователях в текущей подписке. После миграции вам потребуется настроить компоненты, добавленные в Microsoft 365 Business.

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a>Различия между Office 365 E3 и Microsoft 365 Бизнес

В этой таблице показаны различия между Microsoft 365 Business и Office 365 E3.

| Компонент   | Поддержка в Microsoft 365 Business | Поддержка в Office 365 E3 | 
|:-------|:-----|:-----|
| **Локальная среда**       | | | 
| Приложения Office<sup>1</sup>   | Office 365 бизнес   | Office 365 профессиональный плюс | 
| **Облачные приложения для работы**       | | | 
| Exchange Online и Outlook   | 50 ГБ дискового пространства для почтового ящика и неограниченная Архивация на базе Exchange Online   | 100 ГБ дискового пространства для почтового ящика и неограниченная Архивация на базе Exchange Online | 
| Teams | ![Входит в состав Microsoft 365 Business](./media/check-mark.png)   | ![Входит в состав Office 365 E3](./media/check-mark.png) | 
| OneDrive для бизнеса | ограничения на размер хранилища на одного пользователя (1 ТБ)   | Без ограничений | 
| Yammer, SharePoint Online, планировщик, поток    | ![Входит в состав Microsoft 365 Business](./media/check-mark.png)   | ![Входит в состав Office 365 E3](./media/check-mark.png) | 
| StaffHub  | ![Входит в состав Microsoft 365 Business](./media/check-mark.png)   | ![Входит в состав Office 365 E3](./media/check-mark.png) | 
| Диспетчер клиентов Outlook, Милеик  | ![Входит в состав Microsoft 365 Business](./media/check-mark.png)   | | 
| **Защита от угроз**     | | | 
| Office 365 Advanced Threat protection (ATP), план 1 | ![Входит в состав Microsoft 365 Business](./media/check-mark.png)  | Не включено, но его можно добавить на | 
| **управление удостоверениями;**       | | | 
| Самостоятельный сброс паролей для гибридных учетных записей Azure Active Directory (Azure AD), служба Azure Multi-Factor Authentication (MFA), условный доступ, обратная запись пароля для локальных удостоверений|    ![Входит в состав Microsoft 365 Business](./media/check-mark.png) |  | 
| **Управление устройствами и приложениями**     | | |
| Microsoft Intune, Windows для автопилота|  ![Входит в состав Microsoft 365 Business](./media/check-mark.png) |  |
| Активация совместно используемого компьютера|   ![Входит в состав Microsoft 365 Business](./media/check-mark.png) | ![Входит в состав Office 365 E3](./media/check-mark.png)| 
| Права на обновление до Windows 10 Pro из лицензий Win 7/8.1 Pro|     ![Входит в состав Microsoft 365 Business](./media/check-mark.png) || 
| **Защита информации**        | | |
|Защита от потери данных в Office 365|   ![Входит в состав Microsoft 365 Business](./media/check-mark.png)|![Входит в состав Office 365 E3](./media/check-mark.png)|
|Azure Information Protection (план 1), принудительное применение BitLocker|![Входит в состав Microsoft 365 Business](./media/check-mark.png)||
|Azure Information Protection (план 1), метки чувствительности|![Входит в состав Microsoft 365 Business](./media/check-mark.png)||
|**Лицензия клиентского доступа (права CAL)**|||
|Набор корпоративных лицензий CAL (Exchange, SharePoint, Skype)||![Входит в состав Office 365 E3](./media/check-mark.png)|

<sup>1</sup> в microsoft Office 365 бизнес версия приложений Office не включает активацию корпоративных лицензий с помощью групповой политики, телеметрии приложений, элементов управления обновления, сравнения и выполнения запросов, а также бизнес-аналитики.

## <a name="migration"></a>Миграция

Чтобы перенести свою подписку, ознакомьтесь с инструкциями, приведенными в статье [Переключение к другому плану, вручную](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually) , если вы хотите переместить всего нескольких пользователей в Microsoft 365 Business. Вы также можете [обновлять пользователей автоматически](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan)или работать с партнером, чтобы перенести подписку на E3 и лицензии на Microsoft 365 Business.
В следующих разделах описываются изменения, которые необходимо выполнить, если они есть, и действия, которые можно выполнить после миграции.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Конфигурация и данные подписки на Office 365 E3
Вам не нужно вносить никаких изменений в текущую подписку или данные перед миграцией, включая следующие:

- Конфигурация подписки, например записи DNS и доменные имена.
- Учетные записи пользователей и групп и параметры проверки подлинности, такие как многофакторная проверка подлинности или политики условного доступа.
- Конфигурации служб производительности и их данные, такие как Teams, почтовые ящики Exchange Online, сайты SharePoint Online, папки OneDrive для бизнеса и записные книжки OneNote.

### <a name="windows-10"></a>Windows 10

Если Windows не находится в обновлении Windows Pro Creator, [обновите их до версии Windows Pro](upgrade-to-windows-pro-creators-update.md)Creators.

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Настройка политик для защиты устройств и файлов пользователей

> [!NOTE]
> Если вы настроили политики и устройства для Office 365 MDM, эти устройства будут перечислены на странице " **устройства** " центра администрирования Microsoft 365. Все настроенные политики будут отображаться в списке классических политик на [портале Intune](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).

После назначения лицензий Microsoft 365 Business можно приступить к защите устройств и файлов пользователей.

Если вы обновили всех пользователей в Организации до Microsoft 365 Business, вы увидите мастер установки на домашней странице, а также можете воспользоваться инструкциями по [настройке Microsoft 365 для бизнеса в мастере установки](set-up.md) , чтобы защитить файлы и мобильные устройства.

Вы также можете выполнить следующие действия на странице "устройства":
  
1. В левой панели навигации центра администрирования перейдите к разделу **политики** **устройств** \> .
    
2. На странице " **политики устройств** " нажмите кнопку **Добавить**.
    
3. В области **Добавить политику** укажите имя политики, а затем выберите **тип политики** из раскрывающегося меню. 
    
     Вы можете настроить политики приложений для защиты файлов на устройствах с Android и iPhone, а также в Windows 10, а также настроить политики конфигурации устройств для устройств с Windows 10, принадлежащих компании. Для получения подробных сведений ознакомьтесь со следующими ссылками:
    
  - [Настройка параметров защиты приложений для устройств с Android и iOS](app-protection-settings-for-android-and-ios.md)
    
  - [Настройка параметров защиты приложений для устройств с Windows 10](protection-settings-for-windows-10-devices.md)
    
  - [Настройка параметров защиты устройств для компьютеров с Windows 10](protection-settings-for-windows-10-pcs.md)
  
4. После настройки политик вы и ваши сотрудники смогут настраивать устройства:
    
  - Пошаговые инструкции по [настройке устройств Windows для Microsoft 365 бизнес-пользователей](set-up-windows-devices.md) для устройств с Windows. 
    
  - Выполните действия, описанные в [статье Настройка мобильных устройств для пользователей Microsoft 365 Business](set-up-mobile-devices.md) для телефонов с Android и iPhone. 

### <a name="threat-protection"></a>Защита от угроз

После перехода на Microsoft 365 Business вы получите Office 365 ATP. Обзор [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) для просмотра. Чтобы настроить, ознакомьтесь со статьей [Настройка безопасных ссылок ATP](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [Настройка безопасных вложений ATP](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)и [Настройка антифишинга ATP](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).

### <a name="sensitivity-labels"></a>Метки конфиденциальности

Чтобы приступить к использованию меток конфиденциальности, ознакомьтесь со статьей [Обзор меток конфиденциальности](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) , а затем [Создайте видео метки конфиденциальности и управляйте ими](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) .
