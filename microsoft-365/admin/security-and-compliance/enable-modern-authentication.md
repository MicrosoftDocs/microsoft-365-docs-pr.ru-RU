---
title: Включение современной проверки подлинности для Office 2013 на устройствах с Windows
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Научитесь устанавливать ключи реестра, чтобы включить современную проверку подлинности для устройств, Microsoft Office 2013 г.
ms.openlocfilehash: 8bfe515fefed9d58f140a67e53ce0d078457aa72
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393659"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Включение современной проверки подлинности для Office 2013 на устройствах с Windows

Чтобы включить современную проверку подлинности для устройств Windows, на которых установлен Office 2013, необходимо настроить разделы реестра.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Включение современной проверки подлинности для клиентов Office 2013

> [!NOTE]
> Современная проверка подлинности уже включена для клиентов Office 2016. Настраивать разделы реестра для Office 2016 не нужно. 
  
Чтобы включить современную проверку подлинности для устройства с Windows (например, ноутбука или планшета), на котором установлен Microsoft Office 2013, необходимо настроить указанные ниже разделы реестра. Это нужно сделать для каждого устройства, на котором вы хотите включить современную проверку подлинности.
  
|**Раздел реестра**|**Тип**|**Значение** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
   
После задания ключей реестра можно Office 2013 г. приложениям для использования многофакторной проверки подлинности [(MFA)](set-up-multi-factor-authentication.md) с помощью Microsoft 365. 
  
Если вы вошли в одно из клиентских приложений, выйдите из него и войдите снова, чтобы изменения вступили в силу. В противном случае, файлы, с которыми вы недавно работали, и настройки роуминга останутся недоступными до тех пор, пока не будет установлено удостоверение библиотек ADAL.
  
## <a name="disable-modern-authentication-on-devices"></a>Отключение современный проверки подлинности на устройствах

Чтобы отключить современную проверку подлинности на устройстве, настройте на нем следующие разделы реестра:
  
|**Раздел реестра**|**Тип**|**Значение**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL |REG_DWORD|0|
   
## <a name="related-content"></a>См. также:

[Вход в Office 2013 г.](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) со вторым методом проверки (статья)\
[Outlook для](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) пароля и не использует современную проверку подлинности для подключения к Office 365 (статья)

