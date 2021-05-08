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
description: Узнайте о Microsoft 365 для бизнеса, его настройка и подготовка устройств и компьютеров пользователей для обеспечения их защиты Microsoft 365 для бизнеса.
ms.openlocfilehash: cc54147e75a27fbb93255d6f706b4f9044c75858
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245131"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Начало работы с Microsoft 365 для бизнеса

## <a name="what-is-microsoft-365-for-business"></a>Что Microsoft 365 для бизнеса

Microsoft 365 для бизнеса — это полный набор инструментов производительности и совместной работы, таких как Outlook, Word, Excel и другие продукты Office, которые всегда в курсе. Вы можете защитить свои файлы на всех устройствах iOS, Android и Windows 10 с безопасностью корпоративного уровня, которая проста в управлении.

Просмотрите это видео для краткого обзора Microsoft 365 для бизнеса.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 для бизнеса рассчитано на до 300 лицензий. Если вам нужно больше лицензий, см. Документацию [Microsoft 365 корпоративный](../enterprise/index.yml) для получения дополнительной информации. 
  
## <a name="get-microsoft-365-for-business"></a>Получить Microsoft 365 для бизнеса

- Если у вас есть партнер, они получат Microsoft 365 для бизнеса: получите Microsoft 365 [бизнеса из Центра](get-microsoft-365-business.md)партнеров Майкрософт .
    
- Если у вас нет партнера и вы хотите получить Microsoft 365 для бизнеса, вы можете [купить его здесь](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-for-business"></a>Настройка Microsoft 365 для бизнеса

 **Обзор Microsoft 365 для набора бизнес-услуг**
  
На следующей схеме описывается, как администраторы Microsoft 365 для бизнеса. В нем также описываются действия по подготовке Windows компьютеров для Microsoft 365 для бизнеса. Вы также можете добавить новые устройства в центре администрирования Microsoft 365 с [помощью Windows AutoPilot.](add-autopilot-devices-and-profile.md) Вы можете использовать AutoPilot для настройки и предварительной настройки новых устройств, чтобы они были готовы к продуктивному использованию, как только пользователь впишется в Microsoft 365 для бизнес-учетных данных.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Просмотрите это видео, чтобы просмотреть Microsoft 365 для бизнес-настройки.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Если это видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](../business-video/index.yml).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1. Настройка Microsoft 365 для бизнеса (Admin)

Во входе [Microsoft 365 центр администрирования](https://portal.office.com/adminportal/home) с глобальными учетными данными администратора и выполните следующие действия по Microsoft 365 для бизнеса. 
  
1. [Необходимые условия для защиты данных на устройствах с Microsoft 365 для бизнеса](pre-requisites-for-data-protection.md)
    
    Сначала ознакомьтесь с необходимыми условиями, чтобы убедиться, что ваши устройства готовы Microsoft 365 для бизнеса.
    
2. [Используйте мастер установки для настройки Microsoft 365 для бизнеса](set-up.md)
    
    Если вы постоянно переходите из локального Active **Directory** в облако, вы можете перейти в центр администрирования Microsoft 365 и использовать мастер установки, чтобы вручную добавлять пользователей, или вы можете синхронизироваться с Azure AD Подключение. Это можно сделать двумя способами: 
    
    - Если у вас также есть сервер Exchange 2010, Exchange 2013 или Exchange 2016 г., вы можете использовать минимальный гибрид для быстрой миграции Exchange почтовых ящиков в [Microsoft 365](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate). Минимальные гибридные действия включают разовую синхронизацию пользователей с Azure AD и миграцию электронной почты из локального в облако. После завершения миграции электронной почты синхронизация каталогов автоматически отключается при использовании этого метода.
    
    - Используйте мастер синхронизации каталогов, чтобы синхронизировать пользователей с облаком. Выполните действия в [настройках](../enterprise/set-up-directory-synchronization.md) синхронизации каталогов для Microsoft 365 для завершения этого процесса. После синхронизации пользователей с облаком необходимо отключить синхронизацию каталогов для [Microsoft 365.](../enterprise/turn-off-directory-synchronization.md)
    
    Вы также должны предоставить каждому пользователю, который был добавлен таким образом лицензию, чтобы Microsoft 365 для бизнеса. Это можно сделать в мастере [установки или](set-up.md) назначить [лицензии пользователям.](../admin/manage/assign-licenses-to-users.md)
    
### <a name="2-prepare-mobile-devices"></a>2. Подготовка мобильных устройств

Следуйте шагам в настройках мобильных устройств для Microsoft 365 для бизнес-Office приложений на устройствах и убедитесь, что они Microsoft 365 для бизнеса. [](set-up-mobile-devices.md) 
  
### <a name="3-prepare-pcs"></a>3. Подготовка компьютеров

Администраторы могут предварительно выбрать параметры для новых компьютеров Windows 10 с помощью [Windows AutoPilot](add-autopilot-devices-and-profile.md). Пользователи могут настроить существующие или Windows 10 устройства, следуя шагам в этом разделе: Настройка Windows компьютеров для Microsoft 365 [для бизнес-пользователей](set-up-windows-devices.md). Для существующих устройств пользователи могут **дополнительно перемещать** файлы [в OneDrive для бизнеса.](move-files-to-onedrive.md) Они также могут использовать сторонние средства для перемещения файлов, связанных с Windows профилем, в OneDrive.
  
Если организация использует Windows Server Active Directory на локальной основе, вы можете настроить Microsoft 365 для бизнеса для защиты Windows 10 устройств, сохраняя при этом доступ к локальным ресурсам, которые требуют локальной проверки подлинности. Выполните действия в [включить устройства, Windows 10 с](manage-windows-devices.md) помощью Microsoft 365 для бизнеса, чтобы настроить это. Этот метод является предпочтительным, и устройства в этом состоянии называются гибридными устройствами **Azure AD.** 
  
Если вы сохраните локальный Active Directory, содержащий некоторые локальные ресурсы (например, файловые акции и принтеры), вы можете предоставить своим устройствам **Azure AD-присоединенный** доступ к этим ресурсам, следуя указанным ниже шагам: доступ к локальным ресурсам с устройства [Azure AD](access-resources.md)в Microsoft 365 для бизнеса .
  
  
## <a name="contact-support"></a>Обращение в службу поддержки

 **Если вам нужно обратиться в службу поддержки:**
  
- Обратитесь к своему партнеру.
    
- В качестве Microsoft 365 для администратора бизнеса у вас есть доступ к нашей группе поддержки клиентов: поддержка контактов для бизнес-продуктов **[— справка администратора](../admin/contact-support-for-business-products.md)**
    
## <a name="related-content"></a>См. также:

[Microsoft 365 для бизнес-документации и ресурсов](./index.yml)
  
[Управление Microsoft 365 для бизнеса](manage.md)[Миграция в Microsoft 365 для бизнеса](migrate-to-microsoft-365-business.md)

[Обучающие видеоролики по Microsoft 365 для бизнеса](../business-video/index.yml)