---
title: Закрытие или удаление дела
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: e2719df640a202f5ad88534920ef525f6da97189
ms.sourcegitcommit: caa3f681a68daf5e463093a922c3d6f378143d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "39191174"
---
# <a name="close-or-delete-a-case"></a><span data-ttu-id="6c8e0-102">Закрытие или удаление дела</span><span class="sxs-lookup"><span data-stu-id="6c8e0-102">Close or delete a case</span></span>

<span data-ttu-id="6c8e0-103">При наличии судебного разбирательства или расследования, поддерживаемого вариантом обнаружения электронных данных, можно закрыть обращение.</span><span class="sxs-lookup"><span data-stu-id="6c8e0-103">When the legal case or investigation supported by an eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="6c8e0-104">Вот что происходит при закрытии дела:</span><span class="sxs-lookup"><span data-stu-id="6c8e0-104">Here's what happens when you close a case:</span></span>

- <span data-ttu-id="6c8e0-105">Если обращение содержит какие – либо расположения контента на удержании, эти удержания будут отключены.</span><span class="sxs-lookup"><span data-stu-id="6c8e0-105">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="6c8e0-106">Это может привести к необратимому удалению или очистке контента либо пользователем, либо автоматическим процессом, например политики удаления.</span><span class="sxs-lookup"><span data-stu-id="6c8e0-106">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="6c8e0-107">При закрытии обращения отключаются только удержания, связанные с этим обращением.</span><span class="sxs-lookup"><span data-stu-id="6c8e0-107">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="6c8e0-108">Если в расположении содержимого есть другие удержания (например, удержание для судебного разбирательства).</span><span class="sxs-lookup"><span data-stu-id="6c8e0-108">If other holds are place on a content location (such as a Litigation Hold.</span></span> <span data-ttu-id="6c8e0-109">Политика сохранения или удержание из другого случая обнаружения электронных данных.) эти удержания будут поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="6c8e0-109">a Preservation Policy, or a hold from a different eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="6c8e0-110">Обращение по-прежнему отображается на странице Обнаружение электронных данных в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="6c8e0-110">The case is still listed on the eDiscovery page in the Security & Compliance Center.</span></span> <span data-ttu-id="6c8e0-111">Сохраняются сведения, удержания, Поиск и элементы закрытого обращения.</span><span class="sxs-lookup"><span data-stu-id="6c8e0-111">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="6c8e0-112">Вы можете изменить обращение после его закрытия.</span><span class="sxs-lookup"><span data-stu-id="6c8e0-112">You can edit a case after it's closed.</span></span> <span data-ttu-id="6c8e0-113">Например, вы можете добавлять и удалять элементы, создавать поисковые запросы, экспортировать результаты поиска и подготавливать результаты поиска для анализа в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="6c8e0-113">For example, you can add or removing members, create searches, export search results, and prepare search result for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="6c8e0-114">Основное различие между активными и закрытыми случаями заключается в том, что при закрытом обращении удержания отключаются.</span><span class="sxs-lookup"><span data-stu-id="6c8e0-114">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="6c8e0-115">Чтобы закрыть ситуацию, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6c8e0-115">To close a case:</span></span>

1. <span data-ttu-id="6c8e0-116">На странице **Advanced eDiscovery (Advanced eDiscovery** ) выберите обращение, которое нужно закрыть.</span><span class="sxs-lookup"><span data-stu-id="6c8e0-116">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="6c8e0-117">На вкладке **Параметры** в разделе **сведения о варианте case**нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="6c8e0-117">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="6c8e0-118">Нажмите кнопку **Закрыть обращение**.</span><span class="sxs-lookup"><span data-stu-id="6c8e0-118">Click **Close case**.</span></span>

<span data-ttu-id="6c8e0-119">Чтобы удалить обращение:</span><span class="sxs-lookup"><span data-stu-id="6c8e0-119">To delete a case:</span></span>

1. <span data-ttu-id="6c8e0-120">На странице **Advanced eDiscovery (Advanced eDiscovery** ) выберите вариант, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="6c8e0-120">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="6c8e0-121">На вкладке **Параметры** в разделе **сведения о варианте case**нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="6c8e0-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="6c8e0-122">Нажмите кнопку **Удалить обращение**.</span><span class="sxs-lookup"><span data-stu-id="6c8e0-122">Click **Delete case**.</span></span> 
