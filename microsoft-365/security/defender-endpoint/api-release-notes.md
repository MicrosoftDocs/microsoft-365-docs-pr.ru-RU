---
title: Заметки о выпуске API для Защитника Майкрософт для конечной точки
description: Заметки о выпуске обновлений, сделанных в набор API Для конечной точки Microsoft Defender для конечной точки.
keywords: Заметки о выпуске API для Защитника Майкрософт для конечных точек, mde, API API, Microsoft Defender для endpoint, обновления, заметки, выпуск
search.product: eADQiWindows 10XVcnh
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 02fd995b04c1644e88b38fd0feebc2c80a3681ac
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933629"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="162bb-104">Заметки о выпуске API для Защитника Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="162bb-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="162bb-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="162bb-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="162bb-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="162bb-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="162bb-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="162bb-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="162bb-108">В следующих сведениях перечислены обновления, сделанные в API Microsoft Defender для конечных точек, и даты, которые они были сделаны.</span><span class="sxs-lookup"><span data-stu-id="162bb-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>


> [!TIP]
> <span data-ttu-id="162bb-109">RSS-канал. Получите уведомление об обновлении этой страницы путем копирования и вклейки следующего URL-адреса в читателя каналов:</span><span class="sxs-lookup"><span data-stu-id="162bb-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span> 
>```
>https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
>```


### <a name="10022021"></a><span data-ttu-id="162bb-110">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="162bb-110">10.02.2021</span></span>
<hr>

- <span data-ttu-id="162bb-111">Добавлен новый API: [пакетные оповещения об обновлении.](batch-update-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="162bb-111">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span> 

<br>

### <a name="25012021"></a><span data-ttu-id="162bb-112">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="162bb-112">25.01.2021</span></span>
<hr>

- <span data-ttu-id="162bb-113">Обновленные ограничения скорости для [API предварительной](run-advanced-query-api.md) охоты от 15 до 45 запросов в минуту.</span><span class="sxs-lookup"><span data-stu-id="162bb-113">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span> 

<br>

### <a name="21012021"></a><span data-ttu-id="162bb-114">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="162bb-114">21.01.2021</span></span>
<hr>

- <span data-ttu-id="162bb-115">Добавлен новый API: [поиск устройств по тегу](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="162bb-115">Added new API: [Find devices by tag](machine-tags.md).</span></span> 
- <span data-ttu-id="162bb-116">Добавлен новый API: [Показатели импорта.](import-ti-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="162bb-116">Added new API: [Import Indicators](import-ti-indicators.md).</span></span> 

<br>

### <a name="03012021"></a><span data-ttu-id="162bb-117">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="162bb-117">03.01.2021</span></span>
<hr>

- <span data-ttu-id="162bb-118">Обновленные данные оповещения: добавлены ***detectionStatus** _, _*_parentProcessFilePath_*_ и _ *_parentProcessFileName_** свойства.</span><span class="sxs-lookup"><span data-stu-id="162bb-118">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="162bb-119">Обновленный [объект Alert:](alerts.md) ***добавлено свойство detectorId.***</span><span class="sxs-lookup"><span data-stu-id="162bb-119">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

<br>

### <a name="15122020"></a><span data-ttu-id="162bb-120">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="162bb-120">15.12.2020</span></span>
<hr>

- <span data-ttu-id="162bb-121">Обновленная [сущность устройства:](machine.md) добавлен ***список IpInterfaces.***</span><span class="sxs-lookup"><span data-stu-id="162bb-121">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="162bb-122">См. [список устройств](get-machines.md).</span><span class="sxs-lookup"><span data-stu-id="162bb-122">See [List devices](get-machines.md).</span></span>

<br>

### <a name="04112020"></a><span data-ttu-id="162bb-123">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="162bb-123">04.11.2020</span></span>
<hr>

- <span data-ttu-id="162bb-124">Добавлен новый API: [за установите значение устройства.](set-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="162bb-124">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="162bb-125">Обновленная [сущность устройства:](machine.md) ***добавлено свойство deviceValue.***</span><span class="sxs-lookup"><span data-stu-id="162bb-125">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

<br>

### <a name="01092020"></a><span data-ttu-id="162bb-126">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="162bb-126">01.09.2020</span></span>
<hr>

- <span data-ttu-id="162bb-127">Добавлена возможность расширения сущности Alert с помощью связанных с ней данных.</span><span class="sxs-lookup"><span data-stu-id="162bb-127">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="162bb-128">См. [список оповещений](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="162bb-128">See [List Alerts](get-alerts.md).</span></span>

<br>
<br>