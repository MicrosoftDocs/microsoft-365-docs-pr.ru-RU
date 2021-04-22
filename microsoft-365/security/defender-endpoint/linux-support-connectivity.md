---
title: Устранение неполадок с облачными подключениями для Microsoft Defender для конечной точки в Linux
ms.reviewer: ''
description: Устранение неполадок с облачными подключениями для Microsoft Defender для конечной точки в Linux
keywords: Microsoft, defender, Microsoft Defender for Endpoint, Linux, cloud, connectivity, communication
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
ms.openlocfilehash: 0345d7f88d147abb750e66a5e61f516abf38d553
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933113"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="844c3-104">Устранение неполадок с облачными подключениями для Microsoft Defender для конечной точки в Linux</span><span class="sxs-lookup"><span data-stu-id="844c3-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="844c3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="844c3-105">**Applies to:**</span></span>
- [<span data-ttu-id="844c3-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="844c3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="844c3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="844c3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="844c3-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="844c3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="844c3-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="844c3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a><span data-ttu-id="844c3-110">Запуск теста подключения</span><span class="sxs-lookup"><span data-stu-id="844c3-110">Run the connectivity test</span></span>

<span data-ttu-id="844c3-111">Чтобы проверить, может ли Defender для конечной точки в Linux общаться с облаком с текущими сетевыми настройками, запустите тест на подключение из командной строки:</span><span class="sxs-lookup"><span data-stu-id="844c3-111">To test if Defender for Endpoint on Linux can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="844c3-112">ожидаемый выход:</span><span class="sxs-lookup"><span data-stu-id="844c3-112">expected output:</span></span>

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

<span data-ttu-id="844c3-113">Если тест подключения не работает, проверьте, есть ли [](microsoft-defender-endpoint-linux.md#network-connections) у устройства доступ к Интернету и заблокированы ли какие-либо конечные точки, необходимые продукту, прокси-сервером или брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="844c3-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-linux.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="844c3-114">Сбои с ошибкой завитка 35 или 60 указывают на отказ от закрепления сертификата.</span><span class="sxs-lookup"><span data-stu-id="844c3-114">Failures with curl error 35 or 60, indicate certificate pinning rejection.</span></span> <span data-ttu-id="844c3-115">Проверьте, находится ли подключение под проверкой SSL или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="844c3-115">Please check if the connection is under SSL or HTTPS inspection.</span></span> <span data-ttu-id="844c3-116">Если это так, добавьте Microsoft Defender для конечной точки в список допустимой точки.</span><span class="sxs-lookup"><span data-stu-id="844c3-116">If so, add Microsoft Defender for Endpoint to the allow list.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a><span data-ttu-id="844c3-117">Действия по устранению неполадок для сред без прокси или с прозрачным прокси-сервером</span><span class="sxs-lookup"><span data-stu-id="844c3-117">Troubleshooting steps for environments without proxy or with transparent proxy</span></span>

<span data-ttu-id="844c3-118">Чтобы проверить, не блокируется ли подключение в среде без прокси-сервера или прозрачного прокси-сервера, запустите следующую команду в терминале:</span><span class="sxs-lookup"><span data-stu-id="844c3-118">To test that a connection is not blocked in an environment without a proxy or with a transparent proxy, run the following command in the terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="844c3-119">Выход из этой команды должен быть похож на:</span><span class="sxs-lookup"><span data-stu-id="844c3-119">The output from this command should be similar to:</span></span>

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a><span data-ttu-id="844c3-120">Действия по устранению неполадок для сред с помощью статического прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="844c3-120">Troubleshooting steps for environments with static proxy</span></span>

> [!WARNING]
> <span data-ttu-id="844c3-121">Прокси-панели PAC, WPAD и прокси-устройства с проверкой подлинности не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="844c3-121">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="844c3-122">Убедитесь, что используется только статичный прокси или прозрачный прокси.</span><span class="sxs-lookup"><span data-stu-id="844c3-122">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="844c3-123">Проверка SSL и перехват прокси также не поддерживаются по соображениям безопасности.</span><span class="sxs-lookup"><span data-stu-id="844c3-123">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="844c3-124">Настройте исключение для проверки SSL и прокси-сервера, чтобы напрямую передавать данные из Defender для конечной точки на Linux в соответствующие URL-адреса без перехвата.</span><span class="sxs-lookup"><span data-stu-id="844c3-124">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="844c3-125">Добавление сертификата перехвата в глобальный магазин не позволяет перехватывать.</span><span class="sxs-lookup"><span data-stu-id="844c3-125">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="844c3-126">Если требуется статичный прокси-сервер, добавьте прокси-параметр в вышеуказанную команду, где соответствует прокси-адрес `proxy_address:port` и порт:</span><span class="sxs-lookup"><span data-stu-id="844c3-126">If a static proxy is required, add a proxy parameter to the above command, where `proxy_address:port` correspond to the proxy address and port:</span></span>

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="844c3-127">Убедитесь, что вы используете тот же прокси-адрес и порт, который настроен в `/lib/system/system/mdatp.service` файле.</span><span class="sxs-lookup"><span data-stu-id="844c3-127">Ensure that you use the same proxy address and port as configured in the `/lib/system/system/mdatp.service` file.</span></span> <span data-ttu-id="844c3-128">Проверьте конфигурацию прокси,если есть ошибки из вышеперечисленных команд.</span><span class="sxs-lookup"><span data-stu-id="844c3-128">Check your proxy configuration if there are errors from the above commands.</span></span>

> [!WARNING]
> <span data-ttu-id="844c3-129">Статическое прокси-сервер не может быть настроено с помощью переменной среды для всей `HTTPS_PROXY` системы.</span><span class="sxs-lookup"><span data-stu-id="844c3-129">The static proxy cannot be configured through a system-wide `HTTPS_PROXY` environment variable.</span></span> <span data-ttu-id="844c3-130">Вместо этого убедитесь, `HTTPS_PROXY` что это правильно заложено в `/lib/system/system/mdatp.service` файле.</span><span class="sxs-lookup"><span data-stu-id="844c3-130">Instead, ensure that `HTTPS_PROXY` is properly set in the `/lib/system/system/mdatp.service` file.</span></span>

<span data-ttu-id="844c3-131">Для использования статического прокси-сервера `mdatp.service` необходимо изменить файл.</span><span class="sxs-lookup"><span data-stu-id="844c3-131">To use a static proxy, the `mdatp.service` file must be modified.</span></span> <span data-ttu-id="844c3-132">Убедитесь, `#` что ведущая удаляется, чтобы удалить следующую строку `/lib/systemd/system/mdatp.service` из:</span><span class="sxs-lookup"><span data-stu-id="844c3-132">Ensure the leading `#` is removed to uncomment the following line from `/lib/systemd/system/mdatp.service`:</span></span>

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

<span data-ttu-id="844c3-133">Кроме того, убедитесь, что для замены заполняется правильный статичный прокси-адрес. `address:port`</span><span class="sxs-lookup"><span data-stu-id="844c3-133">Also ensure that the correct static proxy address is filled in to replace `address:port`.</span></span>

<span data-ttu-id="844c3-134">Если этот файл является правильным, попробуйте запускать следующую команду в терминале, чтобы перезагрузить Defender для конечной точки на Linux и распространять параметр:</span><span class="sxs-lookup"><span data-stu-id="844c3-134">If this file is correct, try running the following command in the terminal to reload Defender for Endpoint on Linux and propagate the setting:</span></span>

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

<span data-ttu-id="844c3-135">После успешной попытки другой тест подключения из командной строки:</span><span class="sxs-lookup"><span data-stu-id="844c3-135">Upon success, attempt another connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="844c3-136">Если проблема сохраняется, обратитесь в службу поддержки клиентов.</span><span class="sxs-lookup"><span data-stu-id="844c3-136">If the problem persists, contact customer support.</span></span>

## <a name="resources"></a><span data-ttu-id="844c3-137">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="844c3-137">Resources</span></span>

- <span data-ttu-id="844c3-138">Дополнительные сведения о настройке продукта для использования статического прокси-сервера см. в дополнительных сведениях о настройке Microsoft Defender для конечной точки для обнаружения [статического прокси-сервера.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="844c3-138">For more information about how to configure the product to use a static proxy, see [Configure Microsoft Defender for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).</span></span>
