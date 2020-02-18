---
title: Развертывание команд с тремя уровнями защиты файлов
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: Сведения о создании и настройке команд с помощью Microsoft Teams для применения различных уровней защиты информации, содержащейся в файлах.
ms.openlocfilehash: 63a4b6763165f38e1de5331324e5a7b3573ea0f1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083354"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a><span data-ttu-id="2af8a-103">Развертывание команд с тремя уровнями защиты файлов</span><span class="sxs-lookup"><span data-stu-id="2af8a-103">Deploy teams for three tiers of protection for files</span></span>

<span data-ttu-id="2af8a-104">В этой статье показано создание и развертывание базовых, конфиденциальных и строго конфиденциальных команд.</span><span class="sxs-lookup"><span data-stu-id="2af8a-104">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential teams.</span></span> <span data-ttu-id="2af8a-105">Дополнительные сведения об этих трех уровнях защиты см. в статье [Защита файлов в Microsoft Teams](secure-files-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2af8a-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>

## <a name="baseline-teams"></a><span data-ttu-id="2af8a-106">Команды базового уровня</span><span class="sxs-lookup"><span data-stu-id="2af8a-106">Baseline teams</span></span>

<span data-ttu-id="2af8a-107">Базовая защита распространяется на общедоступные и закрытые команды.</span><span class="sxs-lookup"><span data-stu-id="2af8a-107">Baseline protection includes both public and private teams.</span></span> <span data-ttu-id="2af8a-108">Обнаруживать общедоступные команды и получать к ним доступ может любой пользователь в организации.</span><span class="sxs-lookup"><span data-stu-id="2af8a-108">Public teams can be discovered and accessed by anybody in the organization.</span></span> <span data-ttu-id="2af8a-109">Частный сайт могут найти и открыть только члены группы Office 365, связанной с этой командой.</span><span class="sxs-lookup"><span data-stu-id="2af8a-109">Private sites can only be discovered and accessed by members of the Office 365 group associated with the team.</span></span> <span data-ttu-id="2af8a-110">Оба типа команд позволяют участникам делиться содержимым сайта.</span><span class="sxs-lookup"><span data-stu-id="2af8a-110">Both of these types of teams allow members to share the site with others.</span></span>

### <a name="public"></a><span data-ttu-id="2af8a-111">Общедоступное</span><span class="sxs-lookup"><span data-stu-id="2af8a-111">Public</span></span>

<span data-ttu-id="2af8a-112">Следуйте инструкциям, приведенным в [этой статье](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b), чтобы создать команду базового уровня с открытым доступом и соответствующими разрешениями.</span><span class="sxs-lookup"><span data-stu-id="2af8a-112">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline Team with public access and permissions.</span></span>

<span data-ttu-id="2af8a-113">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="2af8a-113">Here is your resulting configuration.</span></span>

![Базовый уровень защиты для общедоступной команды.](../../media/baseline-public-team.png)

### <a name="private"></a><span data-ttu-id="2af8a-115">Личные сведения</span><span class="sxs-lookup"><span data-stu-id="2af8a-115">Private</span></span>

<span data-ttu-id="2af8a-116">Следуйте инструкциям, приведенным в [этой статье](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b), чтобы создать команду базового уровня с закрытым доступом и соответствующими разрешениями.</span><span class="sxs-lookup"><span data-stu-id="2af8a-116">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline Team with private access and permissions.</span></span>

<span data-ttu-id="2af8a-117">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="2af8a-117">Here is your resulting configuration.</span></span>

![Базовый уровень защиты для закрытой команды.](../../media/baseline-private-team.png)

## <a name="sensitive-teams"></a><span data-ttu-id="2af8a-119">Конфиденциальные команды</span><span class="sxs-lookup"><span data-stu-id="2af8a-119">Sensitive teams</span></span>

<span data-ttu-id="2af8a-120">Для работы с конфиденциальными командами необходимо сначала [создать закрытую команду](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="2af8a-120">For a sensitive team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="2af8a-121">После этого настройте базовый сайт SharePoint таким образом, чтобы предотвратить общий доступ к нему для участников команды.</span><span class="sxs-lookup"><span data-stu-id="2af8a-121">Next, you configure the underlying SharePoint site to prevent sharing by team members.</span></span>

1. <span data-ttu-id="2af8a-122">На панели инструментов команды щелкните **Файлы**.</span><span class="sxs-lookup"><span data-stu-id="2af8a-122">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="2af8a-123">Щелкните многоточие, а затем — **Открыть в SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="2af8a-123">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="2af8a-124">На панели инструментов базового сайта SharePoint щелкните значок параметров и выберите вариант **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="2af8a-124">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="2af8a-125">В области **Разрешения для сайта** в разделе **Параметры общего доступа** щелкните **Изменить параметры общего доступа**.</span><span class="sxs-lookup"><span data-stu-id="2af8a-125">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="2af8a-126">В разделе **Разрешения на предоставление общего доступа** выберите **Только владельцы сайта могут делиться файлами, папками и сайтом** и щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2af8a-126">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="2af8a-127">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="2af8a-127">Here is your resulting configuration.</span></span>

![Конфиденциальный уровень защиты для команды.](../../media/sensitive-team.png)

## <a name="highly-confidential-teams"></a><span data-ttu-id="2af8a-129">Строго конфиденциальные команды</span><span class="sxs-lookup"><span data-stu-id="2af8a-129">Highly confidential teams</span></span>

<span data-ttu-id="2af8a-130">Для работы со строго конфиденциальными командами необходимо сначала [создать закрытую команду](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="2af8a-130">With a highly confidential team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="2af8a-131">После этого настройте базовый сайт SharePoint таким образом, чтобы предотвратить общий доступ к нему для участников команды и запретить запросы на доступ от лиц, не являющихся участниками команды.</span><span class="sxs-lookup"><span data-stu-id="2af8a-131">Next, you configure the underlying SharePoint site to prevent sharing by team members and the requesting of access by non-members of the team.</span></span>

1. <span data-ttu-id="2af8a-132">На панели инструментов команды щелкните **Файлы**.</span><span class="sxs-lookup"><span data-stu-id="2af8a-132">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="2af8a-133">Щелкните многоточие, а затем — **Открыть в SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="2af8a-133">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="2af8a-134">На панели инструментов базового сайта SharePoint щелкните значок параметров и выберите вариант **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="2af8a-134">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="2af8a-135">В области **Разрешения для сайта** в разделе **Параметры общего доступа** щелкните **Изменить параметры общего доступа**.</span><span class="sxs-lookup"><span data-stu-id="2af8a-135">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="2af8a-136">В разделе **Разрешения на предоставление общего доступа** установите флажок **Только владельцы сайта могут делиться файлами, папками и сайтом**.</span><span class="sxs-lookup"><span data-stu-id="2af8a-136">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>

6. <span data-ttu-id="2af8a-137">Отключите параметр **Разрешить запросы на доступ** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2af8a-137">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="2af8a-138">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="2af8a-138">Here is your resulting configuration.</span></span>

![Строго конфиденциальный уровень защиты для команды.](../../media/highly-confidential-team.png)

## <a name="next-step"></a><span data-ttu-id="2af8a-140">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="2af8a-140">Next step</span></span>

[<span data-ttu-id="2af8a-141">Защита файлов в командах с помощью меток хранения и политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="2af8a-141">Protect files in teams with retention labels and DLP</span></span>](deploy-teams-retention-DLP.md)

## <a name="see-also"></a><span data-ttu-id="2af8a-142">См. также</span><span class="sxs-lookup"><span data-stu-id="2af8a-142">See also</span></span>

[<span data-ttu-id="2af8a-143">Защита файлов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2af8a-143">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)

[<span data-ttu-id="2af8a-144">Освоение облака и гибридные решения</span><span class="sxs-lookup"><span data-stu-id="2af8a-144">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
