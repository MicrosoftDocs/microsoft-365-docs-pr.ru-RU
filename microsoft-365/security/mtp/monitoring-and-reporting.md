---
title: Мониторинг и просмотр отчетов — Центр безопасности
description: В этой статье описывается, как Центр безопасности Microsoft 365 предоставляет краткий обзор состояния защиты и безопасности.
keywords: безопасность, вредоносные программы, Microsoft 365, M365, Центр безопасности, монитор, отчет, состояние
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 4667c39a8d416d7e186d41063d7057109758cd33
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930406"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="1ccd0-104">Мониторинг и просмотр отчетов в Центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1ccd0-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="1ccd0-105">Хотите испытать Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="1ccd0-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="1ccd0-106">Вы можете [оценить его в лабораторной среде](https://aka.ms/mtp-trial-lab) или запустить [пилотный проект в производственной среде.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="1ccd0-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="1ccd0-107">Центр безопасности Microsoft 365 предоставляет сводку о состоянии защиты и безопасности в среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ccd0-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="1ccd0-108">Центр безопасности включает раздел **"Отчеты",** в котором содержится ряд карточек, охватывающих различные области.</span><span class="sxs-lookup"><span data-stu-id="1ccd0-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="1ccd0-109">Аналитики безопасности и администраторы могут отслеживать карточки в рамках своей ежедневной работы.</span><span class="sxs-lookup"><span data-stu-id="1ccd0-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="1ccd0-110">При детализации карточки предоставляют подробные отчеты и, в некоторых случаях, параметры управления.</span><span class="sxs-lookup"><span data-stu-id="1ccd0-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="1ccd0-111">Настройка представлений</span><span class="sxs-lookup"><span data-stu-id="1ccd0-111">Customize views</span></span>

<span data-ttu-id="1ccd0-112">По умолчанию карточки группифицются по указанным категориям.</span><span class="sxs-lookup"><span data-stu-id="1ccd0-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="1ccd0-113">[Удостоверения](monitor-and-report-identities.md) — учетные записи пользователей и учетные данные</span><span class="sxs-lookup"><span data-stu-id="1ccd0-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="1ccd0-114">[Данные](monitor-data.md) — содержимое электронной почты и документов</span><span class="sxs-lookup"><span data-stu-id="1ccd0-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="1ccd0-115">[Устройства](monitor-devices.md) — компьютеры, мобильные телефоны и другие устройства</span><span class="sxs-lookup"><span data-stu-id="1ccd0-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="1ccd0-116">[Приложения](monitor-apps.md) — программы и подключенные веб-службы</span><span class="sxs-lookup"><span data-stu-id="1ccd0-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="1ccd0-117">Переключиться **в группу по темам,** чтобы изменить ранг карточек и сгруппировать их в следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="1ccd0-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="1ccd0-118">**Риск** — карточки, которые выделяют объекты, такие как учетные записи и устройства, которые могут быть под угрозой.</span><span class="sxs-lookup"><span data-stu-id="1ccd0-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="1ccd0-119">Эти карточки также выделяют возможные источники риска, такие как новые кампании по угрозам и привилегированные облачные приложения</span><span class="sxs-lookup"><span data-stu-id="1ccd0-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="1ccd0-120">**Тенденции обнаружения** — карточки, которые выделяют новые обнаружения угроз, аномалии и нарушения политики</span><span class="sxs-lookup"><span data-stu-id="1ccd0-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="1ccd0-121">**Конфигурация и состояние** — карточки, которые охватывают настройку и развертывание элементов управления безопасностью, в том числе состояния подключения устройств к службам управления</span><span class="sxs-lookup"><span data-stu-id="1ccd0-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="1ccd0-122">**Другие —** все остальные карточки, не классифицируются по другим темам</span><span class="sxs-lookup"><span data-stu-id="1ccd0-122">**Other** - all other cards not categorized under other topics</span></span>
