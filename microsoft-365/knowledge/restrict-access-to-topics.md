---
title: Ограничение доступа к темам
description: Как исключить разделы, чтобы предотвратить их обнаружение.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: b23d01585d9282132d9e55c74bb22bcdc6ca314a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699067"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a><span data-ttu-id="54b52-103">Ограничение доступа к темам в разделе "Возможности"</span><span class="sxs-lookup"><span data-stu-id="54b52-103">Restrict access to topics in Topic Experiences</span></span>

<span data-ttu-id="54b52-104">В разделе "Опыт" заинтересованным лицам в вашей организации может потребоваться убедиться, что определенные темы не будут обнаружены и не будут открыты для лицензированных пользователей.</span><span class="sxs-lookup"><span data-stu-id="54b52-104">In Topic Experiences, stakeholders in your organization may want to make sure that specific topics are not discovered and exposed to your licensed users.</span></span> <span data-ttu-id="54b52-105">Например, возможно, вы работаете над проектом, сведения о нем пока не нужны.</span><span class="sxs-lookup"><span data-stu-id="54b52-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="54b52-106">Несмотря на то что разрешения Office 365 на сайтах, файлах и других ресурсах не смогут просматривать конфиденциальную информацию в темах, существуют дополнительные средства защиты, которые предотвращают обнаружение определенных разделов.</span><span class="sxs-lookup"><span data-stu-id="54b52-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="54b52-107">Хотя администраторы знаний контролируют параметры сети знаний, чтобы предотвратить обнаружение разделов, руководители знаний и другие заинтересованные лица должны знать, как это делается, чтобы они могли совместно работать над этой темой.</span><span class="sxs-lookup"><span data-stu-id="54b52-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to be know how this is done so that they can work collaboratively on this.</span></span>

> [!Important] 
> <span data-ttu-id="54b52-108">В этой статье описаны способы предотвращения идентифицирования тем с помощью ИИ или просмотра в вашей среде в качестве дополнительной меры безопасности.</span><span class="sxs-lookup"><span data-stu-id="54b52-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="54b52-109">Важно отметить, что в разделе "Возможности для тем" пользователям не разрешено просматривать что-либо в теме, к чему им не разрешен доступ с помощью разрешений Office 365.</span><span class="sxs-lookup"><span data-stu-id="54b52-109">It is important to note that in Topic Experiences, users are not allowed to view anything in a topic that they are not allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="54b52-110">Даже если пользователи могут просматривать раздел, его файлы, сайты и страницы, у которых нет разрешений на просмотр в Office 365, они не будут им видны.</span><span class="sxs-lookup"><span data-stu-id="54b52-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="54b52-111">Обеспечение правильности установленных разрешений для конфиденциальных файлов должно быть основной мерой безопасности.</span><span class="sxs-lookup"><span data-stu-id="54b52-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="54b52-112">Предотвращение идентифицирования тем</span><span class="sxs-lookup"><span data-stu-id="54b52-112">Prevent topics from being identified</span></span>

<span data-ttu-id="54b52-113">Администратор знаний может ограничить доступ к определенным темам, не мешая найти их при первоначальном индексации.</span><span class="sxs-lookup"><span data-stu-id="54b52-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="54b52-114">Это можно сделать двумя способами в параметрах администрирования сети знаний в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="54b52-114">There are two ways to do this in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="54b52-115">[Выберите сайты SharePoint,](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)которые необходимо исключить из обнаружения тем. Этот параметр можно использовать, чтобы запретить обход определенных сайтов SharePoint для тем.</span><span class="sxs-lookup"><span data-stu-id="54b52-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="54b52-116">[Исключить разделы по имени:](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)администраторы могут использовать этот параметр, чтобы предотвратить обнаружение определенных разделов по имени.</span><span class="sxs-lookup"><span data-stu-id="54b52-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="54b52-117">В параметрах администратора сети знаний администратор может отправить список разделов, которые необходимо исключить из CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="54b52-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="54b52-118">Можно исключить темы, которые имеют точные или частичные совпадения с именем темы.</span><span class="sxs-lookup"><span data-stu-id="54b52-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="54b52-119">Запретить просмотр тем определенными пользователями</span><span class="sxs-lookup"><span data-stu-id="54b52-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="54b52-120">Администраторы знаний также [могут выбирать, кто может просматривать разделы в организации.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)</span><span class="sxs-lookup"><span data-stu-id="54b52-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="54b52-121">Этот параметр позволяет выбрать, какие лицензированные пользователи могут просматривать все разделы.</span><span class="sxs-lookup"><span data-stu-id="54b52-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="54b52-122">Например, в пилотной среде может потребоваться разрешить просмотр тем только небольшой группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="54b52-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="54b52-123">Удаление просматриваемой темы</span><span class="sxs-lookup"><span data-stu-id="54b52-123">Remove topics from being viewed</span></span>

<span data-ttu-id="54b52-124">Менеджеры по знаниям могут удалять [разделы,](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) чтобы пользователи не могли их видеть.</span><span class="sxs-lookup"><span data-stu-id="54b52-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="54b52-125">На странице **"Управление темами"** в Центре тем менеджеры по знаниям могут отклонить определенные темы, чтобы запретить их просмотр. </span><span class="sxs-lookup"><span data-stu-id="54b52-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="54b52-126">Разделы можно удалить независимо от того, находятся ли они в рекомендуемом или подтвержденного состоянии.</span><span class="sxs-lookup"><span data-stu-id="54b52-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="54b52-127">Позднее в качестве просматриваемых тем можно при необходимости добавить удаленную статью.</span><span class="sxs-lookup"><span data-stu-id="54b52-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="54b52-128">См. также</span><span class="sxs-lookup"><span data-stu-id="54b52-128">See also</span></span>



  






