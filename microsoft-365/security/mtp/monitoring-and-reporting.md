---
title: Мониторинг и просмотр отчетов в центре безопасности Microsoft 365
description: В этой статье описано, как центр безопасности Microsoft 365 предоставляет краткий обзор защиты и состояния безопасности.
keywords: безопасность, вредоносные программы, Microsoft 365, M365, центр безопасности, монитор, отчет, состояние
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 5b2dee5916a793221e8030dd41c8c0ba33ea7a0d
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910136"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="8b44e-104">Мониторинг и просмотр отчетов в центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8b44e-104">Monitor and view reports in the Microsoft 365 security center</span></span>

<span data-ttu-id="8b44e-105">Центр безопасности Microsoft 365 предоставляет краткий обзор защиты и состояния безопасности в среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8b44e-105">The Microsoft 365 security center provides at a glance summary of protection and security status across your Microsoft 365 environment.</span></span>

<span data-ttu-id="8b44e-106">Центр обеспечения безопасности включает раздел " **отчеты** ", в котором размещается узел карточек, охватывающий различные области, которые отслеживаются аналитиками и администраторами безопасности в рамках повседневных операций.</span><span class="sxs-lookup"><span data-stu-id="8b44e-106">The security center includes a **Reports** section which features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span> <span data-ttu-id="8b44e-107">При детализации карточки предоставляют подробные отчеты и, в некоторых случаях, параметры управления.</span><span class="sxs-lookup"><span data-stu-id="8b44e-107">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="8b44e-108">Настройка представлений</span><span class="sxs-lookup"><span data-stu-id="8b44e-108">Customize views</span></span>

<span data-ttu-id="8b44e-109">По умолчанию карточки группируются в следующие категории:</span><span class="sxs-lookup"><span data-stu-id="8b44e-109">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="8b44e-110">[Удостоверения](monitor-and-report-identities.md) — учетные записи пользователей и учетные данные</span><span class="sxs-lookup"><span data-stu-id="8b44e-110">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="8b44e-111">[Данные](monitor-data.md) — электронная почта и содержимое документа</span><span class="sxs-lookup"><span data-stu-id="8b44e-111">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="8b44e-112">[Устройства](monitor-devices.md) — компьютеры, мобильные телефоны и другие устройства</span><span class="sxs-lookup"><span data-stu-id="8b44e-112">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="8b44e-113">[Приложения](monitor-apps.md) — программы и подключенные веб-службы</span><span class="sxs-lookup"><span data-stu-id="8b44e-113">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="8b44e-114">Переключитесь в **раздел группировать по разделу**, чтобы изменить порядок карточек и сгруппировать их в следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="8b44e-114">Switch to **Group by topic**, to rearrange the cards and group them into the following:</span></span>

* <span data-ttu-id="8b44e-115">**Риски** — карты, которые выделяют сущности, такие как учетные записи и устройства, которые могут быть подвержены риску.</span><span class="sxs-lookup"><span data-stu-id="8b44e-115">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="8b44e-116">Эти карточки также выделяют возможные источники риска, такие как новые кампании по угрозе и привилегированные облачные приложения</span><span class="sxs-lookup"><span data-stu-id="8b44e-116">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="8b44e-117">**Тенденции обнаружения** — карты, которые выделяют новые средства обнаружения и аномалии угроз и нарушения политик</span><span class="sxs-lookup"><span data-stu-id="8b44e-117">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="8b44e-118">Карточки **конфигурации и работоспособности** , охватывающие конфигурацию и развертывание элементов управления безопасностью, в том числе состояния подключения устройств к службам управления</span><span class="sxs-lookup"><span data-stu-id="8b44e-118">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="8b44e-119">**Другие** карточки, не отнесенные к другим разделам</span><span class="sxs-lookup"><span data-stu-id="8b44e-119">**Other** - all other cards not categorized under other topics</span></span>