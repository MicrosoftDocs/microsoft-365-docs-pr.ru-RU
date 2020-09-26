---
title: 'Около обнаружения повторяющихся данных: исследование данных'
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
description: При управлении расследованиями данных используйте около обнаружения повторяющихся данных для группировки документов, похожих на текст, при анализе доказательств в расследовании данных (Предварительная версия).
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 37ce968016e674ec83da536c65361d2075cf9bbb
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285955"
---
# <a name="near-duplicate-detection"></a><span data-ttu-id="c8644-103">Обнаружение схожих документов (почти дубликатов)</span><span class="sxs-lookup"><span data-stu-id="c8644-103">Near duplicate detection</span></span>

<span data-ttu-id="c8644-104">Рассмотрите возможность рассмотрения набора документов, в которых подмножество основано на одном и том же шаблоне, и в основном имеет тот же стандартный язык, но здесь есть некоторые различия.</span><span class="sxs-lookup"><span data-stu-id="c8644-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="c8644-105">Если проверяющий может определить это подмножество, внимательно изучите один из них и изучите различия в оставшейся части, они не пропустили уникальную информацию, в то же время предприняла бы лишь часть времени, которая бы предприняла бы на чтение всех документов.</span><span class="sxs-lookup"><span data-stu-id="c8644-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="c8644-106">Рядом с поиском повторяющихся групп "Поиск повторяющихся текстов" — это похожие документы, позволяющие повысить эффективность процесса проверки.</span><span class="sxs-lookup"><span data-stu-id="c8644-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="c8644-107">Как это работает?</span><span class="sxs-lookup"><span data-stu-id="c8644-107">How does it work?</span></span>

<span data-ttu-id="c8644-108">Когда будет запущена функция обнаружения повторяющихся совпадений, система анализирует все документы с текстом.</span><span class="sxs-lookup"><span data-stu-id="c8644-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="c8644-109">Затем он сравнивает все документы друг с другом, чтобы определить, больше ли их сходства, чем пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="c8644-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="c8644-110">Если это так, то документы группируются вместе.</span><span class="sxs-lookup"><span data-stu-id="c8644-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="c8644-111">После того как все документы будут сравниваться и сгруппированы, документ из каждой группы помечается как "сведение". При просмотре документов сначала можно просмотреть сводную таблицу, а остальные документы — в том же расположении, что и в ходе сводной таблицы.</span><span class="sxs-lookup"><span data-stu-id="c8644-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
