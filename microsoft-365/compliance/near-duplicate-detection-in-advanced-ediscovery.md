---
title: Обнаружение практически дубликатов — обнаружение электронных данных
f1.keywords:
- NOCSH
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
description: Используйте обнаружение практически дубликатов для группировки текстовых похожих документов при анализе данных дела в Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286025"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a><span data-ttu-id="246e7-103">Обнаружение практически дубликатов в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="246e7-103">Near duplicate detection in Advanced eDiscovery</span></span>

<span data-ttu-id="246e7-104">Рассмотрите набор документов, которые необходимо просмотреть, в которых подмножество основано на одном шаблоне и имеет в основном один и тот же язык шаблона с несколькими отличиями здесь и там.</span><span class="sxs-lookup"><span data-stu-id="246e7-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="246e7-105">Если рецензент может определить это подмножество, тщательно изучить один из них и проанализировать различия для остальных, он не пропустил бы никаких уникальных сведений, затеряв лишь часть времени, за который он мог бы ознакомиться со всеми документами.</span><span class="sxs-lookup"><span data-stu-id="246e7-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="246e7-106">Рядом с повторяюмися группами обнаружения текстово похожие документы вместе, чтобы сделать процесс проверки более эффективным.</span><span class="sxs-lookup"><span data-stu-id="246e7-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="246e7-107">Как это работает?</span><span class="sxs-lookup"><span data-stu-id="246e7-107">How does it work?</span></span>

<span data-ttu-id="246e7-108">При запуске обнаружения почти дубликатов система разночет каждый документ с текстом.</span><span class="sxs-lookup"><span data-stu-id="246e7-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="246e7-109">Затем он сравнивает каждый документ друг с другом, чтобы определить, превышает ли их сходство пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="246e7-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="246e7-110">В этом случае документы группироваться.</span><span class="sxs-lookup"><span data-stu-id="246e7-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="246e7-111">После того как все документы были сравнены и сгруппированы, документ из каждой группы помечается как "pivot"; При просмотре документов вы можете сначала просмотреть списку и другие документы в том же почти дублирующем наборе, уделив особое внимание различиям между этой и просматриваемой документами.</span><span class="sxs-lookup"><span data-stu-id="246e7-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
