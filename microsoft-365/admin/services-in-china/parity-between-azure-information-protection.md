---
title: Служба Office 365, которой управляет 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- MET150
- GEU150
- GEA150
description: Узнайте больше о службе Azure Information Protection для Office 365 под управлением 21Vianet и о том, как настроить его для клиентов в Китае.
monikerRange: o365-21vianet
ms.openlocfilehash: a4eb8c3370a123b939fdccc53eec3905f79ee806
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42247941"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Четность между службой Azure Information Protection для Office 365 под управлением 21Vianet и коммерческих услуг

Несмотря на то, что наша цель состоит в том, чтобы предоставить клиентам в Китае все коммерческие функции и функции с помощью Azure Information Protection для Office 365, предоставляемого компанией 21Vianet, есть некоторые функции, которые мы хотели бы выделить.

Это существующие промежутки между службой Azure Information Protection для Office 365 под управлением 21Vianet и наших коммерческих услуг на 2019 июля:

- Управление правами на доступ к данным (IRM) поддерживается только для Office 365 ProPlus (сборка 11731,10000 или более поздняя). Office 2010, Office 2013 и другие версии Office 2016 не поддерживаются.

- Миграция из службы управления правами Active Directory (AD RMS) в Azure Information Protection в настоящее время недоступна.
  
- Поддерживается общий доступ к защищенным сообщениям электронной почты для пользователей в коммерческом облаке.
  
- Общий доступ к документам и вложениям электронной почты для пользователей в коммерческом облаке в настоящее время недоступен. Это включает Office 365 под управлением 21Vianet в коммерческом облаке, а не в Office 365, который управляется пользователями 21Vianet в коммерческом облаке, и пользователями с лицензией RMS для индивидуальных пользователей.
  
- IRM с SharePoint (сайты и библиотеки, защищенные службой управления правами), в настоящее время недоступна.
  
- В настоящее время соединитель управления правами недоступен.
  
- Расширение мобильных устройств для AD RMS в настоящее время недоступно.

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>Настройка Azure Information Protection для клиентов в Китае

### <a name="enable-rights-management-for-the-tenant"></a>Включение управления правами для клиента

Для правильной работы шифрования необходимо включить службу управления правами для клиента.

- Проверьте, включена ли служба управления правами:
  1. Запустите PowerShell от имени администратора.
  2. Если модуль Аипсервице не установлен, запустите `Install-Module AipService`его.
  3. Импортируйте модуль с `Import-Module AipService`помощью.
  4. Подключаться к службе `Connect-AipService -environmentname azurechinacloud`с помощью.
  5. Запустите `(Get-AipServiceConfiguration).FunctionalState` и проверьте, есть `Enabled`ли состояние.

- Если функциональное состояние — `Disabled`, запустите `Enable-AipService`.

### <a name="dns-configuration-for-encryption-windows"></a>Конфигурация DNS для шифрования (Windows)

Чтобы шифрование работало правильно, клиентские приложения Office должны подключаться к экземпляру службы Китая и выполнять начальную загрузку. Чтобы перенаправить клиентские приложения на правильный экземпляр службы, администратор клиента должен настроить запись DNS SRV со сведениями об URL-адресе Azure RMS. При отсутствии DNS-записи SRV клиентское приложение попытается подключиться к экземпляру общедоступного облака по умолчанию и завершится с ошибками.

Кроме того, предполагается, что пользователи выполняют вход с именем пользователя, основанным на домене, принадлежащем клиенту ( `joe@contoso.cn`например,), а `onmschina` не именем пользователя (например `joe@contoso.onmschina.cn`,). Имя домена из имени пользователя используется для перенаправления DNS на соответствующий экземпляр службы.

- Получение идентификатора службы управления правами:
  1. Запустите PowerShell от имени администратора.
  2. Если модуль Аипсервице не установлен, запустите `Install-Module AipService`его.
  3. Подключаться к службе `Connect-AipService -environmentname azurechinacloud`с помощью.
  4. Запустите `(Get-AipServiceConfiguration).RightsManagementServiceId` , чтобы получить идентификатор службы управления правами.

- Выполните вход в систему поставщика DNS, перейдите к параметрам DNS для домена и добавьте новую запись SRV.
  - Service = `_rmsredir`
  - Protocol = `_http`
  - Name = `_tcp`
  - Target = `[GUID].rms.aadrm.cn` (где GUID — идентификатор RMS)
  - Priority, Weight, seconds, TTL = значения по умолчанию

- Свяжите личный домен с клиентом на [портале Azure](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains). Это приведет к добавлению записи в DNS, что может занять несколько минут, чтобы проверить его после добавления значения в параметры DNS.

- Войдите в центр администрирования Microsoft 365, используя соответствующие учетные данные глобального администратора, и добавьте домен (например, `contoso.cn`) для создания пользователя. В процессе проверки могут потребоваться дополнительные изменения DNS. После завершения проверки пользователи могут быть созданы.

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>Конфигурация DNS для шифрования (Mac, iOS, Android)

- Выполните вход в систему поставщика DNS, перейдите к параметрам DNS для домена и добавьте новую запись SRV.
  - Service = `_rmsdisco`
  - Protocol = `_http`
  - Name = `_tcp`
  - Target = `api.aadrm.cn`
  - Порт = `80`
  - Priority, Weight, seconds, TTL = значения по умолчанию
