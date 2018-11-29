---
title: Включение присоединенный к домену устройств Windows 10 для управления Microsoft 365 для бизнеса
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Узнайте, как включить 365 Майкрософт для защиты локального AD в состав Windows 10 устройств.
ms.openlocfilehash: 6e66a2c5417c9037232c1ada654d4cac3c520607
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870588"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Включение присоединенный к домену устройств Windows 10 для управления Microsoft 365 для бизнеса

Если организация использует Windows Server Active Directory в локальной, Microsoft 365 Business можно настроить для защиты устройство Windows 10, при этом обеспечивают доступ к локальным ресурсам, которые требуют проверки подлинности на локальном. Это можно настроить путем синхронизации Active Directory с Azure Active Directory, следуют регистрации устройств Windows 10 Azure AD и подача заявок на их для управления мобильного устройства с Microsoft 365 для бизнеса.
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Настройка устройств, присоединенный к домену для управления Microsoft 365 для бизнеса

Для настройки устройств присоединенный к домену организации, чтобы использовать возможности, предоставляемые Azure Active Directory в дополнение к локальной службы Active Directory, можно реализовать **гибридного Azure AD в состав устройств**. Это устройства, входящих в состав к Active Directory в локальной и Azure Active Directory. Гибридные Azure AD в состав устройств можно защищенного и управлять посредством 365 Microsoft Business... 
  
Выполните следующие действия, чтобы сделать устройство Windows 10 гибридного Azure AD в состав и управлять посредством Microsoft 365 для бизнеса.
  
1. Для синхронизации пользователей, групп и контактов из локального Active Directory в Azure Active Directory, запустите мастер синхронизации каталогов и Azure Active Directory подключение как описано в [Настройка синхронизации службы каталогов для Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
    > [!NOTE]
    > Действия полностью совпадают для Microsoft 365 для бизнеса. 
  
2. Прежде чем завершить шаг 3, чтобы включить устройств Windows 10 для гибридных присоединился к Azure AD, необходимо убедитесь в том, что выполняются следующие требования:
    
   - Последние версии Azure AD подключения.
    
   - Подключение Azure AD синхронизировано все объекты-компьютеры устройств, которые необходимо объединить гибридного присоединился к Azure AD. Если объекты-компьютеры принадлежат определенного подразделения (OU), а затем убедитесь, что эти подразделения устанавливаются в Azure AD для синхронизации подключение также.
    
3. Регистрация существующего устройства присоединенный к домену Windows 10 гибридного Соединяемая Azure AD и назначить им для управления мобильного устройства с Intune (Microsoft 365 Business):
    
4. Следуйте инструкциям Пошаговое руководство по [настройке гибридного Azure Active Directory в состав устройств](https://go.microsoft.com/fwlink/p/?linkid=872870). Это позволит синхронизации Active Directory локальной в состав Windows 10 компьютеров и их в облаке Готово.
    
5. Чтобы зарегистрировать устройства Windows 10 для управление мобильными устройствами, в разделе [Регистрация устройства Windows 10 Intune, с помощью групповой политики](https://go.microsoft.com/fwlink/p/?linkid=872871) для получения инструкций. Для настройки групповой политики на локальном компьютере уровня или для каждой массовой операции можно создать этот параметр групповой политики на сервере контроллера домена. 
    

