---
title: Поддерживаемые API ответов Microsoft Defender для конечных точек
description: Узнайте о конкретных вызовах API API Microsoft Defender для конечной точки.
keywords: API ответа, api графа, поддерживаемые apis, actor, alerts, device, user, domain, ip, file
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 36ed1f624fda7ae413ffbbf807925cf00e0a23ca
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933773"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a><span data-ttu-id="a2520-104">Поддерживаемые API запросов Для защитника Майкрософт для конечных точек</span><span class="sxs-lookup"><span data-stu-id="a2520-104">Supported Microsoft Defender for Endpoint query APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a2520-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a2520-105">**Applies to:**</span></span>
- [<span data-ttu-id="a2520-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a2520-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> <span data-ttu-id="a2520-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="a2520-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a2520-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="a2520-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

<span data-ttu-id="a2520-109">Сведения о поддерживаемых вызовах API, связанных с ответами, которые можно выполнить, а также сведения, такие как необходимые заглавные главы запросов и ожидаемый ответ от звонков.</span><span class="sxs-lookup"><span data-stu-id="a2520-109">Learn about the supported response-related API calls you can run and details such as the required request headers, and expected response from the calls.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a2520-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a2520-110">In this section</span></span>
<span data-ttu-id="a2520-111">Статья</span><span class="sxs-lookup"><span data-stu-id="a2520-111">Topic</span></span> | <span data-ttu-id="a2520-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a2520-112">Description</span></span>
:---|:---
<span data-ttu-id="a2520-113">Сбор пакета исследования</span><span class="sxs-lookup"><span data-stu-id="a2520-113">Collect investigation package</span></span> | <span data-ttu-id="a2520-114">Запустите этот API для сбора пакета исследований с устройства.</span><span class="sxs-lookup"><span data-stu-id="a2520-114">Run this API to collect an investigation package from a device.</span></span>
<span data-ttu-id="a2520-115">Изолировать устройство</span><span class="sxs-lookup"><span data-stu-id="a2520-115">Isolate device</span></span> | <span data-ttu-id="a2520-116">Запустите этот API, чтобы изолировать устройство от сети.</span><span class="sxs-lookup"><span data-stu-id="a2520-116">Run this API to isolate a device from the network.</span></span>
<span data-ttu-id="a2520-117">Устройство Unisolate</span><span class="sxs-lookup"><span data-stu-id="a2520-117">Unisolate device</span></span> | <span data-ttu-id="a2520-118">Удалите устройство из изоляции.</span><span class="sxs-lookup"><span data-stu-id="a2520-118">Remove a device from isolation.</span></span> 
<span data-ttu-id="a2520-119">Ограничение выполнения кода</span><span class="sxs-lookup"><span data-stu-id="a2520-119">Restrict code execution</span></span> | <span data-ttu-id="a2520-120">Запустите этот API, чтобы содержать атаку, остановив вредоносные процессы.</span><span class="sxs-lookup"><span data-stu-id="a2520-120">Run this API to contain an attack by stopping malicious processes.</span></span> <span data-ttu-id="a2520-121">Вы также можете заблокировать устройство и предотвратить последующие попытки запуска потенциально вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="a2520-121">You can also lock down a device and prevent subsequent attempts of potentially malicious programs from running.</span></span>
<span data-ttu-id="a2520-122">Неограниченное выполнение кода</span><span class="sxs-lookup"><span data-stu-id="a2520-122">Unrestrict code execution</span></span> | <span data-ttu-id="a2520-123">Запустите это, чтобы отменить ограничение политики приложений после проверки того, что скомпрометированное устройство исправлено.</span><span class="sxs-lookup"><span data-stu-id="a2520-123">Run this to reverse the restriction of applications policy after you have verified that the compromised device has been remediated.</span></span>
<span data-ttu-id="a2520-124">Запуск проверки на вирусы</span><span class="sxs-lookup"><span data-stu-id="a2520-124">Run antivirus scan</span></span> | <span data-ttu-id="a2520-125">Удаленно инициировать антивирусное сканирование, чтобы помочь определить и устранять вредоносные программы, которые могут присутствовать на взломаемом устройстве.</span><span class="sxs-lookup"><span data-stu-id="a2520-125">Remotely initiate an antivirus scan to help identify and remediate malware that might be present on a compromised device.</span></span>
<span data-ttu-id="a2520-126">Остановка и помещение на карантин файла</span><span class="sxs-lookup"><span data-stu-id="a2520-126">Stop and quarantine file</span></span> |  <span data-ttu-id="a2520-127">Запустите этот вызов, чтобы остановить запуск процессов, карантиных файлов и удаление сохраняемости, например ключей реестра.</span><span class="sxs-lookup"><span data-stu-id="a2520-127">Run this call to stop running processes, quarantine  files, and delete persistency such as registry keys.</span></span>
<span data-ttu-id="a2520-128">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="a2520-128">Request sample</span></span> | <span data-ttu-id="a2520-129">Запустите этот вызов, чтобы запросить образец файла с определенного устройства.</span><span class="sxs-lookup"><span data-stu-id="a2520-129">Run this call to request a sample of a file from a specific device.</span></span> <span data-ttu-id="a2520-130">Файл будет собираться с устройства и загружаться в безопасное хранилище.</span><span class="sxs-lookup"><span data-stu-id="a2520-130">The file will be collected from the device and uploaded to a secure storage.</span></span>
<span data-ttu-id="a2520-131">Файл блокировки</span><span class="sxs-lookup"><span data-stu-id="a2520-131">Block file</span></span> | <span data-ttu-id="a2520-132">Запустите этот API, чтобы предотвратить дальнейшее распространение атаки в организации, запретив потенциально вредоносные файлы или подозрительные вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="a2520-132">Run this API to prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 
<span data-ttu-id="a2520-133">Разблокировка файла</span><span class="sxs-lookup"><span data-stu-id="a2520-133">Unblock file</span></span> | <span data-ttu-id="a2520-134">Разрешить запуск файла в организации с помощью антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a2520-134">Allow a file run in the organization using Microsoft Defender Antivirus.</span></span>
<span data-ttu-id="a2520-135">Получить пакет SAS URI</span><span class="sxs-lookup"><span data-stu-id="a2520-135">Get package SAS URI</span></span> | <span data-ttu-id="a2520-136">Запустите этот API, чтобы получить URI, который позволяет скачивать пакет исследования.</span><span class="sxs-lookup"><span data-stu-id="a2520-136">Run this API to get a URI that allows downloading an investigation package.</span></span>
<span data-ttu-id="a2520-137">Получить объект MachineAction</span><span class="sxs-lookup"><span data-stu-id="a2520-137">Get MachineAction object</span></span> | <span data-ttu-id="a2520-138">Запустите этот API, чтобы получить объект MachineAction.</span><span class="sxs-lookup"><span data-stu-id="a2520-138">Run this API to get MachineAction object.</span></span>
<span data-ttu-id="a2520-139">Получить коллекцию MachineActions</span><span class="sxs-lookup"><span data-stu-id="a2520-139">Get MachineActions collection</span></span> | <span data-ttu-id="a2520-140">Запустите это, чтобы получить коллекцию MachineAction.</span><span class="sxs-lookup"><span data-stu-id="a2520-140">Run this to get MachineAction collection.</span></span>
<span data-ttu-id="a2520-141">Получить коллекцию FileActions</span><span class="sxs-lookup"><span data-stu-id="a2520-141">Get FileActions collection</span></span> | <span data-ttu-id="a2520-142">Запустите этот API, чтобы получить коллекцию FileActions.</span><span class="sxs-lookup"><span data-stu-id="a2520-142">Run this API to get FileActions collection.</span></span>
<span data-ttu-id="a2520-143">Получить объект FileMachineAction</span><span class="sxs-lookup"><span data-stu-id="a2520-143">Get FileMachineAction object</span></span> | <span data-ttu-id="a2520-144">Запустите этот API, чтобы получить объект FileMachineAction.</span><span class="sxs-lookup"><span data-stu-id="a2520-144">Run this API to get FileMachineAction object.</span></span>
<span data-ttu-id="a2520-145">Получить коллекцию FileMachineActions</span><span class="sxs-lookup"><span data-stu-id="a2520-145">Get FileMachineActions collection</span></span> | <span data-ttu-id="a2520-146">Запустите этот API, чтобы получить коллекцию FileMachineAction.</span><span class="sxs-lookup"><span data-stu-id="a2520-146">Run this API to get FileMachineAction collection.</span></span>
