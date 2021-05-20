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
description: Microsoft Teams чатов и каналов поддерживает политики предотвращения потери данных (DLP).
ms.openlocfilehash: e55bfa34b2495465f573bcede3ebda2308dbbbbc
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583392"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="e296b-103">Защита от потери данных и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e296b-103">Data loss prevention and Microsoft Teams</span></span>

<span data-ttu-id="e296b-104">Если в организации есть меры по предотвращению потери данных (DLP), можно определить политики, которые мешают людям делиться конфиденциальной информацией в Microsoft Teams канале или сеансе чата.</span><span class="sxs-lookup"><span data-stu-id="e296b-104">If your organization has data loss prevention (DLP), you can define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="e296b-105">Вот несколько примеров работы этой защиты.</span><span class="sxs-lookup"><span data-stu-id="e296b-105">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="e296b-106">**Пример 1. Защита конфиденциальной информации в сообщениях.**</span><span class="sxs-lookup"><span data-stu-id="e296b-106">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="e296b-107">Предположим, что кто-то пытается поделиться конфиденциальной информацией в Teams чате или канале с гостями (внешними пользователями).</span><span class="sxs-lookup"><span data-stu-id="e296b-107">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="e296b-108">Если для предотвращения этого установлена политика DLP, сообщения с конфиденциальной информацией, которые отправляются внешним пользователям, удаляются.</span><span class="sxs-lookup"><span data-stu-id="e296b-108">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="e296b-109">Это происходит автоматически и в течение нескольких секунд в соответствии с настройкой политики DLP.</span><span class="sxs-lookup"><span data-stu-id="e296b-109">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e296b-110">DLP для Microsoft Teams блокирует конфиденциальный контент при совместном Microsoft Teams пользователями, у которых есть:</span><span class="sxs-lookup"><span data-stu-id="e296b-110">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="e296b-111">- [гостевой доступ](/MicrosoftTeams/guest-access) в командах и каналах; или</span><span class="sxs-lookup"><span data-stu-id="e296b-111">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="e296b-112">- [внешний доступ](/MicrosoftTeams/manage-external-access) к собраниям и сеансам чата.</span><span class="sxs-lookup"><span data-stu-id="e296b-112">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="e296b-113">DLP для внешних сеансов чата будет работать только в том случае, если отправитель и приемник находятся в режиме Teams только и используют Microsoft Teams [федерацию](/microsoftteams/manage-external-access).</span><span class="sxs-lookup"><span data-stu-id="e296b-113">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="e296b-114">DLP для Teams не блокирует сообщения [](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) в ходе Skype для бизнеса сеансов чата с федеративами.</span><span class="sxs-lookup"><span data-stu-id="e296b-114">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="e296b-115">**Пример 2. Защита конфиденциальной информации в документах.**</span><span class="sxs-lookup"><span data-stu-id="e296b-115">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="e296b-116">Предположим, что кто-то пытается поделиться документом с гостями в Microsoft Teams канале или чате, а документ содержит конфиденциальные сведения.</span><span class="sxs-lookup"><span data-stu-id="e296b-116">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="e296b-117">Если для предотвращения этого установлена политика DLP, документ не будет открыт для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="e296b-117">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="e296b-118">Для применения защиты необходимо, чтобы политика защиты от потери данных включала SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="e296b-118">Your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="e296b-119">Это пример DLP для SharePoint, отображаемого в Microsoft Teams, и поэтому требует, чтобы пользователи лицензированы на Office 365 DLP (включены в Office 365 E3), но не требуют лицензии пользователей для Office 365 Advanced Compliance.)</span><span class="sxs-lookup"><span data-stu-id="e296b-119">This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="dlp-licensing-for-microsoft-teams"></a><span data-ttu-id="e296b-120">Лицензирование DLP для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e296b-120">DLP Licensing for Microsoft Teams</span></span>

<span data-ttu-id="e296b-121">[Возможности предотвращения потери](dlp-learn-about-dlp.md) данных были расширены, чтобы включить Microsoft Teams и сообщения каналов, в том числе сообщения частных **каналов** для:</span><span class="sxs-lookup"><span data-stu-id="e296b-121">[Data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages** for:</span></span>

- <span data-ttu-id="e296b-122">Office 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="e296b-122">Office 365 E5/A5</span></span>
- <span data-ttu-id="e296b-123">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="e296b-123">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="e296b-124">Защита информации и управление данными в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e296b-124">Microsoft 365 Information Protection and Governance</span></span>
- <span data-ttu-id="e296b-125">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="e296b-125">Office 365 Advanced Compliance</span></span>

<span data-ttu-id="e296b-126">Office 365 и Microsoft 365 E3 включают защиту DLP для SharePoint Online, OneDrive и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e296b-126">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="e296b-127">Это также включает файлы, которые Teams, поскольку Teams использует SharePoint Online и OneDrive для общего использования файлов.</span><span class="sxs-lookup"><span data-stu-id="e296b-127">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>

<span data-ttu-id="e296b-128">Поддержка защиты DLP в Teams чате требует E5.</span><span class="sxs-lookup"><span data-stu-id="e296b-128">Support for DLP protection in Teams Chat requires E5.</span></span>

<span data-ttu-id="e296b-129">Дополнительные сведения о требованиях к лицензированию см. в статье [Рекомендации по лицензированию служб на уровне клиента Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="e296b-129">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e296b-130">DLP применяется только к фактическим сообщениям в потоке чата или канала.</span><span class="sxs-lookup"><span data-stu-id="e296b-130">DLP applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="e296b-131">Уведомления об активности, которые включают краткий предварительный просмотр сообщений и  отображаются на основе параметров уведомлений пользователя, не включаются в Teams DLP.</span><span class="sxs-lookup"><span data-stu-id="e296b-131">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP.</span></span> <span data-ttu-id="e296b-132">Все конфиденциальные сведения, представленные в части сообщения, которое отображается в предварительном просмотре, будут видны в уведомлении даже после того, как политика DLP была применена и удалена конфиденциальную информацию самого сообщения.</span><span class="sxs-lookup"><span data-stu-id="e296b-132">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

## <a name="scope-of-dlp-protection"></a><span data-ttu-id="e296b-133">Область защиты DLP</span><span class="sxs-lookup"><span data-stu-id="e296b-133">Scope of DLP protection</span></span>

<span data-ttu-id="e296b-134">Защита DLP применяется по-разному к Teams сущностям.</span><span class="sxs-lookup"><span data-stu-id="e296b-134">DLP protection are applied differently to Teams entities.</span></span>

|<span data-ttu-id="e296b-135">Учетные записи пользователей/группы/список</span><span class="sxs-lookup"><span data-stu-id="e296b-135">User Accounts/Groups/List</span></span>  |<span data-ttu-id="e296b-136">Teams Entity</span><span class="sxs-lookup"><span data-stu-id="e296b-136">Teams Entity</span></span> |<span data-ttu-id="e296b-137">Доступная защита от DLP</span><span class="sxs-lookup"><span data-stu-id="e296b-137">DLP protection available</span></span>|
|---------|---------|---------|
|<span data-ttu-id="e296b-138">отдельные учетные записи пользователей</span><span class="sxs-lookup"><span data-stu-id="e296b-138">individual user accounts</span></span>     |<span data-ttu-id="e296b-139">1:1/n чаты</span><span class="sxs-lookup"><span data-stu-id="e296b-139">1:1/n chats</span></span>         |<span data-ttu-id="e296b-140">Да</span><span class="sxs-lookup"><span data-stu-id="e296b-140">yes</span></span>         |
|     |<span data-ttu-id="e296b-141">общие чаты</span><span class="sxs-lookup"><span data-stu-id="e296b-141">general chats</span></span>         |<span data-ttu-id="e296b-142">нет</span><span class="sxs-lookup"><span data-stu-id="e296b-142">no</span></span>         |
|     |<span data-ttu-id="e296b-143">общие каналы</span><span class="sxs-lookup"><span data-stu-id="e296b-143">shared channels</span></span>         |<span data-ttu-id="e296b-144">нет</span><span class="sxs-lookup"><span data-stu-id="e296b-144">no</span></span>         |
|     |<span data-ttu-id="e296b-145">частные каналы</span><span class="sxs-lookup"><span data-stu-id="e296b-145">private channels</span></span>         |<span data-ttu-id="e296b-146">Да</span><span class="sxs-lookup"><span data-stu-id="e296b-146">yes</span></span>         |
|<span data-ttu-id="e296b-147">группы безопасности и списки рассылки</span><span class="sxs-lookup"><span data-stu-id="e296b-147">security groups/distribution lists</span></span>  | <span data-ttu-id="e296b-148">1:1/n чаты</span><span class="sxs-lookup"><span data-stu-id="e296b-148">1:1/n chats</span></span>         |<span data-ttu-id="e296b-149">Да</span><span class="sxs-lookup"><span data-stu-id="e296b-149">yes</span></span>         |
|     |<span data-ttu-id="e296b-150">общие чаты</span><span class="sxs-lookup"><span data-stu-id="e296b-150">general chats</span></span>         |<span data-ttu-id="e296b-151">нет</span><span class="sxs-lookup"><span data-stu-id="e296b-151">no</span></span>         |
|     |<span data-ttu-id="e296b-152">общие каналы</span><span class="sxs-lookup"><span data-stu-id="e296b-152">shared channels</span></span>         |<span data-ttu-id="e296b-153">нет</span><span class="sxs-lookup"><span data-stu-id="e296b-153">no</span></span>      |
|     |<span data-ttu-id="e296b-154">частные каналы</span><span class="sxs-lookup"><span data-stu-id="e296b-154">private channels</span></span>         |<span data-ttu-id="e296b-155">Да</span><span class="sxs-lookup"><span data-stu-id="e296b-155">yes</span></span>        |
|<span data-ttu-id="e296b-156">Microsoft 365 группы</span><span class="sxs-lookup"><span data-stu-id="e296b-156">Microsoft 365 group</span></span>    |<span data-ttu-id="e296b-157">1:1/n чаты</span><span class="sxs-lookup"><span data-stu-id="e296b-157">1:1/n chats</span></span>          |<span data-ttu-id="e296b-158">нет</span><span class="sxs-lookup"><span data-stu-id="e296b-158">no</span></span>         |
|     |<span data-ttu-id="e296b-159">общие чаты</span><span class="sxs-lookup"><span data-stu-id="e296b-159">general chats</span></span>          |<span data-ttu-id="e296b-160">Да</span><span class="sxs-lookup"><span data-stu-id="e296b-160">yes</span></span>        |
|     |<span data-ttu-id="e296b-161">общие каналы</span><span class="sxs-lookup"><span data-stu-id="e296b-161">shared channels</span></span>|<span data-ttu-id="e296b-162">Да</span><span class="sxs-lookup"><span data-stu-id="e296b-162">yes</span></span> |
|     |<span data-ttu-id="e296b-163">частные каналы</span><span class="sxs-lookup"><span data-stu-id="e296b-163">private channels</span></span>|<span data-ttu-id="e296b-164">нет</span><span class="sxs-lookup"><span data-stu-id="e296b-164">no</span></span>| 


## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="e296b-165">Советы по политике помогают обучать пользователей</span><span class="sxs-lookup"><span data-stu-id="e296b-165">Policy tips help educate users</span></span>

<span data-ttu-id="e296b-166">Подобно тому, как DLP работает в [Exchange, Outlook, Outlook](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)в Интернете, [SharePoint Online, OneDrive для бизнеса](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)сайтах и [Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)клиенты настольных компьютеров, советы по политике отображаются при запуске действия с политикой DLP.</span><span class="sxs-lookup"><span data-stu-id="e296b-166">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action triggers with a DLP policy.</span></span> <span data-ttu-id="e296b-167">Вот пример подсказки политики:</span><span class="sxs-lookup"><span data-stu-id="e296b-167">Here's an example of a policy tip:</span></span>

![Заблокированное уведомление о сообщении в Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="e296b-169">Здесь отправитель попытался поделиться номером социального обеспечения в Microsoft Teams канале.</span><span class="sxs-lookup"><span data-stu-id="e296b-169">Here, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="e296b-170">Ссылка **Что я могу сделать?** открывает диалоговое окно, которое предоставляет варианты для отправитель для решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="e296b-170">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="e296b-171">Обратите внимание, что отправитель может переопределить политику или уведомить об этом администратора.</span><span class="sxs-lookup"><span data-stu-id="e296b-171">Notice that, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![Параметры для устранения заблокированного сообщения](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="e296b-173">В организации можно разрешить пользователям переопределять политику DLP.</span><span class="sxs-lookup"><span data-stu-id="e296b-173">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="e296b-174">При настройке политик DLP можно использовать советы по политике по умолчанию или настроить советы по политике [для](#to-customize-policy-tips) организации.</span><span class="sxs-lookup"><span data-stu-id="e296b-174">When you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="e296b-175">Возвращаясь к нашему примеру, когда отправитель поделился номером социального обеспечения в канале Teams, вот что увидел получатель:</span><span class="sxs-lookup"><span data-stu-id="e296b-175">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e296b-176">![Заблокировано сообщение](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="e296b-176">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="e296b-177">Настройка подсказок политики</span><span class="sxs-lookup"><span data-stu-id="e296b-177">To customize policy tips</span></span>

<span data-ttu-id="e296b-178">Для выполнения этой задачи вам должна быть назначена роль с разрешениями на редактирование политик защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="e296b-178">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="e296b-179">Дополнительные сведения см. в статье [Разрешения](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="e296b-179">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="e296b-180">Перейдите в Центр соответствия требованиям [https://compliance.microsoft.com](https://compliance.microsoft.com) () и войдите.</span><span class="sxs-lookup"><span data-stu-id="e296b-180">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="e296b-181">Выберите **Защита от потери данных** > **Политика**.</span><span class="sxs-lookup"><span data-stu-id="e296b-181">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="e296b-182">Выберите политику, а рядом с настройками **политики** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e296b-182">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="e296b-183">Создайте новое правило или отредактировать существующее правило для политики.</span><span class="sxs-lookup"><span data-stu-id="e296b-183">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e296b-184">![Изменение правила для политики](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="e296b-184">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="e296b-185">На **вкладке Уведомления пользователя** выберите **Настройка** текста электронной почты и/или настройка вариантов текста **подсказки** политики.</span><span class="sxs-lookup"><span data-stu-id="e296b-185">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e296b-186">![Настройка пользовательских уведомлений и советов по политике](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="e296b-186">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="e296b-187">Укажите текст, который необходимо использовать для уведомлений электронной почты и/или советов по политике, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e296b-187">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="e296b-188">На **вкладке Параметры политики** выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e296b-188">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="e296b-189">Разрешить примерно один час, чтобы изменения работали через центр обработки данных и синхронизируются с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="e296b-189">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="e296b-190">Добавление Microsoft Teams в качестве расположения к существующим политикам защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="e296b-190">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="e296b-191">Для выполнения этой задачи вам должна быть назначена роль с разрешениями на редактирование политик защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="e296b-191">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="e296b-192">Дополнительные сведения см. в статье [Разрешения](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="e296b-192">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="e296b-193">Перейдите в Центр соответствия требованиям [https://compliance.microsoft.com](https://compliance.microsoft.com) () и войдите.</span><span class="sxs-lookup"><span data-stu-id="e296b-193">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="e296b-194">Выберите **Защита от потери данных** > **Политика**.</span><span class="sxs-lookup"><span data-stu-id="e296b-194">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="e296b-195">Выберите политику и посмотрите на значения в **"Расположениях".**</span><span class="sxs-lookup"><span data-stu-id="e296b-195">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="e296b-196">Если вы видите **Teams и сообщения каналов,** вы все настроены.</span><span class="sxs-lookup"><span data-stu-id="e296b-196">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="e296b-197">Если этого не делать, нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e296b-197">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e296b-198">![Расположения для существующей политики](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="e296b-198">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="e296b-199">В **столбце Состояние** включаем политику для Teams **и сообщений каналов.**</span><span class="sxs-lookup"><span data-stu-id="e296b-199">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e296b-200">![DLP для Teams и каналов](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="e296b-200">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="e296b-201">На **вкладке Выбор расположения** сохраняйте параметр по умолчанию для всех учетных записей или выберите **Позвольте мне выбрать определенные расположения.**</span><span class="sxs-lookup"><span data-stu-id="e296b-201">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="e296b-202">Можно указать:</span><span class="sxs-lookup"><span data-stu-id="e296b-202">You can specify:</span></span>

    1. <span data-ttu-id="e296b-203">до 1000 отдельных учетных записей, которые необходимо включить или исключить</span><span class="sxs-lookup"><span data-stu-id="e296b-203">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="e296b-204">списки рассылки и группы безопасности, которые необходимо включить или исключить.</span><span class="sxs-lookup"><span data-stu-id="e296b-204">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="e296b-205">Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e296b-205">Then choose **Next**.</span></span>

7. <span data-ttu-id="e296b-206">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e296b-206">Click **Save**.</span></span>

<span data-ttu-id="e296b-207">Разрешить примерно один час, чтобы изменения работали через центр обработки данных и синхронизируются с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="e296b-207">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="e296b-208">Определение новой политики защиты от потери данных для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e296b-208">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="e296b-209">Для выполнения этой задачи вам должна быть назначена роль с разрешениями на редактирование политик защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="e296b-209">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="e296b-210">Дополнительные сведения см. в статье [Разрешения](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="e296b-210">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="e296b-211">Перейдите в Центр соответствия требованиям [https://compliance.microsoft.com](https://compliance.microsoft.com) () и войдите.</span><span class="sxs-lookup"><span data-stu-id="e296b-211">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="e296b-212">Выберите **Защита от потери данных** > **Политика** > **Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="e296b-212">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="e296b-213">Выберите [шаблон,](data-loss-prevention-policies.md#dlp-policy-templates)а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e296b-213">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="e296b-214">В нашем примере мы выбрали шаблон персональных данных, идентифицируемый в США.</span><span class="sxs-lookup"><span data-stu-id="e296b-214">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e296b-215">![Шаблон конфиденциальности для политики DLP](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="e296b-215">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="e296b-216">На **вкладке Имя политики** укажите имя и описание политики, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e296b-216">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="e296b-217">На **вкладке Выбор расположения** сохраняйте параметр по умолчанию для всех учетных записей или выберите **Позвольте мне выбрать определенные расположения.**</span><span class="sxs-lookup"><span data-stu-id="e296b-217">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="e296b-218">Можно указать:</span><span class="sxs-lookup"><span data-stu-id="e296b-218">You can specify:</span></span>

    1. <span data-ttu-id="e296b-219">до 1000 отдельных учетных записей, которые необходимо включить или исключить</span><span class="sxs-lookup"><span data-stu-id="e296b-219">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="e296b-220">списки рассылки и группы безопасности, которые необходимо включить или исключить.</span><span class="sxs-lookup"><span data-stu-id="e296b-220">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="e296b-221">**Это функция предварительного просмотра.**</span><span class="sxs-lookup"><span data-stu-id="e296b-221">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![Расположения политик DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="e296b-223">Если вы хотите убедиться, что документы, содержащие конфиденциальную информацию,  не будут Teams в Teams, убедитесь, что SharePoint сайты и **OneDrive** учетные записи включены, а также Teams чата и сообщений каналов **.**</span><span class="sxs-lookup"><span data-stu-id="e296b-223">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="e296b-224">На **вкладке** Параметры политики в статье **Настройка** типа контента, который необходимо защитить, сохраняем простые параметры по умолчанию или выберите **Использование** расширенных параметров, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e296b-224">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="e296b-225">Если вы выбираете расширенные параметры, вы можете создать или изменить правила для вашей политики.</span><span class="sxs-lookup"><span data-stu-id="e296b-225">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="e296b-226">Чтобы получить помощь в этом, [см. в примере Simple settings vs. advanced settings.](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)</span><span class="sxs-lookup"><span data-stu-id="e296b-226">To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).</span></span>

7.  <span data-ttu-id="e296b-227">На **вкладке Параметры** политики в статье Что нужно сделать, если мы обнаруживаем конфиденциальную **информацию?,** просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="e296b-227">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="e296b-228">Здесь можно сохранить советы по политике по умолчанию и [уведомления](use-notifications-and-policy-tips.md)электронной почты или настроить их.</span><span class="sxs-lookup"><span data-stu-id="e296b-228">Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e296b-229">![Параметры политики DLP с подсказками и уведомлениями](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="e296b-229">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="e296b-230">По завершению проверки или редактирования параметров выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e296b-230">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="e296b-231">На  вкладке Параметры политики в статье Вы хотите сначала включить политику или протестировать **ее?** Выберите, включить ли [политику,](dlp-overview-plan-for-dlp.md#policy-deployment)сначала протестировать ее или отключить, а затем выбрать **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e296b-231">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](dlp-overview-plan-for-dlp.md#policy-deployment), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e296b-232">![Укажите, следует ли включить политику](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="e296b-232">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="e296b-233">На **вкладке Обзор параметров** просмотрите параметры новой политики.</span><span class="sxs-lookup"><span data-stu-id="e296b-233">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="e296b-234">Выберите **Изменить,** чтобы внести изменения.</span><span class="sxs-lookup"><span data-stu-id="e296b-234">Choose **Edit** to make changes.</span></span> <span data-ttu-id="e296b-235">По завершению выберите **Create**.</span><span class="sxs-lookup"><span data-stu-id="e296b-235">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="e296b-236">Разрешить примерно один час для новой политики, чтобы работать свой путь через центр обработки данных и синхронизировать с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="e296b-236">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="e296b-237">Запрет внешнего доступа к конфиденциальным документам</span><span class="sxs-lookup"><span data-stu-id="e296b-237">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="e296b-238">Чтобы убедиться SharePoint документы, содержащие конфиденциальные сведения, не могут быть доступны внешним гостям из SharePoint или Teams по умолчанию, выберите следующее:</span><span class="sxs-lookup"><span data-stu-id="e296b-238">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="e296b-239">Вы можете гарантировать, что документы будут защищены до тех пор, пока DLP не сканирует и не пометит их как безопасные для обмена, пометив новые файлы как конфиденциальные [по умолчанию.](/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="e296b-239">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="e296b-240">Рекомендуемая структура политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="e296b-240">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="e296b-241">**Conditions**</span><span class="sxs-lookup"><span data-stu-id="e296b-241">**Conditions**</span></span>
        - <span data-ttu-id="e296b-242">Содержимое содержит любой из этих типов конфиденциальной информации: [Выберите все, что применяется]</span><span class="sxs-lookup"><span data-stu-id="e296b-242">Content contains any of these sensitive information types: [Select all that apply]</span></span>
        
        - <span data-ttu-id="e296b-243">Содержимое совместно Microsoft 365 с людьми за пределами моей организации</span><span class="sxs-lookup"><span data-stu-id="e296b-243">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="e296b-244">![Условия DLP для обнаружения внешнего обмена конфиденциальным контентом](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="e296b-244">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="e296b-245">**Actions**</span><span class="sxs-lookup"><span data-stu-id="e296b-245">**Actions**</span></span>
        - <span data-ttu-id="e296b-246">Ограничение доступа к содержимому для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="e296b-246">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="e296b-247">Уведомлять пользователей с помощью сообщения электронной почты и подсказок политики</span><span class="sxs-lookup"><span data-stu-id="e296b-247">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="e296b-248">Отправлять отчеты об инцидентах администратору</span><span class="sxs-lookup"><span data-stu-id="e296b-248">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="e296b-249">![Действие DLP для блокировки внешнего обмена конфиденциальным контентом](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="e296b-249">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="e296b-250">Политика DLP в действии при попытке поделиться документом в SharePoint, который содержит конфиденциальную информацию с внешним гостем:</span><span class="sxs-lookup"><span data-stu-id="e296b-250">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e296b-251">![Заблокирован внешний общий доступ](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="e296b-251">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="e296b-252">Политика DLP в действии, когда гость пытается открыть документ в Teams с блокировкой внешних:</span><span class="sxs-lookup"><span data-stu-id="e296b-252">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e296b-253">![Внешний доступ заблокирован](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="e296b-253">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="e296b-254">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="e296b-254">Related articles</span></span>

- [<span data-ttu-id="e296b-255">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="e296b-255">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="e296b-256">Отправка почтовых уведомлений и отображение подсказок для политик защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="e296b-256">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
