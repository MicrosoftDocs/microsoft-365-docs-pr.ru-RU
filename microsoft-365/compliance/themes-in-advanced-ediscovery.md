---
title: Темы — eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Используйте темы в Advanced eDiscovery для организации наборов проверки, найдя главную тему в каждом документе.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285535"
---
# <a name="themes-in-advanced-ediscovery"></a><span data-ttu-id="558c9-103">Темы в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="558c9-103">Themes in Advanced eDiscovery</span></span>

<span data-ttu-id="558c9-104">Как человек пишет документ?</span><span class="sxs-lookup"><span data-stu-id="558c9-104">How does a person write a document?</span></span> <span data-ttu-id="558c9-105">Как правило, они начинаются с одной или более идей, которые они хотят передать в документе, и составляют их, используя слова, соответствующие идеям.</span><span class="sxs-lookup"><span data-stu-id="558c9-105">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="558c9-106">Чем распространена идея, тем чаще чаще используются слова, связанные с этой идею.</span><span class="sxs-lookup"><span data-stu-id="558c9-106">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="558c9-107">Это также сообщает о том, как люди будут использовать документы.</span><span class="sxs-lookup"><span data-stu-id="558c9-107">This informs how people consume documents as well.</span></span> <span data-ttu-id="558c9-108">При чтении документа важно понимать идеи, которые документ пытается передать, какие идеи отображаются в этом месте и каковы связи между идеями.</span><span class="sxs-lookup"><span data-stu-id="558c9-108">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="558c9-109">Это может быть расширено до того, как человек хочет использовать набор документов.</span><span class="sxs-lookup"><span data-stu-id="558c9-109">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="558c9-110">Они хотят увидеть, какие идеи присутствуют в наборах и какие документы говорят об этих идеях.</span><span class="sxs-lookup"><span data-stu-id="558c9-110">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="558c9-111">Кроме того, если они находят нужный документ, они хотят иметь возможность видеть документы, в которые обсуждаются похожие идеи.</span><span class="sxs-lookup"><span data-stu-id="558c9-111">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="558c9-112">Функция "Темы" в Advanced eDiscovery пытается имитировать причину работы  с документами, анализируя темы, которые обсуждаются в наборе для проверки, и назначая тему документам в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="558c9-112">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="558c9-113">В Advanced eDiscovery темы на один шаг дальше и определяют доминантную тему *в* каждом документе.</span><span class="sxs-lookup"><span data-stu-id="558c9-113">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="558c9-114">Доминантная тема — это тема, которая чаще всего отображается в документе.</span><span class="sxs-lookup"><span data-stu-id="558c9-114">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="558c9-115">Как работают темы?</span><span class="sxs-lookup"><span data-stu-id="558c9-115">How does Themes work?</span></span>

<span data-ttu-id="558c9-116">Функции "Темы" анализируют документы с текстом в наборе для анализа распространенных тем, которые отображаются во всех документах в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="558c9-116">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="558c9-117">Advanced eDiscovery назначает эти темы документам, в которых они отображаются.</span><span class="sxs-lookup"><span data-stu-id="558c9-117">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="558c9-118">В ней также пометка каждой темы со словами, используемыми в документах, которые являются представителем темы.</span><span class="sxs-lookup"><span data-stu-id="558c9-118">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="558c9-119">Поскольку документ может содержать различные типы тем, Advanced eDiscovery часто назначает документы нескольким темам.</span><span class="sxs-lookup"><span data-stu-id="558c9-119">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="558c9-120">Тема, которая наиболее заметно отображается в документе, обозначена в качестве основной темы.</span><span class="sxs-lookup"><span data-stu-id="558c9-120">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
