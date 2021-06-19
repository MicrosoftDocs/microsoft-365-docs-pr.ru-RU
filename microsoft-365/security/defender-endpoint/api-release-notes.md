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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 5e72db8d986ad096d6312f90530d9f9ff246afc3
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022298"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="69922-104">Заметки о выпуске API для Защитника Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="69922-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="69922-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="69922-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="69922-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="69922-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="69922-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="69922-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="69922-108">В следующих сведениях перечислены обновления, сделанные в API Microsoft Defender для конечных точек, и даты, которые они были сделаны.</span><span class="sxs-lookup"><span data-stu-id="69922-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="69922-109">RSS-канал. Получите уведомление об обновлении этой страницы путем копирования и вклейки следующего URL-адреса в читателя каналов:</span><span class="sxs-lookup"><span data-stu-id="69922-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> /api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a><span data-ttu-id="69922-110">Заметки о выпуске — самые новые для самых старых (dd.mm.yyyyy)</span><span class="sxs-lookup"><span data-stu-id="69922-110">Release notes - newest to oldest (dd.mm.yyyy)</span></span>

### <a name="06102021"></a><span data-ttu-id="69922-111">06.10.2021</span><span class="sxs-lookup"><span data-stu-id="69922-111">06.10.2021</span></span>

- <span data-ttu-id="69922-112">Добавлен новый метод API оценки экспорта — оценка уязвимостей программного обеспечения _Delta Export (ответ JSON)_ Методы оценки экспорта и [свойства каждого устройства.](get-assessment-methods-properties.md)</span><span class="sxs-lookup"><span data-stu-id="69922-112">Added new Export assessment API method  - _Delta Export software vulnerabilities assessment (JSON response)_ [Export assessment methods and properties per device](get-assessment-methods-properties.md).</span></span>

### <a name="05252021"></a><span data-ttu-id="69922-113">05.25.2021</span><span class="sxs-lookup"><span data-stu-id="69922-113">05.25.2021</span></span>

- <span data-ttu-id="69922-114">Добавлены новые методы и свойства оценки экспорта API [на устройство.](get-assessment-methods-properties.md)</span><span class="sxs-lookup"><span data-stu-id="69922-114">Added new API [Export assessment methods and properties per device](get-assessment-methods-properties.md).</span></span>

### <a name="03052021"></a><span data-ttu-id="69922-115">03.05.2021</span><span class="sxs-lookup"><span data-stu-id="69922-115">03.05.2021</span></span>

- <span data-ttu-id="69922-116">Добавлен новый API: [методы](get-remediation-methods-properties.md)и свойства действий по исправлению.</span><span class="sxs-lookup"><span data-stu-id="69922-116">Added new API: [Remediation activity methods and properties](get-remediation-methods-properties.md).</span></span>

### <a name="10022021"></a><span data-ttu-id="69922-117">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="69922-117">10.02.2021</span></span>

- <span data-ttu-id="69922-118">Добавлен новый API: [пакетные оповещения об обновлении.](batch-update-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="69922-118">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="69922-119">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="69922-119">25.01.2021</span></span>

- <span data-ttu-id="69922-120">Обновленные ограничения скорости для [API предварительной](run-advanced-query-api.md) охоты от 15 до 45 запросов в минуту.</span><span class="sxs-lookup"><span data-stu-id="69922-120">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="69922-121">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="69922-121">21.01.2021</span></span>

- <span data-ttu-id="69922-122">Добавлен новый API: [поиск устройств по тегу](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="69922-122">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="69922-123">Добавлен новый API: [Показатели импорта.](import-ti-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="69922-123">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="69922-124">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="69922-124">03.01.2021</span></span>

- <span data-ttu-id="69922-125">Обновленные данные оповещения: добавлены ***detectionStatus** _, _*_parentProcessFilePath_*_ и _ *_parentProcessFileName_** свойства.</span><span class="sxs-lookup"><span data-stu-id="69922-125">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="69922-126">Обновленный [объект Alert:](alerts.md) ***добавлено свойство detectorId.***</span><span class="sxs-lookup"><span data-stu-id="69922-126">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="69922-127">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="69922-127">15.12.2020</span></span>

- <span data-ttu-id="69922-128">Обновленная [сущность устройства:](machine.md) добавлен ***список IpInterfaces.***</span><span class="sxs-lookup"><span data-stu-id="69922-128">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="69922-129">См. [список устройств](get-machines.md).</span><span class="sxs-lookup"><span data-stu-id="69922-129">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="69922-130">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="69922-130">04.11.2020</span></span>

- <span data-ttu-id="69922-131">Добавлен новый API: [за установите значение устройства.](set-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="69922-131">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="69922-132">Обновленная [сущность устройства:](machine.md) ***добавлено свойство deviceValue.***</span><span class="sxs-lookup"><span data-stu-id="69922-132">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="69922-133">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="69922-133">01.09.2020</span></span>

- <span data-ttu-id="69922-134">Добавлена возможность расширения сущности Alert с помощью связанных с ней данных.</span><span class="sxs-lookup"><span data-stu-id="69922-134">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="69922-135">См. [список оповещений](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="69922-135">See [List Alerts](get-alerts.md).</span></span>
