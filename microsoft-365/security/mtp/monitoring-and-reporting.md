---
title: Мониторинг и просмотр отчетов — центр безопасности
description: В этой статье описано, как центр безопасности Microsoft 365 предоставляет краткий обзор защиты и состояния безопасности.
keywords: безопасность, вредоносные программы, Microsoft 365, M365, центр безопасности, монитор, отчет, состояние
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90d9fcc45e768abd5fddef948fcafdaf9e77f5fb
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2020
ms.locfileid: "46866723"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="e2cc3-104">Мониторинг и просмотр отчетов в центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e2cc3-104">Monitor and view reports in the Microsoft 365 security center</span></span>

<span data-ttu-id="e2cc3-105">Центр безопасности Microsoft 365 предоставляет сводку по состояниям защиты и безопасности в среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2cc3-105">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="e2cc3-106">Центр обеспечения безопасности включает раздел " **отчеты** ", в котором размещается узел карточек, охватывающий различные области.</span><span class="sxs-lookup"><span data-stu-id="e2cc3-106">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="e2cc3-107">С помощью аналитик и администраторов безопасности можно отслеживать карты в рамках повседневных операций.</span><span class="sxs-lookup"><span data-stu-id="e2cc3-107">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="e2cc3-108">При детализации карточки предоставляют подробные отчеты и, в некоторых случаях, параметры управления.</span><span class="sxs-lookup"><span data-stu-id="e2cc3-108">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="e2cc3-109">Настройка представлений</span><span class="sxs-lookup"><span data-stu-id="e2cc3-109">Customize views</span></span>

<span data-ttu-id="e2cc3-110">По умолчанию карточки группируются в следующие категории:</span><span class="sxs-lookup"><span data-stu-id="e2cc3-110">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="e2cc3-111">[Удостоверения](monitor-and-report-identities.md) — учетные записи пользователей и учетные данные</span><span class="sxs-lookup"><span data-stu-id="e2cc3-111">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="e2cc3-112">[Данные](monitor-data.md) — электронная почта и содержимое документа</span><span class="sxs-lookup"><span data-stu-id="e2cc3-112">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="e2cc3-113">[Устройства](monitor-devices.md) — компьютеры, мобильные телефоны и другие устройства</span><span class="sxs-lookup"><span data-stu-id="e2cc3-113">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="e2cc3-114">[Приложения](monitor-apps.md) — программы и подключенные веб-службы</span><span class="sxs-lookup"><span data-stu-id="e2cc3-114">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="e2cc3-115">Переключитесь в **раздел группировать по разделу**, чтобы изменить порядок карточек и сгруппировать их в следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="e2cc3-115">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="e2cc3-116">**Риски** — карты, которые выделяют сущности, такие как учетные записи и устройства, которые могут быть подвержены риску.</span><span class="sxs-lookup"><span data-stu-id="e2cc3-116">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="e2cc3-117">Эти карточки также выделяют возможные источники риска, такие как новые кампании по угрозе и привилегированные облачные приложения</span><span class="sxs-lookup"><span data-stu-id="e2cc3-117">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="e2cc3-118">**Тенденции обнаружения** — карты, которые выделяют новые средства обнаружения и аномалии угроз и нарушения политик</span><span class="sxs-lookup"><span data-stu-id="e2cc3-118">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="e2cc3-119">Карточки **конфигурации и работоспособности** , охватывающие конфигурацию и развертывание элементов управления безопасностью, в том числе состояния подключения устройств к службам управления</span><span class="sxs-lookup"><span data-stu-id="e2cc3-119">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="e2cc3-120">**Другие** карточки, не отнесенные к другим разделам</span><span class="sxs-lookup"><span data-stu-id="e2cc3-120">**Other** - all other cards not categorized under other topics</span></span>
