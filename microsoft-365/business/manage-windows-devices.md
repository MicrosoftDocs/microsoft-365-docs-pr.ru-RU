---
title: Включение управления подключенными к домену устройств с Windows 10 в Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Сведения о том, как включить Microsoft 365 для защиты локальных подключенных устройств AD к Windows 10.
ms.openlocfilehash: af0e78ef6e79bfd612b11a16538e7afcd377ffb0
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071557"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Включение управления подключенными к домену устройств с Windows 10 в Microsoft 365 Business

Если ваша организация использует локальную службу Windows Server Active Directory, вы можете настроить Microsoft 365 бизнес для защиты устройств с Windows 10, сохраняя доступ к локальным ресурсам, требующим локальной проверки подлинности. Это можно сделать с помощью первой синхронизации Active Directory с Azure Active Directory, а затем зарегистрировать устройства Windows 10 с помощью Azure AD и зарегистрировать их для управления мобильными устройствами в Microsoft 365 Business.
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Настройка устройств, присоединенных к домену, для управления с помощью Microsoft 365 Business

Чтобы настроить устройства, присоединенные к домену организации, для использования возможностей, предоставляемых Azure Active Directory, в дополнение к локальной службе Active Directory, можно внедрить **гибридные подключенные устройства Azure AD**. Это устройства, которые присоединяются к локальному каталогу Active Directory и вашей службе Azure Active Directory. Гибридные подключенные устройства Azure AD можно защищать и управлять ими с помощью Microsoft 365 Business. 
  
Выполните приведенные ниже действия, чтобы сделать гибридную службу Windows 10 Devices (Windows 10) присоединенной и управляемой Microsoft 365 Business.
  
1. Чтобы синхронизировать пользователей, группы и контакты из локальной службы Active Directory с Azure Active Directory, запустите мастер синхронизации каталогов и Azure Active Directory Connect, как описано в статье [Настройка синхронизации каталогов для Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
    > [!NOTE]
    > Эти действия одинаковы для Microsoft 365 Business. 
  
2. Прежде чем выполнить шаг 3, чтобы включить гибридные устройства с Windows 10 для гибридной службы Azure AD, необходимо убедиться, что выполняются следующие предварительные требования:

   - Вы используете последнюю версию Azure AD Connect.

   - Azure AD Connect синхронизирует все объекты компьютеров устройств, которые вы хотите объединить в гибридную службу Azure AD. Если объекты компьютера принадлежат определенным подразделениям (OU), убедитесь, что эти подразделения настроены для синхронизации в Azure AD Connect.
    
3. Регистрация существующих устройств с Windows 10, присоединенных к домену, в гибридное подключение Azure AD и регистрация их для управления мобильными устройствами в Intune (Microsoft 365 бизнес):
    
4. Выполните пошаговые инструкции по [настройке подключенных устройств гибридной службы Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=872870). Это позволит синхронизировать локальную службу Active Directory с компьютерами с Windows 10 и подготовить их к работе в облаке.
    
5. Чтобы зарегистрировать устройство Windows 10 для управления мобильными устройствами, ознакомьтесь с инструкциями в статье [Регистрация устройства Windows 10 с помощью Intune с помощью групповой политики](https://go.microsoft.com/fwlink/p/?linkid=872871) . Вы можете настроить групповую политику на уровне локального компьютера или для массовых операций, вы можете создать этот параметр групповой политики на сервере контроллера домена.