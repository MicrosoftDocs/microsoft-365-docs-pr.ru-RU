---
title: Устранение неполадок с облачными подключениями для Microsoft Defender для конечной точки на macOS
description: В этом разделе описывается устранение неполадок с облачными подключениями для Microsoft Defender для конечной точки на macOS
keywords: Microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 08e3701283dd7a2de7396a66e07214b997236bed
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764079"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Устранение неполадок с облачными подключениями для Microsoft Defender для конечной точки на macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**MacOS** платформы

В этом разделе описывается, как устранить проблемы с облачным подключением для Microsoft Defender для конечной точки на macOS.

## <a name="run-the-connectivity-test"></a>Запуск теста подключения
Чтобы проверить, может ли Defender для конечной точки на Mac взаимодействовать с облаком с текущими сетевыми настройками, запустите тест на подключение из командной строки:

```Bash
mdatp connectivity test
```

ожидаемый выход:
```Bash
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

Если тест подключения не работает, проверьте, есть ли [](microsoft-defender-endpoint-mac.md#network-connections) у устройства доступ к Интернету и заблокированы ли какие-либо конечные точки, необходимые продукту, прокси-сервером или брандмауэром.

Сбои с ошибкой завитка 35 или 60 указывают на отклонение при закреплении сертификата, что указывает на потенциальную проблему с проверкой SSL или HTTPS. Ниже приведены инструкции по конфигурации проверки SSL.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a>Действия по устранению неполадок для сред без прокси-сервера или с помощью автоконфига Прокси (PAC) или протокола автообнаружия веб-прокси (WPAD)
Используйте следующую процедуру, чтобы проверить, не блокируется ли подключение в среде без прокси-сервера или с помощью прокси-автоконфига (PAC) или протокола автообнаружения веб-прокси (WPAD).

Если прокси-сервер или брандмауэр блокирует анонимный трафик, убедитесь, что анонимный трафик разрешен в указанных ранее URL-адресах.

> [!WARNING]
> Прокси-прокси с проверкой подлинности не поддерживаются. Убедитесь, что используется только PAC, WPAD или статический прокси. Проверка SSL и перехват прокси также не поддерживаются по соображениям безопасности. Настройте исключение для проверки SSL и прокси-сервера, чтобы напрямую передавать данные из Microsoft Defender для конечной точки на macOS в соответствующие URL-адреса без перехвата. Добавление сертификата перехвата в глобальный магазин не позволяет перехватывать.
Проверка того, что подключение не заблокировано: в браузере, например Microsoft Edge для Mac или Safari, открываются https://x.cp.wd.microsoft.com/api/report и https://cdn.x.cp.wd.microsoft.com/ping .

Необязательно в Терминале запустите следующую команду:

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

Выход из этой команды должен быть похож на:
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
