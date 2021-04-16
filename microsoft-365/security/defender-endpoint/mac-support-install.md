---
title: Проблемы с установкой неполадок для Microsoft Defender для конечной точки для Mac
description: Устранение неполадок при установке в Microsoft Defender для конечной точки для Mac.
keywords: Microsoft, defender, atp, mac, install
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d2ad3160c9f36a27dc98f44365433de5f8b26bb2
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861435"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Проблемы с установкой неполадок для Microsoft Defender для конечной точки на macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки в macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a>Сбой установки

Для ручной установки на странице Сводка мастера установки говорится: "Во время установки произошла ошибка. Установщик столкнулся с ошибкой, из-за которой установка не справилась с работой. Обратитесь за помощью к производителю программного обеспечения". Для развертывания MDM он также отображается как общий сбой установки.

Хотя мы не отображаем точную ошибку конечному пользователю, мы храним файл журнала с ходом установки `/Library/Logs/Microsoft/mdatp/install.log` в . Каждый сеанс установки примыкает к этому файлу журнала. Для вывода последнего сеанса установки можно `sed` использовать только:

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

В этом примере фактической причиной является префикс `[ERROR]` с .
Установка не удалось, так как понижение между этими версиями не поддерживается.

## <a name="mdatp-install-log-missing-or-not-updated"></a>Журнал установки MDATP отсутствует или не обновляется

В редких случаях установка не оставляет следов в файле MDATP /Library/Logs/Microsoft/mdatp/install.log.
Вы можете проверить, произошла ли установка, и проанализировать возможные ошибки, запросив журналы macOS (это полезно в развертывании MDM, когда нет пользовательского интерфейса клиента). Мы рекомендуем использовать узкое окно времени для выполнения запроса и фильтровать по имени процесса ведения журнала, так как будет огромное количество информации.

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
