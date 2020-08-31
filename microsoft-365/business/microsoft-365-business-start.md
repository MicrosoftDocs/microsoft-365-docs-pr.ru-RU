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
description: Узнайте о Microsoft 365 для бизнеса, о том, как настроить его и как подготовить устройства и компьютеры пользователей, чтобы убедиться, что они защищены Microsoft 365 для бизнеса.
ms.openlocfilehash: ec50036f589cfd8497b0e7e9af6519b30d25dcd3
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306496"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Начало работы с Microsoft 365 для бизнеса

## <a name="what-is-microsoft-365-for-business"></a>Что такое Microsoft 365 для бизнеса

Microsoft 365 для бизнеса — это комплексный набор средств для совместной работы и совместной работы, таких как Outlook, Word, Excel и другие продукты Office, которые всегда актуальны. Вы можете защитить свои рабочие файлы на всех устройствах с iOS, Android и Windows 10 с помощью безопасности корпоративного уровня, который легко управлять.

Просмотрите это видео, чтобы получить краткий обзор Microsoft 365 для бизнеса.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 для бизнеса предназначено для лицензий на 300. Если вам нужно больше лицензий, см. Документацию [Microsoft 365 корпоративный](https://go.microsoft.com/fwlink/p/?linkid=860986) для получения дополнительной информации. 
  
## <a name="get-microsoft-365-for-business"></a>Получение Microsoft 365 для бизнеса

- Если у вас есть партнер, он получит Microsoft 365 для бизнеса: [Получение microsoft 365 для бизнеса из центра партнеров Майкрософт](get-microsoft-365-business.md).
    
- Если у вас нет партнера и вы хотите получить Microsoft 365 для бизнеса, вы можете [приобрести его здесь](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-for-business"></a>Настройка Microsoft 365 для бизнеса

 **Общие сведения о настройке Microsoft 365 для бизнес-приложений**
  
На следующей схеме показано, как администраторы настроили Microsoft 365 для бизнеса. Здесь также описываются действия по подготовке компьютеров с Windows для Microsoft 365 для бизнеса. Вы также можете добавлять новые устройства в центре администрирования Microsoft 365 с помощью [Windows автопилота](add-autopilot-devices-and-profile.md). С помощью автопилота можно настроить и предварительно настроить новые устройства, чтобы они были готовы к эффективному использованию, как только пользователь войдет в систему с помощью учетных данных Microsoft 365 для бизнеса.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

В этом видеоролике приводится обзор программы установки Microsoft 365 для бизнеса.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Если этот видеоролик помог вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: Настройка Microsoft 365 для бизнеса (администратор)

Войдите в [центр администрирования microsoft 365](https://portal.office.com/adminportal/home) с помощью учетных данных глобального администратора и выполните указанные ниже действия, чтобы настроить Microsoft 365 для бизнеса. 
  
1. [Необходимые условия для защиты данных на устройствах с помощью Microsoft 365 для бизнеса](pre-requisites-for-data-protection.md)
    
    Сначала ознакомьтесь с предварительными условиями, чтобы убедиться, что ваши устройства готовы к работе с Microsoft 365 для бизнеса.
    
2. [Использование мастера установки для настройки Microsoft 365 для бизнеса](set-up.md)
    
    Если вы **безвозвратно переходите из локальной службы Active Directory в облако**, вы можете перейти в центр администрирования Microsoft 365 и использовать мастер установки для добавления пользователей вручную или выполнять однократную синхронизацию с Azure AD Connect. Это можно сделать двумя способами: 
    
    - Если у вас также есть сервер Exchange 2010, Exchange 2013 или Exchange 2016, вы можете [использовать минимальную гибридную среду для быстрой миграции почтовых ящиков Exchange в Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate). Минимальными этапами гибридного развертывания являются однократная синхронизация пользователей с Azure AD и миграция электронной почты из локальной среды в облако. После завершения миграции электронной почты при использовании этого метода Синхронизация службы каталогов автоматически отключается.
    
    - Используйте мастер синхронизации каталогов для синхронизации пользователей с облаком. Выполните действия, описанные в статье [Настройка синхронизации каталогов для Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) , чтобы завершить этот процесс. После синхронизации пользователей с облаком необходимо [Отключить синхронизацию службы каталогов для Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/turn-off-directory-synchronization).
    
    Кроме того, вам потребуется предоставить каждому пользователю, который был добавлен таким образом, как лицензия на Microsoft 365 для бизнеса. Это можно сделать в [мастере установки](set-up.md) или [назначить лицензии пользователям](../admin/manage/assign-licenses-to-users.md).
    
### <a name="2-prepare-mobile-devices"></a>2: Подготовка мобильных устройств

Выполните действия, описанные в статье [Настройка мобильных устройств для microsoft 365](set-up-mobile-devices.md) , чтобы пользователи могли установить приложения Office на устройствах и убедиться, что они защищены корпорацией Майкрософт 365 для бизнеса. 
  
### <a name="3-prepare-pcs"></a>3: подготовка компьютеров

Администраторы могут предварительно выбрать параметры для новых компьютеров с Windows 10 с помощью [Windows автопилота](add-autopilot-devices-and-profile.md). Пользователи могут настраивать существующие или новые устройства с Windows 10, выполнив действия, описанные в этой статье: [Настройка компьютеров с Windows для Microsoft 365 для бизнеса](set-up-windows-devices.md). В **случае существующих устройств пользователи могут** [перемещать файлы в OneDrive для бизнеса](move-files-to-onedrive.md). Кроме того, они могут использовать сторонние средства для перемещения файлов, связанных с профилем Windows, в OneDrive.
  
Если ваша организация использует локальную службу Windows Server Active Directory, вы можете настроить Microsoft 365 для бизнеса, чтобы защитить устройства с Windows 10, сохраняя доступ к локальным ресурсам, требующим локальной проверки подлинности. Выполните действия, описанные в разделе " [Включение устройств, присоединенных к домену" с Windows 10, для управления в Microsoft 365 для бизнеса](manage-windows-devices.md) , чтобы настроить его. Этот метод предпочтителен, и устройства в этом состоянии называются **гибридными подключенными устройствами Azure AD**. 
  
Если вы сохранили локальную службу Active Directory, которая содержит некоторые локальные ресурсы (например, файловые ресурсы и принтеры), вы можете предоставить **подключенным устройствам Azure AD** доступ к этим ресурсам, выполнив действия, описанные здесь: [доступ к локальным ресурсам из устройства, подключенного к Azure AD, в Microsoft 365 для бизнеса](access-resources.md).
  
  
## <a name="contact-support"></a>Обратитесь в службу поддержки

 **Если вам нужно обратиться в службу поддержки:**
  
- Обратитесь к своему партнеру.
    
- Как администратор Майкрософт 365 для бизнеса, у вас есть доступ к группе поддержки клиентов: ** [обратитесь в службу поддержки для бизнеса: Справка для администраторов](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)**
    
## <a name="see-also"></a>См. также

[Документация и ресурсы Microsoft 365 для бизнеса](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
Перенесите [microsoft 365 для бизнеса](manage.md)[в Microsoft 365 для бизнеса](migrate-to-microsoft-365-business.md)

[Обучающие видеоролики по Microsoft 365 для бизнеса](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) 
