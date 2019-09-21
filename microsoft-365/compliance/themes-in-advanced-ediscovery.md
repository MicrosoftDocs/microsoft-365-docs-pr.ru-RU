---
title: темы;
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
ms.openlocfilehash: b26b031b767f23504294880f4424be5042350c71
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091350"
---
# <a name="themes"></a><span data-ttu-id="488d5-102">темы;</span><span class="sxs-lookup"><span data-stu-id="488d5-102">Themes</span></span>
<span data-ttu-id="488d5-103">Как пользователь пишет документ?</span><span class="sxs-lookup"><span data-stu-id="488d5-103">How does a person write a document?</span></span> <span data-ttu-id="488d5-104">Как правило, они начинаются с одной или нескольких идей, которые необходимо передать в документ, а также состоят из слов, которые соответствуют идеям.</span><span class="sxs-lookup"><span data-stu-id="488d5-104">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="488d5-105">Более распространенная идея — более частые слова, которые связаны с этой идеей.</span><span class="sxs-lookup"><span data-stu-id="488d5-105">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="488d5-106">В этой процедуре сообщается, как люди используют документы и. важно знать, что документ пытается передать, а какие идеи и какие связи между идеями появятся в документе.</span><span class="sxs-lookup"><span data-stu-id="488d5-106">This informs how people consume documents as well; the important thing to get from reading a document is the ideas that the document is trying to convey, and which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="488d5-107">Это может быть продлено до того, как пользователь хочет использовать набор документов.</span><span class="sxs-lookup"><span data-stu-id="488d5-107">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="488d5-108">Они хотят узнать, какие идеи присутствуют в наборах, и какие документы говорят об этих идеях.</span><span class="sxs-lookup"><span data-stu-id="488d5-108">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="488d5-109">Кроме того, если у вас есть определенный документ, он будет иметь возможность просматривать документы, которые обсуждают похожие идеи.</span><span class="sxs-lookup"><span data-stu-id="488d5-109">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="488d5-110">Модуль "темы" пытается имитировать причины людей с документами, анализируя "темы", обсуждаемые в наборе рецензирования и назначая их документам.</span><span class="sxs-lookup"><span data-stu-id="488d5-110">Themes module tries to mimic how humans reason about documents, by analyzing the "themes" that are discussed in a review set and assigning them to documents.</span></span> <span data-ttu-id="488d5-111">Темы отводятся на один шаг дальше и идентифицируют документ "доминирующей темой"; Например, наиболее часто отображается тема.</span><span class="sxs-lookup"><span data-stu-id="488d5-111">Themes goes one step further and identifies per document the "dominant theme"; i.e. the theme that appears the most.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="488d5-112">Как работают темы?</span><span class="sxs-lookup"><span data-stu-id="488d5-112">How does Themes work?</span></span>
<span data-ttu-id="488d5-113">Темы анализируют документы с текстом в наборе рецензирования, чтобы анализировать общие темы, которые отображаются в документах.</span><span class="sxs-lookup"><span data-stu-id="488d5-113">Themes analyzes documents with text in a review set to parse out common themes that appear accross the documents.</span></span> <span data-ttu-id="488d5-114">Затем эти темы присваиваются документам, в которых они отображаются.</span><span class="sxs-lookup"><span data-stu-id="488d5-114">Then, it assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="488d5-115">Кроме того, он помечает все слова, используемые в документах, которые являются представителями темы.</span><span class="sxs-lookup"><span data-stu-id="488d5-115">It also labels each with words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="488d5-116">Так как документ может содержать более одного субъекта, во многих случаях для документа назначено несколько тем.</span><span class="sxs-lookup"><span data-stu-id="488d5-116">Since a document can be about more than one subject matter, in many cases a document has more than one themes assigned to it.</span></span> <span data-ttu-id="488d5-117">Тема, которая чаще всего отображается в документе, выделяется в качестве его доминирующей темы.</span><span class="sxs-lookup"><span data-stu-id="488d5-117">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>