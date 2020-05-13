---
title: Настроить фильтрацию исходящего спама
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как просматривать, создавать, изменять и удалять политики исходящей нежелательной почты в Exchange Online Protection (EOP).
ms.openlocfilehash: 9970956c2d05a47032cd47b867b8b4e9e92abc29
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209575"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="733e4-103">Настройка фильтрации исходящих нежелательных сообщений в EOP</span><span class="sxs-lookup"><span data-stu-id="733e4-103">Configure outbound spam filtering in EOP</span></span>

<span data-ttu-id="733e4-104">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или Exchange Online Protection (EOP) без почтовых ящиков Exchange Online сообщения исходящей электронной почты, отправляемые через EOP, автоматически проверяются на наличие нежелательной почты и нестандартных действий</span><span class="sxs-lookup"><span data-stu-id="733e4-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="733e4-105">Исходящая Нежелательная почта от пользователя в организации обычно указывает на скомпрометированную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="733e4-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="733e4-106">Подозрительные исходящие сообщения помечаются как спам (независимо от вероятности нежелательной почты или ВЕРОЯТНОсти нежелательной почты) и направляются через [пул доставки с высоким уровнем риска](high-risk-delivery-pool-for-outbound-messages.md) , чтобы обеспечить защиту репутации службы (то есть, храните исходные почтовые серверы Microsoft 365 из списков заблокированных IP-адресов).</span><span class="sxs-lookup"><span data-stu-id="733e4-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="733e4-107">Администраторы автоматически получают уведомление о подозрительных действиях с исходящей электронной почтой и заблокированных пользователях с помощью [политик оповещений](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="733e4-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="733e4-108">EOP использует политики исходящей нежелательной почты в рамках общей защиты Организации от спама.</span><span class="sxs-lookup"><span data-stu-id="733e4-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="733e4-109">Дополнительные сведения см. в статье [Защита от нежелательной почты](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="733e4-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="733e4-110">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику исходящей нежелательной почты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="733e4-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="733e4-111">Для большей детализации можно также создать настраиваемые политики исходящей почты, которые применяются к определенным пользователям, группам или доменам в Организации.</span><span class="sxs-lookup"><span data-stu-id="733e4-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="733e4-112">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="733e4-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="733e4-113">Политики исходящей нежелательной почты можно настроить в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для Microsoft 365 организации с почтовыми ящиками в Exchange Online; изолированная оболочка EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="733e4-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a><span data-ttu-id="733e4-114">Политики исходящей нежелательной почты в центре безопасности & соответствия требованиям VS Exchange Online PowerShell или Exchange Online Protection PowerShell</span><span class="sxs-lookup"><span data-stu-id="733e4-114">Outbound spam policies in the Security & Compliance Center vs Exchange Online PowerShell or Exchange Online Protection PowerShell</span></span>

<span data-ttu-id="733e4-115">Основными элементами политики исходящей нежелательной почты в EOP являются:</span><span class="sxs-lookup"><span data-stu-id="733e4-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="733e4-116">**Политика фильтрации исходящей нежелательной почты**определяет действия для фильтрации исходящих нежелательной почты вердиктс и параметры уведомлений.</span><span class="sxs-lookup"><span data-stu-id="733e4-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="733e4-117">**Правило фильтрации нежелательной почты**определяет приоритет и фильтры получателей (к которым применяется политика) для политики фильтрации исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="733e4-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="733e4-118">Различия между этими двумя элементами не очевидны при управлении политиками исходящей нежелательной почты в центре безопасности & соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="733e4-118">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="733e4-119">При создании политики нежелательной почты в центре безопасности & соответствия требованиям вы фактически создаете правило фильтрации нежелательной почты и связанную политику фильтрации нежелательной почты одновременно с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="733e4-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="733e4-120">При изменении политики исходящей нежелательной почты в центре безопасности & соответствия требованиям параметры, связанные с фильтрами имен, приоритетов, включенных или отключенных и получателей, изменяют правило фильтрации исходящих сообщений о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="733e4-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="733e4-121">Все остальные параметры изменяют соответствующую политику фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="733e4-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="733e4-122">При удалении политики исходящей нежелательной почты из центра безопасности & соответствия требованиям правило фильтрации исходящей почты и связанная политика фильтрации нежелательной почты удаляются.</span><span class="sxs-lookup"><span data-stu-id="733e4-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="733e4-123">В Exchange Online PowerShell или отдельном Exchange Online Protection PowerShell различия между политиками фильтрации исходящей нежелательной почты и фильтром исходящей нежелательной почты очевидны.</span><span class="sxs-lookup"><span data-stu-id="733e4-123">In Exchange Online PowerShell or standalone Exchange Online Protection PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="733e4-124">Управление политиками фильтрации нежелательной почты осуществляется с помощью командлетов \*\* \* – хостедаутбаундспамфилтерполици\*\* и управление правилами фильтрации нежелательной почты с помощью командлетов \*\* \* – хостедаутбаундспамфилтерруле\*\* .</span><span class="sxs-lookup"><span data-stu-id="733e4-124">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="733e4-125">В PowerShell сначала создается политика фильтрации исходящей нежелательной почты, а затем создается правило фильтрации исходящих сообщений, определяющее политику, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="733e4-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="733e4-126">В PowerShell параметры политики фильтрации исходящей нежелательной почты и фильтрации исходящих сообщений можно изменить отдельно.</span><span class="sxs-lookup"><span data-stu-id="733e4-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="733e4-127">При удалении политики фильтрации исходящей нежелательной почты из PowerShell соответствующее правило фильтрации нежелательной почты не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="733e4-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="733e4-128">Политика исходящих сообщений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="733e4-128">Default outbound spam policy</span></span>

<span data-ttu-id="733e4-129">Каждая организация имеет встроенную политику исходящей почты с именем Default, которая имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="733e4-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="733e4-130">Политика фильтрации исходящих сообщений по умолчанию применяется ко всем получателям в Организации, несмотря на то, что правило фильтрации исходящих сообщений (фильтры получателей) связано с политикой.</span><span class="sxs-lookup"><span data-stu-id="733e4-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="733e4-131">Для политики с именем "По умолчанию" задано специальное значение приоритета **Самый низкий**, которое невозможно изменить (эта политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="733e4-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="733e4-132">Все созданные специальные политики всегда имеют более высокий приоритет, чем политика с именем "По умолчанию".</span><span class="sxs-lookup"><span data-stu-id="733e4-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="733e4-133">Политика с именем "По умолчанию" является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.</span><span class="sxs-lookup"><span data-stu-id="733e4-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="733e4-134">Чтобы повысить эффективность фильтрации исходящей нежелательной почты, можно создать настраиваемые политики нежелательной почты с более жесткими параметрами, которые применяются к определенным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="733e4-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="733e4-135">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="733e4-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="733e4-136">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="733e4-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="733e4-137">Чтобы сразу перейти к странице **Параметры защиты от нежелательной почты**, используйте ссылку <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="733e4-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="733e4-138">Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="733e4-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="733e4-139">Сведения о подключении к автономной службе Exchange Online Protection PowerShell см. в статье [Подключение к PowerShell для Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="733e4-139">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="733e4-140">Для выполнения этих процедур необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="733e4-140">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="733e4-141">Для добавления, изменения и удаления политик исходящей нежелательной почты необходимо быть членом группы ролей " **Управление организацией** " или " **администратор безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="733e4-141">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="733e4-142">Для доступа только для чтения к политикам исходящей нежелательной почты необходимо быть участником группы ролей " **читатель безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="733e4-142">For read-only access to outbound spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="733e4-143">Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="733e4-143">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="733e4-144">Наши Рекомендуемые параметры политик нежелательной почты приведены в разделе [Параметры политики фильтрации исходящих сообщений EOP](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="733e4-144">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="733e4-145">[Политики оповещений](../../compliance/alert-policies.md) по умолчанию с именем " **лимит отправки электронной почты" превышены**, **обнаружены подозрительные шаблоны отправки электронной почты**, а пользователь, использующий **отправку сообщений** электронной почты, уже отправит уведомления участникам группы **тенантадминс** (**Глобальные администраторы**) о необычных действиях с исходящей электронной почтой и заблокированных пользователях</span><span class="sxs-lookup"><span data-stu-id="733e4-145">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="733e4-146">Дополнительные сведения см. [в статье Проверка параметров оповещений для пользователей с ограниченным доступом](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="733e4-146">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="733e4-147">Рекомендуется использовать эти политики оповещений вместо параметров уведомлений в политиках исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="733e4-147">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="733e4-148">Использование центра безопасности & соответствия требованиям для создания политик исходящей нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="733e4-148">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="733e4-149">Создание настраиваемой политики нежелательной почты в центре безопасности & соответствия требованиям создает правило фильтрации нежелательной почты и связанную политику фильтрации нежелательной почты одновременно с одним и тем же именем.</span><span class="sxs-lookup"><span data-stu-id="733e4-149">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="733e4-150">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="733e4-150">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="733e4-151">На странице **Параметры защиты от нежелательной почты** нажмите кнопку **создать политику исходящей**почты.</span><span class="sxs-lookup"><span data-stu-id="733e4-151">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="733e4-152">В открывшемся диалоговом окне **Политика фильтрации нежелательной почты** настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="733e4-152">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="733e4-153">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="733e4-153">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="733e4-154">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="733e4-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="733e4-155">Необязательно Разверните раздел **уведомления** , чтобы настроить дополнительных пользователей, которые должны получать копии и уведомления о подозрительных исходящих сообщениях электронной почты:</span><span class="sxs-lookup"><span data-stu-id="733e4-155">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="733e4-156">**Отправлять копии подозрительных исходящих сообщений электронной почты определенным людям**: этот параметр добавляет указанных пользователей в качестве получателей скрытой копии в подозрительные исходящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="733e4-156">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span> <span data-ttu-id="733e4-157">Чтобы включить этот параметр, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="733e4-157">To enable this setting:</span></span>

     <span data-ttu-id="733e4-158">а.</span><span class="sxs-lookup"><span data-stu-id="733e4-158">a.</span></span> <span data-ttu-id="733e4-159">Установите этот флажок, чтобы включить параметр.</span><span class="sxs-lookup"><span data-stu-id="733e4-159">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="733e4-160">б.</span><span class="sxs-lookup"><span data-stu-id="733e4-160">b.</span></span> <span data-ttu-id="733e4-161">Нажмите кнопку **Добавить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="733e4-161">Click **Add people**.</span></span> <span data-ttu-id="733e4-162">В появившемся всплывающем окне **Добавление или удаление получателей** :</span><span class="sxs-lookup"><span data-stu-id="733e4-162">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="733e4-163">в.</span><span class="sxs-lookup"><span data-stu-id="733e4-163">c.</span></span> <span data-ttu-id="733e4-164">Введите электронный адрес отправителя.</span><span class="sxs-lookup"><span data-stu-id="733e4-164">Enter the sender's email address.</span></span> <span data-ttu-id="733e4-165">Можно указать несколько адресов электронной почты, разделенных точкой с запятой (;) или по одному получателю в строке.</span><span class="sxs-lookup"><span data-stu-id="733e4-165">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="733e4-166">г.</span><span class="sxs-lookup"><span data-stu-id="733e4-166">d.</span></span> <span data-ttu-id="733e4-167">Щелкните</span><span class="sxs-lookup"><span data-stu-id="733e4-167">Click</span></span> ![Значок добавления](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="733e4-169">для добавления получателей.</span><span class="sxs-lookup"><span data-stu-id="733e4-169">to add the recipients.</span></span>

        <span data-ttu-id="733e4-170">Повторите эти действия необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="733e4-170">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="733e4-171">Добавленные получатели отображаются в разделе **список получателей** в всплывающем меню.</span><span class="sxs-lookup"><span data-stu-id="733e4-171">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="733e4-172">Чтобы удалить получателя, нажмите кнопку ![ удалить кнопку ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="733e4-172">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="733e4-173">д.</span><span class="sxs-lookup"><span data-stu-id="733e4-173">e.</span></span> <span data-ttu-id="733e4-174">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="733e4-174">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="733e4-175">Чтобы отключить этот параметр, снимите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="733e4-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="733e4-176">**Уведомлять определенных людей, если отправитель блокируется из-за отправки нежелательной почты**.</span><span class="sxs-lookup"><span data-stu-id="733e4-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="733e4-177">[Политика оповещений](../../compliance/alert-policies.md) по умолчанию с именем "пользователь", которая **ограничена отправкой электронной почты** , уже отправляет уведомления по электронной почте членам группы **тенантадминс** (**Глобальные администраторы**), когда пользователи блокируются из-за превышения ограничений в разделе **ограничения получателей** .</span><span class="sxs-lookup"><span data-stu-id="733e4-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="733e4-178">Мы рекомендуем использовать политику оповещений, а не этот параметр в политике исходящей нежелательной почты для уведомления администраторов и других пользователей.</span><span class="sxs-lookup"><span data-stu-id="733e4-178">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="733e4-179">Инструкции приведены в разделе [Проверка параметров оповещений для пользователей с ограниченным доступом](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="733e4-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

     <span data-ttu-id="733e4-180">Чтобы включить этот параметр, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="733e4-180">To enable this setting:</span></span>

     <span data-ttu-id="733e4-181">а.</span><span class="sxs-lookup"><span data-stu-id="733e4-181">a.</span></span> <span data-ttu-id="733e4-182">Установите этот флажок, чтобы включить параметр.</span><span class="sxs-lookup"><span data-stu-id="733e4-182">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="733e4-183">б.</span><span class="sxs-lookup"><span data-stu-id="733e4-183">b.</span></span> <span data-ttu-id="733e4-184">Нажмите кнопку **Добавить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="733e4-184">Click **Add people**.</span></span> <span data-ttu-id="733e4-185">В появившемся всплывающем окне **Добавление или удаление получателей** :</span><span class="sxs-lookup"><span data-stu-id="733e4-185">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="733e4-186">в.</span><span class="sxs-lookup"><span data-stu-id="733e4-186">c.</span></span> <span data-ttu-id="733e4-187">Введите электронный адрес отправителя.</span><span class="sxs-lookup"><span data-stu-id="733e4-187">Enter the sender's email address.</span></span> <span data-ttu-id="733e4-188">Можно указать несколько адресов электронной почты, разделенных точкой с запятой (;) или по одному получателю в строке.</span><span class="sxs-lookup"><span data-stu-id="733e4-188">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="733e4-189">г.</span><span class="sxs-lookup"><span data-stu-id="733e4-189">d.</span></span> <span data-ttu-id="733e4-190">Щелкните</span><span class="sxs-lookup"><span data-stu-id="733e4-190">Click</span></span> ![Значок добавления](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="733e4-192">для добавления получателей.</span><span class="sxs-lookup"><span data-stu-id="733e4-192">to add the recipients.</span></span>

        <span data-ttu-id="733e4-193">Повторите эти действия необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="733e4-193">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="733e4-194">Добавленные получатели отображаются в разделе **список получателей** в всплывающем меню.</span><span class="sxs-lookup"><span data-stu-id="733e4-194">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="733e4-195">Чтобы удалить получателя, нажмите кнопку ![ удалить кнопку ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="733e4-195">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="733e4-196">д.</span><span class="sxs-lookup"><span data-stu-id="733e4-196">e.</span></span> <span data-ttu-id="733e4-197">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="733e4-197">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="733e4-198">Чтобы отключить этот параметр, снимите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="733e4-198">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="733e4-199">Необязательно Разверните раздел **ограничения получателей** , чтобы настроить ограничения и действия для подозрительных исходящих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="733e4-199">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="733e4-200">Эти параметры применяются только к облачным почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="733e4-200">These settings are only applicable to cloud-based mailboxes.</span></span>
     
   - <span data-ttu-id="733e4-201">**Максимальное количество получателей на одного пользователя**</span><span class="sxs-lookup"><span data-stu-id="733e4-201">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="733e4-202">Допустимые значения: от 0 до 10000.</span><span class="sxs-lookup"><span data-stu-id="733e4-202">A valid value is 0 to 10000.</span></span> <span data-ttu-id="733e4-203">Значение по умолчанию — 0, что означает, что используются значения по умолчанию для службы.</span><span class="sxs-lookup"><span data-stu-id="733e4-203">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="733e4-204">Для получения дополнительных сведений [365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)см.</span><span class="sxs-lookup"><span data-stu-id="733e4-204">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

     - <span data-ttu-id="733e4-205">**Внешнее почасовое ограничение**: максимальное число внешних получателей в час.</span><span class="sxs-lookup"><span data-stu-id="733e4-205">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="733e4-206">**Внутреннее почасовое ограничение**: максимальное число внутренних получателей в час.</span><span class="sxs-lookup"><span data-stu-id="733e4-206">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="733e4-207">**Ежедневное ограничение**: максимальное общее количество получателей в день.</span><span class="sxs-lookup"><span data-stu-id="733e4-207">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="733e4-208">**Действие, когда пользователь превышает указанные выше пределы**: Настройте действие, которое будет выполняться при превышении одного из **пределов получателей** .</span><span class="sxs-lookup"><span data-stu-id="733e4-208">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="733e4-209">Для всех действий получатели, указанные в **учетной записи пользователя, имеют ограниченную отправку политики оповещений по электронной почте** (и в разделе теперь избыточность **уведомлять определенных людей, если отправитель заблокирован из-за отправки параметра нежелательной почты** в политике нежелательной почты получать уведомления по электронной почте</span><span class="sxs-lookup"><span data-stu-id="733e4-209">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="733e4-210">**Запретить пользователю отправлять почту до следующего дня**: это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="733e4-210">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="733e4-211">Уведомления по электронной почте отправляются, и пользователь не сможет отправлять больше сообщений до следующего дня, исходя из времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="733e4-211">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="733e4-212">Администратор не может переопределить этот блок.</span><span class="sxs-lookup"><span data-stu-id="733e4-212">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="733e4-213">Оповещение об активности с именем **User Restricted from Send e-mail** уведомляет администраторов (через электронную почту и на странице " **Просмотр оповещений** ").</span><span class="sxs-lookup"><span data-stu-id="733e4-213">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="733e4-214">Все получатели, указанные в поле **уведомлять определенных людей, если отправитель заблокирован из-за отправки настройки исходящей нежелательной почты** в политике, также получают уведомления.</span><span class="sxs-lookup"><span data-stu-id="733e4-214">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="733e4-215">Пользователь не сможет отправлять больше сообщений до следующего дня, основываясь на времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="733e4-215">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="733e4-216">Администратор не может переопределить этот блок.</span><span class="sxs-lookup"><span data-stu-id="733e4-216">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="733e4-217">**Запретить пользователю отправлять почту**: отправляются уведомления по электронной почте, пользователь добавляется на портал \*\*[пользователи с ограниченными правами] <https://sip.protection.office.com/restrictedusers> \*\* в центре безопасности & соответствия требованиям, и пользователь не может отправлять электронную почту до тех пор, пока администратор не удалит их из портала **ограниченных пользователей** . После того как администратор удалит пользователя из списка, он не будет снова ограничен в течение этого дня.</span><span class="sxs-lookup"><span data-stu-id="733e4-217">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="733e4-218">Инструкции приведены в статье [Удаление пользователя с портала ограниченных пользователей после отправки нежелательной почты](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="733e4-218">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="733e4-219">**Без действия, только оповещение**: отправляются уведомления по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="733e4-219">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="733e4-220">Потребоваться Разверните раздел **применено** , чтобы определить внутренних отправителей, к которым применяется политика.</span><span class="sxs-lookup"><span data-stu-id="733e4-220">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="733e4-221">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="733e4-221">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="733e4-222">Несколько значений одного условия или использования или логики исключения (например, _ \< sender1 \> _ или _ \< sender2 \> _).</span><span class="sxs-lookup"><span data-stu-id="733e4-222">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="733e4-223">Разные условия или исключения используют и логику (например, _ \< sender1 \> _ и _ \< Member of Group 1 \> _).</span><span class="sxs-lookup"><span data-stu-id="733e4-223">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="733e4-224">Проще всего нажать кнопку **Добавить условие** три раза, чтобы увидеть все доступные условия.</span><span class="sxs-lookup"><span data-stu-id="733e4-224">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="733e4-225">Чтобы удалить условия, которые не нужно настраивать, можно щелкнуть ![Кнопка удаления](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="733e4-225">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="733e4-226">**Домен отправителя**: указывает отправители из одного или нескольких настроенных обслуживаемых доменов в Организации.</span><span class="sxs-lookup"><span data-stu-id="733e4-226">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="733e4-227">Щелкните поле **Добавить тег**, чтобы просмотреть и выбрать домен.</span><span class="sxs-lookup"><span data-stu-id="733e4-227">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="733e4-228">Еще раз щелкните поле **Добавить тег**, чтобы выбрать дополнительные домены, если доступно несколько доменов.</span><span class="sxs-lookup"><span data-stu-id="733e4-228">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="733e4-229">**Отправитель**: указывает одного или нескольких пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="733e4-229">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="733e4-230">Щелкните в поле **Добавить тег** и начните вводить текст, чтобы отфильтровать список.</span><span class="sxs-lookup"><span data-stu-id="733e4-230">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="733e4-231">Еще раз щелкните поле **Добавить тег** , чтобы выбрать дополнительных отправители.</span><span class="sxs-lookup"><span data-stu-id="733e4-231">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="733e4-232">**Отправитель является участником**: указывает одну или несколько групп в Организации.</span><span class="sxs-lookup"><span data-stu-id="733e4-232">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="733e4-233">Щелкните в поле **Добавить тег** и начните вводить текст, чтобы отфильтровать список.</span><span class="sxs-lookup"><span data-stu-id="733e4-233">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="733e4-234">Еще раз щелкните поле **Добавить тег** , чтобы выбрать дополнительных отправители.</span><span class="sxs-lookup"><span data-stu-id="733e4-234">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="733e4-235">**За исключением случаев, когда**. Чтобы добавить исключение из правила, щелкните **Добавьте условие** три раза, чтобы увидеть все доступные исключения.</span><span class="sxs-lookup"><span data-stu-id="733e4-235">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="733e4-236">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="733e4-236">The settings and behavior are exactly like the conditions.</span></span>

7. <span data-ttu-id="733e4-237">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="733e4-237">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="733e4-238">Использование центра безопасности & соответствия требованиям для просмотра политик нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="733e4-238">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="733e4-239">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="733e4-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="733e4-240">На странице **Параметры защиты от нежелательной почты** нажмите ![ развернуть значок, ](../../media/scc-expand-icon.png) чтобы развернуть политику нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="733e4-240">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="733e4-241">Политика по умолчанию с именем **Исходящая политика фильтрации нежелательной почты**.</span><span class="sxs-lookup"><span data-stu-id="733e4-241">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="733e4-242">Создана настраиваемая политика, где значение в столбце **тип** является **настраиваемой политикой исходящих сообщений о нежелательной почте**.</span><span class="sxs-lookup"><span data-stu-id="733e4-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="733e4-243">Параметры политики отображаются в отображаемых сведениях расширенной политики или можно щелкнуть **изменить политику**.</span><span class="sxs-lookup"><span data-stu-id="733e4-243">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="733e4-244">Использование центра безопасности & соответствия требованиям для изменения политик исходящей нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="733e4-244">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="733e4-245">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="733e4-245">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="733e4-246">На странице **Параметры защиты от нежелательной почты** нажмите ![ развернуть значок, ](../../media/scc-expand-icon.png) чтобы развернуть политику нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="733e4-246">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="733e4-247">Политика по умолчанию с именем **Исходящая политика фильтрации нежелательной почты**.</span><span class="sxs-lookup"><span data-stu-id="733e4-247">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="733e4-248">Создана настраиваемая политика, где значение в столбце **тип** является **настраиваемой политикой исходящих сообщений о нежелательной почте**.</span><span class="sxs-lookup"><span data-stu-id="733e4-248">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="733e4-249">Щелкните **Изменение политики**.</span><span class="sxs-lookup"><span data-stu-id="733e4-249">Click **Edit policy**.</span></span>

<span data-ttu-id="733e4-250">Для настраиваемых политик нежелательной почты доступные параметры в всплывающем меню идентичны тем, которые описаны в разделе [использование & безопасности центра соответствия требованиям для создания раздела политики исходящих сообщений о нежелательной почте](#use-the-security--compliance-center-to-create-outbound-spam-policies) .</span><span class="sxs-lookup"><span data-stu-id="733e4-250">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="733e4-251">Для политики исходящих сообщений по умолчанию с именем " **Политика фильтрации нежелательной почты**" раздел **применено к** (политика применяется для всех), и вы не можете переименовать политику.</span><span class="sxs-lookup"><span data-stu-id="733e4-251">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="733e4-252">Сведения о включении или отключении политики, настройке приоритета политики или настройке уведомлений пользователей о карантине см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="733e4-252">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="733e4-253">Включение и отключение политик исходящей нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="733e4-253">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="733e4-254">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="733e4-254">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="733e4-255">На странице **Параметры защиты от нежелательной почты** нажмите ![ развернуть значок, ](../../media/scc-expand-icon.png) чтобы развернуть созданную настраиваемую политику (значение в столбце **тип** — **настраиваемая политика исходящей почты**).</span><span class="sxs-lookup"><span data-stu-id="733e4-255">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="733e4-256">В развернутых сведениях политики обратите внимание на значение в столбце **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="733e4-256">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="733e4-257">Чтобы отключить политику, переместите переключатель влево:</span><span class="sxs-lookup"><span data-stu-id="733e4-257">Move the toggle to the left to disable the policy:</span></span> ![Выключенный переключатель](../../media/scc-toggle-off.png)

   <span data-ttu-id="733e4-259">Чтобы включить политику, переместите переключатель вправо:</span><span class="sxs-lookup"><span data-stu-id="733e4-259">Move the toggle to the right to enable the policy:</span></span> ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="733e4-261">Отключить политику исходящей почты по умолчанию невозможно.</span><span class="sxs-lookup"><span data-stu-id="733e4-261">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="733e4-262">Установка приоритета настраиваемых политик нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="733e4-262">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="733e4-263">По умолчанию политикам исходящих сообщений по умолчанию назначен приоритет, основанный на порядке, в котором они были созданы (более новые политики имеют более высокий приоритет, чем старые политики).</span><span class="sxs-lookup"><span data-stu-id="733e4-263">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="733e4-264">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="733e4-264">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="733e4-265">Приоритеты двух политик не могут совпадать.</span><span class="sxs-lookup"><span data-stu-id="733e4-265">No two policies can have the same priority.</span></span>

<span data-ttu-id="733e4-266">Настраиваемые политики исходящей почты отображаются в порядке их обработки (первая политика имеет значение **приоритета** 0).</span><span class="sxs-lookup"><span data-stu-id="733e4-266">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="733e4-267">По умолчанию политика **фильтрации** нежелательной почты имеет значение Priority **наименьшее**, и вы не можете изменить его.</span><span class="sxs-lookup"><span data-stu-id="733e4-267">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="733e4-268">Чтобы изменить приоритет политики, переместите ее вверх или вниз в списке (в Центре безопасности и соответствия требованиям невозможно напрямую изменить значение свойства **Приоритет**).</span><span class="sxs-lookup"><span data-stu-id="733e4-268">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="733e4-269">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="733e4-269">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="733e4-270">На странице **Параметры защиты от нежелательной почты** найдите политики, в которых значение столбца **тип** является **настраиваемой политикой исходящих сообщений**о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="733e4-270">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="733e4-271">Обратите внимание на значения в столбце **Приоритет**:</span><span class="sxs-lookup"><span data-stu-id="733e4-271">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="733e4-272">Настраиваемая политика нежелательной почты с наивысшим приоритетом имеет ![ значок стрелки вниз ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="733e4-272">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="733e4-273">Настраиваемая политика нежелательной почты с наименьшим приоритетом имеет ![ значок стрелки вверх ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (например, ![ значок со стрелкой вверх ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="733e4-273">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="733e4-274">Если у вас есть три или более настраиваемых политик нежелательной почты, политики между самым высоким и самым низким приоритетом имеют значок стрелка ![ вверх со ](../../media/ITPro-EAC-UpArrowIcon.png)![ стрелкой вниз ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (например, значок ![ со стрелкой вверх ](../../media/ITPro-EAC-UpArrowIcon.png)![ вниз значок ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="733e4-274">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="733e4-275">Щелкните</span><span class="sxs-lookup"><span data-stu-id="733e4-275">Click</span></span> ![Значок "Стрелка вверх"](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="733e4-277">или</span><span class="sxs-lookup"><span data-stu-id="733e4-277">or</span></span> ![Значок "Стрелка вниз"](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="733e4-279">Перемещение настраиваемой политики нежелательной почты в списке приоритет.</span><span class="sxs-lookup"><span data-stu-id="733e4-279">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="733e4-280">Использование центра безопасности & соответствия требованиям для удаления политик нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="733e4-280">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="733e4-281">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="733e4-281">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="733e4-282">На странице **параметров защиты от нежелательной почты** нажмите ![ развернуть значок, ](../../media/scc-expand-icon.png) чтобы развернуть пользовательскую политику, которую нужно удалить (в столбце **тип** — **настраиваемая политика нежелательной почты**).</span><span class="sxs-lookup"><span data-stu-id="733e4-282">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="733e4-283">В развернутых сведениях политики щелкните **Удалить политику**.</span><span class="sxs-lookup"><span data-stu-id="733e4-283">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="733e4-284">Нажмите **Да** в появившемся предупреждающем диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="733e4-284">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="733e4-285">Политику по умолчанию удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="733e4-285">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="733e4-286">Настройка политик нежелательной почты с помощью Exchange Online PowerShell или Exchange Online Protection PowerShell</span><span class="sxs-lookup"><span data-stu-id="733e4-286">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="733e4-287">Создание политик нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="733e4-287">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="733e4-288">Процесс создания политики нежелательной почты в PowerShell состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="733e4-288">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="733e4-289">Создайте политику фильтрации исходящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="733e4-289">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="733e4-290">Создайте правило фильтрации исходящих сообщений о нежелательной почте, которое указывает политику фильтрации исходящих сообщений, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="733e4-290">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="733e4-291">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="733e4-291">**Notes**:</span></span>

- <span data-ttu-id="733e4-292">Вы можете создать новое правило фильтрации нежелательной почты и назначить для него существующую, не связанную с ней политику фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="733e4-292">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="733e4-293">Правило фильтрации исходящих сообщений не может быть связано с несколькими политиками фильтрации исходящей почты.</span><span class="sxs-lookup"><span data-stu-id="733e4-293">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="733e4-294">Вы можете настроить следующие параметры для новых политик фильтрации нежелательной почты в PowerShell, которые недоступны в центре безопасности & соответствия требованиям, пока не будет создана политика:</span><span class="sxs-lookup"><span data-stu-id="733e4-294">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="733e4-295">Создайте новую политику как отключенную (_включена_ `$false` в командлете **New-хостедаутбаундспамфилтерруле** ).</span><span class="sxs-lookup"><span data-stu-id="733e4-295">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="733e4-296">Задайте приоритет политики во время создания (_приоритет_ _ \< \> ) для_командлета **New-хостедаутбаундспамфилтерруле** .</span><span class="sxs-lookup"><span data-stu-id="733e4-296">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="733e4-297">Новая политика фильтрации исходящих сообщений, созданная в PowerShell, не отображается в центре безопасности &, пока политика не будет назначена правилу фильтрации спама.</span><span class="sxs-lookup"><span data-stu-id="733e4-297">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="733e4-298">Шаг 1: использование PowerShell для создания политики фильтрации исходящей нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="733e4-298">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="733e4-299">Чтобы создать политику фильтрации нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="733e4-299">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="733e4-300">В этом примере создается политика фильтрации исходящих сообщений с именем Contoso Executives со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="733e4-300">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="733e4-301">Ограничения скорости получателя ограничены меньшими значениями, используемыми по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="733e4-301">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="733e4-302">Для получения дополнительных сведений [365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)см.</span><span class="sxs-lookup"><span data-stu-id="733e4-302">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="733e4-303">По истечении одного из этих пределов пользователю запрещено отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="733e4-303">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="733e4-304">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – хостедаутбаундспамфилтерполици](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="733e4-304">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="733e4-305">Шаг 2: использование PowerShell для создания правила фильтрации исходящей нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="733e4-305">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="733e4-306">Чтобы создать правило фильтрации исходящих сообщений, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="733e4-306">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="733e4-307">В этом примере создается правило фильтрации исходящих сообщений с именем Contoso Executives с этими параметрами:</span><span class="sxs-lookup"><span data-stu-id="733e4-307">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="733e4-308">Политика фильтрации исходящей нежелательной почты с именем Contoso Executives связана с правилом.</span><span class="sxs-lookup"><span data-stu-id="733e4-308">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="733e4-309">Правило применяется к участникам группы Contoso Executives (Руководители Contoso).</span><span class="sxs-lookup"><span data-stu-id="733e4-309">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="733e4-310">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="733e4-310">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="733e4-311">Просмотр политик фильтрации исходящей нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="733e4-311">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="733e4-312">Чтобы получить сводный список всех политик фильтрации нежелательной почты, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="733e4-312">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="733e4-313">Чтобы получить подробные сведения о конкретной политике фильтрации нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="733e4-313">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="733e4-314">В этом примере возвращаются все значения свойств для политики фильтрации исходящей нежелательной почты с именем Executives.</span><span class="sxs-lookup"><span data-stu-id="733e4-314">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="733e4-315">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – хостедаутбаундспамфилтерполици](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="733e4-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="733e4-316">Просмотр правил фильтрации исходящей нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="733e4-316">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="733e4-317">Чтобы просмотреть существующие правила фильтрации нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="733e4-317">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="733e4-318">Чтобы получить сводный список всех правил фильтрации нежелательной почты, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="733e4-318">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="733e4-319">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="733e4-319">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="733e4-320">Чтобы получить подробные сведения об определенном правиле фильтрации нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="733e4-320">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="733e4-321">В этом примере возвращаются все значения свойств для правила фильтрации нежелательной почты Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="733e4-321">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="733e4-322">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="733e4-322">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="733e4-323">Использование PowerShell для изменения политик фильтрации исходящей нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="733e4-323">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="733e4-324">Те же параметры доступны при изменении политики фильтрации вредоносных программ в PowerShell так же, как и при создании политики, как описано в [шаге 1: с помощью PowerShell создайте в этой статье раздел Политика фильтрации исходящей нежелательной почты](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) .</span><span class="sxs-lookup"><span data-stu-id="733e4-324">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

<span data-ttu-id="733e4-325">**Note**: не удается переименовать политику фильтра нежелательной почты (командлет **Set-хостедаутбаундспамфилтерполици** не имеет параметра _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="733e4-325">**Note**: You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="733e4-326">При переименовании политики исходящей нежелательной почты в центре безопасности & соответствия требованиям Вы переименовываете только _правило_фильтрации исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="733e4-326">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="733e4-327">Чтобы изменить политику фильтрации нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="733e4-327">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="733e4-328">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – хостедаутбаундспамфилтерполици](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="733e4-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="733e4-329">Использование PowerShell для изменения правил фильтрации исходящей нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="733e4-329">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="733e4-330">Единственный параметр, недоступный при изменении правила фильтрации нежелательной почты в PowerShell, это параметр _Enabled_ , позволяющий создать отключенное правило.</span><span class="sxs-lookup"><span data-stu-id="733e4-330">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="733e4-331">Чтобы включить или отключить существующие правила фильтрации нежелательной почты, ознакомьтесь со статьей, приведенным в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="733e4-331">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="733e4-332">В противном случае дополнительные параметры не будут доступны при изменении правила фильтрации нежелательной почты в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="733e4-332">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="733e4-333">Те же параметры доступны при создании правила, как описано в [шаге 2: используйте PowerShell, чтобы создать раздел правил фильтрации нежелательной почты](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) , приведенный ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="733e4-333">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="733e4-334">Чтобы изменить правило фильтрации исходящих сообщений, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="733e4-334">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="733e4-335">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="733e4-335">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="733e4-336">Включение и отключение правил фильтрации исходящих сообщений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="733e4-336">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="733e4-337">Включение или отключение правила фильтрации исходящей нежелательной почты в PowerShell включает или отключает полную политику исходящей нежелательной почты (правило фильтрации нежелательной почты и назначенную политику фильтрации нежелательной почты).</span><span class="sxs-lookup"><span data-stu-id="733e4-337">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="733e4-338">Вы не можете включить или отключить политику исходящей почты по умолчанию (она всегда применяется ко всем получателям).</span><span class="sxs-lookup"><span data-stu-id="733e4-338">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="733e4-339">Чтобы включить или отключить правило фильтрации исходящих сообщений в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="733e4-339">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="733e4-340">В этом примере отключается правило фильтрации исходящих сообщений с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="733e4-340">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="733e4-341">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="733e4-341">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="733e4-342">Подробные сведения о синтаксисе и параметрах можно найти в статье [Enable – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) and [Disable – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="733e4-342">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="733e4-343">Установка приоритета правил фильтрации исходящих сообщений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="733e4-343">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="733e4-344">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="733e4-344">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="733e4-345">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="733e4-345">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="733e4-346">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="733e4-346">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="733e4-347">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="733e4-347">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="733e4-348">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="733e4-348">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="733e4-349">Чтобы задать приоритет правила фильтрации исходящей нежелательной почты в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="733e4-349">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="733e4-p146">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="733e4-p146">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="733e4-352">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="733e4-352">**Notes**:</span></span>

- <span data-ttu-id="733e4-353">Чтобы задать приоритет нового правила при его создании, используйте параметр _Priority_ в командлете **New – хостедаутбаундспамфилтерруле** .</span><span class="sxs-lookup"><span data-stu-id="733e4-353">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="733e4-354">Исходящая политика фильтрации нежелательной почты по умолчанию не имеет соответствующего правила фильтрации нежелательной почты и всегда имеет неизменяемое значение приоритета **.**</span><span class="sxs-lookup"><span data-stu-id="733e4-354">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="733e4-355">Удаление политик фильтрации нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="733e4-355">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="733e4-356">При использовании PowerShell для удаления политики фильтрации исходящей нежелательной почты соответствующее правило фильтрации нежелательной почты не удаляется.</span><span class="sxs-lookup"><span data-stu-id="733e4-356">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="733e4-357">Чтобы удалить политику фильтрации нежелательной почты в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="733e4-357">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="733e4-358">В этом примере удаляется политика фильтрации исходящей нежелательной почты с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="733e4-358">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="733e4-359">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – хостедаутбаундспамфилтерполици](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="733e4-359">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="733e4-360">Удаление правил фильтрации нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="733e4-360">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="733e4-361">При использовании PowerShell для удаления правила фильтрации нежелательной почты соответствующая политика фильтрации исходящих сообщений не удаляется.</span><span class="sxs-lookup"><span data-stu-id="733e4-361">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="733e4-362">Чтобы удалить правило фильтрации нежелательной почты в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="733e4-362">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="733e4-363">В этом примере удаляется правило фильтрации исходящих сообщений с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="733e4-363">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="733e4-364">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="733e4-364">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="733e4-365">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="733e4-365">For more information</span></span>

[<span data-ttu-id="733e4-366">Удаление заблокированных пользователей с портала "Пользователи с ограниченным доступом"</span><span class="sxs-lookup"><span data-stu-id="733e4-366">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="733e4-367">Пул доставки сообщений с высоким уровнем опасности</span><span class="sxs-lookup"><span data-stu-id="733e4-367">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="733e4-368">Вопросы и ответы по защите от нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="733e4-368">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
