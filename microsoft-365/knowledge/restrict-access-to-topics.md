---
title: Ограничение доступа к темам в Microsoft Viva Topics
description: Как исключить темы, чтобы предотвратить их обнаружение.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: d6dfb2f7f432a40c5b6e96a9437f50ba47e23387
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500882"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a><span data-ttu-id="5562d-103">Ограничение доступа к темам в Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="5562d-103">Restrict access to topics in Microsoft Viva Topics</span></span>

<span data-ttu-id="5562d-104">В Microsoft Viva заинтересованные стороны в организации могут убедиться, что определенные темы не будут обнаружены и не будут открыты для лицензированных пользователей.</span><span class="sxs-lookup"><span data-stu-id="5562d-104">In Microsoft Viva, stakeholders in your organization may want to make sure that specific topics aren't discovered and exposed to your licensed users.</span></span> <span data-ttu-id="5562d-105">Например, вы можете работать над проектом, который пока не нужно обналичить.</span><span class="sxs-lookup"><span data-stu-id="5562d-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="5562d-106">Хотя Office 365 разрешений на сайтах, файлах и других ресурсах не позволит пользователям Topic Experiences просматривать конфиденциальные сведения в разделах, существуют дополнительные меры предосторожности, чтобы предотвратить обнаружение определенных тем.</span><span class="sxs-lookup"><span data-stu-id="5562d-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="5562d-107">Хотя администраторы знаний контролируют параметры, чтобы предотвратить обнаружение тем, руководителям знаний и другим заинтересованным сторонам необходимо знать, как это делается, чтобы они могли работать совместно.</span><span class="sxs-lookup"><span data-stu-id="5562d-107">While knowledge admins control the settings to prevent topics from being discovered, knowledge managers and other stakeholders need to know how it is done so that they can work collaboratively.</span></span>

> [!Important] 
> <span data-ttu-id="5562d-108">В этой статье описываются способы предотвращения идентифицирования тем с помощью AI или просмотра в среде в качестве дополнительной защиты безопасности.</span><span class="sxs-lookup"><span data-stu-id="5562d-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="5562d-109">Важно отметить, что в Viva Topics пользователям не разрешается просматривать что-либо в теме, доступ к Office 365 разрешений.</span><span class="sxs-lookup"><span data-stu-id="5562d-109">It is important to note that in Viva Topics, users aren't allowed to view anything in a topic that they aren't allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="5562d-110">Даже если пользователи могут просматривать тему, ее файлы, сайты и страницы, у которых нет Office 365 разрешений для просмотра, не будут видны для них.</span><span class="sxs-lookup"><span data-stu-id="5562d-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="5562d-111">Обеспечение правильного набора разрешений на конфиденциальные файлы должно быть основной гарантией безопасности.</span><span class="sxs-lookup"><span data-stu-id="5562d-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="5562d-112">Предотвращение идентифицирования тем</span><span class="sxs-lookup"><span data-stu-id="5562d-112">Prevent topics from being identified</span></span>

<span data-ttu-id="5562d-113">Администратор знаний может ограничить доступ к определенным темам, предотвращая их в начальной индексации.</span><span class="sxs-lookup"><span data-stu-id="5562d-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="5562d-114">Существует два способа решения этой задачи в настройках администрирования Viva Topics в центре Microsoft 365 администрирования.</span><span class="sxs-lookup"><span data-stu-id="5562d-114">There are two ways to do this task in the Viva Topics admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="5562d-115">[Выберите SharePoint](./topic-experiences-discovery.md#select-sharepoint-topic-sources)сайты, чтобы исключить из обнаружения темы. Этот параметр можно использовать для предотвращения обхода определенных SharePoint для тем.</span><span class="sxs-lookup"><span data-stu-id="5562d-115">[Select SharePoint sites to exclude from topic discovery](./topic-experiences-discovery.md#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="5562d-116">[Исключить темы по имени.](./topic-experiences-discovery.md#exclude-topics-by-name)Администраторы могут использовать этот параметр, чтобы предотвратить обнаружение определенных тем по имени.</span><span class="sxs-lookup"><span data-stu-id="5562d-116">[Exclude topics by name](./topic-experiences-discovery.md#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="5562d-117">В настройках администратора Viva Topics администратор может загрузить список тем, которые будут исключены в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="5562d-117">In the Viva Topics admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="5562d-118">Можно исключить темы, которые имеют точные или частичные совпадения имени темы.</span><span class="sxs-lookup"><span data-stu-id="5562d-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="5562d-119">Предотвращение просмотра тем определенными пользователями</span><span class="sxs-lookup"><span data-stu-id="5562d-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="5562d-120">Администраторы знаний также [могут выбирать, кто может просматривать темы в организации.](./topic-experiences-knowledge-rules.md)</span><span class="sxs-lookup"><span data-stu-id="5562d-120">Knowledge admins can also [select who can view topics in your organization](./topic-experiences-knowledge-rules.md).</span></span> <span data-ttu-id="5562d-121">Этот параметр позволяет выбрать, какие лицензированные пользователи могут просматривать все темы.</span><span class="sxs-lookup"><span data-stu-id="5562d-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="5562d-122">Например, в пилотной среде может потребоваться разрешить просмотр тем только небольшой группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="5562d-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="5562d-123">Удаление просмотров тем</span><span class="sxs-lookup"><span data-stu-id="5562d-123">Remove topics from being viewed</span></span>

<span data-ttu-id="5562d-124">Руководители знаний могут удалять [темы,](./manage-topics.md) чтобы пользователи больше не могли их видеть.</span><span class="sxs-lookup"><span data-stu-id="5562d-124">Knowledge managers can choose to [remove topics](./manage-topics.md) so that users can no longer see them.</span></span> <span data-ttu-id="5562d-125">На странице **Управление темами** в центре **Темы** руководители знаний могут отказаться от определенных тем, чтобы предотвратить их просмотр.</span><span class="sxs-lookup"><span data-stu-id="5562d-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="5562d-126">Темы могут быть удалены независимо от того, находятся ли они в предложенной или подтвержденной состоянии.</span><span class="sxs-lookup"><span data-stu-id="5562d-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="5562d-127">Позже удалены темы могут быть добавлены в качестве просматриваемых тем, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="5562d-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="5562d-128">См. также</span><span class="sxs-lookup"><span data-stu-id="5562d-128">See also</span></span>



