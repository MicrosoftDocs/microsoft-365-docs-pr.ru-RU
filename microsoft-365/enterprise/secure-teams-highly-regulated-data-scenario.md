---
title: Teams для строго регулируемых данных
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Создайте защищенную команду для хранения наиболее важных и конфиденциальных файлов.
ms.openlocfilehash: 5117d310ccd877a7377e6e538e7fba13daaad4ef
ms.sourcegitcommit: 80dc9ceb14e3eb3ae61b0fc2c8c3d73d564a7ef9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "37617267"
---
# <a name="teams-for-highly-regulated-data"></a><span data-ttu-id="04fae-103">Teams для строго регулируемых данных</span><span class="sxs-lookup"><span data-stu-id="04fae-103">Microsoft Teams for highly regulated data</span></span>

<span data-ttu-id="04fae-104">Эта статья содержит рекомендации и инструкции по настройке закрытой команды в Microsoft Teams, разрешающей доступ к функциям Teams, таким как чаты, собрания и файлы, только участникам и владельцам группы Office 365 команды.</span><span class="sxs-lookup"><span data-stu-id="04fae-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams that locks down access to Teams features—such as chats, meetings, and files—to only members and owners of the Office 365 group for the team.</span></span> 

<span data-ttu-id="04fae-105">Помимо закрытого доступа на основе группы Office 365, в этой статье описывается способ настройки базового закрытого сайта группы SharePoint, доступного из раздела **Файлы** канала команды. Это обеспечивает дополнительную защиту, требующуюся для хранения строго регулируемых данных.</span><span class="sxs-lookup"><span data-stu-id="04fae-105">Beyond the private access based on the Office 365 group, this article describes how to configure the underlying private SharePoint team site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span> <span data-ttu-id="04fae-106">На этом сайте группы SharePoint можно хранить файлы, страницы, общий календарь, задачи, записную книжку и списки, а также совместно работать над ними.</span><span class="sxs-lookup"><span data-stu-id="04fae-106">On this SharePoint team site, you can store and collaborate on files, pages, a shared calendar, tasks, a notebook, and lists.</span></span>

<span data-ttu-id="04fae-107">Элементы настройки команды для работы со строго регулируемыми данными:</span><span class="sxs-lookup"><span data-stu-id="04fae-107">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="04fae-108">Закрытая команда с соответствующей группой Office 365, в которой есть учетные записи владельца и участника.</span><span class="sxs-lookup"><span data-stu-id="04fae-108">A private team with a corresponding Office 365 group that has owner and member user accounts.</span></span>
- <span data-ttu-id="04fae-109">Дополнительная защита на базовом сайте SharePoint для команды, которая:</span><span class="sxs-lookup"><span data-stu-id="04fae-109">Additional security on the underlying SharePoint site for the team that:</span></span>
  - <span data-ttu-id="04fae-110">запрещает предоставление участниками сайта доступа третьим лицам;</span><span class="sxs-lookup"><span data-stu-id="04fae-110">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="04fae-111">блокирует запросы на доступ к сайту от лиц, которые не являются участниками сайта.</span><span class="sxs-lookup"><span data-stu-id="04fae-111">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="04fae-112">Метка хранения Office 365 для базового сайта SharePoint, автоматически применяющаяся к новым файлам сайта в качестве стандартного способа определения политик хранения.</span><span class="sxs-lookup"><span data-stu-id="04fae-112">An Office 365 retention label for the underlying SharePoint site that is automatically applied to new files on the site as a default way to define retention policies.</span></span>
- <span data-ttu-id="04fae-113">Политика защиты от потери данных (DLP), использующая метку хранения и блокирующая предоставление пользователями общего доступа к файлам или их отправку за пределы организации.</span><span class="sxs-lookup"><span data-stu-id="04fae-113">A Data Loss Prevention (DLP) policy that uses the retention label and blocks users from sharing or sending files outside the organization.</span></span>
- <span data-ttu-id="04fae-114">Метка конфиденциальности Office 365 или вложенная метка строго регулируемой метки с включенным шифрованием и разрешениями на совместное редактирование для группы Office 365 команды.</span><span class="sxs-lookup"><span data-stu-id="04fae-114">An Office 365 sensitivity label or a sublabel of a highly regulated label that has encryption enabled and Co-Author permissions for the Office 365 group of the team.</span></span> <span data-ttu-id="04fae-115">Пользователи применяют метку или вложенную метку к файлам, хранящимся в разделе **Файлы** команды, из параметра строки меню "Конфиденциальность" в Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="04fae-115">Users apply the label or sublabel to files stored in **Files** section of the team from the Sensitivity menu bar option in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="04fae-116">Ниже показана итоговая конфигурация с меткой конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="04fae-116">Here is the resulting configuration with a sensitivity label.</span></span>

![Настройка сценария защищенной команды](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)
 
## <a name="configuration"></a><span data-ttu-id="04fae-118">Настройка</span><span class="sxs-lookup"><span data-stu-id="04fae-118">Configuration</span></span>

<span data-ttu-id="04fae-119">Полная настройка защищенной команды состоит из следующих этапов:</span><span class="sxs-lookup"><span data-stu-id="04fae-119">The end-to-end configuration of a secure team consists of these steps:</span></span>

1. <span data-ttu-id="04fae-120">Настройка удостоверений и доступа для устройств.</span><span class="sxs-lookup"><span data-stu-id="04fae-120">Configure identity and device access.</span></span>
2. <span data-ttu-id="04fae-121">Создание закрытой команды.</span><span class="sxs-lookup"><span data-stu-id="04fae-121">Create a team</span></span>
3. <span data-ttu-id="04fae-122">Настройка базового сайта SharePoint для дополнительной безопасности.</span><span class="sxs-lookup"><span data-stu-id="04fae-122">Configure the underlying SharePoint site for additional security.</span></span>
4. <span data-ttu-id="04fae-123">Создание метки хранения и политики защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="04fae-123">Create a retention label and DLP policy.</span></span>
5. <span data-ttu-id="04fae-124">Создание метки или вложенной метки для метки строго регулируемых данных.</span><span class="sxs-lookup"><span data-stu-id="04fae-124">Create the label or sublabel of the highly regulated label.</span></span>

### <a name="step-1-configure-identity-and-device-access"></a><span data-ttu-id="04fae-125">Шаг 1. Настройка удостоверений и доступа для устройств</span><span class="sxs-lookup"><span data-stu-id="04fae-125">Step 1: Configure identity and device access</span></span>

<span data-ttu-id="04fae-126">Чтобы защитить доступ к команде или ее базовому сайту SharePoint, убедитесь, что вы настроили [политики удостоверений и доступа для устройств](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies), а также рекомендуемые [политики доступа к SharePoint Online](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="04fae-126">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) and the [recommended SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="step-2-create-a-private-team"></a><span data-ttu-id="04fae-127">Шаг 2. Создание закрытой команды</span><span class="sxs-lookup"><span data-stu-id="04fae-127">Step 2: Create a private team</span></span>

<span data-ttu-id="04fae-128">Чтобы создать закрытую команду, следуйте [инструкциям](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="04fae-128">Follow [these instructions](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a private SharePoint team site.</span></span>

<span data-ttu-id="04fae-129">При создании закрытой команды применяются следующие разрешения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="04fae-129">When you create a private team, here are the default permissions:</span></span>

- <span data-ttu-id="04fae-130">Группа Office 365 для команды (группа команды) содержит владельцев и участников групп</span><span class="sxs-lookup"><span data-stu-id="04fae-130">The Office 365 group for the team (the Team Group) has group owners and group members</span></span>
- <span data-ttu-id="04fae-131">Для базового сайта SharePoint команды (сайт команды):</span><span class="sxs-lookup"><span data-stu-id="04fae-131">For the underlying SharePoint site for the team (the Team Site):</span></span>
  - <span data-ttu-id="04fae-132">Администраторы семейства веб-сайтов настроены в качестве владельцев группы команды</span><span class="sxs-lookup"><span data-stu-id="04fae-132">The Site Collection Administrators is configured for the Team Group owners</span></span>
  - <span data-ttu-id="04fae-133">Для сайта команды:</span><span class="sxs-lookup"><span data-stu-id="04fae-133">For the Team Site:</span></span> 
    - <span data-ttu-id="04fae-134">Группа SharePoint владельцев сайта команды с уровнем разрешений "Полный доступ" настроена для владельцев группы команды</span><span class="sxs-lookup"><span data-stu-id="04fae-134">The Team Site Owners SharePoint group—with the Full Control permission level—is set to the Team Group owners</span></span>
    - <span data-ttu-id="04fae-135">Группа SharePoint участников сайта команды с уровнем разрешений "Изменить" настроена для участников группы команды</span><span class="sxs-lookup"><span data-stu-id="04fae-135">The Team Site Members SharePoint group—with the Edit permission level—is set to the Team Group members</span></span>
    - <span data-ttu-id="04fae-136">У группы SharePoint посетителей сайта команды с уровнем разрешений "Чтение" нет групп или учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="04fae-136">The Team Site Visitors SharePoint group—with the Read permission level—has no groups or user accounts</span></span>

<span data-ttu-id="04fae-137">Ниже представлены разрешения по умолчанию для сайта команды.</span><span class="sxs-lookup"><span data-stu-id="04fae-137">Here are the default permissions for the Team Site.</span></span>

![Разрешения по умолчанию для сайта команды](./media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
><span data-ttu-id="04fae-139">Если вы просматриваете группу SharePoint владельцев \<имя команды> на наличие разрешений "Изменить", в ней не отображаются владельцы \<имя команды>.</span><span class="sxs-lookup"><span data-stu-id="04fae-139">If you view the \<team name> Owners SharePoint group for the Edit permission level, it does not display \<team name> Owners.</span></span>
>

<span data-ttu-id="04fae-140">Итоговые разрешения позволяют следующее:</span><span class="sxs-lookup"><span data-stu-id="04fae-140">The resulting permissions allow:</span></span>

- <span data-ttu-id="04fae-141">Владельцы группы команды могут администрировать сайт и обладают полным доступом к содержимому сайта.</span><span class="sxs-lookup"><span data-stu-id="04fae-141">Team Group owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="04fae-142">Участники группы команды могут создавать и редактировать файлы на сайте.</span><span class="sxs-lookup"><span data-stu-id="04fae-142">Team Group members to create and edit files on the site.</span></span> 

<span data-ttu-id="04fae-143">Управление разрешениями аналогично управлению участниками и владельцами команды.</span><span class="sxs-lookup"><span data-stu-id="04fae-143">Permissions maintenance is the same as team member and owner maintenance.</span></span>

<span data-ttu-id="04fae-144">Ниже показана итоговая конфигурация на текущий момент.</span><span class="sxs-lookup"><span data-stu-id="04fae-144">Here’s the resulting configuration so far.</span></span>

![Шаг 2 настройки сценария защищенной команды](./media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a><span data-ttu-id="04fae-146">Шаг 3. Настройка базового сайта SharePoint для дополнительной безопасности</span><span class="sxs-lookup"><span data-stu-id="04fae-146">Step 3: Configure the underlying SharePoint site for additional security</span></span>

<span data-ttu-id="04fae-147">Настройте следующие параметры разрешений на сайте команды.</span><span class="sxs-lookup"><span data-stu-id="04fae-147">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="04fae-148">На панели инструментов щелкните значок параметров и выберите вариант **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="04fae-148">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="04fae-149">В области **Разрешения для сайта** в разделе **Параметры общего доступа** щелкните **Изменить параметры общего доступа**.</span><span class="sxs-lookup"><span data-stu-id="04fae-149">In the **Site permissions** pane,, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="04fae-150">В разделе **Разрешения на предоставление общего доступа** установите флажок **Только владельцы сайта могут делиться файлами, папками и сайтом**.</span><span class="sxs-lookup"><span data-stu-id="04fae-150">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="04fae-151">Отключите параметр **Разрешить запросы на доступ** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="04fae-151">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="04fae-152">При выборе этих параметров отключается возможность для участников группы команды предоставлять общий доступ к сайту команды другим пользователям, а также возможность запрашивать доступ к сайту команды для лиц, не являющихся участниками.</span><span class="sxs-lookup"><span data-stu-id="04fae-152">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

<span data-ttu-id="04fae-153">Ниже показана итоговая конфигурация на текущий момент.</span><span class="sxs-lookup"><span data-stu-id="04fae-153">Here’s the resulting configuration so far.</span></span>

![Шаг 3 настройки сценария защищенной команды](./media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a><span data-ttu-id="04fae-155">Шаг 4. Создание метки хранения и политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="04fae-155">Step 4: Create a retention label and DLP policy</span></span>

<span data-ttu-id="04fae-156">Воспользуйтесь [этими инструкциями](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) для следующих действий:</span><span class="sxs-lookup"><span data-stu-id="04fae-156">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="04fae-157">Создание и публикация метки хранения для строго регулируемых данных (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="04fae-157">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="04fae-158">Настройка сайта команды для использования метки хранения, созданной на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="04fae-158">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="04fae-159">Создание политики защиты от потери данных для строго регулируемых данных, использующей метку хранения, созданную на шаге 2, и запрещающей пользователям отправлять файлы за пределы организации.</span><span class="sxs-lookup"><span data-stu-id="04fae-159">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span> <span data-ttu-id="04fae-160">Кроме того, можно настроить политику для дополнительных требований, например для отраслевых норм здравоохранения и финансов, на основе [шаблонов политики DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span><span class="sxs-lookup"><span data-stu-id="04fae-160">You can also configure the policy for additional requirements, such as those for health and financial industry regulations, based on [DLP policy templates](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span></span>

<span data-ttu-id="04fae-161">Ниже показана итоговая конфигурация на текущий момент.</span><span class="sxs-lookup"><span data-stu-id="04fae-161">Here’s the resulting configuration so far.</span></span>

![Шаг 4 настройки сценария защищенной команды](./media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-the-label-or-a-sublabel-of-the-highly-regulated-label"></a><span data-ttu-id="04fae-163">Шаг 5. Создание метки или вложенной метки для метки строго регулируемых данных</span><span class="sxs-lookup"><span data-stu-id="04fae-163">Step 5: Create the label or a sublabel of the highly regulated label</span></span>

<span data-ttu-id="04fae-164">В отличие от метки конфиденциальности для строго регулируемых данных, которую любой пользователь может применить к любому файлу, защищенной команде требуется собственная метка или вложенная метка, чтобы файлы, которым она назначена:</span><span class="sxs-lookup"><span data-stu-id="04fae-164">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="04fae-165">были зашифрованы и оставались зашифрованными при перемещении;</span><span class="sxs-lookup"><span data-stu-id="04fae-165">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="04fae-166">содержали настраиваемые разрешения, благодаря которым их могут открыть только участники группы команды.</span><span class="sxs-lookup"><span data-stu-id="04fae-166">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="04fae-167">Чтобы установить этот дополнительный уровень безопасности для файлов, хранящихся на сайте команды, требуется настроить новую метку конфиденциальности, являющуюся самостоятельной меткой или вложенной меткой для общей метки строго регулируемых файлов.</span><span class="sxs-lookup"><span data-stu-id="04fae-167">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="04fae-168">Только участники группы команды будут видеть ее в списке своих меток. </span><span class="sxs-lookup"><span data-stu-id="04fae-168">Only Team Group members will see it in their list of labels.</span></span>

<span data-ttu-id="04fae-169">Используйте метку конфиденциальности, если требуется небольшое число меток для общих и отдельных закрытых команд.</span><span class="sxs-lookup"><span data-stu-id="04fae-169">Use a sensitivity label when you need is a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="04fae-170">Используйте вложенную метку конфиденциальности, если у вас большое число меток или нужно упорядочить метки для закрытых команд под меткой строго регулируемых данных.</span><span class="sxs-lookup"><span data-stu-id="04fae-170">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams the under the highly regulated label.</span></span>

<span data-ttu-id="04fae-171">[Используйте эти инструкции](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels), чтобы настроить отдельную метку или вложенную метку со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="04fae-171">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="04fae-172">имя метки содержит название команды;</span><span class="sxs-lookup"><span data-stu-id="04fae-172">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="04fae-173">включено шифрование;</span><span class="sxs-lookup"><span data-stu-id="04fae-173">Encryption is enabled.</span></span>
- <span data-ttu-id="04fae-174">группа команды имеет разрешения на совместное редактирование.</span><span class="sxs-lookup"><span data-stu-id="04fae-174">The Team Group has Co-Author permissions</span></span>

<span data-ttu-id="04fae-175">Ниже представлена итоговая конфигурация с новой меткой.</span><span class="sxs-lookup"><span data-stu-id="04fae-175">Here’s the resulting configuration with the new label.</span></span>

![Шаг 5 настройки сценария защищенной команды](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="04fae-177">Ниже показаны отношения между метками конфиденциальности и группой команды.</span><span class="sxs-lookup"><span data-stu-id="04fae-177">Here’s the relationship between the sensitivity label and the Team Group.</span></span>

![Отношения между группой команды и разрешениями меток](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
><span data-ttu-id="04fae-179">Если настроена метка конфиденциальности или вложенная метка для пользовательских разрешений или со сроком действия, вы не сможете открыть файл из Teams или SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="04fae-179">If you configure the sensitivity label or sublabel for user-defined permissions or with an expiration date, you cannot open the file from Teams or SharePoint Online.</span></span> <span data-ttu-id="04fae-180">Потребуется использовать приложение Office.</span><span class="sxs-lookup"><span data-stu-id="04fae-180">You must use an Office app.</span></span>
>

## <a name="using-the-team-and-a-sensitivity-label"></a><span data-ttu-id="04fae-181">Использование команды и метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="04fae-181">Using the team and a sensitivity label</span></span>

<span data-ttu-id="04fae-182">Участники группы команды могут получить доступ к команде и всем ее ресурсам, включая чаты, собрания и другие приложения.</span><span class="sxs-lookup"><span data-stu-id="04fae-182">Members of the Team Group can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="04fae-183">При работе с файлами из раздела **Файлы** канала участники группы команды должны назначать метку конфиденциальности или вложенную метку файлам, создаваемым для защищенной команды.</span><span class="sxs-lookup"><span data-stu-id="04fae-183">When working with files from the **Files** section of a channel, members of the Team Group must assign the sensitivity label or sublabel to files created for the secure team.</span></span> <span data-ttu-id="04fae-184">Приведем пример.</span><span class="sxs-lookup"><span data-stu-id="04fae-184">Here’s an example.</span></span>

![Пример метки, применяемой к файлу в защищенной команде](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
<span data-ttu-id="04fae-186">После применения метки к файлу он становится защищенным.</span><span class="sxs-lookup"><span data-stu-id="04fae-186">When the label gets applied to the file it is secured.</span></span> <span data-ttu-id="04fae-187">Участники группы команды могут открывать его в Teams и совместно работать с ним в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="04fae-187">Members of the Team Group can open it in Teams and collaborate in real time.</span></span> <span data-ttu-id="04fae-188">Он зашифрован и содержит разрешения на совместное редактирование, настроенные для участников группы команды.</span><span class="sxs-lookup"><span data-stu-id="04fae-188">It is encrypted and includes the Co-Author permissions set to the Team Group members.</span></span> <span data-ttu-id="04fae-189">Если файл покидает сайт и пересылается злоумышленнику, ему потребуется предоставить учетные данные пользователя, являющегося участником группы команды, чтобы открыть его и просмотреть содержимое.</span><span class="sxs-lookup"><span data-stu-id="04fae-189">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the Team Group to open the file and view its contents.</span></span> 

<span data-ttu-id="04fae-190">Вы можете узнать, каким файлам присвоены метки, просмотрев папку в SharePoint Online и добавив столбец **Конфиденциальность** с помощью параметра **Показать/скрыть столбцы** элемента **Добавить столбец**.</span><span class="sxs-lookup"><span data-stu-id="04fae-190">You can see which files have a label assigned by viewing a folder in SharePoint Online and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

## <a name="custom-permissions"></a><span data-ttu-id="04fae-191">Настраиваемые разрешения</span><span class="sxs-lookup"><span data-stu-id="04fae-191">Custom permissions</span></span>

<span data-ttu-id="04fae-192">Вы также можете настроить собственные разрешения сайта SharePoint для сайта команды и соответствующую метку конфиденциальности при необходимости.</span><span class="sxs-lookup"><span data-stu-id="04fae-192">You can also configure custom SharePoint site permissions for the Team Site and, if needed, its corresponding sensitivity label.</span></span> <span data-ttu-id="04fae-193">Вот два примера.</span><span class="sxs-lookup"><span data-stu-id="04fae-193">Here are two examples.</span></span>

### <a name="example-1-delegating-sharepoint-site-administration"></a><span data-ttu-id="04fae-194">Пример 1. Делегирование администрирования сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="04fae-194">Example 1: Delegating SharePoint site administration</span></span>

<span data-ttu-id="04fae-195">Если владелец команды не имеет опыта администрирования SharePoint или хочет делегировать управление сайтом команды, он может добавить учетную запись администратора SharePoint в список владельцев команды.</span><span class="sxs-lookup"><span data-stu-id="04fae-195">If the team owner does not have SharePoint administration experience or wants to delegate administration of the Team Site, they could add the user account of a SharePoint administrator to the list of team owners.</span></span> <span data-ttu-id="04fae-196">Но после этого администратор SharePoint получит полный доступ к команде и всем ее ресурсам и сможет открыть файл с примененной меткой конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="04fae-196">But then the SharePoint administrator would have full access to the team and all its resources and would be able to open a file with the sensitivity label applied.</span></span> 

<span data-ttu-id="04fae-197">Чтобы предотвратить такое предоставление избыточных разрешений, добавьте учетную запись администратора SharePoint в группу SharePoint владельцев сайта команды в разделе дополнительных разрешений для сайта.</span><span class="sxs-lookup"><span data-stu-id="04fae-197">To prevent this over-granting of privileges, add the user account of the SharePoint administrator to the Team Site Owners SharePoint group in the advanced permissions settings of the site.</span></span> <span data-ttu-id="04fae-198">Администратор SharePoint сможет управлять сайтом, но не сможет получить доступ к команде и ее ресурсам или открыть файлы с присвоенной меткой конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="04fae-198">The SharePoint administrator can administer the site but will not be able to access the team and any of its resources or open the files with the sensitivity label assigned.</span></span>

### <a name="example-2-allowing-view-only-access-to-labeled-files"></a><span data-ttu-id="04fae-199">Пример 2. Предоставление доступа только для просмотра файлов с метками</span><span class="sxs-lookup"><span data-stu-id="04fae-199">Example 2: Allowing view-only access to labeled files</span></span>

<span data-ttu-id="04fae-200">Если некоторым сотрудникам требуется просматривать содержимое файлов с метками на сайте команды, добавьте их отдельные учетные записи пользователей в:</span><span class="sxs-lookup"><span data-stu-id="04fae-200">If some staff only need to view the contents of labeled files in the Team Site, add their individual user accounts to the:</span></span>

- <span data-ttu-id="04fae-201">группу SharePoint посетителей \<название команды>, по умолчанию имеющую уровень разрешений "Чтение";</span><span class="sxs-lookup"><span data-stu-id="04fae-201">\<team name> Visitors SharePoint group, which by default has the Read permission level.</span></span> 
- <span data-ttu-id="04fae-202">метку конфиденциальности с разрешениями для просмотра.</span><span class="sxs-lookup"><span data-stu-id="04fae-202">The sensitivity label with the Viewer permissions.</span></span>

<span data-ttu-id="04fae-203">Ниже представлены итоговые разрешения для метки.</span><span class="sxs-lookup"><span data-stu-id="04fae-203">Here are the resulting permissions on the label.</span></span>

![Пример настраиваемых разрешений для просмотра файлов с метками](./media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
<span data-ttu-id="04fae-205">Посетители сайта смогут напрямую получить доступ к сайту команды и просмотреть содержимое файлов с примененными вложенными метками.</span><span class="sxs-lookup"><span data-stu-id="04fae-205">The site visitors will be able to access the Team Site directly and view the contents of files that have the sublabel applied.</span></span> <span data-ttu-id="04fae-206">Но так как они не являются участниками группы команды, они не смогут получить доступ к команде и ее ресурсам.</span><span class="sxs-lookup"><span data-stu-id="04fae-206">But because they are not members of the Team Group, they will not be able to access the team or any of its resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="04fae-207">См. также</span><span class="sxs-lookup"><span data-stu-id="04fae-207">See also</span></span>

[<span data-ttu-id="04fae-208">Сайты SharePoint для строго регулируемых данных</span><span class="sxs-lookup"><span data-stu-id="04fae-208">SharePoint sites for highly regulated data</span></span>](teams-sharepoint-online-sites-highly-regulated-data.md)

[<span data-ttu-id="04fae-209">Руководство по развертыванию</span><span class="sxs-lookup"><span data-stu-id="04fae-209">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
