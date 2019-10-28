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
ms.openlocfilehash: d917e14719744dad8a681e15a8547655c3a0457f
ms.sourcegitcommit: d95aab99d7827dbb9248280044748ca05ebec786
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "37657806"
---
# <a name="teams-for-highly-regulated-data"></a><span data-ttu-id="11e92-103">Teams для строго регулируемых данных</span><span class="sxs-lookup"><span data-stu-id="11e92-103">Teams for highly regulated data</span></span>

<span data-ttu-id="11e92-104">Эта статья содержит рекомендации и инструкции по настройке закрытой команды в Microsoft Teams, разрешающей доступ к функциям Teams, таким как чаты, собрания и файлы, только участникам и владельцам группы Office 365 команды.</span><span class="sxs-lookup"><span data-stu-id="11e92-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams that locks down access to Teams features—such as chats, meetings, and files—to only members and owners of the Office 365 group for the team.</span></span> 

<span data-ttu-id="11e92-105">Помимо закрытого доступа на основе группы Office 365, в этой статье описывается способ настройки базового закрытого сайта группы SharePoint, доступного из раздела **Файлы** канала команды. Это обеспечивает дополнительную защиту, требующуюся для хранения строго регулируемых данных.</span><span class="sxs-lookup"><span data-stu-id="11e92-105">Beyond the private access based on the Office 365 group, this article describes how to configure the underlying private SharePoint team site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span> <span data-ttu-id="11e92-106">На этом сайте группы SharePoint можно хранить файлы, страницы, общий календарь, задачи, записную книжку и списки, а также совместно работать над ними.</span><span class="sxs-lookup"><span data-stu-id="11e92-106">On this SharePoint team site, you can store and collaborate on files, pages, a shared calendar, tasks, a notebook, and lists.</span></span>

<span data-ttu-id="11e92-107">Элементы настройки команды для работы со строго регулируемыми данными:</span><span class="sxs-lookup"><span data-stu-id="11e92-107">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="11e92-108">Закрытая команда с соответствующей группой Office 365, в которой есть учетные записи владельца и участника.</span><span class="sxs-lookup"><span data-stu-id="11e92-108">A private team with a corresponding Office 365 group that has owner and member user accounts.</span></span>
- <span data-ttu-id="11e92-109">Дополнительная защита на базовом сайте SharePoint для команды, которая:</span><span class="sxs-lookup"><span data-stu-id="11e92-109">Additional security on the underlying SharePoint site for the team that:</span></span>
  - <span data-ttu-id="11e92-110">запрещает предоставление участниками сайта доступа третьим лицам;</span><span class="sxs-lookup"><span data-stu-id="11e92-110">Prevents members of the site from granting access to others.</span></span>
  - <span data-ttu-id="11e92-111">блокирует запросы на доступ к сайту от лиц, которые не являются участниками сайта.</span><span class="sxs-lookup"><span data-stu-id="11e92-111">Prevents non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="11e92-112">Метка хранения Office 365 для базового сайта SharePoint, автоматически применяющаяся к новым файлам сайта в качестве стандартного способа определения политик хранения.</span><span class="sxs-lookup"><span data-stu-id="11e92-112">An Office 365 retention label for the underlying SharePoint site that is automatically applied to new files on the site as a default way to define retention policies.</span></span>
- <span data-ttu-id="11e92-113">Политика защиты от потери данных (DLP), использующая метку хранения и блокирующая предоставление пользователями общего доступа к файлам или их отправку за пределы организации.</span><span class="sxs-lookup"><span data-stu-id="11e92-113">A Data Loss Prevention (DLP) policy that uses the retention label and blocks users from sharing or sending files outside the organization.</span></span>
- <span data-ttu-id="11e92-114">Метка конфиденциальности Office 365 или вложенная метка строго регулируемой метки с включенным шифрованием и разрешениями на совместное редактирование для группы Office 365 команды.</span><span class="sxs-lookup"><span data-stu-id="11e92-114">An Office 365 sensitivity label or a sublabel of a highly regulated label that has encryption enabled and Co-Author permissions for the Office 365 group of the team.</span></span> <span data-ttu-id="11e92-115">Пользователи применяют метку или вложенную метку к файлам, хранящимся в разделе **Файлы** команды, из параметра строки меню "Конфиденциальность" в Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="11e92-115">Users apply the label or sublabel to files stored in **Files** section of the team from the Sensitivity menu bar option in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="11e92-116">Ниже показана итоговая конфигурация с меткой конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="11e92-116">Here is the resulting configuration with a sensitivity label.</span></span>

![Настройка сценария защищенной команды](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)
 
## <a name="phase-1-configure-a-team-for-highly-regulated-data"></a><span data-ttu-id="11e92-118">Этап 1. Настройка команды для строго регулируемых данных</span><span class="sxs-lookup"><span data-stu-id="11e92-118">Phase 1: Configure a team for highly regulated data</span></span>

<span data-ttu-id="11e92-119">Полная настройка состоит из следующих этапов:</span><span class="sxs-lookup"><span data-stu-id="11e92-119">The end-to-end configuration consists of these steps:</span></span>

1. <span data-ttu-id="11e92-120">Настройка удостоверений и доступа для устройств.</span><span class="sxs-lookup"><span data-stu-id="11e92-120">Configure identity and device access.</span></span>
2. <span data-ttu-id="11e92-121">Создание закрытой команды.</span><span class="sxs-lookup"><span data-stu-id="11e92-121">Create a private team.</span></span>
3. <span data-ttu-id="11e92-122">Настройка базового сайта SharePoint для дополнительной безопасности.</span><span class="sxs-lookup"><span data-stu-id="11e92-122">Configure the underlying SharePoint site for additional security.</span></span>
4. <span data-ttu-id="11e92-123">Создание метки хранения и политики защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="11e92-123">Create a retention label and DLP policy.</span></span>
5. <span data-ttu-id="11e92-124">Создание метки или вложенной метки для метки строго регулируемых данных.</span><span class="sxs-lookup"><span data-stu-id="11e92-124">Create the label or sublabel of the highly regulated label.</span></span>

### <a name="step-1-configure-identity-and-device-access"></a><span data-ttu-id="11e92-125">Шаг 1. Настройка удостоверений и доступа для устройств</span><span class="sxs-lookup"><span data-stu-id="11e92-125">Step 1: Configure identity and device access</span></span>

<span data-ttu-id="11e92-126">Чтобы защитить доступ к команде или ее базовому сайту SharePoint, убедитесь, что вы настроили [политики удостоверений и доступа для устройств](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies), а также рекомендуемые [политики доступа к SharePoint Online](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="11e92-126">To protect access to the team and its underlying SharePoint site, ensure that you have configured [identity and device access policies](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) and the recommended [SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="step-2-create-a-private-team"></a><span data-ttu-id="11e92-127">Шаг 2. Создание закрытой команды</span><span class="sxs-lookup"><span data-stu-id="11e92-127">Step 2: Create a private team</span></span>

<span data-ttu-id="11e92-128">Чтобы создать закрытую команду, следуйте [инструкциям](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="11e92-128">Use [these instructions](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a private team.</span></span>

<span data-ttu-id="11e92-129">При создании закрытой команды применяются следующие разрешения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="11e92-129">When you create a private team, here are the default permissions:</span></span>

- <span data-ttu-id="11e92-130">Группа Office 365 для команды (группа команды) содержит владельцев и участников групп</span><span class="sxs-lookup"><span data-stu-id="11e92-130">The Office 365 group for the team (the Team Group) has group owners and group members</span></span>
- <span data-ttu-id="11e92-131">Для базового сайта SharePoint команды (сайт команды):</span><span class="sxs-lookup"><span data-stu-id="11e92-131">For the underlying SharePoint site for the team (the Team Site):</span></span>
  - <span data-ttu-id="11e92-132">Администраторы семейства веб-сайтов настроены в качестве владельцев группы команды</span><span class="sxs-lookup"><span data-stu-id="11e92-132">The Site Collection Administrators is configured for the Team Group owners</span></span>
  - <span data-ttu-id="11e92-133">Для сайта команды:</span><span class="sxs-lookup"><span data-stu-id="11e92-133">For the Team Site:</span></span> 
    - <span data-ttu-id="11e92-134">Группа SharePoint владельцев сайта команды с уровнем разрешений "Полный доступ" настроена для владельцев группы команды</span><span class="sxs-lookup"><span data-stu-id="11e92-134">The Team Site Owners SharePoint group—with the Full Control permission level—is set to the Team Group owners</span></span>
    - <span data-ttu-id="11e92-135">Группа SharePoint участников сайта команды с уровнем разрешений "Изменить" настроена для участников группы команды</span><span class="sxs-lookup"><span data-stu-id="11e92-135">The Team Site Members SharePoint group—with the Edit permission level—is set to the Team Group members</span></span>
    - <span data-ttu-id="11e92-136">У группы SharePoint посетителей сайта команды с уровнем разрешений "Чтение" нет групп или учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="11e92-136">The Team Site Visitors SharePoint group—with the Read permission level—has no groups or user accounts</span></span>

<span data-ttu-id="11e92-137">Ниже представлены разрешения по умолчанию для сайта команды.</span><span class="sxs-lookup"><span data-stu-id="11e92-137">Here are the default permissions for the Team Site.</span></span>

![Разрешения по умолчанию для сайта команды](./media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
><span data-ttu-id="11e92-139">Если вы просматриваете группу SharePoint владельцев \<имя команды> на наличие разрешений "Изменить", в ней не отображаются владельцы \<имя команды>.</span><span class="sxs-lookup"><span data-stu-id="11e92-139">If you view the \<team name> Owners SharePoint group for the Edit permission level, it does not display \<team name> Owners.</span></span>
>

<span data-ttu-id="11e92-140">Итоговые разрешения позволяют следующее:</span><span class="sxs-lookup"><span data-stu-id="11e92-140">The resulting permissions allow:</span></span>

- <span data-ttu-id="11e92-141">Владельцы группы команды могут администрировать сайт и обладают полным доступом к содержимому сайта.</span><span class="sxs-lookup"><span data-stu-id="11e92-141">Team Group owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="11e92-142">Участники группы команды могут создавать и редактировать файлы на сайте.</span><span class="sxs-lookup"><span data-stu-id="11e92-142">Team Group members to create and edit files on the site.</span></span> 

<span data-ttu-id="11e92-143">Управление разрешениями аналогично управлению участниками и владельцами команды.</span><span class="sxs-lookup"><span data-stu-id="11e92-143">Permissions maintenance is the same as team member and owner maintenance.</span></span>

<span data-ttu-id="11e92-144">Ниже показана итоговая конфигурация на текущий момент.</span><span class="sxs-lookup"><span data-stu-id="11e92-144">Here’s the resulting configuration so far.</span></span>

![Шаг 2 настройки сценария защищенной команды](./media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a><span data-ttu-id="11e92-146">Шаг 3. Настройка базового сайта SharePoint для дополнительной безопасности</span><span class="sxs-lookup"><span data-stu-id="11e92-146">Step 3: Configure the underlying SharePoint site for additional security</span></span>

<span data-ttu-id="11e92-147">Настройте следующие параметры разрешений на сайте команды.</span><span class="sxs-lookup"><span data-stu-id="11e92-147">From the Team Site, configure these permission settings.</span></span>

1. <span data-ttu-id="11e92-148">На панели инструментов щелкните значок параметров и выберите вариант **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="11e92-148">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="11e92-149">В области **Разрешения для сайта** в разделе **Параметры общего доступа** щелкните **Изменить параметры общего доступа**.</span><span class="sxs-lookup"><span data-stu-id="11e92-149">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="11e92-150">В разделе **Разрешения на предоставление общего доступа** установите флажок **Только владельцы сайта могут делиться файлами, папками и сайтом**.</span><span class="sxs-lookup"><span data-stu-id="11e92-150">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="11e92-151">Отключите параметр **Разрешить запросы на доступ** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="11e92-151">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="11e92-152">При выборе этих параметров отключается возможность для участников группы команды предоставлять общий доступ к сайту команды другим пользователям, а также возможность запрашивать доступ к сайту команды для лиц, не являющихся участниками.</span><span class="sxs-lookup"><span data-stu-id="11e92-152">With these settings, the ability for Team Group members to share the Team Site with other members or for non-members to request access to the Team Site is disabled.</span></span>

<span data-ttu-id="11e92-153">Ниже показана итоговая конфигурация на текущий момент.</span><span class="sxs-lookup"><span data-stu-id="11e92-153">Here’s the resulting configuration so far.</span></span>

![Шаг 3 настройки сценария защищенной команды](./media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a><span data-ttu-id="11e92-155">Шаг 4. Создание метки хранения и политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="11e92-155">Step 4: Create a retention label and DLP policy</span></span>

<span data-ttu-id="11e92-156">Воспользуйтесь [этими инструкциями](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) для следующих действий:</span><span class="sxs-lookup"><span data-stu-id="11e92-156">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="11e92-157">Создание и публикация метки хранения для строго регулируемых данных (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="11e92-157">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="11e92-158">Настройка сайта команды для использования метки хранения, созданной на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="11e92-158">Configure the Team Site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="11e92-159">Создание политики защиты от потери данных для строго регулируемых данных, использующей метку хранения, созданную на шаге 2, и запрещающей пользователям отправлять файлы за пределы организации.</span><span class="sxs-lookup"><span data-stu-id="11e92-159">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization.</span></span> <span data-ttu-id="11e92-160">Кроме того, можно настроить политику для дополнительных требований, например для отраслевых норм здравоохранения и финансов, на основе [шаблонов политики DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span><span class="sxs-lookup"><span data-stu-id="11e92-160">You can also configure the policy for additional requirements, such as those for health and financial industry regulations, based on [DLP policy templates](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span></span>

<span data-ttu-id="11e92-161">Ниже показана итоговая конфигурация на текущий момент.</span><span class="sxs-lookup"><span data-stu-id="11e92-161">Here’s the resulting configuration so far.</span></span>

![Шаг 4 настройки сценария защищенной команды](./media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-the-label-or-a-sublabel-of-the-highly-regulated-label"></a><span data-ttu-id="11e92-163">Шаг 5. Создание метки или вложенной метки для метки строго регулируемых данных</span><span class="sxs-lookup"><span data-stu-id="11e92-163">Step 5: Create the label or a sublabel of the highly regulated label</span></span>

<span data-ttu-id="11e92-164">В отличие от метки конфиденциальности для строго регулируемых данных, которую любой пользователь может применить к любому файлу, защищенной команде требуется собственная метка или вложенная метка, чтобы файлы, которым она назначена:</span><span class="sxs-lookup"><span data-stu-id="11e92-164">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="11e92-165">были зашифрованы и оставались зашифрованными при перемещении;</span><span class="sxs-lookup"><span data-stu-id="11e92-165">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="11e92-166">содержали настраиваемые разрешения, благодаря которым их могут открыть только участники группы команды.</span><span class="sxs-lookup"><span data-stu-id="11e92-166">Contain custom permissions so that only members of the Team Group can open it.</span></span>

<span data-ttu-id="11e92-167">Чтобы установить этот дополнительный уровень безопасности для файлов, хранящихся на сайте команды, требуется настроить новую метку конфиденциальности, являющуюся самостоятельной меткой или вложенной меткой для общей метки строго регулируемых файлов.</span><span class="sxs-lookup"><span data-stu-id="11e92-167">To accomplish this additional level of security for files stored in the Team Site, you must configure a new sensitivity label that is either its own label a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="11e92-168">Только участники группы команды будут видеть ее в списке своих меток. </span><span class="sxs-lookup"><span data-stu-id="11e92-168">Only Team Group members will see it in their list of labels.</span></span>

<span data-ttu-id="11e92-169">Используйте метку конфиденциальности, если требуется небольшое число меток для общих и отдельных закрытых команд.</span><span class="sxs-lookup"><span data-stu-id="11e92-169">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="11e92-170">Используйте вложенную метку конфиденциальности, если у вас большое число меток или нужно упорядочить метки для закрытых команд под меткой строго регулируемых данных.</span><span class="sxs-lookup"><span data-stu-id="11e92-170">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams the under the highly regulated label.</span></span>

<span data-ttu-id="11e92-171">[Используйте эти инструкции](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels), чтобы настроить отдельную метку или вложенную метку со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="11e92-171">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="11e92-172">имя метки содержит название команды;</span><span class="sxs-lookup"><span data-stu-id="11e92-172">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="11e92-173">включено шифрование;</span><span class="sxs-lookup"><span data-stu-id="11e92-173">Encryption is enabled</span></span>
- <span data-ttu-id="11e92-174">группа команды имеет разрешения на совместное редактирование.</span><span class="sxs-lookup"><span data-stu-id="11e92-174">The Team Group has Co-Author permissions</span></span>

<span data-ttu-id="11e92-175">Ниже представлена итоговая конфигурация с новой меткой.</span><span class="sxs-lookup"><span data-stu-id="11e92-175">Here’s the resulting configuration with the new label.</span></span>

![Шаг 5 настройки сценария защищенной команды](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="11e92-177">Ниже показаны отношения между метками конфиденциальности и группой команды.</span><span class="sxs-lookup"><span data-stu-id="11e92-177">Here’s the relationship between the sensitivity label and the Team Group.</span></span>

![Отношения между группой команды и разрешениями меток](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
><span data-ttu-id="11e92-179">Если настроена метка или вложенная метка конфиденциальности для пользовательских разрешений или со сроком действия, вы не сможете открыть файл из Teams или SharePoint.</span><span class="sxs-lookup"><span data-stu-id="11e92-179">If you configure the sensitivity label or sublabel for user-defined permissions or with an expiration date, you cannot open the file from Teams or SharePoint.</span></span> <span data-ttu-id="11e92-180">Потребуется использовать приложение Office.</span><span class="sxs-lookup"><span data-stu-id="11e92-180">You must use an Office app.</span></span>
>

### <a name="custom-permissions"></a><span data-ttu-id="11e92-181">Настраиваемые разрешения</span><span class="sxs-lookup"><span data-stu-id="11e92-181">Custom permissions</span></span>

<span data-ttu-id="11e92-182">Вы также можете настроить собственные разрешения сайта SharePoint для сайта команды и соответствующую метку конфиденциальности при необходимости.</span><span class="sxs-lookup"><span data-stu-id="11e92-182">You can also configure custom SharePoint site permissions for the Team Site and, if needed, its corresponding sensitivity label.</span></span> <span data-ttu-id="11e92-183">Вот два примера.</span><span class="sxs-lookup"><span data-stu-id="11e92-183">Here are two examples.</span></span>

#### <a name="example-1-delegating-sharepoint-site-administration"></a><span data-ttu-id="11e92-184">Пример 1. Делегирование администрирования сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="11e92-184">Example 1: Delegating SharePoint site administration</span></span>

<span data-ttu-id="11e92-185">Если владелец команды не имеет опыта администрирования SharePoint или хочет делегировать управление сайтом команды, он может добавить учетную запись администратора SharePoint в список владельцев команды.</span><span class="sxs-lookup"><span data-stu-id="11e92-185">If the team owner does not have SharePoint administration experience or wants to delegate administration of the Team Site, they could add the user account of a SharePoint administrator to the list of team owners.</span></span> <span data-ttu-id="11e92-186">Но после этого администратор SharePoint получит полный доступ к команде и всем ее ресурсам и сможет открыть файл с примененной меткой конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="11e92-186">But then the SharePoint administrator would have full access to the team and all its resources and would be able to open a file with the sensitivity label applied.</span></span> 

<span data-ttu-id="11e92-187">Чтобы предотвратить такое предоставление избыточных разрешений, добавьте учетную запись администратора SharePoint в группу SharePoint владельцев сайта команды в разделе дополнительных разрешений для сайта.</span><span class="sxs-lookup"><span data-stu-id="11e92-187">To prevent this over-granting of privileges, add the user account of the SharePoint administrator to the Team Site Owners SharePoint group in the advanced permissions settings of the site.</span></span> <span data-ttu-id="11e92-188">Администратор SharePoint сможет управлять сайтом, но не сможет получить доступ к команде и ее ресурсам или открыть файлы с присвоенной меткой конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="11e92-188">The SharePoint administrator can administer the site but will not be able to access the team and any of its resources or open the files with the sensitivity label assigned.</span></span>

#### <a name="example-2-allowing-view-only-access-to-labeled-files"></a><span data-ttu-id="11e92-189">Пример 2. Предоставление доступа только для просмотра файлов с метками</span><span class="sxs-lookup"><span data-stu-id="11e92-189">Example 2: Allowing view-only access to labeled files</span></span>

<span data-ttu-id="11e92-190">Если некоторым сотрудникам требуется просматривать содержимое файлов с метками на сайте команды, добавьте их отдельные учетные записи пользователей в:</span><span class="sxs-lookup"><span data-stu-id="11e92-190">If some staff only need to view the contents of labeled files in the Team Site, add their individual user accounts to the:</span></span>

- <span data-ttu-id="11e92-191">группу SharePoint посетителей \<название команды>, по умолчанию имеющую уровень разрешений "Чтение";</span><span class="sxs-lookup"><span data-stu-id="11e92-191">\<team name> Visitors SharePoint group, which by default has the Read permission level.</span></span> 
- <span data-ttu-id="11e92-192">метку конфиденциальности с разрешениями для просмотра.</span><span class="sxs-lookup"><span data-stu-id="11e92-192">The sensitivity label with the Viewer permissions.</span></span>

<span data-ttu-id="11e92-193">Ниже представлены итоговые разрешения для метки.</span><span class="sxs-lookup"><span data-stu-id="11e92-193">Here are the resulting permissions on the label.</span></span>

![Пример настраиваемых разрешений для просмотра файлов с метками](./media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
<span data-ttu-id="11e92-195">Посетители сайта смогут напрямую получить доступ к сайту команды и просмотреть содержимое файлов с примененными вложенными метками.</span><span class="sxs-lookup"><span data-stu-id="11e92-195">The site visitors will be able to access the Team Site directly and view the contents of files that have the sublabel applied.</span></span> <span data-ttu-id="11e92-196">Но так как они не являются участниками группы команды, они не смогут получить доступ к команде и ее ресурсам.</span><span class="sxs-lookup"><span data-stu-id="11e92-196">But because they are not members of the Team Group, they will not be able to access the team or any of its resources.</span></span>


## <a name="phase-2-drive-user-adoption-for-team-members"></a><span data-ttu-id="11e92-197">Этап 2. Внедрение возможностей среди участников команды</span><span class="sxs-lookup"><span data-stu-id="11e92-197">Phase 2: Drive user adoption for team members</span></span>

<span data-ttu-id="11e92-198">После создания команды нужно обеспечить применение ее возможностей и дополнительной защиты для участников команды.</span><span class="sxs-lookup"><span data-stu-id="11e92-198">With the team in place, it’s time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="11e92-199">Шаг 1. Обучение пользователей</span><span class="sxs-lookup"><span data-stu-id="11e92-199">Step 1: Train your users</span></span>

<span data-ttu-id="11e92-200">Участники группы команды могут получить доступ к команде и всем ее ресурсам, включая чаты, собрания и другие приложения.</span><span class="sxs-lookup"><span data-stu-id="11e92-200">Members of the Team Group can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="11e92-201">При работе с файлами из раздела **Файлы** канала участники группы команды должны назначать метку конфиденциальности или вложенную метку файлам, создаваемым для защищенной команды.</span><span class="sxs-lookup"><span data-stu-id="11e92-201">When working with files from the **Files** section of a channel, members of the Team Group must assign the sensitivity label or sublabel to files created for the secure team.</span></span> <span data-ttu-id="11e92-202">Приведем пример.</span><span class="sxs-lookup"><span data-stu-id="11e92-202">Here’s an example.</span></span>

![Пример метки, применяемой к файлу в защищенной команде](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
<span data-ttu-id="11e92-204">После применения метки к файлу он становится защищенным.</span><span class="sxs-lookup"><span data-stu-id="11e92-204">When the label gets applied to the file it is secured.</span></span> <span data-ttu-id="11e92-205">Участники группы команды могут открывать его в Teams и совместно работать с ним в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="11e92-205">Members of the Team Group can open it in Teams and collaborate in real time.</span></span> <span data-ttu-id="11e92-206">Он зашифрован и содержит разрешения на совместное редактирование, настроенные для участников группы команды.</span><span class="sxs-lookup"><span data-stu-id="11e92-206">It is encrypted and includes the Co-Author permissions set to the Team Group members.</span></span> <span data-ttu-id="11e92-207">Если файл покидает сайт и пересылается злоумышленнику, ему потребуется предоставить учетные данные пользователя, являющегося участником группы команды, чтобы открыть его и просмотреть содержимое.</span><span class="sxs-lookup"><span data-stu-id="11e92-207">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the Team Group to open the file and view its contents.</span></span> 

<span data-ttu-id="11e92-208">Обучите участников команды, рассказав им:</span><span class="sxs-lookup"><span data-stu-id="11e92-208">Train your team members:</span></span>

- <span data-ttu-id="11e92-209">насколько важно использовать новую команду для чатов, собраний, файлов и других ресурсов сайта команды, а также о последствиях утечки жестко регламентированных данных, таких как юридические последствия, штрафные санкции за несоблюдение нормативно-правовых актов, появление программ-шантажистов или потеря конкурентного преимущества;</span><span class="sxs-lookup"><span data-stu-id="11e92-209">On the importance of using the new team for chats, meetings, files, and the other resources of the Team Site and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="11e92-210">как получить доступ к команде;</span><span class="sxs-lookup"><span data-stu-id="11e92-210">How to access the team.</span></span>
- <span data-ttu-id="11e92-211">как создавать файлы на сайте и отправлять новые файлы, которые хранятся локально;</span><span class="sxs-lookup"><span data-stu-id="11e92-211">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="11e92-212">каким образом политика защиты от потери данных блокирует пользователей при попытке отправить файлы за пределы организации;</span><span class="sxs-lookup"><span data-stu-id="11e92-212">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="11e92-213">как пометить файлы с помощью настраиваемых меток или вложенных меток для команды;</span><span class="sxs-lookup"><span data-stu-id="11e92-213">How to label files with the custom label or sublabel for the team.</span></span>
- <span data-ttu-id="11e92-214">как метка или вложенная метка защищает файлы даже в случае их утечки с сайта.</span><span class="sxs-lookup"><span data-stu-id="11e92-214">How the label or sublabel protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="11e92-215">В программу такого обучения следует включить практические занятия, где участники команды смогут опробовать эти возможности и ознакомиться с результатами.</span><span class="sxs-lookup"><span data-stu-id="11e92-215">This training should include hands-on exercises so that your team members can experience these capabilities and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="11e92-216">Шаг 2. Проведение периодических проверок использования и ответы на отзывы участников команды</span><span class="sxs-lookup"><span data-stu-id="11e92-216">Step 2: Conduct periodic reviews of usage and address team member feedback</span></span>

<span data-ttu-id="11e92-217">В последующие за обучением недели:</span><span class="sxs-lookup"><span data-stu-id="11e92-217">In the weeks after training:</span></span>

- <span data-ttu-id="11e92-218">Быстро рассмотрите отзывы участников команды и отрегулируйте политики и настройки.</span><span class="sxs-lookup"><span data-stu-id="11e92-218">Quickly address team member feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="11e92-219">Проанализируйте использование команды и сравните результаты с требованиями к использованию.</span><span class="sxs-lookup"><span data-stu-id="11e92-219">Analyze usage for the team and compare it with usage expectations.</span></span>
- <span data-ttu-id="11e92-220">Убедитесь в правильном применении настраиваемых меток или вложенных меток конфиденциальности к строго регулируемым файлам.</span><span class="sxs-lookup"><span data-stu-id="11e92-220">Verify that highly regulated files have been properly labeled with the custom sensitivity label or sublabel.</span></span>

  <span data-ttu-id="11e92-221">Вы можете узнать, каким файлам присвоены метки, просмотрев папку в SharePoint и добавив столбец **Конфиденциальность** с помощью параметра **Показать/скрыть столбцы** элемента **Добавить столбец**.</span><span class="sxs-lookup"><span data-stu-id="11e92-221">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="11e92-222">При необходимости следует провести повторное обучение пользователей.</span><span class="sxs-lookup"><span data-stu-id="11e92-222">Retrain your users as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="11e92-223">См. также</span><span class="sxs-lookup"><span data-stu-id="11e92-223">See also</span></span>

[<span data-ttu-id="11e92-224">Сайты SharePoint для строго регулируемых данных</span><span class="sxs-lookup"><span data-stu-id="11e92-224">SharePoint sites for highly regulated data</span></span>](teams-sharepoint-online-sites-highly-regulated-data.md)

[<span data-ttu-id="11e92-225">Рабочие нагрузки и сценарии Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="11e92-225">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="11e92-226">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="11e92-226">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="11e92-227">Руководство по развертыванию</span><span class="sxs-lookup"><span data-stu-id="11e92-227">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
