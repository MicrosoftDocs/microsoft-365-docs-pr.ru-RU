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
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a><span data-ttu-id="da83f-104">Устранение неполадок в Microsoft Defender для проблем с ответом в прямом эфире endpoint</span><span class="sxs-lookup"><span data-stu-id="da83f-104">Troubleshoot Microsoft Defender for Endpoint live response issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="da83f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="da83f-105">**Applies to:**</span></span>
- [<span data-ttu-id="da83f-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="da83f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="da83f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da83f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="da83f-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="da83f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="da83f-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="da83f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="da83f-110">На этой странице подробно описаны действия по устранению неполадок в прямом эфире.</span><span class="sxs-lookup"><span data-stu-id="da83f-110">This page provides detailed steps to troubleshoot live response issues.</span></span>

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a><span data-ttu-id="da83f-111">Файл нельзя получить во время сеансов живого ответа</span><span class="sxs-lookup"><span data-stu-id="da83f-111">File cannot be accessed during live response sessions</span></span>
<span data-ttu-id="da83f-112">Если при попытке предпринять действие во время сеанса ответа в прямом эфире вы столкнулись с сообщением об ошибке, указывав на то, что к файлу нельзя получить доступ, необходимо использовать ниже действия для решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="da83f-112">If while trying to take an action during a live response session, you encounter an error message stating that the file can't be accessed, you'll need to use the steps below to address the issue.</span></span>

1. <span data-ttu-id="da83f-113">Скопируйте следующий фрагмент кода скрипта и сохраните его в виде файла PS1:</span><span class="sxs-lookup"><span data-stu-id="da83f-113">Copy the following script code snippet and save it as a PS1 file:</span></span>

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


2. <span data-ttu-id="da83f-114">Добавьте скрипт в библиотеку ответов в прямом эфире.</span><span class="sxs-lookup"><span data-stu-id="da83f-114">Add the script to the live response library.</span></span>
3. <span data-ttu-id="da83f-115">Запустите скрипт с одним параметром: путь файла для копирования файла.</span><span class="sxs-lookup"><span data-stu-id="da83f-115">Run the script with one parameter: the file path of the file to be copied.</span></span>
4. <span data-ttu-id="da83f-116">Перейдите в папку TEMP.</span><span class="sxs-lookup"><span data-stu-id="da83f-116">Navigate to your TEMP folder.</span></span>
5. <span data-ttu-id="da83f-117">Запустите действие, необходимое для скопированного файла.</span><span class="sxs-lookup"><span data-stu-id="da83f-117">Run the action you wanted to take on the copied file.</span></span>

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a><span data-ttu-id="da83f-118">Медленные сеансы живого ответа или задержки во время начальных подключений</span><span class="sxs-lookup"><span data-stu-id="da83f-118">Slow live response sessions or delays during initial connections</span></span>
<span data-ttu-id="da83f-119">Live response использует регистрацию датчиков Defender для конечной точки с помощью службы WNS в Windows.</span><span class="sxs-lookup"><span data-stu-id="da83f-119">Live response leverages Defender for Endpoint sensor registration with WNS service in Windows.</span></span> <span data-ttu-id="da83f-120">Если у вас возникли проблемы с подключением с живой реакцией, подтвердите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="da83f-120">If you are having connectivity issues with live response, confirm the following details:</span></span>
1. <span data-ttu-id="da83f-121">`notify.windows.com` не блокируется в среде.</span><span class="sxs-lookup"><span data-stu-id="da83f-121">`notify.windows.com` is not blocked in your environment.</span></span> <span data-ttu-id="da83f-122">Дополнительные сведения см. в [перенастройке](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)параметров прокси-сервера устройства и подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="da83f-122">For more information, see, [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>
2. <span data-ttu-id="da83f-123">Служба WpnService (Система push-уведомлений Windows) не отключена.</span><span class="sxs-lookup"><span data-stu-id="da83f-123">WpnService (Windows Push Notifications System Service) is not disabled.</span></span>

<span data-ttu-id="da83f-124">Обратитесь к статьям ниже, чтобы полностью понять поведение и требования службы WpnService:</span><span class="sxs-lookup"><span data-stu-id="da83f-124">Refer to the articles below to fully understand the WpnService service behavior and requirements:</span></span>
- [<span data-ttu-id="da83f-125">Обзор windows Push службы Notification Services (WNS)</span><span class="sxs-lookup"><span data-stu-id="da83f-125">Windows Push Notification Services (WNS) overview</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [<span data-ttu-id="da83f-126">Корпоративный брандмауэр и конфигурации прокси для поддержки трафика WNS</span><span class="sxs-lookup"><span data-stu-id="da83f-126">Enterprise Firewall and Proxy Configurations to Support WNS Traffic</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [<span data-ttu-id="da83f-127">Microsoft Push Notifications Service (MPNS) Public IP ranges</span><span class="sxs-lookup"><span data-stu-id="da83f-127">Microsoft Push Notifications Service (MPNS) Public IP ranges</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

