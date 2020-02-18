---
title: Teams для строго регулируемых данных
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Создайте защищенную команду для хранения наиболее важных и конфиденциальных файлов.
ms.openlocfilehash: e2499c6e9061704846f4649ade43f74bd5632e8b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42084288"
---
# <a name="teams-for-highly-regulated-data"></a><span data-ttu-id="9bfc8-103">Teams для строго регулируемых данных</span><span class="sxs-lookup"><span data-stu-id="9bfc8-103">Teams for highly regulated data</span></span>

<span data-ttu-id="9bfc8-104">Эта статья содержит рекомендации и инструкции по настройке закрытой команды в Microsoft Teams, разрешающей доступ к функциям Teams, таким как чаты, собрания и файлы, только участникам и владельцам группы Office 365 команды.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams that locks down access to Teams features—such as chats, meetings, and files—to only members and owners of the Office 365 group for the team.</span></span> 

<span data-ttu-id="9bfc8-105">Помимо закрытого доступа на основе группы Office 365, в этой статье описывается способ настройки базового закрытого сайта группы SharePoint, доступного из раздела **Файлы** канала команды. Это обеспечивает дополнительную защиту, требующуюся для хранения строго регулируемых данных.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-105">Beyond the private access based on the Office 365 group, this article describes how to configure the underlying private SharePoint team site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span> <span data-ttu-id="9bfc8-106">На этом сайте группы SharePoint можно хранить файлы, страницы, общий календарь, задачи, записную книжку и списки, а также совместно работать над ними.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-106">On this SharePoint team site, you can store and collaborate on files, pages, a shared calendar, tasks, a notebook, and lists.</span></span>

>[!Note]
> <span data-ttu-id="9bfc8-107">Похожий сценарий, в котором используется SharePoint, см. [здесь](teams-sharepoint-online-sites-highly-regulated-data.md).</span><span class="sxs-lookup"><span data-stu-id="9bfc8-107">A similar scenario using SharePoint is [here](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
>

<span data-ttu-id="9bfc8-108">Элементы настройки команды для работы со строго регулируемыми данными:</span><span class="sxs-lookup"><span data-stu-id="9bfc8-108">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="9bfc8-109">Закрытая команда с соответствующей группой Office 365, в которой есть учетные записи владельца и участника.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-109">A private team with a corresponding Office 365 group that has owner and member user accounts.</span></span>
- <span data-ttu-id="9bfc8-110">Дополнительная защита на базовом сайте SharePoint для команды, которая:</span><span class="sxs-lookup"><span data-stu-id="9bfc8-110">Additional security on the underlying SharePoint site for the team that:</span></span>
  - <span data-ttu-id="9bfc8-111">запрещает предоставление участниками сайта доступа третьим лицам;</span><span class="sxs-lookup"><span data-stu-id="9bfc8-111">Prevents members of the site from granting access to others.</span></span>
  - <span data-ttu-id="9bfc8-112">блокирует запросы на доступ к сайту от лиц, которые не являются участниками сайта.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-112">Prevents non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="9bfc8-113">Метка хранения Office 365 для базового сайта SharePoint, автоматически применяющаяся к новым файлам сайта в качестве стандартного способа определения политик хранения.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-113">An Office 365 retention label for the underlying SharePoint site that is automatically applied to new files on the site as a default way to define retention policies.</span></span>
- <span data-ttu-id="9bfc8-114">Политика защиты от потери данных (DLP), использующая метку хранения и блокирующая предоставление пользователями общего доступа к файлам или их отправку за пределы организации.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-114">A Data Loss Prevention (DLP) policy that uses the retention label and blocks users from sharing or sending files outside the organization.</span></span>
- <span data-ttu-id="9bfc8-115">Метка конфиденциальности Office 365 или вложенная метка строго регулируемой метки с включенным шифрованием и разрешениями на совместное редактирование для группы Office 365 команды.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-115">An Office 365 sensitivity label or a sublabel of a highly regulated label that has encryption enabled and Co-Author permissions for the Office 365 group of the team.</span></span> <span data-ttu-id="9bfc8-116">Пользователи применяют метку или вложенную метку к файлам, хранящимся в разделе **Файлы** команды, из параметра строки меню **Конфиденциальность** в Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-116">Users apply the label or sublabel to files stored in **Files** section of the team from the **Sensitivity** menu bar option in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="9bfc8-117">Ниже показана итоговая конфигурация с меткой конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-117">Here is the resulting configuration with a sensitivity label.</span></span>

![Настройка сценария защищенной команды](../media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="9bfc8-119">Краткий обзор приведен в этом коротком видеоролике.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-119">For a quick overview, watch this short video.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mGHf]

<a name="poster"></a> <span data-ttu-id="9bfc8-120">Одностраничную сводку этого сценария см. на плакате [Teams для строго регулируемых данных](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf).</span><span class="sxs-lookup"><span data-stu-id="9bfc8-120">For a 1-page summary of this scenario, see the [Teams for highly regulated data poster](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf).</span></span>

<span data-ttu-id="9bfc8-121">[Плакат ![Teams для строго регулируемых данных](../media/secure-teams-highly-regulated-data-scenario/teams-highly-regulated-data-poster.png)](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)</span><span class="sxs-lookup"><span data-stu-id="9bfc8-121">[![Teams for highly regulated data poster](../media/secure-teams-highly-regulated-data-scenario/teams-highly-regulated-data-poster.png)](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)</span></span>

<span data-ttu-id="9bfc8-122">Вы также можете скачать этот плакат в формате [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf) или [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/secure-teams-highly-regulated-data-scenario/Teams-Highly-Regulated-Data-Poster.pptx) и распечатать его на бумаге размера letter, legal или tabloid (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="9bfc8-122">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/secure-teams-highly-regulated-data-scenario/Teams-Highly-Regulated-Data-Poster.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>

## <a name="phase-1-configure-a-team-for-highly-regulated-data"></a><span data-ttu-id="9bfc8-123">Этап 1. Настройка команды для строго регулируемых данных</span><span class="sxs-lookup"><span data-stu-id="9bfc8-123">Phase 1: Configure a team for highly regulated data</span></span>

<span data-ttu-id="9bfc8-124">Полная настройка состоит из следующих этапов:</span><span class="sxs-lookup"><span data-stu-id="9bfc8-124">The end-to-end configuration consists of these steps:</span></span>

1. <span data-ttu-id="9bfc8-125">Настройка удостоверений и доступа для устройств.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-125">Configure identity and device access.</span></span>
2. <span data-ttu-id="9bfc8-126">Создание закрытой команды.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-126">Create a private team.</span></span>
3. <span data-ttu-id="9bfc8-127">Настройка базового сайта SharePoint для дополнительной безопасности.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-127">Configure the underlying SharePoint site for additional security.</span></span>
4. <span data-ttu-id="9bfc8-128">Создание метки хранения и политики защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-128">Create a retention label and DLP policy.</span></span>
5. <span data-ttu-id="9bfc8-129">Создание метки или вложенной метки для метки строго регулируемых данных.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-129">Create the label or sublabel of the highly regulated label.</span></span>

### <a name="step-1-configure-identity-and-device-access"></a><span data-ttu-id="9bfc8-130">Шаг 1. Настройка удостоверений и доступа для устройств</span><span class="sxs-lookup"><span data-stu-id="9bfc8-130">Step 1: Configure identity and device access</span></span>

<span data-ttu-id="9bfc8-131">Чтобы защитить доступ к команде или ее базовому сайту SharePoint, убедитесь, что вы настроили [политики удостоверений и доступа для устройств](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies), а также рекомендуемые [политики доступа к SharePoint Online](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="9bfc8-131">To protect access to the team and its underlying SharePoint site, ensure that you have configured [identity and device access policies](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) and the recommended [SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="step-2-create-a-private-team"></a><span data-ttu-id="9bfc8-132">Шаг 2. Создание закрытой команды</span><span class="sxs-lookup"><span data-stu-id="9bfc8-132">Step 2: Create a private team</span></span>

<span data-ttu-id="9bfc8-133">Чтобы создать закрытую команду, следуйте [инструкциям](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="9bfc8-133">Use [these instructions](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a private team.</span></span>

<span data-ttu-id="9bfc8-134">При создании закрытой команды применяются следующие разрешения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="9bfc8-134">When you create a private team, here are the default permissions:</span></span>

- <span data-ttu-id="9bfc8-135">Группа Office 365 для команды (группа команды) содержит владельцев и участников групп</span><span class="sxs-lookup"><span data-stu-id="9bfc8-135">The Office 365 group for the team (the Team Group) has group owners and group members</span></span>
- <span data-ttu-id="9bfc8-136">Для базового сайта SharePoint команды (сайт команды):</span><span class="sxs-lookup"><span data-stu-id="9bfc8-136">For the underlying SharePoint site for the team (the Team Site):</span></span>
  - <span data-ttu-id="9bfc8-137">Администраторы семейства веб-сайтов настроены в качестве владельцев группы команды</span><span class="sxs-lookup"><span data-stu-id="9bfc8-137">The Site Collection Administrators is configured for the Team Group owners</span></span>
  - <span data-ttu-id="9bfc8-138">Для сайта команды:</span><span class="sxs-lookup"><span data-stu-id="9bfc8-138">For the Team Site:</span></span> 
    - <span data-ttu-id="9bfc8-139">Группа SharePoint владельцев сайта команды с уровнем разрешений "Полный доступ" настроена для владельцев группы команды</span><span class="sxs-lookup"><span data-stu-id="9bfc8-139">The Team Site Owners SharePoint group—with the Full Control permission level—is set to the Team Group owners</span></span>
    - <span data-ttu-id="9bfc8-140">Группа SharePoint участников сайта команды с уровнем разрешений "Изменить" настроена для участников группы команды</span><span class="sxs-lookup"><span data-stu-id="9bfc8-140">The Team Site Members SharePoint group—with the Edit permission level—is set to the Team Group members</span></span>
    - <span data-ttu-id="9bfc8-141">У группы SharePoint посетителей сайта команды с уровнем разрешений "Чтение" нет групп или учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="9bfc8-141">The Team Site Visitors SharePoint group—with the Read permission level—has no groups or user accounts</span></span>

<span data-ttu-id="9bfc8-142">Ниже представлены разрешения по умолчанию для сайта команды.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-142">Here are the default permissions for the Team Site.</span></span>

![Разрешения по умолчанию для сайта команды](../media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
><span data-ttu-id="9bfc8-144">Если вы просматриваете группу SharePoint владельцев \<имя команды> на наличие разрешений "Изменить", в ней не отображаются владельцы \<имя команды>.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-144">If you view the \<team name> Owners SharePoint group for the Edit permission level, it does not display \<team name> Owners.</span></span>
>

<span data-ttu-id="9bfc8-145">Итоговые разрешения позволяют следующее:</span><span class="sxs-lookup"><span data-stu-id="9bfc8-145">The resulting permissions allow:</span></span>

- <span data-ttu-id="9bfc8-146">Владельцы группы команды могут администрировать сайт и обладают полным доступом к содержимому сайта.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-146">Team Group owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="9bfc8-147">Участники группы команды могут создавать и редактировать файлы на сайте.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-147">Team Group members to create and edit files on the site.</span></span> 

<span data-ttu-id="9bfc8-148">Управление разрешениями аналогично управлению участниками и владельцами команды.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-148">Permissions maintenance is the same as team member and owner maintenance.</span></span>

<span data-ttu-id="9bfc8-149">Ниже показана итоговая конфигурация на текущий момент.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-149">Here’s the resulting configuration so far.</span></span>

![Шаг 2 настройки сценария защищенной команды](../media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a><span data-ttu-id="9bfc8-151">Шаг 3. Настройка базового сайта SharePoint для дополнительной безопасности</span><span class="sxs-lookup"><span data-stu-id="9bfc8-151">Step 3: Configure the underlying SharePoint site for additional security</span></span>

<span data-ttu-id="9bfc8-152">Настройте следующие параметры разрешений на сайте команды.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-152">From the Team Site, configure these permission settings.</span></span>

1. <span data-ttu-id="9bfc8-153">На панели инструментов щелкните значок параметров и выберите вариант **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-153">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="9bfc8-154">В области **Разрешения для сайта** в разделе **Параметры общего доступа** щелкните **Изменить параметры общего доступа**.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-154">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="9bfc8-155">В разделе **Разрешения на предоставление общего доступа** установите флажок **Только владельцы сайта могут делиться файлами, папками и сайтом**.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-155">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="9bfc8-156">Отключите параметр **Разрешить запросы на доступ** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-156">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="9bfc8-157">При выборе этих параметров отключается возможность для участников группы команды предоставлять общий доступ к сайту команды другим пользователям, а также возможность запрашивать доступ к сайту команды для лиц, не являющихся участниками.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-157">With these settings, the ability for Team Group members to share the Team Site with other members or for non-members to request access to the Team Site is disabled.</span></span>

<span data-ttu-id="9bfc8-158">Ниже показана итоговая конфигурация на текущий момент.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-158">Here’s the resulting configuration so far.</span></span>

![Шаг 3 настройки сценария защищенной команды](../media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a><span data-ttu-id="9bfc8-160">Шаг 4. Создание метки хранения и политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="9bfc8-160">Step 4: Create a retention label and DLP policy</span></span>

<span data-ttu-id="9bfc8-161">Воспользуйтесь [этими инструкциями](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp) для следующих действий:</span><span class="sxs-lookup"><span data-stu-id="9bfc8-161">Use [these instructions](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp) to:</span></span>

1. <span data-ttu-id="9bfc8-162">Создание и публикация метки хранения для строго регулируемых данных (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="9bfc8-162">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="9bfc8-163">Настройка сайта команды для использования метки хранения, созданной на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-163">Configure the Team Site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="9bfc8-164">Создание политики защиты от потери данных для строго регулируемых данных, использующей метку хранения, созданную на шаге 2, и запрещающей пользователям отправлять файлы за пределы организации.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-164">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization.</span></span> <span data-ttu-id="9bfc8-165">Кроме того, можно настроить политику для дополнительных требований, например для отраслевых норм здравоохранения и финансов, на основе [шаблонов политики DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span><span class="sxs-lookup"><span data-stu-id="9bfc8-165">You can also configure the policy for additional requirements, such as those for health and financial industry regulations, based on [DLP policy templates](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span></span>

<span data-ttu-id="9bfc8-166">Ниже показана итоговая конфигурация на текущий момент.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-166">Here’s the resulting configuration so far.</span></span>

![Шаг 4 настройки сценария защищенной команды](../media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-a-sensitivity-label-or-a-sublabel-of-the-highly-regulated-sensitivity-label"></a><span data-ttu-id="9bfc8-168">Шаг 5. Создание метки конфиденциальности или вложенной метки для строго регулируемых данных</span><span class="sxs-lookup"><span data-stu-id="9bfc8-168">Step 5: Create a sensitivity label or a sublabel of the highly regulated sensitivity label</span></span>

<span data-ttu-id="9bfc8-169">В отличие от метки конфиденциальности для строго регулируемых данных, которую любой пользователь может применить к любому файлу, защищенной команде требуется собственная метка или вложенная метка, чтобы файлы, которым она назначена:</span><span class="sxs-lookup"><span data-stu-id="9bfc8-169">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="9bfc8-170">были зашифрованы и оставались зашифрованными при перемещении;</span><span class="sxs-lookup"><span data-stu-id="9bfc8-170">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="9bfc8-171">содержали настраиваемые разрешения, благодаря которым их могут открыть только участники группы команды.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-171">Contain custom permissions so that only members of the Team Group can open it.</span></span>

<span data-ttu-id="9bfc8-172">Чтобы установить этот дополнительный уровень безопасности для файлов, хранящихся на сайте команды, требуется настроить новую метку конфиденциальности, являющуюся самостоятельной меткой или вложенной меткой для общей метки строго регулируемых файлов.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-172">To accomplish this additional level of security for files stored in the Team Site, you must configure a new sensitivity label that is either its own label a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="9bfc8-173">Только участники группы команды будут видеть ее в списке своих меток. </span><span class="sxs-lookup"><span data-stu-id="9bfc8-173">Only Team Group members will see it in their list of labels.</span></span>

<span data-ttu-id="9bfc8-174">Используйте метку конфиденциальности, если требуется небольшое число меток для общих и отдельных закрытых команд.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-174">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="9bfc8-175">Используйте вложенную метку конфиденциальности, если у вас большое число меток или нужно упорядочить метки для закрытых команд под меткой строго регулируемых данных.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-175">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams under the highly regulated label.</span></span>

<span data-ttu-id="9bfc8-176">[Используйте эти инструкции](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels), чтобы настроить отдельную метку или вложенную метку со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="9bfc8-176">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="9bfc8-177">имя метки содержит название команды;</span><span class="sxs-lookup"><span data-stu-id="9bfc8-177">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="9bfc8-178">включено шифрование;</span><span class="sxs-lookup"><span data-stu-id="9bfc8-178">Encryption is enabled</span></span>
- <span data-ttu-id="9bfc8-179">группа команды имеет разрешения на совместное редактирование.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-179">The Team Group has Co-Author permissions</span></span>

<span data-ttu-id="9bfc8-180">Ниже представлена итоговая конфигурация с новой меткой.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-180">Here’s the resulting configuration with the new label.</span></span>

![Шаг 5 настройки сценария защищенной команды](../media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="9bfc8-182">Ниже показаны отношения между метками конфиденциальности и группой команды.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-182">Here’s the relationship between the sensitivity label and the Team Group.</span></span>

![Отношения между группой команды и разрешениями меток](../media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
><span data-ttu-id="9bfc8-184">Если настроена метка или вложенная метка конфиденциальности для пользовательских разрешений или со сроком действия, вы не сможете открыть файл из Teams или SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-184">If you configure the sensitivity label or sublabel for user-defined permissions or with an expiration date, you cannot open the file from Teams or SharePoint.</span></span> <span data-ttu-id="9bfc8-185">Потребуется использовать приложение Office.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-185">You must use an Office app.</span></span>
>

### <a name="custom-permissions"></a><span data-ttu-id="9bfc8-186">Настраиваемые разрешения</span><span class="sxs-lookup"><span data-stu-id="9bfc8-186">Custom permissions</span></span>

<span data-ttu-id="9bfc8-187">Вы также можете настроить собственные разрешения сайта SharePoint для сайта команды и соответствующую метку конфиденциальности при необходимости.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-187">You can also configure custom SharePoint site permissions for the Team Site and, if needed, its corresponding sensitivity label.</span></span> <span data-ttu-id="9bfc8-188">Вот два примера.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-188">Here are two examples.</span></span>

#### <a name="example-1-delegating-sharepoint-site-administration"></a><span data-ttu-id="9bfc8-189">Пример 1. Делегирование администрирования сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="9bfc8-189">Example 1: Delegating SharePoint site administration</span></span>

<span data-ttu-id="9bfc8-190">Если владелец команды не имеет опыта администрирования SharePoint или хочет делегировать управление сайтом команды, он может добавить учетную запись администратора SharePoint в список владельцев команды.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-190">If the team owner does not have SharePoint administration experience or wants to delegate administration of the Team Site, they could add the user account of a SharePoint administrator to the list of team owners.</span></span> <span data-ttu-id="9bfc8-191">Но после этого администратор SharePoint получит полный доступ к команде и всем ее ресурсам и сможет открыть файл с примененной меткой конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-191">But then the SharePoint administrator would have full access to the team and all its resources and would be able to open a file with the sensitivity label applied.</span></span> 

<span data-ttu-id="9bfc8-192">Чтобы предотвратить такое предоставление избыточных разрешений, добавьте учетную запись администратора SharePoint в группу SharePoint владельцев сайта команды в разделе дополнительных разрешений для сайта.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-192">To prevent this over-granting of privileges, add the user account of the SharePoint administrator to the Team Site Owners SharePoint group in the advanced permissions settings of the site.</span></span> <span data-ttu-id="9bfc8-193">Администратор SharePoint сможет управлять сайтом, но не сможет получить доступ к команде и ее ресурсам или открыть файлы с присвоенной меткой конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-193">The SharePoint administrator can administer the site but will not be able to access the team and any of its resources or open the files with the sensitivity label assigned.</span></span>

#### <a name="example-2-allowing-view-only-access-to-labeled-files"></a><span data-ttu-id="9bfc8-194">Пример 2. Предоставление доступа только для просмотра файлов с метками</span><span class="sxs-lookup"><span data-stu-id="9bfc8-194">Example 2: Allowing view-only access to labeled files</span></span>

<span data-ttu-id="9bfc8-195">Если некоторым сотрудникам требуется просматривать содержимое файлов с метками на сайте команды, добавьте их отдельные учетные записи пользователей в:</span><span class="sxs-lookup"><span data-stu-id="9bfc8-195">If some staff only need to view the contents of labeled files in the Team Site, add their individual user accounts to the:</span></span>

- <span data-ttu-id="9bfc8-196">группу SharePoint посетителей \<название команды>, по умолчанию имеющую уровень разрешений "Чтение";</span><span class="sxs-lookup"><span data-stu-id="9bfc8-196">\<team name> Visitors SharePoint group, which by default has the Read permission level.</span></span> 
- <span data-ttu-id="9bfc8-197">метку конфиденциальности с разрешениями для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-197">The sensitivity label with the Viewer permissions.</span></span>

<span data-ttu-id="9bfc8-198">Ниже представлены итоговые разрешения для метки.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-198">Here are the resulting permissions on the label.</span></span>

![Пример настраиваемых разрешений для просмотра файлов с метками](../media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
<span data-ttu-id="9bfc8-200">Посетители сайта смогут напрямую получить доступ к сайту команды и просмотреть содержимое файлов с примененными вложенными метками.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-200">The site visitors will be able to access the Team Site directly and view the contents of files that have the sublabel applied.</span></span> <span data-ttu-id="9bfc8-201">Но так как они не являются участниками группы команды, они не смогут получить доступ к команде и ее ресурсам.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-201">But because they are not members of the Team Group, they will not be able to access the team or any of its resources.</span></span>


## <a name="phase-2-drive-user-adoption-for-team-members"></a><span data-ttu-id="9bfc8-202">Этап 2. Внедрение возможностей среди участников команды</span><span class="sxs-lookup"><span data-stu-id="9bfc8-202">Phase 2: Drive user adoption for team members</span></span>

<span data-ttu-id="9bfc8-203">После создания команды нужно обеспечить применение ее возможностей и дополнительной защиты для участников команды.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-203">With the team in place, it’s time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="9bfc8-204">Шаг 1. Обучение пользователей</span><span class="sxs-lookup"><span data-stu-id="9bfc8-204">Step 1: Train your users</span></span>

<span data-ttu-id="9bfc8-205">Участники группы команды могут получить доступ к команде и всем ее ресурсам, включая чаты, собрания и другие приложения.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-205">Members of the Team Group can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="9bfc8-206">При работе с файлами из раздела **Файлы** канала участники группы команды должны назначать метку конфиденциальности или вложенную метку файлам, создаваемым для защищенной команды.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-206">When working with files from the **Files** section of a channel, members of the Team Group must assign the sensitivity label or sublabel to files created for the secure team.</span></span> <span data-ttu-id="9bfc8-207">Приведем пример.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-207">Here’s an example.</span></span>

![Пример метки, применяемой к файлу в защищенной команде](../media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
<span data-ttu-id="9bfc8-209">После применения метки к файлу он становится защищенным.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-209">When the label gets applied to the file it is secured.</span></span> <span data-ttu-id="9bfc8-210">Участники группы команды могут открывать его в Teams и совместно работать с ним в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-210">Members of the Team Group can open it in Teams and collaborate in real time.</span></span> <span data-ttu-id="9bfc8-211">Он зашифрован и содержит разрешения на совместное редактирование, настроенные для участников группы команды.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-211">It is encrypted and includes the Co-Author permissions set to the Team Group members.</span></span> <span data-ttu-id="9bfc8-212">Если файл покидает сайт и пересылается злоумышленнику, ему потребуется предоставить учетные данные пользователя, являющегося участником группы команды, чтобы открыть его и просмотреть содержимое.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-212">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the Team Group to open the file and view its contents.</span></span> 

<span data-ttu-id="9bfc8-213">Обучите участников команды, рассказав им:</span><span class="sxs-lookup"><span data-stu-id="9bfc8-213">Train your team members:</span></span>

- <span data-ttu-id="9bfc8-214">насколько важно использовать новую команду для чатов, собраний, файлов и других ресурсов сайта команды, а также о последствиях утечки жестко регламентированных данных, таких как юридические последствия, штрафные санкции за несоблюдение нормативно-правовых актов, появление программ-шантажистов или потеря конкурентного преимущества;</span><span class="sxs-lookup"><span data-stu-id="9bfc8-214">On the importance of using the new team for chats, meetings, files, and the other resources of the Team Site and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="9bfc8-215">как получить доступ к команде;</span><span class="sxs-lookup"><span data-stu-id="9bfc8-215">How to access the team.</span></span>
- <span data-ttu-id="9bfc8-216">как создавать файлы на сайте и отправлять новые файлы, которые хранятся локально;</span><span class="sxs-lookup"><span data-stu-id="9bfc8-216">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="9bfc8-217">каким образом политика защиты от потери данных блокирует пользователей при попытке отправить файлы за пределы организации;</span><span class="sxs-lookup"><span data-stu-id="9bfc8-217">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="9bfc8-218">как пометить файлы с помощью настраиваемых меток или вложенных меток для команды;</span><span class="sxs-lookup"><span data-stu-id="9bfc8-218">How to label files with the custom label or sublabel for the team.</span></span>
- <span data-ttu-id="9bfc8-219">как метка или вложенная метка защищает файлы даже в случае их утечки с сайта.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-219">How the label or sublabel protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="9bfc8-220">В программу такого обучения следует включить практические занятия, где участники команды смогут опробовать эти возможности и ознакомиться с результатами.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-220">This training should include hands-on exercises so that your team members can experience these capabilities and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="9bfc8-221">Шаг 2. Проведение периодических проверок использования и ответы на отзывы участников команды</span><span class="sxs-lookup"><span data-stu-id="9bfc8-221">Step 2: Conduct periodic reviews of usage and address team member feedback</span></span>

<span data-ttu-id="9bfc8-222">В последующие за обучением недели:</span><span class="sxs-lookup"><span data-stu-id="9bfc8-222">In the weeks after training:</span></span>

- <span data-ttu-id="9bfc8-223">Быстро рассмотрите отзывы участников команды и отрегулируйте политики и настройки.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-223">Quickly address team member feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="9bfc8-224">Проанализируйте использование команды и сравните результаты с требованиями к использованию.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-224">Analyze usage for the team and compare it with usage expectations.</span></span>
- <span data-ttu-id="9bfc8-225">Убедитесь в правильном применении настраиваемых меток или вложенных меток конфиденциальности к строго регулируемым файлам.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-225">Verify that highly regulated files have been properly labeled with the custom sensitivity label or sublabel.</span></span>

  <span data-ttu-id="9bfc8-226">Вы можете узнать, каким файлам присвоены метки, просмотрев папку в SharePoint и добавив столбец **Конфиденциальность** с помощью параметра **Показать/скрыть столбцы** элемента **Добавить столбец**.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-226">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="9bfc8-227">При необходимости следует провести повторное обучение пользователей.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-227">Retrain your users as needed.</span></span>

## <a name="demonstrate-this-in-a-test-environment"></a><span data-ttu-id="9bfc8-228">Демонстрация в тестовой среде</span><span class="sxs-lookup"><span data-stu-id="9bfc8-228">Demonstrate this in a test environment</span></span>

<span data-ttu-id="9bfc8-229">Чтобы создать собственную тестовую среду для тестирования команд с применением конфиденциальных и строго конфиденциальных файлов, см. [эти инструкции](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-team-for-files-in-a-dev-test-environment).</span><span class="sxs-lookup"><span data-stu-id="9bfc8-229">To build out your own test environment to test teams for sensitive and highly confidential files, see [these instructions](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-team-for-files-in-a-dev-test-environment).</span></span> 

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)

## <a name="how-the-contoso-corporation-used-a-secure-team-for-a-top-secret-project"></a><span data-ttu-id="9bfc8-231">Как корпорация Contoso использовала защищенную команду для сверхсекретного проекта</span><span class="sxs-lookup"><span data-stu-id="9bfc8-231">How the Contoso Corporation used a secure team for a top-secret project</span></span>

<span data-ttu-id="9bfc8-232">Корпорация Contoso — вымышленная показательная транснациональная промышленная компания-конгломерат.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-232">The Contoso Corporation is a fictional but representative global manufacturing conglomerate.</span></span> <span data-ttu-id="9bfc8-233">Посмотрите, как корпорация Contoso настроила и внедрила [защищенную команду](contoso-team-for-top-secret-project.md) для сверхсекретного проекта по разработке и выводу на рынок нового набора продуктов и услуг.</span><span class="sxs-lookup"><span data-stu-id="9bfc8-233">See how Contoso configured and drove the adoption of a [secure team](contoso-team-for-top-secret-project.md) for a top secret project to develop and bring to market a new set of products and services.</span></span> 

## <a name="see-also"></a><span data-ttu-id="9bfc8-234">См. также</span><span class="sxs-lookup"><span data-stu-id="9bfc8-234">See also</span></span>

[<span data-ttu-id="9bfc8-235">Сайты SharePoint для строго регулируемых данных</span><span class="sxs-lookup"><span data-stu-id="9bfc8-235">SharePoint sites for highly regulated data</span></span>](teams-sharepoint-online-sites-highly-regulated-data.md)

[<span data-ttu-id="9bfc8-236">Рабочие нагрузки и сценарии Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="9bfc8-236">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="9bfc8-237">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="9bfc8-237">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="9bfc8-238">Руководство по развертыванию</span><span class="sxs-lookup"><span data-stu-id="9bfc8-238">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
