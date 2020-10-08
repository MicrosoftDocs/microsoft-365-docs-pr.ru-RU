---
title: Обзор API защиты от угроз Майкрософт
description: Сведения о доступных API-интерфейсах в защите от угроз Майкрософт
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
ms.openlocfilehash: e80d8143898a31f7ae08b2cb1cf9b0eb2fc8bb8e
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198671"
---
# <a name="overview-of--microsoft-threat-protection-apis"></a><span data-ttu-id="9141e-104">Обзор API защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9141e-104">Overview of  Microsoft Threat Protection APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9141e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9141e-105">**Applies to:**</span></span>
- <span data-ttu-id="9141e-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="9141e-106">Microsoft Threat Protection</span></span>


>[!IMPORTANT] 
><span data-ttu-id="9141e-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="9141e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9141e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="9141e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="9141e-109">Решение для защиты от угроз Майкрософт основано на платформе, готовой к интеграции.</span><span class="sxs-lookup"><span data-stu-id="9141e-109">Microsoft Threat Protection solution is built on top of an integration-ready platform.</span></span> 

<span data-ttu-id="9141e-110">API Microsoft Threat Protection на уровне LOP позволяют автоматизировать рабочие процессы, основанные на общем инциденте и расширенных таблицах поиске.</span><span class="sxs-lookup"><span data-stu-id="9141e-110">The lop-level Microsoft Threat Protection APIs will enable you to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="9141e-111">**Объединенная очередь происшествий** — помогает специалистам по безопасности сосредоточиться на том, что является критическим, обеспечивая объединение всей области атак и затронутых активов в единое целое и своевременно задействовать в API инцидента.</span><span class="sxs-lookup"><span data-stu-id="9141e-111">**Combined incidents queue** - Helps security professionals focus on what's critical by ensuring that the full attack scope and impacted assets are grouped together and surfaced in a timely manner under the incident API.</span></span>

- <span data-ttu-id="9141e-112">**Межпродуктная угроза при поиске** и обеспечении безопасности Teams могут использовать свои уникальные организационные знания для поиска подписывания нарушений, создавая собственные пользовательские запросы через API необработанных данных, собранных различными продуктами для защиты.</span><span class="sxs-lookup"><span data-stu-id="9141e-112">**Cross-product threat hunting** - Security teams can leverage their unique organizational knowledge to hunt for signs of compromise by creating their own custom queries via APIs over the raw data collected by the various protection products.</span></span> 

<span data-ttu-id="9141e-113">В дополнение к этим наборам API, каждая из различных продуктов защиты предоставляет дополнительные API, которые помогут вам внедряться в зависимости от возможностей каждого продукта.</span><span class="sxs-lookup"><span data-stu-id="9141e-113">In addition to these set of APIs each of the various protection products expose additional APIs to help you innovate based on each product capabilities.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9141e-114">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="9141e-114">Related topics</span></span>
- [<span data-ttu-id="9141e-115">Доступ к API защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9141e-115">Access the Microsoft Threat Protectin APIs</span></span>](api-access.md)
- [<span data-ttu-id="9141e-116">Другие ресурсы программных интерфейсов</span><span class="sxs-lookup"><span data-stu-id="9141e-116">Other API resources</span></span>](api-articles.md)
