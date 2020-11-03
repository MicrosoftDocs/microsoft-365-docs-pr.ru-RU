---
title: Обзор API-интерфейсов Защитника Microsoft 365
description: Сведения о доступных API-интерфейсах в защитнике Microsoft 365
keywords: API, API, обзор, инцидент, происшествия, Поиск угроз
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 75a5853e7128667420819c84fbc3c50b07d669b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845018"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="e31d7-104">Обзор API-интерфейсов Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e31d7-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e31d7-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e31d7-105">**Applies to:**</span></span>
- <span data-ttu-id="e31d7-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e31d7-106">Microsoft 365 Defender</span></span>


>[!IMPORTANT] 
><span data-ttu-id="e31d7-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="e31d7-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e31d7-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="e31d7-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="e31d7-109">Решение для защитника Microsoft 365 построено на основе платформы, готовой к интеграции.</span><span class="sxs-lookup"><span data-stu-id="e31d7-109">Microsoft 365 Defender solution is built on top of an integration-ready platform.</span></span> 

<span data-ttu-id="e31d7-110">API-интерфейсы защитника Microsoft 365 LOP позволяют автоматизировать рабочие процессы, основанные на общем инциденте и расширенных таблицах поиске.</span><span class="sxs-lookup"><span data-stu-id="e31d7-110">The lop-level Microsoft 365 Defender APIs will enable you to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="e31d7-111">**Объединенная очередь происшествий** — помогает специалистам по безопасности сосредоточиться на том, что важно.</span><span class="sxs-lookup"><span data-stu-id="e31d7-111">**Combined incidents queue** - Helps security professionals focus on what's critical.</span></span> <span data-ttu-id="e31d7-112">Гарантирует, что полная область атак и затронутые активы группируются вместе и помещаются своевременно в API инцидентов.</span><span class="sxs-lookup"><span data-stu-id="e31d7-112">Helps to ensure that the full attack scope and impacted assets are grouped together and surfaced in a timely manner under the incident API.</span></span>

- <span data-ttu-id="e31d7-113">**Межпродуктная угроза при поиске** и обеспечении безопасности Teams могут использовать свои уникальные организационные знания для поиска подписывания нарушений, создавая собственные пользовательские запросы через API необработанных данных, собранных различными продуктами для защиты.</span><span class="sxs-lookup"><span data-stu-id="e31d7-113">**Cross-product threat hunting** - Security teams can leverage their unique organizational knowledge to hunt for signs of compromise by creating their own custom queries via APIs over the raw data collected by the various protection products.</span></span> 

<span data-ttu-id="e31d7-114">В дополнение к этим наборам API, каждый из различных продуктов защиты предоставляет дополнительные API, которые помогут вам внедряться в зависимости от возможностей каждого продукта.</span><span class="sxs-lookup"><span data-stu-id="e31d7-114">In addition to these set of APIs, each of the various protection products expose additional APIs to help you innovate based on each product capability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e31d7-115">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e31d7-115">Related topics</span></span>
- [<span data-ttu-id="e31d7-116">Доступ к API защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e31d7-116">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="e31d7-117">Другие ресурсы программных интерфейсов</span><span class="sxs-lookup"><span data-stu-id="e31d7-117">Other API resources</span></span>](api-articles.md)
