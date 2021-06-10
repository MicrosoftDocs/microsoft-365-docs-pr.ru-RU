---
title: Проблемы с установкой неполадок для Microsoft Defender для конечной точки на Mac
description: Устранение неполадок при установке в Microsoft Defender для конечной точки на Mac.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mac, install
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
ms.openlocfilehash: 5166de3a7c7017979a93ac7026636ba24671892e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935153"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="b9891-104">Проблемы с установкой неполадок для Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="b9891-104">Troubleshoot installation issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b9891-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b9891-105">**Applies to:**</span></span>

- [<span data-ttu-id="b9891-106">Microsoft Defender для конечной точки в macOS</span><span class="sxs-lookup"><span data-stu-id="b9891-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="b9891-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b9891-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b9891-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9891-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b9891-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b9891-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b9891-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b9891-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a><span data-ttu-id="b9891-111">Сбой установки</span><span class="sxs-lookup"><span data-stu-id="b9891-111">Installation failed</span></span>

<span data-ttu-id="b9891-112">Для ручной установки на странице Сводка мастера установки говорится: "Во время установки произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="b9891-112">For manual installation, the Summary page of the installation wizard says, "An error occurred during installation.</span></span> <span data-ttu-id="b9891-113">Установщик столкнулся с ошибкой, из-за которой установка не справилась с работой.</span><span class="sxs-lookup"><span data-stu-id="b9891-113">The Installer encountered an error that caused the installation to fail.</span></span> <span data-ttu-id="b9891-114">Обратитесь за помощью к производителю программного обеспечения".</span><span class="sxs-lookup"><span data-stu-id="b9891-114">Contact the software manufacturer for assistance."</span></span> <span data-ttu-id="b9891-115">Для развертывания MDM он также отображается как общий сбой установки.</span><span class="sxs-lookup"><span data-stu-id="b9891-115">For MDM deployments, it displays as a generic installation failure as well.</span></span>

<span data-ttu-id="b9891-116">Хотя мы не отображаем точную ошибку конечному пользователю, мы храним файл журнала с ходом установки `/Library/Logs/Microsoft/mdatp/install.log` в .</span><span class="sxs-lookup"><span data-stu-id="b9891-116">While we do not display an exact error to the end user, we keep a log file with installation progress in `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="b9891-117">Каждый сеанс установки примыкает к этому файлу журнала.</span><span class="sxs-lookup"><span data-stu-id="b9891-117">Each installation session appends to this log file.</span></span> <span data-ttu-id="b9891-118">Для вывода последнего сеанса установки можно `sed` использовать только:</span><span class="sxs-lookup"><span data-stu-id="b9891-118">You can use `sed` to output the last installation session only:</span></span>

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

<span data-ttu-id="b9891-119">В этом примере фактической причиной является префикс `[ERROR]` с .</span><span class="sxs-lookup"><span data-stu-id="b9891-119">In this example, the actual reason is prefixed with `[ERROR]`.</span></span>
<span data-ttu-id="b9891-120">Установка не удалось, так как понижение между этими версиями не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b9891-120">The installation failed because a downgrade between these versions is not supported.</span></span>

## <a name="mdatp-install-log-missing-or-not-updated"></a><span data-ttu-id="b9891-121">MDATP журнала отсутствует или не обновляется</span><span class="sxs-lookup"><span data-stu-id="b9891-121">MDATP install log missing or not updated</span></span>

<span data-ttu-id="b9891-122">В редких случаях установка не оставляет следов в файле MDATP/Library/Logs/Microsoft/mdatp/install.log.</span><span class="sxs-lookup"><span data-stu-id="b9891-122">In rare cases, installation leaves no trace in MDATP's /Library/Logs/Microsoft/mdatp/install.log file.</span></span>
<span data-ttu-id="b9891-123">Вы можете проверить, произошла ли установка, и проанализировать возможные ошибки, запросив журналы macOS (это полезно в развертывании MDM, когда нет пользовательского интерфейса клиента).</span><span class="sxs-lookup"><span data-stu-id="b9891-123">You can verify that an installation happened and analyze possible errors by querying macOS logs (this is helpful in MDM deployment, when there is no client UI).</span></span> <span data-ttu-id="b9891-124">Мы рекомендуем использовать узкое окно времени для выполнения запроса и фильтровать по имени процесса ведения журнала, так как будет огромное количество информации.</span><span class="sxs-lookup"><span data-stu-id="b9891-124">We recommend that you use a narrow time window to run a query, and that you filter by the logging process name, as there will be a huge amount of information.</span></span>

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
