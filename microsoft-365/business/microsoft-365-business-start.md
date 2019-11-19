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
ms.openlocfilehash: f269e970cc1ee5ba7455ea799b238db577116f09
ms.sourcegitcommit: 38934a2115d5cdeb44c7484d57be07686c6f7720
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2019
ms.locfileid: "38704122"
---
# <a name="get-started-with-microsoft-365-business"></a>Приступая к работе с Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>Что такое Microsoft 365 Бизнес

Microsoft 365 Business — это комплексный набор средств для продуктивной работы и совместной работы, таких как Outlook, Word, Excel и другие продукты Office, которые всегда актуальны. Вы можете защитить свои рабочие файлы на всех устройствах с iOS, Android и Windows 10 с помощью безопасности корпоративного уровня, который легко управлять.
  
Microsoft 365 Business предназначено для работы с лицензиями на 300. Дополнительные сведения о том, как получить дополнительные лицензии, можно найти в [статье Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) Documentation. 
  
## <a name="get-microsoft-365-business"></a>Получение Microsoft 365 бизнес

- Если у вас есть партнер, он получит Microsoft 365 бизнес: [получить microsoft 365 бизнес из центра партнеров Майкрософт](get-microsoft-365-business.md).
    
- Если у вас нет партнера и вы хотите получить Microsoft 365 бизнес, вы можете [приобрести его здесь](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Настройка Microsoft 365 бизнес

 **Обзор настройки Microsoft 365 Business Suite**
  
На следующей схеме показано, как администраторы настроили Microsoft 365 бизнес. На ней также описаны действия по подготовке компьютеров с Windows для Office 365 бизнес. Вы также можете добавлять новые устройства в центре администрирования Microsoft 365 Business с помощью [Windows автопилота](add-autopilot-devices-and-profile.md). С помощью автопилота можно настроить и предварительно настроить новые устройства, чтобы они были готовы к эффективному использованию, как только пользователь войдет с помощью учетных данных Microsoft 365 Business.
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: Настройка Microsoft 365 Business (администратор)

Войдите в [центр администрирования microsoft 365 Business](https://portal.office.com/adminportal/home) с учетными данными глобального администратора и выполните указанные ниже действия, чтобы настроить Microsoft 365 Business. 
  
1. [Необходимые условия для защиты данных на устройствах с помощью Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    Сначала ознакомьтесь с предварительными условиями, чтобы убедиться, что ваши устройства готовы к работе с Microsoft 365 Business.
    
2. [Использование мастера установки для настройки Microsoft 365 Business](set-up.md)
    
    Если вы **безвозвратно переходите из локальной службы Active Directory в облако**, вы можете перейти в центр администрирования Microsoft 365 Business и использовать мастер установки для добавления пользователей вручную или выполнять однократную синхронизацию с Azure AD Connect. Это можно сделать двумя способами: 
    
    - Если у вас также есть сервер Exchange 2010, Exchange 2013 или Exchange 2016, вы можете [использовать минимальную гибридную среду для быстрой миграции почтовых ящиков Exchange в Office 365](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). Минимальными этапами гибридного развертывания являются однократная синхронизация пользователей с Azure AD и миграция электронной почты из локальной среды в облако. После завершения миграции электронной почты при использовании этого метода Синхронизация службы каталогов автоматически отключается.
    
    - Используйте мастер синхронизации каталогов Office 365 для синхронизации пользователей с облаком. Для завершения этого процесса следуйте указаниям, приведенным в статье [Настройка синхронизации службы каталогов для Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846). После синхронизации пользователей с облаком необходимо [Отключить синхронизацию каталогов для Office 365](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    Кроме того, вам потребуется предоставить каждому пользователю, который был добавлен таким образом, как лицензия на Microsoft 365 Business. Это можно сделать в [мастере установки](set-up.md) или [назначить лицензии пользователям в Office 365 для бизнеса](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: Подготовка мобильных устройств

Выполните действия, описанные в статье [Set up Mobile Devices for microsoft 365 Business Users](set-up-mobile-devices.md) , чтобы установить приложения Office на устройствах и убедиться, что они защищены корпорацией Майкрософт 365 Business. 
  
### <a name="3-prepare-pcs"></a>3: подготовка компьютеров

Администраторы могут предварительно выбрать параметры для новых компьютеров с Windows 10 с помощью [Windows автопилота](add-autopilot-devices-and-profile.md). Пользователи могут настраивать существующие или новые устройства с Windows 10, выполнив действия, описанные в этой статье: [Настройка компьютеров с Windows для Microsoft 365 Business Users](set-up-windows-devices.md). В **случае существующих устройств пользователи могут** [перемещать файлы в OneDrive для бизнеса](move-files-to-onedrive.md). Кроме того, они могут использовать сторонние средства для перемещения файлов, связанных с профилем Windows, в OneDrive.
  
Если ваша организация использует локальную службу Windows Server Active Directory, вы можете настроить Microsoft 365 бизнес для защиты устройств с Windows 10, сохраняя доступ к локальным ресурсам, требующим локальной проверки подлинности. Выполните действия, описанные в разделе " [Включение устройств, присоединенных к домену" с Windows 10 для управления в Microsoft 365 Business](manage-windows-devices.md) , чтобы настроить. Этот метод предпочтителен, и устройства в этом состоянии называются **гибридными подключенными устройствами Azure AD**. 
  
Если вы сохранили локальную службу Active Directory, которая содержит некоторые локальные ресурсы (например, файловые ресурсы и принтеры), вы можете предоставить **подключенным устройствам Azure AD** доступ к этим ресурсам, выполнив действия, описанные здесь: [доступ к локальным ресурсам из устройства, подключенного к Azure AD, в Microsoft 365 Business](access-resources.md).
  
  
## <a name="contact-support"></a>Обратитесь в службу поддержки

 **Если вам нужно обратиться в службу поддержки:**
  
- Обратитесь к своему партнеру.
    
- Как администратор Microsoft 365 Business, у вас есть доступ к группе поддержки клиентов: ** [обратитесь в службу поддержки для бизнеса: Справка для администраторов](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="related-topics"></a>Статьи по теме
[Документы и ресурсы по Microsoft 365 Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Управление microsoft 365 бизнес](manage.md)[для миграции в Microsoft 365 бизнес](migrate-to-microsoft-365-business.md)
  

