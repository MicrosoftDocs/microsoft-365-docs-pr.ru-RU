---
title: Начало работы с Microsoft 365 для бизнеса
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Узнайте о Microsoft 365 для бизнеса, ее настройках и подготовке устройств и компьютеров пользователей, чтобы обеспечить их защиту с помощью Microsoft 365 для бизнеса.
ms.openlocfilehash: ec50036f589cfd8497b0e7e9af6519b30d25dcd3
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306496"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Начало работы с Microsoft 365 для бизнеса

## <a name="what-is-microsoft-365-for-business"></a>Что такое Microsoft 365 для бизнеса

Microsoft 365 для бизнеса — это комплексный набор средств для повышения производительности и совместной работы, таких как Outlook, Word, Excel и другие продукты Office, которые всегда в курсе. Вы можете защитить свои файлы на всех устройствах с iOS, Android и Windows 10 с помощью средств безопасности корпоративного уровня, которые легко управлять.

Посмотрите это видео для краткого обзора Microsoft 365 для бизнеса.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 для бизнеса предназначен для получения до 300 лицензий. Если вам нужно больше лицензий, см. Документацию [Microsoft 365 корпоративный](https://go.microsoft.com/fwlink/p/?linkid=860986) для получения дополнительной информации. 
  
## <a name="get-microsoft-365-for-business"></a>Получите Microsoft 365 для бизнеса

- Если у вас есть партнер, он получит Microsoft 365 для бизнеса: получите [Microsoft 365](get-microsoft-365-business.md)для бизнеса из Центра партнеров Майкрософт.
    
- Если у вас нет партнера и вы хотите получить Microsoft 365 для бизнеса, вы можете [приобрести его здесь.](https://www.microsoft.com/microsoft-365/business)
    
## <a name="set-up-microsoft-365-for-business"></a>Настройка Microsoft 365 для бизнеса

 **Обзор набора Microsoft 365 для бизнеса**
  
На следующей схеме описано, как администраторы могут настроить Microsoft 365 для бизнеса. В ней также описаны действия по подготовке компьютеров с Windows для Microsoft 365 для бизнеса. Вы также можете добавить новые устройства в Центр администрирования Microsoft 365 с [помощью Windows AutoPilot.](add-autopilot-devices-and-profile.md) Вы можете использовать AutoPilot для настройки и предварительной настройки новых устройств, чтобы они были готовы к продуктивному использованию, как только пользователь войду с помощью своих учетных данных Microsoft 365 для бизнеса.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Просмотрите это видео, чтобы просмотреть обзор настройки Microsoft 365 для бизнеса.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Если это видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1. Настройка Microsoft 365 для бизнеса (администратор)

Во sign in to [Microsoft 365 admin center](https://portal.office.com/adminportal/home) with your global admin credentials, and complete the following steps to set up Microsoft 365 for business. 
  
1. [Необходимые условия для защиты данных на устройствах с помощью Microsoft 365 для бизнеса](pre-requisites-for-data-protection.md)
    
    Сначала ознакомьтесь с предварительными условиями, чтобы убедиться, что ваши устройства готовы к Microsoft 365 для бизнеса.
    
2. [Настройка Microsoft 365 для бизнеса с помощью мастера настройки](set-up.md)
    
    Если вы навсегда переходите из локальной службы **Active Directory** в облако, вы можете перейти в Центр администрирования Microsoft 365 и воспользоваться мастером настройки для добавления пользователей вручную или синхронизироваться с Azure AD Connect. Это можно сделать двумя способами: 
    
    - Если у вас также есть сервер Exchange 2010, Exchange 2013 или Exchange 2016, вы можете использовать минимальный гибридный вариант для быстрого переноса почтовых ящиков Exchange в [Microsoft 365.](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate) Минимальные гибридные действия включают одновую синхронизацию пользователей с Azure AD и миграцию электронной почты из локальной организации в облако. После завершения миграции электронной почты синхронизация службы каталогов автоматически отключается при использовании этого метода.
    
    - Используйте мастер синхронизации каталогов для синхронизации пользователей с облаком. Выполните действия, которые необходимо выполнить в процедуре "Настройка синхронизации службы [каталогов для Microsoft 365".](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) После синхронизации пользователей с облаком необходимо отключить синхронизацию службы каталогов [для Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/turn-off-directory-synchronization)
    
    Кроме того, каждому пользователю, добавленным таким образом, необходимо предоставить лицензию на Microsoft 365 для бизнеса. Это можно сделать в мастере [установки или](set-up.md) назначить [лицензии пользователям.](../admin/manage/assign-licenses-to-users.md)
    
### <a name="2-prepare-mobile-devices"></a>2. Подготовка мобильных устройств

Чтобы установить приложения Office на устройства и убедиться, что они защищены с помощью Microsoft 365 для бизнеса, выполните действия, которые необходимо предпринять в области "Настройка мобильных устройств для [пользователей Microsoft 365](set-up-mobile-devices.md) для бизнеса". 
  
### <a name="3-prepare-pcs"></a>3. Подготовка компьютеров

Администраторы могут предварительно выбрать параметры для новых компьютеров с Windows 10 с помощью [Windows AutoPilot.](add-autopilot-devices-and-profile.md) Пользователи могут настроить свои существующие или новые устройства с Windows 10, следуя шагам из этой темы: "Настройка компьютеров с Windows для [пользователей Microsoft 365 для бизнеса".](set-up-windows-devices.md) На существующих устройствах пользователи **могут при желании** [перемещать файлы в OneDrive для бизнеса.](move-files-to-onedrive.md) Они также могут использовать сторонние средства для перемещения файлов, связанных с профилем Windows, в OneDrive.
  
Если в вашей организации используется локализованная служба Windows Server Active Directory, вы можете настроить Microsoft 365 для бизнеса для защиты устройств с Windows 10, сохранив при этом доступ к локальным ресурсам, которые требуют локальной проверки подлинности. Чтобы настроить эту возможность, выполните действия, необходимые для того, чтобы устройства с Windows 10, которые присоединились к домену, могли управляться [Microsoft 365](manage-windows-devices.md) для бизнеса. Этот метод предпочтительный, и устройства в этом состоянии называются гибридными устройствами, **которые присоединились к Azure AD.** 
  
Если вы сохраняете локализованную службу Active Directory, которая содержит некоторые локальные ресурсы (например, файловые ресурсы и принтеры), вы можете предоставить устройствам, присоединенным к **Azure AD,** доступ к этим ресурсам, следуя указанным ниже шагам: доступ к локальным ресурсам с устройства, присоединенного к [Azure AD, в Microsoft 365 для бизнеса.](access-resources.md)
  
  
## <a name="contact-support"></a>Обращение в службу поддержки

 **Если вам нужно обратиться в службу поддержки:**
  
- Обратитесь к своему партнеру.
    
- Как администратор Microsoft 365 для бизнеса у вас есть доступ к нашей группе поддержки клиентов: обратитесь в службу поддержки по продуктам для бизнеса **[: справка для администраторов](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)**
    
## <a name="see-also"></a>См. также

[Документация и ресурсы по Microsoft 365 для бизнеса](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Управление миграцией Microsoft 365](manage.md)для бизнеса[на Microsoft 365 для бизнеса](migrate-to-microsoft-365-business.md)

[Обучающие видеоролики по Microsoft 365 для бизнеса](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) 
