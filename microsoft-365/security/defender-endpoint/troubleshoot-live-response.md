---
title: Устранение неполадок в atP защитника Microsoft в прямом эфире
description: Устранение неполадок, которые могут возникнуть при использовании живого ответа в ATP Microsoft Defender
keywords: устранение неполадок живой отклик, живой, ответ, заблокирован, файл
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 27f2c7eb01a857ec38b11797c0703710c02ac1bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076798"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a>Устранение неполадок в Microsoft Defender для проблем с ответом в прямом эфире endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

На этой странице подробно описаны действия по устранению неполадок в прямом эфире.

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a>Файл нельзя получить во время сеансов живого ответа
Если при попытке предпринять действие во время сеанса ответа в прямом эфире вы столкнулись с сообщением об ошибке, указывав на то, что к файлу нельзя получить доступ, необходимо использовать ниже действия для решения проблемы.

1. Скопируйте следующий фрагмент кода скрипта и сохраните его в виде файла PS1:

    ```
    $copied_file_path=$args[0] 
    $action=Copy-Item $copied_file_path -Destination $env:TEMP -PassThru -ErrorAction silentlyContinue
        
    if ($action){
         Write-Host "You copied the file specified in $copied_file_path to $env:TEMP Succesfully"
    }
    
    else{
        Write-Output "Error occoured while trying to copy a file, details:"
        Write-Output  $error[0].exception.message
 
    }
    ```


2. Добавьте скрипт в библиотеку ответов в прямом эфире.
3. Запустите скрипт с одним параметром: путь файла для копирования файла.
4. Перейдите в папку TEMP.
5. Запустите действие, необходимое для скопированного файла.

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a>Медленные сеансы живого ответа или задержки во время начальных подключений
Live response использует регистрацию датчиков Defender для конечной точки с помощью службы WNS в Windows. Если у вас возникли проблемы с подключением с живой реакцией, подтвердите следующие сведения:
1. `notify.windows.com` не блокируется в среде. Дополнительные сведения см. в [перенастройке](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)параметров прокси-сервера устройства и подключения к Интернету.
2. Служба WpnService (Система push-уведомлений Windows) не отключена.

Обратитесь к статьям ниже, чтобы полностью понять поведение и требования службы WpnService:
- [Обзор windows Push службы Notification Services (WNS)](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [Корпоративный брандмауэр и конфигурации прокси для поддержки трафика WNS](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [Microsoft Push Notifications Service (MPNS) Public IP ranges](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

