---
title: Управление настройкой релевантности в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
description: Прочтите рекомендации по настройке обучения релевантности в Advanced eDiscovery для оценки файлов по их релевантности и получения результатов анализа.
ms.openlocfilehash: a6bec149e11fa80fb57cb811120218fa7f2cc45b
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662874"
---
# <a name="manage-relevance-setup-in-advanced-ediscovery-classic"></a><span data-ttu-id="82e7e-103">Управление настройкой релевантности в Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="82e7e-103">Manage Relevance setup in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="82e7e-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="82e7e-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="82e7e-p102">Технология релевантности Advanced eDiscovery предусматривает наличие управляемого специалистами программного обеспечения для оценки файлов по их релевантности. Эту технологию можно применять для скорейшей оценки дел (ECA), отбора и просмотра примеров файлов.</span><span class="sxs-lookup"><span data-stu-id="82e7e-p102">Advanced eDiscovery Relevance technology employs expert-guided software for scoring files by their relevance. Advanced eDiscovery Relevance can be used for Early Case Assessment (ECA), culling, and file sample review.</span></span> 
  
 <span data-ttu-id="82e7e-p103">Advanced eDiscovery включает компоненты, позволяющие выполнять обучение релевантности и расстановку тегов для файлов, относящихся к делу. Advanced eDiscovery обучается на примерах релевантных и нерелевантных файлов, чтобы предоставлять оценку релевантности для каждого файла, и выводит результаты анализа, которые можно применять в процессе проверки файлов и после него.</span><span class="sxs-lookup"><span data-stu-id="82e7e-p103">Advanced eDiscovery includes components for the Relevance training and tagging of files relevant to a case. Advanced eDiscovery learns from the trained samples of Relevant and Not Relevant files to provide Relevance scores for each file, and generates analytical results that can be used during and after the file review process.</span></span> 
  
## <a name="guidelines-for-setting-up-relevance-training"></a><span data-ttu-id="82e7e-110">Рекомендации по настройке обучения релевантности</span><span class="sxs-lookup"><span data-stu-id="82e7e-110">Guidelines for setting up Relevance training</span></span>

 <span data-ttu-id="82e7e-p104">Откройте Advanced eDiscovery, в окне **Дела** выберите дело и щелкните **Перейти к делу**. Щелкните **Релевантность** \> **Настройка релевантности**. Воспользуйтесь этими рекомендациями по настройке релевантности.</span><span class="sxs-lookup"><span data-stu-id="82e7e-p104">In Advance eDiscovery, in the **Cases** window, select a case and click **Go to case**. Click **Relevance** \> **Relevance setup**. Follow these recommended guidelines to set up Relevance.</span></span> 
  
- <span data-ttu-id="82e7e-114">**Расстановка тегов.** Эффективность итеративного процесса обучения релевантности зависит от того, будет ли специалист добавлять теги к примерам файлов точно и согласованно.</span><span class="sxs-lookup"><span data-stu-id="82e7e-114">**Tagging**: The effectiveness of the iterative Relevance training process is dependent on the ability of the expert to tag the file samples with precision and consistency.</span></span>

- <span data-ttu-id="82e7e-115">**Вопросы для дел**.</span><span class="sxs-lookup"><span data-stu-id="82e7e-115">**Case issues**:</span></span>
  
  - <span data-ttu-id="82e7e-p105">С каждым таким вопросом должен работать один и тот же специалист на протяжении всего процесса обучения релевантности. Расстановка тегов для вопроса, которую выполняют одновременно несколько специалистов, не разрешается.</span><span class="sxs-lookup"><span data-stu-id="82e7e-p105">For each issue, use the same expert throughout the entire Relevance training process. Simultaneous tagging of the same issue by multiple experts is not permitted.</span></span>
  
  - <span data-ttu-id="82e7e-118">Определите, соответствует ли каждая группа файлов только указанному вопросу.</span><span class="sxs-lookup"><span data-stu-id="82e7e-118">Determine if each group of files is pertinent only to a specific issue.</span></span>

  - <span data-ttu-id="82e7e-p106">Если слишком обобщить формулировку вопроса, Advanced eDiscovery может предоставить слишком много нерелевантных файлов. Если слишком сузить формулировку вопроса, процесс обучения релевантности может занять больше времени.</span><span class="sxs-lookup"><span data-stu-id="82e7e-p106">If an issue is defined too generally, Advanced eDiscovery may yield too many files that are not relevant. If an issue is defined too narrowly, the Relevance training process may take more time.</span></span> 

  - <span data-ttu-id="82e7e-121">Во время каждого цикла обучения релевантности платформа Advanced eDiscovery фокусируется на одном активном вопросе, промежуточные результаты отображаются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="82e7e-121">During each Relevance training cycle, Advanced eDiscovery focuses on a single active issue and interim sample results are displayed accordingly.</span></span>

  - <span data-ttu-id="82e7e-p107">В сценарии с несколькими вопросами режим выборки позволяет выбирать вопросы, включаемые в обработку. Вопросы, определенные как "отключенные", не обрабатываются до тех пор, пока не изменится режим выборки. Вопрос может быть отмечен как "включенный" или "неактивный" только для одного специалиста.</span><span class="sxs-lookup"><span data-stu-id="82e7e-p107">In a multiple-issue scenario, the Sampling mode enables the selection of issues to be included in processing. Issues defined as "off" are not handled until their Sampling mode is changed. An issue can be "idle" or "on" for only one expert.</span></span>

  - <span data-ttu-id="82e7e-p108">Advanced eDiscovery позволяет определять файлы с потенциальным приоритетом. Укажите отдельный вопрос для приоритета. При возможности сначала выполните обучение и отбор для определения релевантности, а затем — обучение для определения приоритета только в отношении отобранного набора (повторно загрузите отобранный набор как отдельное дело).</span><span class="sxs-lookup"><span data-stu-id="82e7e-p108">Advanced eDiscovery can be used to generate candidate privilege files. Set up a separate issue for privilege. If possible, train and cull for relevance first, and then train for privilege on the culled set only (reload the culled set as a separate case).</span></span> 

  - <span data-ttu-id="82e7e-p109">Оценку пакета можно выполнять только при отсутствии открытых примеров (когда вы щелкните "Оценка пакета", отобразится список пользователей с открытыми примерами). Чтобы "закрыть" примеры других пользователей (это можно выполнить, только если для этих примеров не выполняется расстановка тегов), администратор может воспользоваться служебной программой "Изменение релевантности" с параметром "Пример всех пользователей".</span><span class="sxs-lookup"><span data-stu-id="82e7e-p109">Batch calculation can be performed only when there are no open samples (when clicking Batch Calculation, there will be a list displayed of users with open samples). To "close" samples of other users (this should be performed only if these users are not tagging these samples), an Administrator can use the "Modify relevance" utility with the "All users sample" option.</span></span>

- <span data-ttu-id="82e7e-p110">**Метаданные.** Платформа Advanced eDiscovery фокусируется на контенте. Она не включает метаданные в условия релевантности.</span><span class="sxs-lookup"><span data-stu-id="82e7e-p110">**Metadata**: Advanced eDiscovery focuses on content. It does not consider metadata as part of the relevance criteria.</span></span>

- <span data-ttu-id="82e7e-132">**Степень релевантности.** Если степень релевантности для вопроса менее 3% после оценки, рекомендуем начать обучение с файлов, которые уже определены как релевантные или как нерелевантные.</span><span class="sxs-lookup"><span data-stu-id="82e7e-132">**Richness**: If the Richness for an issue is less than 3% after Assessment, consider seeding the Relevance training with known Relevant and Not Relevant files.</span></span>

- <span data-ttu-id="82e7e-p111">**Размер файла**. Большие файлы (извлеченный текст которых содержит более 5 242 880 символов) игнорируются при оценке релевантности. Такие файлы не включены в процесс обучения релевантности, и их релевантность не оценивается при оценке пакета. Файлы, размер которых составляет более 5 МБ, можно включить в набор оценки.</span><span class="sxs-lookup"><span data-stu-id="82e7e-p111">**File size**: Large files (over 5,242,880 characters of extracted text) are ignored in Relevance. The files do not participate in the Relevance training process and do not receive a Relevance score after Batch Calculation. Files over 5 MB can be included in the Assessment set.</span></span>

## <a name="setting-up-case-issues"></a><span data-ttu-id="82e7e-136">Указание вопросов дела</span><span class="sxs-lookup"><span data-stu-id="82e7e-136">Setting up case issues</span></span>

<span data-ttu-id="82e7e-137">Чтобы получить доступ к параметрам, описанным в этом разделе, откройте Advanced eDiscovery и выберите **Релевантность** \> **Настройка релевантности**.</span><span class="sxs-lookup"><span data-stu-id="82e7e-137">The parameters described in this section are available in the Advanced eDiscovery **Relevance** \> **Relevance setup**.</span></span>
  
- <span data-ttu-id="82e7e-138">Вопросы должны назначаться пользователю, который будет проводить обучение на файлах.</span><span class="sxs-lookup"><span data-stu-id="82e7e-138">Issues must be assigned to a user who will train the files.</span></span>

- <span data-ttu-id="82e7e-139">Импортированные файлы нужно добавить к обрабатываемому полному набору.</span><span class="sxs-lookup"><span data-stu-id="82e7e-139">Imported files must then be added to the load being processed.</span></span>

- <span data-ttu-id="82e7e-140">Точно определяйте и упорядочивайте вопросы, так как это может повлиять на результаты обучения релевантности.</span><span class="sxs-lookup"><span data-stu-id="82e7e-140">Define and organize issues carefully, as this can impact the Relevance training results.</span></span>

<span data-ttu-id="82e7e-141">После настройки параметров проверяющий или специалист может начать обучение на файлах, открыв вкладку **Релевантность**.</span><span class="sxs-lookup"><span data-stu-id="82e7e-141">After parameters are set, the reviewer / expert can start training the files in the **Relevance** tab.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="82e7e-142">См. также</span><span class="sxs-lookup"><span data-stu-id="82e7e-142">See also</span></span>

[<span data-ttu-id="82e7e-143">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="82e7e-143">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="82e7e-144">Определение вопросов и назначение пользователей</span><span class="sxs-lookup"><span data-stu-id="82e7e-144">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="82e7e-145">Настройка полных пакетов для добавления импортированных файлов</span><span class="sxs-lookup"><span data-stu-id="82e7e-145">Setting up loads to add imported files</span></span>](set-up-loads-to-add-imported-files.md)
  
[<span data-ttu-id="82e7e-146">Определение выделенных ключевых слов и дополнительных параметров</span><span class="sxs-lookup"><span data-stu-id="82e7e-146">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

