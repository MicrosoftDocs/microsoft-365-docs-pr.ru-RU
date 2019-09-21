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
ms.openlocfilehash: 30697bfafdd7db69444b97345733f3d8ec5be92a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37089843"
---
# <a name="close-or-delete-a-case"></a><span data-ttu-id="69640-102">Закрытие или удаление дела</span><span class="sxs-lookup"><span data-stu-id="69640-102">Close or delete a case</span></span>

<span data-ttu-id="69640-103">При наличии судебного разбирательства или расследования, поддерживаемого вариантом обнаружения электронных данных, можно закрыть обращение.</span><span class="sxs-lookup"><span data-stu-id="69640-103">When the legal case or investigation supported by an eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="69640-104">Вот что происходит при закрытии дела:</span><span class="sxs-lookup"><span data-stu-id="69640-104">Here's what happens when you close a case:</span></span>

- <span data-ttu-id="69640-105">Если обращение содержит какие – либо расположения контента на удержании, эти удержания будут отключены.</span><span class="sxs-lookup"><span data-stu-id="69640-105">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="69640-106">Это может привести к необратимому удалению или очистке контента либо пользователем, либо автоматическим процессом, например политики удаления.</span><span class="sxs-lookup"><span data-stu-id="69640-106">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="69640-107">При закрытии обращения отключаются только удержания, связанные с этим обращением.</span><span class="sxs-lookup"><span data-stu-id="69640-107">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="69640-108">Если в расположении содержимого есть другие удержания (например, удержание для судебного разбирательства).</span><span class="sxs-lookup"><span data-stu-id="69640-108">If other holds are place on a content location (such as a Litigation Hold.</span></span> <span data-ttu-id="69640-109">Политика сохранения или удержание из другого случая обнаружения электронных данных.) эти удержания будут поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="69640-109">a Preservation Policy, or a hold from a different eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="69640-110">Обращение по-прежнему отображается на странице Обнаружение электронных данных в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="69640-110">The case is still listed on the eDiscovery page in the Security & Compliance Center.</span></span> <span data-ttu-id="69640-111">Сохраняются сведения, удержания, Поиск и элементы закрытого обращения.</span><span class="sxs-lookup"><span data-stu-id="69640-111">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="69640-112">Вы можете изменить обращение после его закрытия.</span><span class="sxs-lookup"><span data-stu-id="69640-112">You can edit a case after it's closed.</span></span> <span data-ttu-id="69640-113">Например, вы можете добавлять и удалять элементы, создавать поисковые запросы, экспортировать результаты поиска и подготавливать результаты поиска для анализа в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="69640-113">For example, you can add or removing members, create searches, export search results, and prepare search result for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="69640-114">Основное различие между активными и закрытыми случаями заключается в том, что при закрытом обращении удержания отключаются.</span><span class="sxs-lookup"><span data-stu-id="69640-114">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="69640-115">Чтобы закрыть ситуацию, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="69640-115">To close a case:</span></span>

1. <span data-ttu-id="69640-116">На странице " **Расширенные функции обнаружения электронных** данных" перейдите к своему случаю.</span><span class="sxs-lookup"><span data-stu-id="69640-116">From the **Advanced eDiscovery** page, go to your case.</span></span>

2. <span data-ttu-id="69640-117">Перейдите в раздел **Параметры** и выберите пункт **сведения о варианте**.</span><span class="sxs-lookup"><span data-stu-id="69640-117">Go to **Settings** and select **Case Information**.</span></span> 

3. <span data-ttu-id="69640-118">Нажмите кнопку **Закрыть обращение**.</span><span class="sxs-lookup"><span data-stu-id="69640-118">Click **Close Case**.</span></span> 

<span data-ttu-id="69640-119">Чтобы удалить обращение:</span><span class="sxs-lookup"><span data-stu-id="69640-119">To delete a case:</span></span>

1. <span data-ttu-id="69640-120">На странице " **Расширенные функции обнаружения электронных** данных" перейдите к своему случаю.</span><span class="sxs-lookup"><span data-stu-id="69640-120">From the **Advanced eDiscovery** page, go to your case.</span></span>

2. <span data-ttu-id="69640-121">Перейдите в раздел **Параметры** и выберите пункт **сведения о варианте**.</span><span class="sxs-lookup"><span data-stu-id="69640-121">Go to **Settings** and select **Case Information**.</span></span> 

3. <span data-ttu-id="69640-122">Нажмите кнопку **Удалить обращение**.</span><span class="sxs-lookup"><span data-stu-id="69640-122">Click **Delete Case**.</span></span> 
