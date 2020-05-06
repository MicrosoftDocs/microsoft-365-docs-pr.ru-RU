---
title: Темы — обнаружение электронных данных
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
description: Используйте темы в разделе Advanced eDiscovery для упорядочения наборов рецензирования, выполнив поиск темы в каждом документе.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: eb008e091cd8c8330d1cdd5b388e252af70922da
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034523"
---
# <a name="themes"></a><span data-ttu-id="45bb1-103">Темы</span><span class="sxs-lookup"><span data-stu-id="45bb1-103">Themes</span></span>

<span data-ttu-id="45bb1-104">Как пользователь пишет документ?</span><span class="sxs-lookup"><span data-stu-id="45bb1-104">How does a person write a document?</span></span> <span data-ttu-id="45bb1-105">Как правило, они начинаются с одной или нескольких идей, которые необходимо передать в документ, а также состоят из слов, которые соответствуют идеям.</span><span class="sxs-lookup"><span data-stu-id="45bb1-105">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="45bb1-106">Более распространенная идея — более частые слова, которые связаны с этой идеей.</span><span class="sxs-lookup"><span data-stu-id="45bb1-106">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="45bb1-107">Это информирует, как люди используют документы.</span><span class="sxs-lookup"><span data-stu-id="45bb1-107">This informs how people consume documents as well.</span></span> <span data-ttu-id="45bb1-108">Важно понимать, что документ пытается передать документ, какие идеи отображаются там, где есть идеи и какие связи между идеями.</span><span class="sxs-lookup"><span data-stu-id="45bb1-108">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="45bb1-109">Это может быть продлено до того, как пользователь хочет использовать набор документов.</span><span class="sxs-lookup"><span data-stu-id="45bb1-109">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="45bb1-110">Они хотят узнать, какие идеи присутствуют в наборах, и какие документы говорят об этих идеях.</span><span class="sxs-lookup"><span data-stu-id="45bb1-110">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="45bb1-111">Кроме того, если у вас есть определенный документ, он будет иметь возможность просматривать документы, которые обсуждают похожие идеи.</span><span class="sxs-lookup"><span data-stu-id="45bb1-111">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="45bb1-112">Функции тем в Advanced eDiscovery пытаются имитировать причины людей с документами, анализируя *темы* , обсуждаемые в наборе рецензирования, и назначив темы документам в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="45bb1-112">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="45bb1-113">В Advanced eDiscovery темы переводятся на один шаг дальше и идентифицируют *тему* в каждом документе.</span><span class="sxs-lookup"><span data-stu-id="45bb1-113">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="45bb1-114">Основная тема — это элемент, который чаще всего встречается в документе.</span><span class="sxs-lookup"><span data-stu-id="45bb1-114">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="45bb1-115">Как работают темы?</span><span class="sxs-lookup"><span data-stu-id="45bb1-115">How does Themes work?</span></span>

<span data-ttu-id="45bb1-116">Функция тем анализирует документы с текстом в наборе рецензирования, чтобы анализировать общие темы, которые отображаются во всех документах в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="45bb1-116">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="45bb1-117">Advanced eDiscovery назначает эти темы документам, в которых они отображаются.</span><span class="sxs-lookup"><span data-stu-id="45bb1-117">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="45bb1-118">Кроме того, она помечает каждую тему словами, используемыми в документах, которые являются представителями темы.</span><span class="sxs-lookup"><span data-stu-id="45bb1-118">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="45bb1-119">Так как документ может содержать различные типы темы, Расширенное обнаружение электронных данных часто назначает документам несколько тем.</span><span class="sxs-lookup"><span data-stu-id="45bb1-119">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="45bb1-120">Тема, которая чаще всего отображается в документе, выделяется в качестве его доминирующей темы.</span><span class="sxs-lookup"><span data-stu-id="45bb1-120">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
