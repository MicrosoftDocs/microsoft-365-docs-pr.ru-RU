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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fbe9d0006a2f1779e1bad60dc283a5a40429dbdd
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51750020"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="dc9dd-104">Устранение неполадок с облачными подключениями для Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="dc9dd-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dc9dd-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="dc9dd-105">**Applies to:**</span></span>
- [<span data-ttu-id="dc9dd-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="dc9dd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dc9dd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc9dd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="dc9dd-108">**MacOS** платформы</span><span class="sxs-lookup"><span data-stu-id="dc9dd-108">**Platform** macOS</span></span>

<span data-ttu-id="dc9dd-109">В этом разделе описывается, как устранить проблемы с облачным подключением для Microsoft Defender для конечной точки на macOS.</span><span class="sxs-lookup"><span data-stu-id="dc9dd-109">This topic describes how to Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on macOS.</span></span>

## <a name="run-the-connectivity-test"></a><span data-ttu-id="dc9dd-110">Запуск теста подключения</span><span class="sxs-lookup"><span data-stu-id="dc9dd-110">Run the connectivity test</span></span>
<span data-ttu-id="dc9dd-111">Чтобы проверить, может ли Defender для конечной точки на Mac взаимодействовать с облаком с текущими сетевыми настройками, запустите тест на подключение из командной строки:</span><span class="sxs-lookup"><span data-stu-id="dc9dd-111">To test if Defender for Endpoint on Mac can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```Bash
mdatp connectivity test
```

<span data-ttu-id="dc9dd-112">ожидаемый выход:</span><span class="sxs-lookup"><span data-stu-id="dc9dd-112">expected output:</span></span>
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

<span data-ttu-id="dc9dd-113">Если тест подключения не работает, проверьте, есть ли [](microsoft-defender-endpoint-mac.md#network-connections) у устройства доступ к Интернету и заблокированы ли какие-либо конечные точки, необходимые продукту, прокси-сервером или брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="dc9dd-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-mac.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="dc9dd-114">Сбои с ошибкой завитка 35 или 60 указывают на отклонение при закреплении сертификата, что указывает на потенциальную проблему с проверкой SSL или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="dc9dd-114">Failures with curl error 35 or 60 indicate certificate pinning rejection, which indicates a potential issue with SSL or HTTPS inspection.</span></span> <span data-ttu-id="dc9dd-115">Ниже приведены инструкции по конфигурации проверки SSL.</span><span class="sxs-lookup"><span data-stu-id="dc9dd-115">See instructions below regarding SSL inspection configuration.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a><span data-ttu-id="dc9dd-116">Действия по устранению неполадок для сред без прокси-сервера или с помощью автоконфига Прокси (PAC) или протокола автообнаружия веб-прокси (WPAD)</span><span class="sxs-lookup"><span data-stu-id="dc9dd-116">Troubleshooting steps for environments without proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD)</span></span>
<span data-ttu-id="dc9dd-117">Используйте следующую процедуру, чтобы проверить, не блокируется ли подключение в среде без прокси-сервера или с помощью прокси-автоконфига (PAC) или протокола автообнаружения веб-прокси (WPAD).</span><span class="sxs-lookup"><span data-stu-id="dc9dd-117">Use the following procedure to test that a connection is not blocked in an environment without a proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD).</span></span>

<span data-ttu-id="dc9dd-118">Если прокси-сервер или брандмауэр блокирует анонимный трафик, убедитесь, что анонимный трафик разрешен в указанных ранее URL-адресах.</span><span class="sxs-lookup"><span data-stu-id="dc9dd-118">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="dc9dd-119">Прокси-прокси с проверкой подлинности не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="dc9dd-119">Authenticated proxies are not supported.</span></span> <span data-ttu-id="dc9dd-120">Убедитесь, что используется только PAC, WPAD или статический прокси.</span><span class="sxs-lookup"><span data-stu-id="dc9dd-120">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span> <span data-ttu-id="dc9dd-121">Проверка SSL и перехват прокси также не поддерживаются по соображениям безопасности.</span><span class="sxs-lookup"><span data-stu-id="dc9dd-121">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="dc9dd-122">Настройте исключение для проверки SSL и прокси-сервера, чтобы напрямую передавать данные из Microsoft Defender для конечной точки на macOS в соответствующие URL-адреса без перехвата.</span><span class="sxs-lookup"><span data-stu-id="dc9dd-122">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint on macOS to the relevant URLs without interception.</span></span> <span data-ttu-id="dc9dd-123">Добавление сертификата перехвата в глобальный магазин не позволяет перехватывать.</span><span class="sxs-lookup"><span data-stu-id="dc9dd-123">Adding your interception certificate to the global store will not allow for interception.</span></span>
<span data-ttu-id="dc9dd-124">Проверка того, что подключение не заблокировано: в браузере, например Microsoft Edge для Mac или Safari, открываются https://x.cp.wd.microsoft.com/api/report и https://cdn.x.cp.wd.microsoft.com/ping .</span><span class="sxs-lookup"><span data-stu-id="dc9dd-124">To test that a connection is not blocked: In a browser such as Microsoft Edge for Mac or Safari open https://x.cp.wd.microsoft.com/api/report and https://cdn.x.cp.wd.microsoft.com/ping.</span></span>

<span data-ttu-id="dc9dd-125">Необязательно в Терминале запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="dc9dd-125">Optionally, in Terminal, run the following command:</span></span>

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

<span data-ttu-id="dc9dd-126">Выход из этой команды должен быть похож на:</span><span class="sxs-lookup"><span data-stu-id="dc9dd-126">The output from this command should be similar to:</span></span>
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
