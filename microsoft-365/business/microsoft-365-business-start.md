---
title: Начало работы с Microsoft 365 для бизнеса
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Узнайте о Microsoft 365 для бизнеса, о настройках и подготовке устройств и компьютеров пользователей для обеспечения их защиты microsoft 365 для бизнеса.
ms.openlocfilehash: 83bd2ff87683c1ad810d20658ba20f3229408968
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580101"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Начало работы с Microsoft 365 для бизнеса

## <a name="what-is-microsoft-365-for-business"></a>Что такое Microsoft 365 для бизнеса

Microsoft 365 для бизнеса — это полный набор инструментов производительности и совместной работы для бизнеса, таких как Outlook, Word, Excel и другие продукты Office, которые всегда находятся в курсе. Вы можете защитить свои файлы на всех устройствах с iOS, Android и Windows 10 с помощью безопасности корпоративного уровня, которая проста в управлении.

Просмотрите это видео для краткого обзора Microsoft 365 для бизнеса.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 для бизнеса рассчитан на до 300 лицензий. Если вам нужно больше лицензий, см. Документацию [Microsoft 365 корпоративный](../enterprise/index.yml) для получения дополнительной информации. 
  
## <a name="get-microsoft-365-for-business"></a>Получить Microsoft 365 для бизнеса

- Если у вас есть партнер, они получат Microsoft 365 для бизнеса: [получите Microsoft 365](get-microsoft-365-business.md)для бизнеса из Центра партнеров Майкрософт .
    
- Если у вас нет партнера и вы хотите получить Microsoft 365 для бизнеса, вы можете [купить его здесь](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-for-business"></a>Настройка Microsoft 365 для бизнеса

 **Обзор набора пакетов Microsoft 365 для бизнеса**
  
На следующей схеме описывается, как администраторы устанавливают Microsoft 365 для бизнеса. В нем также описываются действия по подготовке компьютеров Windows для Microsoft 365 для бизнеса. Вы также можете добавить новые устройства в центр администрирования Microsoft 365 с [помощью Windows AutoPilot.](add-autopilot-devices-and-profile.md) Вы можете использовать АвтоПилот для настройки и предварительной настройки новых устройств, чтобы они были готовы к продуктивному использованию, как только пользователь войду с учетными данными Microsoft 365 для бизнеса.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Просмотрите это видео для обзора Microsoft 365 для настройки бизнеса.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Если это видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1. Настройка Microsoft 365 для бизнеса (Admin)

Вопишитесь в центр администрирования [Microsoft 365](https://portal.office.com/adminportal/home) с глобальными учетными данными администратора и выполните следующие действия, чтобы настроить Microsoft 365 для бизнеса. 
  
1. [Необходимые условия для защиты данных на устройствах с Microsoft 365 для бизнеса](pre-requisites-for-data-protection.md)
    
    Сначала ознакомьтесь с необходимыми условиями, чтобы убедиться, что устройства готовы для Microsoft 365 для бизнеса.
    
2. [Используйте мастер установки для настройки Microsoft 365 для бизнеса](set-up.md)
    
    Если вы постоянно переходите из локального Active **Directory** в облако, вы можете перейти в центр администрирования Microsoft 365 и использовать мастер установки, чтобы добавлять пользователей вручную, или вы можете синхронизироваться с Azure AD Connect. Это можно сделать двумя способами: 
    
    - Если у вас также есть сервер Exchange 2010, Exchange 2013 или Exchange 2016, вы можете использовать минимальный гибрид для быстрой миграции почтовых ящиков Exchange в [Microsoft 365.](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate) Минимальные гибридные действия включают разовую синхронизацию пользователей с Azure AD и миграцию электронной почты из локального в облако. После завершения миграции электронной почты синхронизация каталогов автоматически отключается при использовании этого метода.
    
    - Используйте мастер синхронизации каталогов, чтобы синхронизировать пользователей с облаком. Выполните действия в настройках синхронизации [каталогов для Microsoft 365](../enterprise/set-up-directory-synchronization.md) для завершения этого процесса. После синхронизации пользователей с облаком необходимо отключить синхронизацию каталогов [для Microsoft 365.](../enterprise/turn-off-directory-synchronization.md)
    
    Вы также должны предоставить каждому пользователю, который был добавлен таким образом лицензию на Microsoft 365 для бизнеса. Это можно сделать в мастере [установки или](set-up.md) назначить [лицензии пользователям.](../admin/manage/assign-licenses-to-users.md)
    
### <a name="2-prepare-mobile-devices"></a>2. Подготовка мобильных устройств

Следуйте шагам в настройках мобильных устройств [для Microsoft 365](set-up-mobile-devices.md) для бизнес-пользователей, чтобы установить приложения Office на устройства и убедиться, что они защищены Microsoft 365 для бизнеса. 
  
### <a name="3-prepare-pcs"></a>3. Подготовка компьютеров

Администраторы могут предварительно выбрать параметры для новых компьютеров Windows 10 с помощью [Windows AutoPilot.](add-autopilot-devices-and-profile.md) Пользователи могут настроить существующие или новые устройства с Windows 10, следуя шагам в этом разделе: Настройка компьютеров Windows для [Microsoft 365 для бизнес-пользователей.](set-up-windows-devices.md) Для существующих устройств пользователи могут дополнительно **перемещать** файлы [в OneDrive для бизнеса.](move-files-to-onedrive.md) Они также могут использовать сторонние средства для перемещения файлов, связанных с профилем Windows, в OneDrive.
  
Если в организации используется локальный Windows Server Active Directory, можно настроить Microsoft 365 для бизнеса для защиты устройств Windows 10, сохраняя при этом доступ к локальным ресурсам, которые требуют локальной проверки подлинности. Следуйте шагам в [Включить устройства Windows 10,](manage-windows-devices.md) которые будут управляться Microsoft 365 для бизнеса, чтобы настроить это. Этот метод является предпочтительным, и устройства в этом состоянии называются гибридными устройствами **Azure AD.** 
  
Если вы сохраните локальный Каталог Active Directory, содержащий некоторые локальные ресурсы (например, файловые акции и принтеры), вы можете предоставить своим устройствам **Azure AD-присоединенный** доступ к этим ресурсам, следуя следующим шагам здесь: Доступ к локальным ресурсам с устройства Azure AD в [Microsoft 365 для](access-resources.md)бизнеса .
  
  
## <a name="contact-support"></a>Обратитесь в службу поддержки

 **Если вам нужно обратиться в службу поддержки:**
  
- Обратитесь к своему партнеру.
    
- В качестве администратора Microsoft 365 для бизнеса у вас есть доступ к нашей группе поддержки клиентов: поддержка контактов для бизнес-продуктов **[— справка администратора](../admin/contact-support-for-business-products.md)**
    
## <a name="see-also"></a>См. также

[Microsoft 365 для бизнес-документации и ресурсов](./index.yml)
  
[Управление Microsoft 365 для бизнеса Миграция](manage.md)[в Microsoft 365 для бизнеса](migrate-to-microsoft-365-business.md)

[Обучающие видеоролики по Microsoft 365 для бизнеса](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)