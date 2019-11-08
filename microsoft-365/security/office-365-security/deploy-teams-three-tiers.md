---
title: Развертывание команд с тремя уровнями защиты файлов
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
ms.openlocfilehash: 263a787eb7f1fa8289a127816c6f8df60960feda
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925860"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a><span data-ttu-id="a92c1-103">Развертывание команд с тремя уровнями защиты файлов</span><span class="sxs-lookup"><span data-stu-id="a92c1-103">Deploy teams for three tiers of protection for files</span></span>

<span data-ttu-id="a92c1-104">В этой статье показано создание и развертывание базовых, конфиденциальных и строго конфиденциальных команд.</span><span class="sxs-lookup"><span data-stu-id="a92c1-104">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential SharePoint Online team sites.</span></span> <span data-ttu-id="a92c1-105">Дополнительные сведения об этих трех уровнях защиты см. в статье [Защита файлов в Microsoft Teams](secure-files-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="a92c1-105">For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](secure-files-in-teams.md).</span></span>
  
## <a name="baseline-teams"></a><span data-ttu-id="a92c1-106">Команды базового уровня</span><span class="sxs-lookup"><span data-stu-id="a92c1-106">Baseline teams</span></span>

<span data-ttu-id="a92c1-107">Базовая защита распространяется на общедоступные и закрытые команды.</span><span class="sxs-lookup"><span data-stu-id="a92c1-107">Baseline protection includes both public and private team sites.</span></span> <span data-ttu-id="a92c1-108">Обнаруживать общедоступные команды и получать к ним доступ может любой пользователь в организации.</span><span class="sxs-lookup"><span data-stu-id="a92c1-108">Public sites can be discovered and accessed by anybody in the organization.</span></span> <span data-ttu-id="a92c1-109">Частный сайт могут найти и открыть только члены группы Office 365, связанной с этой командой.</span><span class="sxs-lookup"><span data-stu-id="a92c1-109">Private sites can only be discovered and accessed by members of the Office 365 group associated with the team site.</span></span> <span data-ttu-id="a92c1-110">Оба типа команд позволяют участникам делиться содержимым сайта.</span><span class="sxs-lookup"><span data-stu-id="a92c1-110">Both of these types of team sites allow members to share the site with others.</span></span>
  
### <a name="public"></a><span data-ttu-id="a92c1-111">Общедоступная группа</span><span class="sxs-lookup"><span data-stu-id="a92c1-111">Public</span></span>

<span data-ttu-id="a92c1-112">Следуйте инструкциям, приведенным в [этой статье](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b), чтобы создать команду базового уровня с открытым доступом и соответствующими разрешениями.</span><span class="sxs-lookup"><span data-stu-id="a92c1-112">Follow the instructions in [this article](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline team with public access and permissions.</span></span>

<span data-ttu-id="a92c1-113">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="a92c1-113">Here is your resulting configuration.</span></span>
  
![Базовый уровень защиты для общедоступной команды.](../media/baseline-public-team.png)
  
### <a name="private"></a><span data-ttu-id="a92c1-115">Закрытая группа</span><span class="sxs-lookup"><span data-stu-id="a92c1-115">Private</span></span>

<span data-ttu-id="a92c1-116">Следуйте инструкциям, приведенным в [этой статье](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b), чтобы создать команду базового уровня с закрытым доступом и соответствующими разрешениями.</span><span class="sxs-lookup"><span data-stu-id="a92c1-116">Follow the instructions in [this article](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline team with private access and permissions.</span></span>

<span data-ttu-id="a92c1-117">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="a92c1-117">Here is your resulting configuration.</span></span>

![Базовый уровень защиты для закрытой команды.](../media/baseline-private-team.png)
  
## <a name="sensitive-teams"></a><span data-ttu-id="a92c1-119">Конфиденциальные команды</span><span class="sxs-lookup"><span data-stu-id="a92c1-119">Sensitive teams</span></span>

<span data-ttu-id="a92c1-120">Для работы с конфиденциальными командами необходимо сначала [создать закрытую команду](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="a92c1-120">For a sensitive team, you start by [creating a private team](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="a92c1-121">После этого настройте базовый сайт SharePoint таким образом, чтобы предотвратить общий доступ к нему для участников команды.</span><span class="sxs-lookup"><span data-stu-id="a92c1-121">Next, you configure the underlying SharePoint site to prevent sharing by team members.</span></span>

1.  <span data-ttu-id="a92c1-122">На панели инструментов команды щелкните **Файлы**.</span><span class="sxs-lookup"><span data-stu-id="a92c1-122">In the tool bar for the team, click **Files**.</span></span>
2.  <span data-ttu-id="a92c1-123">Щелкните многоточие, а затем **Открыть в SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a92c1-123">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
3.  <span data-ttu-id="a92c1-124">На панели инструментов базового сайта SharePoint щелкните значок параметров и выберите вариант **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="a92c1-124">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
4.  <span data-ttu-id="a92c1-125">В области **Разрешения для сайта** в разделе **Параметры общего доступа** щелкните **Изменить параметры общего доступа**.</span><span class="sxs-lookup"><span data-stu-id="a92c1-125">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
5.  <span data-ttu-id="a92c1-126">В разделе **Разрешения на предоставление общего доступа** выберите **Только владельцы сайта могут делиться файлами, папками и сайтом** и щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a92c1-126">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>

<span data-ttu-id="a92c1-127">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="a92c1-127">Here is your resulting configuration.</span></span>
  
![Конфиденциальный уровень защиты для команды.](../media/sensitive-team.png)
 

## <a name="highly-confidential-teams"></a><span data-ttu-id="a92c1-129">Строго конфиденциальные команды</span><span class="sxs-lookup"><span data-stu-id="a92c1-129">Highly confidential teams</span></span>

<span data-ttu-id="a92c1-130">Для работы со строго конфиденциальными командами необходимо сначала [создать закрытую команду](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="a92c1-130">With a highly confidential team, you start by [creating a private team](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="a92c1-131">После этого настройте базовый сайт SharePoint таким образом, чтобы предотвратить общий доступ к нему для участников команды и запретить запросы на доступ от лиц, не являющихся участниками команды.</span><span class="sxs-lookup"><span data-stu-id="a92c1-131">Next, you configure the underlying SharePoint site to prevent sharing by team members and the requesting of access by non-members of the team.</span></span>

1.  <span data-ttu-id="a92c1-132">На панели инструментов команды щелкните **Файлы**.</span><span class="sxs-lookup"><span data-stu-id="a92c1-132">In the tool bar for the team, click **Files**.</span></span>
2.  <span data-ttu-id="a92c1-133">Щелкните многоточие, а затем **Открыть в SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a92c1-133">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
3.  <span data-ttu-id="a92c1-134">На панели инструментов базового сайта SharePoint щелкните значок параметров и выберите вариант **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="a92c1-134">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
4.  <span data-ttu-id="a92c1-135">В области **Разрешения для сайта** в разделе **Параметры общего доступа** щелкните **Изменить параметры общего доступа**.</span><span class="sxs-lookup"><span data-stu-id="a92c1-135">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
5.  <span data-ttu-id="a92c1-136">В разделе **Разрешения на предоставление общего доступа** установите флажок **Только владельцы сайта могут делиться файлами, папками и сайтом**.</span><span class="sxs-lookup"><span data-stu-id="a92c1-136">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
6.  <span data-ttu-id="a92c1-137">Отключите параметр **Разрешить запросы на доступ** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a92c1-137">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="a92c1-138">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="a92c1-138">Here is your resulting configuration.</span></span>
  
![Строго конфиденциальный уровень защиты для команды.](../media/highly-confidential-team.png)  
  
## <a name="next-step"></a><span data-ttu-id="a92c1-140">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="a92c1-140">Next step</span></span>

[<span data-ttu-id="a92c1-141">Защита файлов в командах с помощью меток хранения и политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="a92c1-141">Protect SharePoint Online files with retention labels and DLP</span></span>](deploy-teams-retention-DLP.md)

## <a name="see-also"></a><span data-ttu-id="a92c1-142">См. также</span><span class="sxs-lookup"><span data-stu-id="a92c1-142">See also</span></span>

[<span data-ttu-id="a92c1-143">Защита файлов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a92c1-143">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="a92c1-144">Освоение облака и гибридные решения</span><span class="sxs-lookup"><span data-stu-id="a92c1-144">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
