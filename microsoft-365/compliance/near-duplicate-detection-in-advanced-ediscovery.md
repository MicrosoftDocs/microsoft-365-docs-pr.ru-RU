---
title: Рядом с двойным обнаружением — обнаружение электронных данных
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
description: При анализе данных о случаях в Advanced eDiscovery используйте близкое дублирование обнаружения для группового текстовых аналогичных документов.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286025"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a><span data-ttu-id="8e723-103">Рядом с обнаружением дубликата в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8e723-103">Near duplicate detection in Advanced eDiscovery</span></span>

<span data-ttu-id="8e723-104">Рассмотрим набор документов, которые необходимо просмотреть, в которых подмножество основано на одном шаблоне и имеет в основном один и тот же шаблонный язык, с несколькими различиями здесь и там.</span><span class="sxs-lookup"><span data-stu-id="8e723-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="8e723-105">Если бы рецензент мог определить этот подмножество, тщательно просмотреть один из них и проанализировать различия для остальных, он не пропустил бы ни одной уникальной информации, забирая лишь часть времени, которое заняло бы у них чтение всех документов, которые охватываются.</span><span class="sxs-lookup"><span data-stu-id="8e723-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="8e723-106">При обнаружении почти одинаковых документов текстовые документы группируются вместе, чтобы помочь вам сделать процесс проверки более эффективным.</span><span class="sxs-lookup"><span data-stu-id="8e723-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="8e723-107">Как это работает?</span><span class="sxs-lookup"><span data-stu-id="8e723-107">How does it work?</span></span>

<span data-ttu-id="8e723-108">При запуске обнаружения неполных дубликатов система анализирует каждый документ с текстом.</span><span class="sxs-lookup"><span data-stu-id="8e723-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="8e723-109">Затем он сравнивает каждый документ друг с другом, чтобы определить, превышает ли их сходство установленный порог.</span><span class="sxs-lookup"><span data-stu-id="8e723-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="8e723-110">Если это так, документы группируются вместе.</span><span class="sxs-lookup"><span data-stu-id="8e723-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="8e723-111">После того как все документы были сравнены и сгруппированы, документ из каждой группы помечается как "сводный документ". При просмотре документов можно сначала просмотреть сводный документ и просмотреть другие документы в том же наборе неполных дубликатов, сосредоточившись на разнице между сводным и проверяемым документом.</span><span class="sxs-lookup"><span data-stu-id="8e723-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
