---
title: Проверка состояния службы ATP защитника Майкрософт
description: Проверьте состояние службы ATP Защитника Майкрософт, узнайте, возникли ли у службы проблемы, и просмотрите предыдущие проблемы, которые были устранены.
keywords: панель мониторинга, служба, проблемы, состояние службы, текущее состояние, история состояния, сводка последствий, предварительная корневая причина, разрешение, время разрешения, ожидаемое время разрешения
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 45782fcce51e15adf61757d836d313d229558571
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072917"
---
# <a name="check-the-microsoft-defender-for-endpoint-service-health"></a><span data-ttu-id="7d26e-104">Проверка состояния службы "Защитник Майкрософт" для службы конечных точек</span><span class="sxs-lookup"><span data-stu-id="7d26e-104">Check the Microsoft Defender for Endpoint service health</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7d26e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7d26e-105">**Applies to:**</span></span>
- [<span data-ttu-id="7d26e-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7d26e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)



><span data-ttu-id="7d26e-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="7d26e-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7d26e-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="7d26e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-servicestatus-abovefoldlink)

<span data-ttu-id="7d26e-109">**Служба health** предоставляет сведения о текущем состоянии службы Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="7d26e-109">**Service health** provides information on the current status of the Defender for Endpoint service.</span></span> <span data-ttu-id="7d26e-110">Вы сможете проверить, является ли состояние службы здоровым или имеются ли текущие проблемы.</span><span class="sxs-lookup"><span data-stu-id="7d26e-110">You'll be able to verify that the service health is healthy or if there are current issues.</span></span> <span data-ttu-id="7d26e-111">Если есть проблемы, вы увидите сведения, например, когда проблема была обнаружена, какова предварительная корневая причина, и ожидаемое время разрешения.</span><span class="sxs-lookup"><span data-stu-id="7d26e-111">If there are issues, you'll see information such as when the issue was detected, what the preliminary root cause is, and the expected resolution time.</span></span>

<span data-ttu-id="7d26e-112">Вы также увидите сведения об исторических проблемах, которые были устранены, и сведения, такие как дата и время решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="7d26e-112">You'll also see information on historical issues that have been resolved and details such as the date and time when the issue was resolved.</span></span> <span data-ttu-id="7d26e-113">Если в службе нет проблем, вы увидите здоровый статус.</span><span class="sxs-lookup"><span data-stu-id="7d26e-113">When there are no issues on the service, you'll see a healthy status.</span></span>

<span data-ttu-id="7d26e-114">Сведения о состоянии службы можно просмотреть, щелкнув плитку из  панели мониторинга операций безопасности или выбрав меню здоровья службы из области навигации. </span><span class="sxs-lookup"><span data-stu-id="7d26e-114">You can view details on the service health by clicking the tile from the **Security operations dashboard** or selecting the **Service health** menu from the navigation pane.</span></span>

<span data-ttu-id="7d26e-115">На **странице сведения о** здоровье службы есть следующие вкладки:</span><span class="sxs-lookup"><span data-stu-id="7d26e-115">The **Service health** details page has the following tabs:</span></span>

- <span data-ttu-id="7d26e-116">**Текущее состояние**</span><span class="sxs-lookup"><span data-stu-id="7d26e-116">**Current status**</span></span>
- <span data-ttu-id="7d26e-117">**История состояния**</span><span class="sxs-lookup"><span data-stu-id="7d26e-117">**Status history**</span></span>

## <a name="current-status"></a><span data-ttu-id="7d26e-118">Текущее состояние</span><span class="sxs-lookup"><span data-stu-id="7d26e-118">Current status</span></span>
<span data-ttu-id="7d26e-119">На **вкладке Текущий** статус отображает текущее состояние службы Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="7d26e-119">The **Current status** tab shows the current state of the Defender for Endpoint service.</span></span> <span data-ttu-id="7d26e-120">При бесперебойной работе службы отображается здоровое состояние службы.</span><span class="sxs-lookup"><span data-stu-id="7d26e-120">When the service is running smoothly a healthy service health is shown.</span></span> <span data-ttu-id="7d26e-121">Если имеются проблемы, показано, что ниже показаны сведения о службе, которые помогут вам лучше понять проблему:</span><span class="sxs-lookup"><span data-stu-id="7d26e-121">If there are issues seen, the following service details are shown to help you gain better insight about the issue:</span></span>

- <span data-ttu-id="7d26e-122">Дата и время обнаружения проблемы</span><span class="sxs-lookup"><span data-stu-id="7d26e-122">Date and time for when the issue was detected</span></span>
- <span data-ttu-id="7d26e-123">Краткое описание проблемы</span><span class="sxs-lookup"><span data-stu-id="7d26e-123">A short description of the issue</span></span>
- <span data-ttu-id="7d26e-124">Время обновления</span><span class="sxs-lookup"><span data-stu-id="7d26e-124">Update time</span></span>
- <span data-ttu-id="7d26e-125">Сводка последствий</span><span class="sxs-lookup"><span data-stu-id="7d26e-125">Summary of impact</span></span>
- <span data-ttu-id="7d26e-126">Предварительная корневая причина</span><span class="sxs-lookup"><span data-stu-id="7d26e-126">Preliminary root cause</span></span>
- <span data-ttu-id="7d26e-127">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="7d26e-127">Next steps</span></span>
- <span data-ttu-id="7d26e-128">Ожидаемое время разрешения</span><span class="sxs-lookup"><span data-stu-id="7d26e-128">Expected resolution time</span></span>

<span data-ttu-id="7d26e-129">Обновления о ходе выполнения проблемы отражаются на странице по мере решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="7d26e-129">Updates on the progress of an issue are reflected on the page as the issue gets resolved.</span></span> <span data-ttu-id="7d26e-130">Вы увидите обновления сведений, таких как обновленное время разрешения оценки или последующие действия.</span><span class="sxs-lookup"><span data-stu-id="7d26e-130">You'll see updates on information such as an updated estimate resolution time or next steps.</span></span>

<span data-ttu-id="7d26e-131">Когда проблема будет устранена, она будет записана на вкладке **История состояния.**</span><span class="sxs-lookup"><span data-stu-id="7d26e-131">When an issue is resolved, it gets recorded in the **Status history** tab.</span></span>

## <a name="status-history"></a><span data-ttu-id="7d26e-132">История состояния</span><span class="sxs-lookup"><span data-stu-id="7d26e-132">Status history</span></span>
<span data-ttu-id="7d26e-133">Вкладка **История** состояния отражает все исторические проблемы, которые были замечены и устранены.</span><span class="sxs-lookup"><span data-stu-id="7d26e-133">The **Status history** tab reflects all the historical issues that were seen and resolved.</span></span> <span data-ttu-id="7d26e-134">Вы увидите сведения об разрешенных проблемах, а также другие сведения, которые были включены во время их решения.</span><span class="sxs-lookup"><span data-stu-id="7d26e-134">You'll see details of the resolved issues along with the other information that were included while it was being resolved.</span></span>

### <a name="related-topic"></a><span data-ttu-id="7d26e-135">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="7d26e-135">Related topic</span></span>
- [<span data-ttu-id="7d26e-136">Просмотр панели мониторинга операций безопасности</span><span class="sxs-lookup"><span data-stu-id="7d26e-136">View the Security operations dashboard</span></span>](security-operations-dashboard.md)
