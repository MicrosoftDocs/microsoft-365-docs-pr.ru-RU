---
title: Защита от потери данных и Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Теперь политики DLP можно применять для Microsoft Teams чатов и каналов. Ознакомьтесь с этой статьей, чтобы узнать больше о том, как она работает.
ms.openlocfilehash: ac4c326fccd6faccca92844a55c419faa61a8d4c
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114187"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="7e1b6-104">Защита от потери данных и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e1b6-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="7e1b6-105">Недавно в Microsoft Teams сообщения чата и канала для пользователей, лицензированных для Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 защиты и управления или Office 365 Advanced Compliance.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance or Office 365 Advanced Compliance.</span></span> <span data-ttu-id="7e1b6-106">Office 365 и Microsoft 365 E3 включают защиту DLP для SharePoint Online, OneDrive и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="7e1b6-107">Это также включает файлы, которые Teams, поскольку Teams использует SharePoint Online и OneDrive для общего использования файлов.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="7e1b6-108">Поддержка защиты DLP в Teams чате требует E5.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="7e1b6-109">Дополнительные сведения о требованиях к лицензированию см. в статье [Рекомендации по лицензированию служб на уровне клиента Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="7e1b6-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="7e1b6-110">Обзор защиты от потери данных для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e1b6-110">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="7e1b6-111">Недавно [были](dlp-learn-about-dlp.md) расширены возможности по предотвращению потери данных, включив Microsoft Teams сообщения чата и канала, включая сообщения **частных каналов.**</span><span class="sxs-lookup"><span data-stu-id="7e1b6-111">Recently, [data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages**.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="7e1b6-112">В настоящее время DLP применяется только к фактическим сообщениям в потоке чата или канала.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-112">DLP currently applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="7e1b6-113">Уведомления об активности, которые включают краткий предварительный просмотр сообщений и  отображаются на основе параметров уведомлений пользователя, в настоящее время Teams DLP.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-113">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP at this time.</span></span> <span data-ttu-id="7e1b6-114">Все конфиденциальные сведения, представленные в части сообщения, которое отображается в предварительном просмотре, будут видны в уведомлении даже после того, как политика DLP была применена и удалена конфиденциальную информацию самого сообщения.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-114">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

<span data-ttu-id="7e1b6-115">Если в организации есть DLP, теперь можно определить политики, которые мешают людям делиться конфиденциальной информацией в Microsoft Teams канале или сеансе чата.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-115">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="7e1b6-116">Вот несколько примеров работы этой защиты.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-116">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="7e1b6-117">**Пример 1. Защита конфиденциальной информации в сообщениях.**</span><span class="sxs-lookup"><span data-stu-id="7e1b6-117">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="7e1b6-118">Предположим, что кто-то пытается поделиться конфиденциальной информацией в Teams чате или канале с гостями (внешними пользователями).</span><span class="sxs-lookup"><span data-stu-id="7e1b6-118">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="7e1b6-119">Если для предотвращения этого установлена политика DLP, сообщения с конфиденциальной информацией, которые отправляются внешним пользователям, удаляются.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-119">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="7e1b6-120">Это происходит автоматически и в течение нескольких секунд в соответствии с настройкой политики DLP.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-120">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7e1b6-121">DLP для Microsoft Teams блокирует конфиденциальный контент при совместном Microsoft Teams пользователями, у которых есть:</span><span class="sxs-lookup"><span data-stu-id="7e1b6-121">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="7e1b6-122">- [гостевой доступ](/MicrosoftTeams/guest-access) в командах и каналах; или</span><span class="sxs-lookup"><span data-stu-id="7e1b6-122">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="7e1b6-123">- [внешний доступ](/MicrosoftTeams/manage-external-access) к собраниям и сеансам чата.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-123">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="7e1b6-124">DLP для внешних сеансов чата будет работать только в том случае, если отправитель и приемник находятся в режиме Teams только и используют Microsoft Teams [федерацию](/microsoftteams/manage-external-access).</span><span class="sxs-lookup"><span data-stu-id="7e1b6-124">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="7e1b6-125">DLP для Teams не блокирует сообщения [](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) в ходе Skype для бизнеса сеансов чата с федеративами.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-125">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="7e1b6-126">**Пример 2. Защита конфиденциальной информации в документах.**</span><span class="sxs-lookup"><span data-stu-id="7e1b6-126">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="7e1b6-127">Предположим, что кто-то пытается поделиться документом с гостями в Microsoft Teams канале или чате, а документ содержит конфиденциальные сведения.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-127">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="7e1b6-128">Если для предотвращения этого установлена политика DLP, документ не будет открыт для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-128">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="7e1b6-129">Обратите внимание, что в этом случае политика DLP должна включать SharePoint и OneDrive, чтобы обеспечить защиту.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-129">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="7e1b6-130">(Это пример DLP для SharePoint, который появляется в Microsoft Teams, и поэтому требует, чтобы пользователи лицензированы для Office 365 DLP (включен в Office 365 E3), но не требует, чтобы пользователи были лицензированы для Office 365 Advanced Compliance.)</span><span class="sxs-lookup"><span data-stu-id="7e1b6-130">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="7e1b6-131">Советы по политике помогают обучать пользователей</span><span class="sxs-lookup"><span data-stu-id="7e1b6-131">Policy tips help educate users</span></span>

<span data-ttu-id="7e1b6-132">Подобно тому, как DLP работает в [Exchange, Outlook, Outlook](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)в Интернете, [SharePoint Online, OneDrive для бизнеса](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)сайтах и [Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)настольных клиентов, советы по политике появляются при конфликте действий с политикой DLP.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-132">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="7e1b6-133">Вот пример подсказки политики:</span><span class="sxs-lookup"><span data-stu-id="7e1b6-133">Here's an example of a policy tip:</span></span>

![Заблокированное уведомление о сообщении в Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="7e1b6-135">В этом случае отправитель попытался поделиться номером социального обеспечения в Microsoft Teams канале.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-135">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="7e1b6-136">Ссылка **Что я могу сделать?** открывает диалоговое окно, которое предоставляет варианты для отправитель для решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-136">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="7e1b6-137">Обратите внимание, что в этом случае отправитель может переопределить политику или уведомить об этом администратора.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-137">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![Параметры для устранения заблокированного сообщения](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="7e1b6-139">В организации можно разрешить пользователям переопределять политику DLP.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-139">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="7e1b6-140">При настройке политик DLP можно использовать советы по политике по умолчанию или настроить советы по политике [для](#to-customize-policy-tips) организации.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-140">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="7e1b6-141">Возвращаясь к нашему примеру, когда отправитель поделился номером социального обеспечения в канале Teams, вот что увидел получатель:</span><span class="sxs-lookup"><span data-stu-id="7e1b6-141">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7e1b6-142">![Заблокировано сообщение](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="7e1b6-142">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="7e1b6-143">Настройка подсказок политики</span><span class="sxs-lookup"><span data-stu-id="7e1b6-143">To customize policy tips</span></span>

<span data-ttu-id="7e1b6-144">Для выполнения этой задачи вам должна быть назначена роль с разрешениями на редактирование политик защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-144">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="7e1b6-145">Дополнительные сведения см. в статье [Разрешения](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="7e1b6-145">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="7e1b6-146">Перейдите в Центр & безопасности [https://protection.office.com](https://protection.office.com) () и войдите.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-146">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="7e1b6-147">Выберите **политику предотвращения**  >  **потери данных.**</span><span class="sxs-lookup"><span data-stu-id="7e1b6-147">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="7e1b6-148">Выберите политику, а рядом с настройками **политики** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-148">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="7e1b6-149">Создайте новое правило или отредактировать существующее правило для политики.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-149">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7e1b6-150">![Изменение правила для политики](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="7e1b6-150">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="7e1b6-151">На **вкладке Уведомления пользователя** выберите **Настройка** текста электронной почты и/или настройка вариантов текста **подсказки** политики.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-151">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7e1b6-152">![Настройка пользовательских уведомлений и советов по политике](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="7e1b6-152">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="7e1b6-153">Укажите текст, который необходимо использовать для уведомлений электронной почты и/или советов по политике, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-153">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="7e1b6-154">На **вкладке Параметры политики** выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-154">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="7e1b6-155">Разрешить примерно один час, чтобы изменения работали через центр обработки данных и синхронизируются с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-155">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="7e1b6-156">Добавление Microsoft Teams в качестве расположения к существующим политикам защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="7e1b6-156">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="7e1b6-157">Для выполнения этой задачи вам должна быть назначена роль с разрешениями на редактирование политик защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-157">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="7e1b6-158">Дополнительные сведения см. в статье [Разрешения](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="7e1b6-158">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="7e1b6-159">Перейдите в Центр & безопасности [https://protection.office.com](https://protection.office.com) () и войдите.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-159">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="7e1b6-160">Выберите **политику предотвращения**  >  **потери данных.**</span><span class="sxs-lookup"><span data-stu-id="7e1b6-160">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="7e1b6-161">Выберите политику и посмотрите на значения в **"Расположениях".**</span><span class="sxs-lookup"><span data-stu-id="7e1b6-161">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="7e1b6-162">Если вы видите **Teams и сообщения каналов,** вы все настроены.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-162">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="7e1b6-163">Если этого не делать, нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-163">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7e1b6-164">![Расположения для существующей политики](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="7e1b6-164">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="7e1b6-165">В **столбце Состояние** включаем политику для Teams **и сообщений каналов.**</span><span class="sxs-lookup"><span data-stu-id="7e1b6-165">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7e1b6-166">![DLP для Teams и каналов](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="7e1b6-166">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="7e1b6-167">На **вкладке Выбор расположения** сохраняйте параметр по умолчанию для всех учетных записей или выберите **Позвольте мне выбрать определенные расположения.**</span><span class="sxs-lookup"><span data-stu-id="7e1b6-167">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="7e1b6-168">Можно указать:</span><span class="sxs-lookup"><span data-stu-id="7e1b6-168">You can specify:</span></span>

    1. <span data-ttu-id="7e1b6-169">до 1000 отдельных учетных записей, которые необходимо включить или исключить</span><span class="sxs-lookup"><span data-stu-id="7e1b6-169">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="7e1b6-170">списки рассылки и группы безопасности, которые необходимо включить или исключить.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-170">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="7e1b6-171">Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-171">Then choose **Next**.</span></span>

7. <span data-ttu-id="7e1b6-172">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-172">Click **Save**.</span></span>

<span data-ttu-id="7e1b6-173">Разрешить примерно один час, чтобы изменения работали через центр обработки данных и синхронизируются с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-173">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="7e1b6-174">Определение новой политики защиты от потери данных для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e1b6-174">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="7e1b6-175">Для выполнения этой задачи вам должна быть назначена роль с разрешениями на редактирование политик защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-175">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="7e1b6-176">Дополнительные сведения см. в статье [Разрешения](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="7e1b6-176">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="7e1b6-177">Перейдите в Центр & безопасности [https://protection.office.com](https://protection.office.com) () и войдите.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-177">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="7e1b6-178">Выберите **политику предотвращения потери**  >    >  **данных + Создайте политику**.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-178">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="7e1b6-179">Выберите [шаблон,](data-loss-prevention-policies.md#dlp-policy-templates)а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-179">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="7e1b6-180">В нашем примере мы выбрали шаблон персональных данных, идентифицируемый в США.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-180">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7e1b6-181">![Шаблон конфиденциальности для политики DLP](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="7e1b6-181">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="7e1b6-182">На **вкладке Имя политики** укажите имя и описание политики, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-182">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="7e1b6-183">На **вкладке Выбор расположения** сохраняйте параметр по умолчанию для всех учетных записей или выберите **Позвольте мне выбрать определенные расположения.**</span><span class="sxs-lookup"><span data-stu-id="7e1b6-183">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="7e1b6-184">Можно указать:</span><span class="sxs-lookup"><span data-stu-id="7e1b6-184">You can specify:</span></span>

    1. <span data-ttu-id="7e1b6-185">до 1000 отдельных учетных записей, которые необходимо включить или исключить</span><span class="sxs-lookup"><span data-stu-id="7e1b6-185">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="7e1b6-186">списки рассылки и группы безопасности, которые необходимо включить или исключить.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-186">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="7e1b6-187">**Это функция предварительного просмотра.**</span><span class="sxs-lookup"><span data-stu-id="7e1b6-187">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![Расположения политик DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="7e1b6-189">Если вы хотите убедиться, что документы, содержащие конфиденциальную информацию,  не будут Teams в Teams, убедитесь, что SharePoint сайты и **OneDrive** учетные записи включены, а также Teams чата и сообщений каналов **.**</span><span class="sxs-lookup"><span data-stu-id="7e1b6-189">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="7e1b6-190">На **вкладке** Параметры политики в статье **Настройка** типа контента, который необходимо защитить, сохраняем простые параметры по умолчанию или выберите **Использование** расширенных параметров, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-190">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="7e1b6-191">Если вы выбираете расширенные параметры, вы можете создать или изменить правила для вашей политики.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-191">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="7e1b6-192">(Чтобы получить помощь в этом, [см. в примере Simple settings vs. advanced settings.)](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)</span><span class="sxs-lookup"><span data-stu-id="7e1b6-192">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="7e1b6-193">На **вкладке Параметры** политики в статье Что нужно сделать, если мы обнаруживаем конфиденциальную **информацию?,** просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-193">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="7e1b6-194">(Здесь можно сохранить советы по политике по умолчанию и уведомления электронной почты [или](use-notifications-and-policy-tips.md)настроить их.)</span><span class="sxs-lookup"><span data-stu-id="7e1b6-194">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7e1b6-195">![Параметры политики DLP с подсказками и уведомлениями](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="7e1b6-195">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="7e1b6-196">По завершению проверки или редактирования параметров выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-196">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="7e1b6-197">На  вкладке Параметры политики в статье Вы хотите сначала включить политику или протестировать **ее?** Выберите, включить ли [политику,](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)сначала протестировать ее или отключить, а затем выбрать **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-197">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7e1b6-198">![Укажите, следует ли включить политику](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="7e1b6-198">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="7e1b6-199">На **вкладке Обзор параметров** просмотрите параметры новой политики.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-199">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="7e1b6-200">Выберите **Изменить,** чтобы внести изменения.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-200">Choose **Edit** to make changes.</span></span> <span data-ttu-id="7e1b6-201">По завершению выберите **Create**.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-201">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="7e1b6-202">Разрешить примерно один час для новой политики, чтобы работать свой путь через центр обработки данных и синхронизировать с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="7e1b6-202">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="7e1b6-203">Запрет внешнего доступа к конфиденциальным документам</span><span class="sxs-lookup"><span data-stu-id="7e1b6-203">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="7e1b6-204">Чтобы убедиться SharePoint документы, содержащие конфиденциальные сведения, не могут быть доступны внешним гостям из SharePoint или Teams по умолчанию, выберите следующее:</span><span class="sxs-lookup"><span data-stu-id="7e1b6-204">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="7e1b6-205">Вы можете гарантировать, что документы будут защищены до тех пор, пока DLP не сканирует и не пометит их как безопасные для обмена, пометив новые файлы как конфиденциальные [по умолчанию.](/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="7e1b6-205">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="7e1b6-206">Рекомендуемая структура политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="7e1b6-206">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="7e1b6-207">**Conditions**</span><span class="sxs-lookup"><span data-stu-id="7e1b6-207">**Conditions**</span></span>
        - <span data-ttu-id="7e1b6-208">Содержимое содержит любой из этих типов конфиденциальной информации: [Выберите все, что применяется]</span><span class="sxs-lookup"><span data-stu-id="7e1b6-208">Content contains any of these sensitive information types: [Select all that applies]</span></span>
        
        - <span data-ttu-id="7e1b6-209">Содержимое совместно Microsoft 365 с людьми за пределами моей организации</span><span class="sxs-lookup"><span data-stu-id="7e1b6-209">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="7e1b6-210">![Условия DLP для обнаружения внешнего обмена конфиденциальным контентом](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="7e1b6-210">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="7e1b6-211">**Actions**</span><span class="sxs-lookup"><span data-stu-id="7e1b6-211">**Actions**</span></span>
        - <span data-ttu-id="7e1b6-212">Ограничение доступа к содержимому для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="7e1b6-212">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="7e1b6-213">Уведомлять пользователей с помощью сообщения электронной почты и подсказок политики</span><span class="sxs-lookup"><span data-stu-id="7e1b6-213">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="7e1b6-214">Отправлять отчеты об инцидентах администратору</span><span class="sxs-lookup"><span data-stu-id="7e1b6-214">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="7e1b6-215">![Действие DLP для блокировки внешнего обмена конфиденциальным контентом](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="7e1b6-215">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="7e1b6-216">Политика DLP в действии при попытке поделиться документом в SharePoint, который содержит конфиденциальную информацию с внешним гостем:</span><span class="sxs-lookup"><span data-stu-id="7e1b6-216">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7e1b6-217">![Заблокирован внешний общий доступ](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="7e1b6-217">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="7e1b6-218">Политика DLP в действии, когда гость пытается открыть документ в Teams с блокировкой внешних:</span><span class="sxs-lookup"><span data-stu-id="7e1b6-218">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7e1b6-219">![Внешний доступ заблокирован](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="7e1b6-219">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="7e1b6-220">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="7e1b6-220">Related articles</span></span>

[<span data-ttu-id="7e1b6-221">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="7e1b6-221">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="7e1b6-222">Отправка почтовых уведомлений и отображение подсказок для политик защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="7e1b6-222">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
