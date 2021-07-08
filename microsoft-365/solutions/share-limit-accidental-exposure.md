---
title: Ограничение возможности случайного раскрытия
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: Узнайте, как ограничить возможность случайного раскрытия информации при предоставлении общего доступа к файлам пользователям за пределами вашей организации.
ms.openlocfilehash: 1dffa40a0c21f5f611492d5a098a98f8aaa726a5
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53326991"
---
# <a name="limit-accidental-exposure-to-files-when-sharing-with-people-outside-your-organization"></a><span data-ttu-id="dacff-103">Ограничение возможности случайного раскрытия информации при предоставлении общего доступа к файлам пользователям за пределами организации</span><span class="sxs-lookup"><span data-stu-id="dacff-103">Limit accidental exposure to files when sharing with people outside your organization</span></span>

<span data-ttu-id="dacff-104">Существуют различные варианты, позволяющие снизить вероятность случайного раскрытия конфиденциальной информации при предоставлении общего доступа к файлам и папкам пользователям за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="dacff-104">When sharing files and folders with people outside your organization, there are various options to reduce the chances of accidentally sharing sensitive information.</span></span> <span data-ttu-id="dacff-105">Чтобы обеспечить соответствие требованиям вашей организации, можете выбрать один из описанных в этой статье вариантов.</span><span class="sxs-lookup"><span data-stu-id="dacff-105">You can choose from the options in this article to best meet the needs of your organization.</span></span>

## <a name="use-best-practices-for-anyone-links"></a><span data-ttu-id="dacff-106">Следуйте рекомендациям для ссылок типа "Любой пользователь"</span><span class="sxs-lookup"><span data-stu-id="dacff-106">Use best practices for Anyone links</span></span>

<span data-ttu-id="dacff-107">Если сотрудникам вашей организации требуется предоставлять общий доступ без проверки подлинности, но вас беспокоит, что пользователи, не прошедшие проверку подлинности, могут изменять содержимое, см. статью [Рекомендации по предоставлению общего доступа без проверки подлинности](best-practices-anonymous-sharing.md), чтобы узнать, как эту возможность реализовать в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="dacff-107">If people in your organization need to do unauthenticated sharing, but you're concerned about unauthenticated people modifying content, read [Best practices for unauthenticated sharing](best-practices-anonymous-sharing.md) for guidance on how to work with unauthenticated sharing in your organization.</span></span>

## <a name="turn-off-anyone-links"></a><span data-ttu-id="dacff-108">Отключение ссылок типа "Любой пользователь"</span><span class="sxs-lookup"><span data-stu-id="dacff-108">Turn off Anyone links</span></span>

<span data-ttu-id="dacff-109">Рекомендуем оставить тип ссылок *Любой пользователь* включенным для соответствующего содержимого, так как это самый простой способ предоставления общего доступа, который помогает снизить риск применения других решений, неконтролируемых вашим ИТ-отделом.</span><span class="sxs-lookup"><span data-stu-id="dacff-109">We recommend leaving *Anyone* links enabled for appropriate content because it's the easiest way to share and can help reduce the risk of users seeking other solutions that are outside the control of your IT department.</span></span> <span data-ttu-id="dacff-110">Ссылки типа *Любой пользователь* можно пересылать другим, но доступ к файлам предоставляется только тем, у кого есть ссылка.</span><span class="sxs-lookup"><span data-stu-id="dacff-110">*Anyone* links can be forwarded to others, but file access is only available to those who have the link.</span></span>

<span data-ttu-id="dacff-111">Если вы хотите, чтобы пользователи за пределами организации проходили проверку подлинности каждый раз при получении доступа к файлам в SharePoint, "Группах" или Teams, отключите предоставление доступа типа *Любой пользователь*.</span><span class="sxs-lookup"><span data-stu-id="dacff-111">If you always want people outside your organization to authenticate when accessing content in SharePoint, Groups, or Teams, you can turn off *Anyone* sharing.</span></span> <span data-ttu-id="dacff-112">При этом пользователи не смогут предоставлять общий доступ к контенту без проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="dacff-112">This will prevent users from unauthenticated sharing of content.</span></span>

<span data-ttu-id="dacff-113">Если отключить ссылки типа *Любой пользователь*, пользователи все еще смогут легко предоставлять гостям доступ к файлам с помощью ссылок типа *Определенные пользователи*.</span><span class="sxs-lookup"><span data-stu-id="dacff-113">If you disable *Anyone* links, users can still easily share with guests using *Specific people* links.</span></span> <span data-ttu-id="dacff-114">В этом случае, чтобы получить доступ к предоставленному содержимому, пользователям за пределами вашей организации потребуется пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="dacff-114">In this case, all people outside your organization will be required to authenticate before they can access the shared content.</span></span>

<span data-ttu-id="dacff-115">При необходимости можно отключить тип ссылок *Любой пользователь* для определенных сайтов или для всей организации.</span><span class="sxs-lookup"><span data-stu-id="dacff-115">Depending on your needs, you can disable *Anyone* links for specific sites, or for your whole organization.</span></span>

<span data-ttu-id="dacff-116">Отключение типа ссылок *Любой пользователь* для организации</span><span class="sxs-lookup"><span data-stu-id="dacff-116">To turn off *Anyone* links for your organization</span></span>
1. <span data-ttu-id="dacff-117">Откройте Центр администрирования SharePoint и на панели навигации слева нажмите кнопку **Доступ**.</span><span class="sxs-lookup"><span data-stu-id="dacff-117">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
2. <span data-ttu-id="dacff-118">В настройках внешнего общего доступа к SharePoint задайте значение **Новые и существующие гости**.</span><span class="sxs-lookup"><span data-stu-id="dacff-118">Set the SharePoint external sharing settings to **New and existing guests**.</span></span>

   ![Снимок экрана: параметры внешнего общего доступа к сайту SharePoint на уровне организации](../media/sharepoint-organization-external-sharing-controls-new-users.png)

3. <span data-ttu-id="dacff-120">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="dacff-120">Click **Save**.</span></span>

<span data-ttu-id="dacff-121">Отключение типа ссылок *Любой пользователь* для сайта</span><span class="sxs-lookup"><span data-stu-id="dacff-121">To turn off *Anyone* links for a site</span></span>
1. <span data-ttu-id="dacff-122">Откройте Центр администрирования SharePoint, затем на панели навигации слева разверните меню **Сайты** и нажмите **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="dacff-122">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="dacff-123">Выберите сайт, который нужно настроить.</span><span class="sxs-lookup"><span data-stu-id="dacff-123">Select the site that you want to configure.</span></span>
3. <span data-ttu-id="dacff-124">На ленте выберите **Доступ**.</span><span class="sxs-lookup"><span data-stu-id="dacff-124">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="dacff-125">В настройках общего доступа задайте значение **Новые и существующие гости**.</span><span class="sxs-lookup"><span data-stu-id="dacff-125">Ensure that sharing is set to **New and existing guests**.</span></span>

   ![Снимок экрана: параметры внешнего общего доступа к сайту SharePoint на уровне сайта](../media/sharepoint-site-external-sharing-settings.png)

5. <span data-ttu-id="dacff-127">Если внесены изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="dacff-127">If you made changes, click **Save**.</span></span>

## <a name="domain-filtering"></a><span data-ttu-id="dacff-128">Фильтрация доменов</span><span class="sxs-lookup"><span data-stu-id="dacff-128">Domain filtering</span></span>

<span data-ttu-id="dacff-129">Чтобы указать домены, которые ваши сотрудники могут использовать при предоставлении общего доступа пользователям за пределами организации, можно добавить списки разрешенных и запрещенных доменов.</span><span class="sxs-lookup"><span data-stu-id="dacff-129">You can use domain allow or deny lists to specify which domains your users can use when sharing with people outside your organization.</span></span>

<span data-ttu-id="dacff-130">В списке разрешений можно указать домены, в которых ваши сотрудники могут предоставлять общий доступ пользователям за пределами организации.  </span><span class="sxs-lookup"><span data-stu-id="dacff-130">With an allow list, you can specify a list of domains where users in your organization can share with people outside your organization.</span></span> <span data-ttu-id="dacff-131">Предоставление общего доступа пользователям из других доменов заблокировано.</span><span class="sxs-lookup"><span data-stu-id="dacff-131">Sharing with other domains is blocked.</span></span> <span data-ttu-id="dacff-132">Если ваша организация взаимодействует только с пользователями из списка указанных доменов, эта возможность позволит предотвратить доступ из других доменов.</span><span class="sxs-lookup"><span data-stu-id="dacff-132">If your organization only collaborates with people from a list of specific domains, you can use this feature to prevent sharing with other domains.</span></span>

<span data-ttu-id="dacff-133">В списке запретов можно указать домены, из которых ваши сотрудники не могут предоставлять общий доступ пользователям за пределами организации.  </span><span class="sxs-lookup"><span data-stu-id="dacff-133">With a deny list, you can specify a list of domains from which users in your organization cannot share with people outside your organization.</span></span> <span data-ttu-id="dacff-134">Предоставление общего доступа пользователям из перечисленных доменов заблокировано.</span><span class="sxs-lookup"><span data-stu-id="dacff-134">Sharing with the listed domains is blocked.</span></span> <span data-ttu-id="dacff-135">К примеру, это может быть полезно, если у вас есть конкуренты, которые не должны получить доступ к документам вашей организации.</span><span class="sxs-lookup"><span data-stu-id="dacff-135">This can be useful if you have competitors, for example, who you want to prevent from accessing content in your organization.</span></span>

<span data-ttu-id="dacff-136">Списки разрешенных и запрещенных доменов касаются только предоставления доступа гостям.</span><span class="sxs-lookup"><span data-stu-id="dacff-136">The allow and deny lists only affect sharing with guests.</span></span> <span data-ttu-id="dacff-137">Пользователи смогут предоставлять общий доступ пользователям из запрещенных доменов с помощью *общедоступных* ссылок, если вы их не отключите.</span><span class="sxs-lookup"><span data-stu-id="dacff-137">Users can still share with people from prohibited domains by using *Anyone* links if you haven't disabled them.</span></span> <span data-ttu-id="dacff-138">Чтобы списки разрешенных и запрещенных доменов выполняли свою функцию должным образом, отключите ссылки типа *Любой пользователь*, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="dacff-138">For best results with domain allow and deny lists, consider disabling *Anyone* links as described above.</span></span>

<span data-ttu-id="dacff-139">Настройка списка разрешенных и запрещенных доменов</span><span class="sxs-lookup"><span data-stu-id="dacff-139">To set up a domain allow or deny list</span></span>
1. <span data-ttu-id="dacff-140">Откройте Центр администрирования SharePoint и на панели навигации слева нажмите кнопку **Доступ**.</span><span class="sxs-lookup"><span data-stu-id="dacff-140">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
2. <span data-ttu-id="dacff-141">В разделе **Дополнительные параметры для внешнего общего доступа** установите флажок **Ограничение внешнего общего доступа по домену**.</span><span class="sxs-lookup"><span data-stu-id="dacff-141">Under **Advanced settings for external sharing**, select the **Limit external sharing by domain** check box.</span></span>
3. <span data-ttu-id="dacff-142">Нажмите кнопку **Добавить домены**.</span><span class="sxs-lookup"><span data-stu-id="dacff-142">Click **Add domains**.</span></span>
4. <span data-ttu-id="dacff-143">Укажите, нужно ли блокировать домены, введите имена доменов и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dacff-143">Select whether you want to block domains, type the domains, and click **OK**.</span></span>

   ![Снимок экрана: параметр ограничения внешнего общего доступа к SharePoint по домену](../media/sharepoint-sharing-block-domain.png)

5. <span data-ttu-id="dacff-145">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="dacff-145">Click **Save**.</span></span>

<span data-ttu-id="dacff-146">Если вы хотите ограничить предоставление общего доступа по домену на более высоком уровне, чем в SharePoint и OneDrive, вы можете [разрешить или заблокировать приглашения для пользователей B2B из определенных организаций](/azure/active-directory/b2b/allow-deny-list) в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dacff-146">If you want to limit sharing by domain at a higher level than SharePoint and OneDrive, you can [allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list) in Azure Active Directory.</span></span> <span data-ttu-id="dacff-147">Необходимо настроить [интеграцию SharePoint и OneDrive с Azure AD B2B (предварительная версия)](/sharepoint/sharepoint-azureb2b-integration-preview), чтобы эти параметры повлияли на SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="dacff-147">(You must configure the [SharePoint and OneDrive integration with Azure AD B2B Preview](/sharepoint/sharepoint-azureb2b-integration-preview) for these settings to affect SharePoint and OneDrive.)</span></span>

## <a name="limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups"></a><span data-ttu-id="dacff-148">Ограничение общего доступа к файлам, папкам и сайтам для пользователей за пределами организации определенными группами безопасности</span><span class="sxs-lookup"><span data-stu-id="dacff-148">Limit sharing of files, folders, and sites with people outside your organization to specified security groups</span></span>

<span data-ttu-id="dacff-149">Вы можете ограничить доступ к файлам, папкам и сайтам для пользователей за пределами организации, разрешив его только для участников определенной группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="dacff-149">You can restrict sharing of files, folders, and sites with people outside your organization to members of a specific security group.</span></span> <span data-ttu-id="dacff-150">Это полезно, если вы хотите включить внешний общий доступ, но с использованием рабочего процесса утверждения или отправки запроса.</span><span class="sxs-lookup"><span data-stu-id="dacff-150">This is useful if you want to enable external sharing, but with an approval workflow or request process.</span></span> <span data-ttu-id="dacff-151">Кроме того, вы можете требовать от своих пользователей прохождения учебного курса, прежде чем они будут добавлены в группу безопасности и смогут предоставлять внешний общий доступ.</span><span class="sxs-lookup"><span data-stu-id="dacff-151">Alternatively, you might require your users to complete a training course before they're added to the security group and are allowed to share externally.</span></span>

<span data-ttu-id="dacff-152">Ограничение внешнего общего доступа группой безопасности</span><span class="sxs-lookup"><span data-stu-id="dacff-152">To limit external sharing to members of a security group</span></span>
1. <span data-ttu-id="dacff-153">Откройте [Центр администрирования SharePoint](https://admin.microsoft.com/sharepoint) и в области навигации слева в разделе **Политики** щелкните **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="dacff-153">In the [SharePoint admin center](https://admin.microsoft.com/sharepoint), in the left navigation, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="dacff-154">В разделе **Внешний общий доступ** разверните пункт **Другие параметры внешнего общего доступа**.</span><span class="sxs-lookup"><span data-stu-id="dacff-154">Under **External sharing**, expand **More external sharing settings**.</span></span>

3. <span data-ttu-id="dacff-155">Выберите **Разрешить только пользователям из определенных групп безопасности предоставлять внешний общий доступ**, а затем нажмите **Управление группами безопасности**.</span><span class="sxs-lookup"><span data-stu-id="dacff-155">Select **Allow only users in specific security groups to share externally**, and then select **Manage security groups**.</span></span>

    ![Снимок экрана: панель "Управление группами безопасности"](/sharepoint/sharepointonline/media/manage-security-groups.png)

4. <span data-ttu-id="dacff-157">В поле **Добавление группы безопасности** введите имя группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="dacff-157">In the **Add a security group** box, enter a name for a security group.</span></span> <span data-ttu-id="dacff-158">Появится окно группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="dacff-158">The security group box appears.</span></span>

5. <span data-ttu-id="dacff-159">Рядом с именем группы безопасности в раскрывающемся списке **Может делиться с** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="dacff-159">Next to the security group name, from the **Can share with** dropdown, select either:</span></span>

    - <span data-ttu-id="dacff-160">**Только гости, прошедшие проверку подлинности** (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="dacff-160">**Authenticated guests only** (default)</span></span>
    - <span data-ttu-id="dacff-161">**Все**</span><span class="sxs-lookup"><span data-stu-id="dacff-161">**Anyone**</span></span>

6. <span data-ttu-id="dacff-162">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="dacff-162">Select **Save**.</span></span>

<span data-ttu-id="dacff-163">Обратите внимание, что это относится к файлам, папкам и сайтам, но не к группам Microsoft 365 или Teams.</span><span class="sxs-lookup"><span data-stu-id="dacff-163">Note that this affects files, folders, and sites, but not Microsoft 365 groups or Teams.</span></span> <span data-ttu-id="dacff-164">Когда участники приглашают гостей в закрытую группу Microsoft 365 или закрытую команду в Microsoft Teams, приглашение отправляется владельцу группы или команды для утверждения.</span><span class="sxs-lookup"><span data-stu-id="dacff-164">When members invite guests to a private Microsoft 365 group or a private team in Microsoft Teams, the invitation is sent to the group or team owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="dacff-165">См. также</span><span class="sxs-lookup"><span data-stu-id="dacff-165">See Also</span></span>

[<span data-ttu-id="dacff-166">Создание безопасной среды гостевого доступа</span><span class="sxs-lookup"><span data-stu-id="dacff-166">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="dacff-167">Рекомендации по предоставлению общего доступа к файлам и папкам анонимным пользователям</span><span class="sxs-lookup"><span data-stu-id="dacff-167">Best practices for sharing files and folders with anonymous users</span></span>](best-practices-anonymous-sharing.md)
