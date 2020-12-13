---
title: Понимание сходства документов в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: Просмотрите, как в Advanced eDiscovery работает значение сходства документов ( минимальный уровень повторного запроса двух файлов, которые считаются почти дубликатами).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 22eb27e7afdc6ad37ea6fdcba9b64298906f1c35
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663318"
---
# <a name="understand-document-similarity-in-advanced-ediscovery-classic"></a><span data-ttu-id="32058-103">Понимание сходства документов в Advanced eDiscovery (классическая)</span><span class="sxs-lookup"><span data-stu-id="32058-103">Understand document similarity in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="32058-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="32058-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="32058-106">В Advanced eDiscovery сходство документов — это минимальный уровень повторного запроса, необходимый для того, чтобы два документа были считаться почти дубликатами.</span><span class="sxs-lookup"><span data-stu-id="32058-106">In Advanced eDiscovery, Document Similarity is the minimal level of resemblance required for two documents to be considered as near-duplicates.</span></span>
  
> [!TIP]
> <span data-ttu-id="32058-107">Для большинства бизнес-приложений рекомендуется использовать значение similarity 60%-75%.</span><span class="sxs-lookup"><span data-stu-id="32058-107">For most business applications, it is recommended to use a Similarity value of 60%-75%.</span></span> <span data-ttu-id="32058-108">Для материала распознавания оптического (OCR) очень низкого качества можно применять более низкие значения сходства.</span><span class="sxs-lookup"><span data-stu-id="32058-108">For very poor quality optical character recognition (OCR) material, lower Similarity values can be applied.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="32058-109">После того как он задан и запустится для данного случая, значение similarity нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="32058-109">After it's set and run for a given case, the Similarity value cannot be changed.</span></span> 
  
<span data-ttu-id="32058-110">В наборе почти дубликатов (ND) могут быть документы с уровнем повторного перенастройки ниже порогового значения сходства.</span><span class="sxs-lookup"><span data-stu-id="32058-110">Within a Near-duplicate (ND) set, there may be documents with a level of resemblance below the Similarity threshold.</span></span> <span data-ttu-id="32058-111">Чтобы документ присоединяется к набору ND, в наборе ND должен быть по крайней мере один документ с уровнем повторного перенастройки, превышающий схожесть.</span><span class="sxs-lookup"><span data-stu-id="32058-111">For a document to join an ND set, there must be at least one document in the ND set with a level of resemblance exceeding the Similarity.</span></span> 
  
<span data-ttu-id="32058-112">Например, предположим, что для сходства установлено 80 %, документ F1 похож на документ F2 на уровне 85 %, а документ F2 похож на документ F3 на уровне 90%.</span><span class="sxs-lookup"><span data-stu-id="32058-112">For example, assume the Similarity is set to 80%, document F1 resembles document F2 at a level of 85%, and document F2 resembles document F3 at a level of 90%.</span></span> 
  
<span data-ttu-id="32058-113">Однако документ F1 может напоминать документ F3 на уровне только 70 %, что ниже порогового значения.</span><span class="sxs-lookup"><span data-stu-id="32058-113">However, document F1 may resemble document F3 at a level of only 70%, which is below the threshold.</span></span> <span data-ttu-id="32058-114">Тем не менее в этом примере все документы F1, F2 и F3 отображаются в одном наборе ND.</span><span class="sxs-lookup"><span data-stu-id="32058-114">Nonetheless, in this example, documents F1, F2, and F3 all appear in the one ND set.</span></span> <span data-ttu-id="32058-115">Аналогичным образом, используя значение similarity 80%, мы могли создать два набора, EquiSet-1 и EquiSet-2.</span><span class="sxs-lookup"><span data-stu-id="32058-115">Similarly, using a Similarity value of 80%, we may have created two sets, EquiSet-1 and EquiSet-2.</span></span> <span data-ttu-id="32058-116">EquiSet-1 содержит документы E1 и E2.</span><span class="sxs-lookup"><span data-stu-id="32058-116">EquiSet-1 contains documents E1 and E2.</span></span> <span data-ttu-id="32058-117">Equiset-2 содержит документы F1, F2 и F3.</span><span class="sxs-lookup"><span data-stu-id="32058-117">Equiset-2 contains documents F1, F2, and F3.</span></span> 
  
<span data-ttu-id="32058-118">Уровни повторного иллюстрированы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="32058-118">The levels of resemblance are illustrated as follows:</span></span>
  
![Схожесть документов](../media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
<span data-ttu-id="32058-120">Предположим, что теперь вставляется другой документ, X1.</span><span class="sxs-lookup"><span data-stu-id="32058-120">Assume that another document, X1, is now inserted.</span></span> <span data-ttu-id="32058-121">Разница между X1 и E3 составляет 87 %.</span><span class="sxs-lookup"><span data-stu-id="32058-121">The resemblance between X1 and E3 is 87%.</span></span> <span data-ttu-id="32058-122">Аналогичным образом, между X1 и F1 имеется 92 %.</span><span class="sxs-lookup"><span data-stu-id="32058-122">Similarly, the resemblance between X1 and F1 is 92%.</span></span> <span data-ttu-id="32058-123">В результате EquiSet -1, EquiSet -2 и X1 теперь объединяются в один набор ND.</span><span class="sxs-lookup"><span data-stu-id="32058-123">As a result, EquiSet -1, EquiSet -2, and X1 are now combined into one ND set.</span></span>
  
![Похожесть документов](../media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> <span data-ttu-id="32058-125">Если какие-либо два документа назначены одному набору ND, они останутся вместе в том же наборе, даже если в набор добавляются дополнительные документы или если наборы объединены.</span><span class="sxs-lookup"><span data-stu-id="32058-125">If any two documents are assigned to one ND set, they will remain together in the same ND set, even if additional documents are added to the set or if the sets are merged.</span></span> 
  
<span data-ttu-id="32058-126">После слияния наборов документ Pivot может изменяться при добавлении новых документов в набор.</span><span class="sxs-lookup"><span data-stu-id="32058-126">After sets are merged, the Pivot document can change when new documents are added to a set.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="32058-127">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="32058-127">Related topics</span></span>

[<span data-ttu-id="32058-128">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="32058-128">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="32058-129">Настройка параметров анализа</span><span class="sxs-lookup"><span data-stu-id="32058-129">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="32058-130">Настройка игнорирования текста</span><span class="sxs-lookup"><span data-stu-id="32058-130">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="32058-131">Настройка дополнительных параметров анализа</span><span class="sxs-lookup"><span data-stu-id="32058-131">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="32058-132">Просмотр результатов анализа</span><span class="sxs-lookup"><span data-stu-id="32058-132">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

