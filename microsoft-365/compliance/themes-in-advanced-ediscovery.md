---
title: Темы
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
ms.openlocfilehash: ba57a89365c2a76dec215f56d7ed0755f27be12d
ms.sourcegitcommit: caa3f681a68daf5e463093a922c3d6f378143d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "39191213"
---
# <a name="themes"></a><span data-ttu-id="9178b-102">Темы</span><span class="sxs-lookup"><span data-stu-id="9178b-102">Themes</span></span>

<span data-ttu-id="9178b-103">Как пользователь пишет документ?</span><span class="sxs-lookup"><span data-stu-id="9178b-103">How does a person write a document?</span></span> <span data-ttu-id="9178b-104">Как правило, они начинаются с одной или нескольких идей, которые необходимо передать в документ, а также состоят из слов, которые соответствуют идеям.</span><span class="sxs-lookup"><span data-stu-id="9178b-104">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="9178b-105">Более распространенная идея — более частые слова, которые связаны с этой идеей.</span><span class="sxs-lookup"><span data-stu-id="9178b-105">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="9178b-106">Это информирует, как люди используют документы.</span><span class="sxs-lookup"><span data-stu-id="9178b-106">This informs how people consume documents as well.</span></span> <span data-ttu-id="9178b-107">Важно понимать, что документ пытается передать документ, какие идеи отображаются там, где есть идеи и какие связи между идеями.</span><span class="sxs-lookup"><span data-stu-id="9178b-107">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="9178b-108">Это может быть продлено до того, как пользователь хочет использовать набор документов.</span><span class="sxs-lookup"><span data-stu-id="9178b-108">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="9178b-109">Они хотят узнать, какие идеи присутствуют в наборах, и какие документы говорят об этих идеях.</span><span class="sxs-lookup"><span data-stu-id="9178b-109">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="9178b-110">Кроме того, если у вас есть определенный документ, он будет иметь возможность просматривать документы, которые обсуждают похожие идеи.</span><span class="sxs-lookup"><span data-stu-id="9178b-110">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="9178b-111">Функции тем в Advanced eDiscovery пытаются имитировать причины людей с документами, анализируя *темы* , обсуждаемые в наборе рецензирования, и назначив темы документам в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="9178b-111">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="9178b-112">В Advanced eDiscovery темы переводятся на один шаг дальше и идентифицируют *тему* в каждом документе.</span><span class="sxs-lookup"><span data-stu-id="9178b-112">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="9178b-113">Основная тема — это элемент, который чаще всего встречается в документе.</span><span class="sxs-lookup"><span data-stu-id="9178b-113">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="9178b-114">Как работают темы?</span><span class="sxs-lookup"><span data-stu-id="9178b-114">How does Themes work?</span></span>

<span data-ttu-id="9178b-115">Функция тем анализирует документы с текстом в наборе рецензирования, чтобы анализировать общие темы, которые отображаются во всех документах в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="9178b-115">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="9178b-116">Advanced eDiscovery назначает эти темы документам, в которых они отображаются.</span><span class="sxs-lookup"><span data-stu-id="9178b-116">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="9178b-117">Кроме того, она помечает каждую тему словами, используемыми в документах, которые являются представителями темы.</span><span class="sxs-lookup"><span data-stu-id="9178b-117">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="9178b-118">Так как документ может содержать различные типы темы, Расширенное обнаружение электронных данных часто назначает документам несколько тем.</span><span class="sxs-lookup"><span data-stu-id="9178b-118">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="9178b-119">Тема, которая чаще всего отображается в документе, выделяется в качестве его доминирующей темы.</span><span class="sxs-lookup"><span data-stu-id="9178b-119">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>