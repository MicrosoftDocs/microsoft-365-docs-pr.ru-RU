---
title: Выравнивание Advanced eDiscovery с EDRM
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Встроенный рабочий процесс Advanced eDiscovery в Microsoft 365 соответствует процессу обнаружения электронных данных, который определяется эталонной моделью электронного обнаружения (EDRM).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ca94baf1fc57ac014a32a80ddc5705feeb2c842
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841657"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a><span data-ttu-id="bfbed-103">Согласование Advanced eDiscovery с эталонной моделью электронного обнаружения</span><span class="sxs-lookup"><span data-stu-id="bfbed-103">Advanced eDiscovery alignment with the Electronic Discovery Reference Model</span></span>

<span data-ttu-id="bfbed-104">Встроенный рабочий процесс Advanced eDiscovery в Microsoft 365 соответствует процессу обнаружения электронных данных, который определяется эталонной моделью электронного обнаружения (EDRM).</span><span class="sxs-lookup"><span data-stu-id="bfbed-104">The built-in workflow of Advanced eDiscovery in Microsoft 365 aligns with the eDiscovery process outlined by the Electronic Discovery Reference Model (EDRM).</span></span>

![Эталонная модель электронного обнаружения (EDRM)](../media/EDRMv1.png)

<span data-ttu-id="bfbed-106">(Источник изображений предоставлен edrm.net.</span><span class="sxs-lookup"><span data-stu-id="bfbed-106">(Image source courtesy of edrm.net.</span></span> <span data-ttu-id="bfbed-107">Исходный образ был доступен в статье Creative Commons Attribution 3.0 Unported License.)</span><span class="sxs-lookup"><span data-stu-id="bfbed-107">The source image was made available under Creative Commons Attribution 3.0 Unported License.)</span></span>

<span data-ttu-id="bfbed-108">На высоком уровне, как Advanced eDiscovery поддерживает рабочий процесс EDRM:</span><span class="sxs-lookup"><span data-stu-id="bfbed-108">At a high level, here's how Advanced eDiscovery supports the EDRM workflow:</span></span>

- <span data-ttu-id="bfbed-109">**Идентификация.**</span><span class="sxs-lookup"><span data-stu-id="bfbed-109">**Identification.**</span></span> <span data-ttu-id="bfbed-110">После определения потенциальных лиц, которые могут быть заинтересованы в расследовании, вы можете добавить их в качестве хранителей (также называемых хранителями *данных,* так как они могут обладать сведениями, относяными к расследованию), в дело Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="bfbed-110">After you identify potential persons of interest in an investigation, you can add them as custodians (also called *data custodians*, because they may possess information that's relevant to the investigation) to an Advanced eDiscovery case.</span></span> <span data-ttu-id="bfbed-111">После того как пользователи будут добавлены в качестве хранителей, их легко сохранить, собрать и просмотреть.</span><span class="sxs-lookup"><span data-stu-id="bfbed-111">After users are added as custodians, it's easy to preserve, collect, and review custodian documents.</span></span>

- <span data-ttu-id="bfbed-112">**Сохранение.**</span><span class="sxs-lookup"><span data-stu-id="bfbed-112">**Preservation.**</span></span> <span data-ttu-id="bfbed-113">Для сохранения и защиты данных, связанных с расследованием, Advanced eDiscovery позволяет удерживать источники данных, связанные с хранителями, в деле.</span><span class="sxs-lookup"><span data-stu-id="bfbed-113">To preserve and protect data that's relevant to an investigation, Advanced eDiscovery lets you place a legal hold on the data sources associated with the custodians in a case.</span></span> <span data-ttu-id="bfbed-114">Вы также можете разместить на удержании данные, не относя такие данные.</span><span class="sxs-lookup"><span data-stu-id="bfbed-114">You can also place non-custodial data on hold.</span></span> <span data-ttu-id="bfbed-115">Advanced eDiscovery также имеет встроенный рабочий процесс связи, который можно отправлять уведомления об удержании по юридическим основаниям хранителям и отслеживать их подтверждения.</span><span class="sxs-lookup"><span data-stu-id="bfbed-115">Advanced eDiscovery also has a built-in communications workflow so you can send legal hold notifications to custodians and track their acknowledgments.</span></span>

- <span data-ttu-id="bfbed-116">**Коллекция.**</span><span class="sxs-lookup"><span data-stu-id="bfbed-116">**Collection.**</span></span> <span data-ttu-id="bfbed-117">После того как вы определили (и сохранили) источники данных, релевантные для расследования, вы можете использовать встроенное средство поиска в advanced eDiscovery для поиска и сбора актуальных данных из источников данных хранителя (и источников, не влияемых на хранение), которые могут быть применимы к делу.</span><span class="sxs-lookup"><span data-stu-id="bfbed-117">After you identified (and preserved) the data sources relevant to the investigation, you can use the built-in search tool in Advanced eDiscovery search for and collect live data from the custodial data sources (and non-custodial data sources, if applicable) that may be relevant to the case.</span></span>

- <span data-ttu-id="bfbed-118">**Обработка.**</span><span class="sxs-lookup"><span data-stu-id="bfbed-118">**Processing.**</span></span> <span data-ttu-id="bfbed-119">После сбора всех данных, соответствующих делу, следующим шагом является их обработка для дальнейшей проверки и анализа.</span><span class="sxs-lookup"><span data-stu-id="bfbed-119">After you've collected all data relevant to the case, the next step is process it for further review and analysis.</span></span> <span data-ttu-id="bfbed-120">В Advanced eDiscovery данные на месте, которые вы определили на этапе сбора, копируется в хранилище Azure (называемое набором для проверки), которое предоставляет статическое представление данных дела.</span><span class="sxs-lookup"><span data-stu-id="bfbed-120">In Advanced eDiscovery, the in-place data that you identified in the collection phase is copied to an Azure Storage location (called a *review set*), which provides you with a static view of the case data.</span></span> 

- <span data-ttu-id="bfbed-121">**Просмотрите.**</span><span class="sxs-lookup"><span data-stu-id="bfbed-121">**Review.**</span></span> <span data-ttu-id="bfbed-122">После того как данные были добавлены в набор для проверки, можно просмотреть конкретные документы и выполнить дополнительные запросы, чтобы уменьшить количество данных, наиболее релевантных для дела.</span><span class="sxs-lookup"><span data-stu-id="bfbed-122">After data has been added to a review set, you can view specific documents and run additional queries to reduce the data to what is most relevant to the case.</span></span> <span data-ttu-id="bfbed-123">Кроме того, можно примечать и помечать определенные документы.</span><span class="sxs-lookup"><span data-stu-id="bfbed-123">Also, can annotate and tag specific documents.</span></span>

- <span data-ttu-id="bfbed-124">**Анализ.**</span><span class="sxs-lookup"><span data-stu-id="bfbed-124">**Analysis.**</span></span> <span data-ttu-id="bfbed-125">Advanced eDiscovery предоставляет интегрированное средство аналитики, которое помогает дополнительно отодвигать данные из набора для проверки, который, как вы определили, не относится к расследованию.</span><span class="sxs-lookup"><span data-stu-id="bfbed-125">Advanced eDiscovery provides integrated analytics tool that helps you further cull data from the review set that you determine isn't relevant to the investigation.</span></span> <span data-ttu-id="bfbed-126">Дополнительно к уменьшению объема релевантной информации Advance eDiscovery также помогает сократить расходы на проверку юридических данных, позволяя упорядочесть контента, чтобы упростить и эффективнее процесс проверки.</span><span class="sxs-lookup"><span data-stu-id="bfbed-126">In addition to reducing the volume of relevant data, Advance eDiscovery also helps you save legal review costs by letting you organize content to make the review process easier and more efficient.</span></span>

- <span data-ttu-id="bfbed-127">**Производство** и **презентация.**</span><span class="sxs-lookup"><span data-stu-id="bfbed-127">**Production** and **Presentation.**</span></span> <span data-ttu-id="bfbed-128">Когда вы будете готовы, вы можете экспортировать документы из набора для проверки для юридической проверки.</span><span class="sxs-lookup"><span data-stu-id="bfbed-128">When you're ready, you can export documents from a review set for legal review.</span></span> <span data-ttu-id="bfbed-129">Вы можете экспортировать документы в их собственные форматы или в заданном EDRM формате, чтобы их можно было импортировать в сторонние приложения для проверки.</span><span class="sxs-lookup"><span data-stu-id="bfbed-129">You can export documents in their native format or in an EDRM-specified format so they can be imported into third-party review applications.</span></span>

## <a name="more-information"></a><span data-ttu-id="bfbed-130">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="bfbed-130">More information</span></span>

<span data-ttu-id="bfbed-131">Чтобы начать использовать Advanced eDiscovery, см.:</span><span class="sxs-lookup"><span data-stu-id="bfbed-131">To get started using Advanced eDiscovery, see:</span></span>

- [<span data-ttu-id="bfbed-132">Настройка Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="bfbed-132">Set up Advanced eDiscovery</span></span>](get-started-with-advanced-ediscovery.md)

- [<span data-ttu-id="bfbed-133">Создание дела Advanced eDiscovery и управление им</span><span class="sxs-lookup"><span data-stu-id="bfbed-133">Create and manage an Advanced eDiscovery case</span></span>](create-and-manage-advanced-ediscoveryv2-case.md)