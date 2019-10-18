---
title: Приступая к работе с Microsoft 365 Business
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Узнайте, как настроить Microsoft 365 Business.
ms.openlocfilehash: ed302a79d125ffc9c6203d902f437749a5b0f8d4
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575905"
---
# <a name="get-started-with-microsoft-365-business"></a>Приступая к работе с Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>Что такое Microsoft 365 Бизнес

Microsoft 365 бизнес  это полный набор постоянно обновляемых офисных программ и средств для совместной работы, таких как Outlook, Word, Excel и другие продукты Office. Благодаря простой службе безопасности корпоративного уровня вы сможете надежно защитить свои рабочие файлы на устройствах с iOS, Android и Windows 10.
  
Microsoft 365 Business предназначено для использования до 300 лицензий, если вам требуется больше лицензий, обратитесь к разделу [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) Documentation для получения дополнительных сведений. 
  
## <a name="get-microsoft-365-business"></a>Получение Microsoft 365 бизнес

- Если у вас есть партнер, он получит Office 365 бизнес, как описано в статье [Получение Microsoft 365 Business в Центре партнеров Майкрософт](get-microsoft-365-business.md).
    
- Если у вас нет партнера и вы хотите получить Microsoft 365 бизнес, вы можете [приобрести его здесь](https://www.microsoft.com/en-us/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Настройка Microsoft 365 бизнес

 **Обзор настройки Microsoft 365 Business Suite**
  
На следующей схеме показано, как администраторы настроили Microsoft 365 бизнес. На ней также описаны действия по подготовке компьютеров с Windows для Office 365 бизнес. Вы также можете добавить новые устройства в Центре администрирования Office 365 бизнес с помощью [Windows AutoPilot](add-autopilot-devices-and-profile.md). Решение AutoPilot позволяет предварительно настраивать новые устройства, чтобы они были готовы к работе, как только пользователи выполнят вход с помощью учетных данных Office 365 бизнес.
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: Настройка Microsoft 365 Business (администратор)

Войдите в [Центр администрирования Microsoft 365 бизнес](https://portal.office.com/adminportal/home) с помощью учетных данных глобального администратора и выполните приведенные ниже инструкции по настройке Office 365 бизнес. 
  
1. [Предварительные требования для защиты данных на устройствах с помощью Microsoft 365 бизнес](pre-requisites-for-data-protection.md)
    
    Изучите эти требования, чтобы убедиться, что ваши устройства поддерживают Office 365 бизнес.
    
2. [Настройка Microsoft 365 бизнес с помощью мастера](set-up.md)
    
    Если вы **безвозвратно переходите из локальной службы Active Directory в облако**, вы можете добавить пользователей вручную в центр администрирования Microsoft 365 Business с помощью мастера установки или выполнить однократную синхронизацию с Azure AD Connect. Это можно сделать двумя способами: 
    
  - Если у вас также есть сервер Exchange 2010, Exchange 2013 или Exchange 2016, вы можете [использовать минимальную гибридную среду для быстрой миграции почтовых ящиков Exchange в Office 365](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). Она подразумевает единовременную синхронизацию пользователей с Azure AD, а также перенос электронной почты из локальной службы в облако. После завершения переноса электронной почты синхронизация службы каталогов автоматически отключается.
    
  - Для синхронизации пользователей с облаком нужно использовать мастер синхронизации службы каталогов Office 365. Для завершения этого процесса следуйте указаниям, приведенным в статье [Настройка синхронизации службы каталогов для Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846). После синхронизации пользователей с облаком нужно будет [отключить синхронизацию службы каталогов](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    Вам также нужно будет предоставить каждому пользователю, добавленному таким способом, лицензию на Microsoft 365 бизнес. Это можно сделать в [мастере установки](set-up.md)или [назначить лицензии пользователям в Office 365 для бизнеса](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: Подготовка мобильных устройств

Выполните действия, описанные в статье[Настройка мобильных устройств для microsoft 365 бизнес-пользователей](set-up-mobile-devices.md) , чтобы установить приложения Office на устройствах и убедиться в том, что они защищены корпорацией Майкрософт 365 Business. 
  
### <a name="3-prepare-pcs"></a>3: подготовка компьютеров

Администраторы могут предварительно выбрать параметры для новых устройств с Windows 10 для компьютеров с помощью [Windows автопилот](add-autopilot-devices-and-profile.md). Пользователи могут настраивать существующие или новые устройства с Windows 10, выполнив действия, описанные в этой статье: [Настройка компьютеров с Windows для Microsoft 365 Business Users](set-up-windows-devices.md). Для существующих устройств **Пользователи также могут**[перемещать файлы в OneDrive для бизнеса](move-files-to-onedrive.md). Кроме того, они могут использовать сторонние средства для перемещения файлов, связанных с профилем Windows, в OneDrive.
  
Если ваша организация использует локальную службу Windows Server Active Directory, вы можете настроить Microsoft 365 бизнес для защиты устройств с Windows 10, сохраняя доступ к локальным ресурсам, требующим локальной проверки подлинности. Выполните действия, описанные в разделе " [Включение устройств, присоединенных к домену" с Windows 10 для управления в Microsoft 365 Business](manage-windows-devices.md) , чтобы настроить. Это предпочитаемый метод и устройства в этом состоянии называются **гибридными подключенными устройствами Azure AD**. 
  
Если вы сохранили локальную службу Active Directory, которая содержит некоторые локальные ресурсы (например, файловые ресурсы и принтеры), вы можете предоставить **подключенным устройствам Azure AD** доступ к этим ресурсам, выполнив действия, описанные здесь: [доступ к локальным ресурсам из Подключенное к Azure AD устройство в Microsoft 365 Business](access-resources.md).
  
После настройки компьютеров с Windows 10 можно [автоматически установить Office](auto-install-or-uninstall-office.md) на устройствах. 
  
## <a name="contact-support"></a>Обратитесь в службу поддержки

 **Если вам нужно обратиться в службу поддержки:**
  
- Обратитесь к своему партнеру.
    
- Как администратор Microsoft 365 бизнес, у вас есть доступ к группе поддержки клиентов, ** [обратитесь в службу поддержки для бизнеса: Справка для администраторов](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="related-topics"></a>Статьи по теме
[Документы и ресурсы по Microsoft 365 Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Управление microsoft 365 бизнес](manage.md)[для миграции в Microsoft 365 бизнес](migrate-to-microsoft-365-business.md)
  

