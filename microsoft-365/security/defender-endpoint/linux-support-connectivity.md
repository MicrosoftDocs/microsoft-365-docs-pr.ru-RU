---
title: Устранение неполадок с облачными подключениями для ATP Microsoft Defender для Linux
ms.reviewer: ''
description: Устранение неполадок с облачными подключениями для ATP Microsoft Defender для Linux
keywords: Microsoft, defender, atp, linux, cloud, connectivity, communication
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 77ab7bbbb156165f26538cf3d14eae1e5e76d92c
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587543"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-for-linux"></a>Устранение неполадок с облачными подключениями для Microsoft Defender для конечной точки для Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a>Запуск теста подключения

Чтобы проверить, может ли Защитник для конечной точки Для Linux взаимодействовать с облаком с текущими сетевыми настройками, запустите тест на подключение из командной строки:

```bash
mdatp connectivity test
```

ожидаемый выход:

```output
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

Если тест подключения не работает, проверьте, есть ли [](microsoft-defender-endpoint-linux.md#network-connections) у устройства доступ к Интернету и заблокированы ли какие-либо конечные точки, необходимые продукту, прокси-сервером или брандмауэром.

Сбои с ошибкой завитка 35 или 60 указывают на отказ от закрепления сертификата. Проверьте, находится ли подключение под проверкой SSL или HTTPS. Если это так, добавьте Microsoft Defender для конечной точки в список допустимой точки.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a>Действия по устранению неполадок для сред без прокси или с прозрачным прокси-сервером

Чтобы проверить, не блокируется ли подключение в среде без прокси-сервера или прозрачного прокси-сервера, запустите следующую команду в терминале:

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

Выход из этой команды должен быть похож на:

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a>Действия по устранению неполадок для сред с помощью статического прокси-сервера

> [!WARNING]
> Прокси-панели PAC, WPAD и прокси-устройства с проверкой подлинности не поддерживаются. Убедитесь, что используется только статичный прокси или прозрачный прокси.
>
> Проверка SSL и перехват прокси также не поддерживаются по соображениям безопасности. Настройте исключение для проверки SSL и прокси-сервера, чтобы напрямую передавать данные из Defender for Endpoint для Linux в соответствующие URL-адреса без перехвата. Добавление сертификата перехвата в глобальный магазин не позволяет перехватывать.

Если требуется статичный прокси-сервер, добавьте прокси-параметр в вышеуказанную команду, где соответствует прокси-адрес `proxy_address:port` и порт:

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

Убедитесь, что вы используете тот же прокси-адрес и порт, который настроен в `/lib/system/system/mdatp.service` файле. Проверьте конфигурацию прокси,если есть ошибки из вышеперечисленных команд.

> [!WARNING]
> Статическое прокси-сервер не может быть настроено с помощью переменной среды для всей `HTTPS_PROXY` системы. Вместо этого убедитесь, `HTTPS_PROXY` что это правильно заложено в `/lib/system/system/mdatp.service` файле.

Для использования статического прокси-сервера `mdatp.service` необходимо изменить файл. Убедитесь, `#` что ведущая удаляется, чтобы удалить следующую строку `/lib/systemd/system/mdatp.service` из:

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

Кроме того, убедитесь, что для замены заполняется правильный статичный прокси-адрес. `address:port`

Если этот файл является правильным, попробуйте запускать следующую команду в терминале, чтобы перезагрузить Defender для конечной точки для Linux и распространять параметр:

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

После успешной попытки другой тест подключения из командной строки:

```bash
mdatp connectivity test
```

Если проблема сохраняется, обратитесь в службу поддержки клиентов.

## <a name="resources"></a>Ресурсы

- Дополнительные сведения о настройке продукта для использования статического прокси-сервера см. в дополнительных сведениях о настройке Microsoft Defender для конечной точки для обнаружения [статического прокси-сервера.](linux-static-proxy-configuration.md)
