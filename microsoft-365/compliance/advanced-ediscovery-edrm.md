---
title: Согласование расширенных электронных данных с EDRM
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
- m365-security-compliance
search.appverid:
- MOE150
- MET150
description: Встроенный рабочий процесс advanced eDiscovery в Microsoft 365 совпадает с процессом обнаружения электронных данных, описанным справочной моделью электронного обнаружения (EDRM).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f2e7886eb67a58b43e9fb638fafb358fd9ee832c
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727492"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a><span data-ttu-id="1f56d-103">Согласование расширенных данных об обнаружении электронных данных с помощью модели электронного обнаружения</span><span class="sxs-lookup"><span data-stu-id="1f56d-103">Advanced eDiscovery alignment with the Electronic Discovery Reference Model</span></span>

<span data-ttu-id="1f56d-104">Встроенный рабочий процесс advanced eDiscovery в Microsoft 365 совпадает с процессом обнаружения электронных данных, описанным справочной моделью электронного обнаружения (EDRM).</span><span class="sxs-lookup"><span data-stu-id="1f56d-104">The built-in workflow of Advanced eDiscovery in Microsoft 365 aligns with the eDiscovery process outlined by the Electronic Discovery Reference Model (EDRM).</span></span>

![Эталонная модель электронного обнаружения (EDRM)](../media/EDRMv1.png)

<span data-ttu-id="1f56d-106">(Источник изображений предоставлен edrm.net.</span><span class="sxs-lookup"><span data-stu-id="1f56d-106">(Image source courtesy of edrm.net.</span></span> <span data-ttu-id="1f56d-107">Исходный образ был доступен в статье Creative Commons Attribution 3.0 Unported License.)</span><span class="sxs-lookup"><span data-stu-id="1f56d-107">The source image was made available under Creative Commons Attribution 3.0 Unported License.)</span></span>

<span data-ttu-id="1f56d-108">На высоком уровне можно узнать, как advanced eDiscovery поддерживает рабочий процесс EDRM:</span><span class="sxs-lookup"><span data-stu-id="1f56d-108">At a high level, here's how Advanced eDiscovery supports the EDRM workflow:</span></span>

- <span data-ttu-id="1f56d-109">**Идентификация.**</span><span class="sxs-lookup"><span data-stu-id="1f56d-109">**Identification.**</span></span> <span data-ttu-id="1f56d-110">После идентификации потенциальных лиц, интересуемого расследованием, вы можете добавить их в качестве хранителей (также называемых хранителями *данных,* так как они могут обладать сведениями, которые имеют отношение к расследованию) к делу о предварительном обнаружении электронных данных.</span><span class="sxs-lookup"><span data-stu-id="1f56d-110">After you identify potential persons of interest in an investigation, you can add them as custodians (also called *data custodians*, because they may possess information that's relevant to the investigation) to an Advanced eDiscovery case.</span></span> <span data-ttu-id="1f56d-111">После того как пользователи будут добавлены в качестве хранителей, легко сохранить, собрать и просмотреть документы хранителя.</span><span class="sxs-lookup"><span data-stu-id="1f56d-111">After users are added as custodians, it's easy to preserve, collect, and review custodian documents.</span></span>

- <span data-ttu-id="1f56d-112">**Сохранение.**</span><span class="sxs-lookup"><span data-stu-id="1f56d-112">**Preservation.**</span></span> <span data-ttu-id="1f56d-113">Для сохранения и защиты данных, которые имеют отношение к расследованию, advanced eDiscovery позволяет хранить юридические источники данных, связанные с хранителями в деле.</span><span class="sxs-lookup"><span data-stu-id="1f56d-113">To preserve and protect data that's relevant to an investigation, Advanced eDiscovery lets you place a legal hold on the data sources associated with the custodians in a case.</span></span> <span data-ttu-id="1f56d-114">Кроме того, можно разместить данные, не веские для хранения.</span><span class="sxs-lookup"><span data-stu-id="1f56d-114">You can also place non-custodial data on hold.</span></span> <span data-ttu-id="1f56d-115">Advanced eDiscovery также имеет встроенный рабочий процесс коммуникации, чтобы можно было отправлять уведомления о удержании на законных основаниях хранителям и отслеживать их подтверждения.</span><span class="sxs-lookup"><span data-stu-id="1f56d-115">Advanced eDiscovery also has a built-in communications workflow so you can send legal hold notifications to custodians and track their acknowledgments.</span></span>

- <span data-ttu-id="1f56d-116">**Коллекция.**</span><span class="sxs-lookup"><span data-stu-id="1f56d-116">**Collection.**</span></span> <span data-ttu-id="1f56d-117">После того как вы определили (и сохранили) источники данных, соответствующие расследованию, вы можете использовать встроенный инструмент поиска в advanced eDiscovery для поиска и сбора живых данных из источников данных хранения (и, если применимо), которые могут иметь отношение к делу.</span><span class="sxs-lookup"><span data-stu-id="1f56d-117">After you identified (and preserved) the data sources relevant to the investigation, you can use the built-in search tool in Advanced eDiscovery search for and collect live data from the custodial data sources (and non-custodial data sources, if applicable) that may be relevant to the case.</span></span>

- <span data-ttu-id="1f56d-118">**Обработка.**</span><span class="sxs-lookup"><span data-stu-id="1f56d-118">**Processing.**</span></span> <span data-ttu-id="1f56d-119">После сбора всех данных, соответствующих делу, следующий шаг — обработка их для дальнейшего анализа и анализа.</span><span class="sxs-lookup"><span data-stu-id="1f56d-119">After you've collected all data relevant to the case, the next step is process it for further review and analysis.</span></span> <span data-ttu-id="1f56d-120">В advanced eDiscovery данные на месте, которые вы идентифицировали на этапе сбора, копируется в расположение Хранилища Azure (называемый набором обзоров), которое предоставляет статическое представление данных о случае.</span><span class="sxs-lookup"><span data-stu-id="1f56d-120">In Advanced eDiscovery, the in-place data that you identified in the collection phase is copied to an Azure Storage location (called a *review set*), which provides you with a static view of the case data.</span></span> 

- <span data-ttu-id="1f56d-121">**Обзор.**</span><span class="sxs-lookup"><span data-stu-id="1f56d-121">**Review.**</span></span> <span data-ttu-id="1f56d-122">После того как данные были добавлены в набор отзывов, можно просмотреть конкретные документы и запустить дополнительные запросы, чтобы уменьшить количество данных до наиболее релевантной для дела.</span><span class="sxs-lookup"><span data-stu-id="1f56d-122">After data has been added to a review set, you can view specific documents and run additional queries to reduce the data to what is most relevant to the case.</span></span> <span data-ttu-id="1f56d-123">Кроме того, можно аннотировать и теги определенных документов.</span><span class="sxs-lookup"><span data-stu-id="1f56d-123">Also, can annotate and tag specific documents.</span></span>

- <span data-ttu-id="1f56d-124">**Анализ.**</span><span class="sxs-lookup"><span data-stu-id="1f56d-124">**Analysis.**</span></span> <span data-ttu-id="1f56d-125">Advanced eDiscovery предоставляет интегрированный инструмент аналитики, который помогает дополнительно отодвигать данные из набора отзывов, которые, как вы определили, не имеют отношения к расследованию.</span><span class="sxs-lookup"><span data-stu-id="1f56d-125">Advanced eDiscovery provides integrated analytics tool that helps you further cull data from the review set that you determine isn't relevant to the investigation.</span></span> <span data-ttu-id="1f56d-126">Помимо сокращения объема соответствующих данных, advance eDiscovery также помогает сэкономить затраты на юридический обзор, позволяя организовать контент, чтобы сделать процесс проверки проще и эффективнее.</span><span class="sxs-lookup"><span data-stu-id="1f56d-126">In addition to reducing the volume of relevant data, Advance eDiscovery also helps you save legal review costs by letting you organize content to make the review process easier and more efficient.</span></span>

- <span data-ttu-id="1f56d-127">**Производство** и **презентация.**</span><span class="sxs-lookup"><span data-stu-id="1f56d-127">**Production** and **Presentation.**</span></span> <span data-ttu-id="1f56d-128">Когда вы будете готовы, вы можете экспортировать документы из набора отзывов для юридической проверки.</span><span class="sxs-lookup"><span data-stu-id="1f56d-128">When you're ready, you can export documents from a review set for legal review.</span></span> <span data-ttu-id="1f56d-129">Документы можно экспортировать в родном формате или в указанном EDRM формате, чтобы они могли быть импортироваться в сторонние приложения для проверки.</span><span class="sxs-lookup"><span data-stu-id="1f56d-129">You can export documents in their native format or in an EDRM-specified format so they can be imported into third-party review applications.</span></span>

## <a name="more-information"></a><span data-ttu-id="1f56d-130">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="1f56d-130">More information</span></span>

<span data-ttu-id="1f56d-131">Чтобы начать работу с расширенным электронным открытием, см.:</span><span class="sxs-lookup"><span data-stu-id="1f56d-131">To get started using Advanced eDiscovery, see:</span></span>

- [<span data-ttu-id="1f56d-132">Настройка Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1f56d-132">Set up Advanced eDiscovery</span></span>](get-started-with-advanced-ediscovery.md)

- [<span data-ttu-id="1f56d-133">Создание и управление случаем advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1f56d-133">Create and manage an Advanced eDiscovery case</span></span>](create-and-manage-advanced-ediscoveryv2-case.md)