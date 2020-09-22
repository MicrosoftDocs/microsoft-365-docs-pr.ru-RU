---
title: Настроить фильтрацию исходящего спама
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
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
ms.openlocfilehash: 2c7a48280487944352f4ee8afc1e7f0596186a3d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203303"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="69ee5-103">Настройка фильтрации исходящих нежелательных сообщений в EOP</span><span class="sxs-lookup"><span data-stu-id="69ee5-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="69ee5-104">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или Exchange Online Protection (EOP) без почтовых ящиков Exchange Online сообщения исходящей электронной почты, отправляемые через EOP, автоматически проверяются на наличие нежелательной почты и нестандартных действий</span><span class="sxs-lookup"><span data-stu-id="69ee5-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="69ee5-105">Исходящая Нежелательная почта от пользователя в организации обычно указывает на скомпрометированную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="69ee5-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="69ee5-106">Подозрительные исходящие сообщения помечаются как спам (независимо от вероятности нежелательной почты или ВЕРОЯТНОсти нежелательной почты) и направляются через [пул доставки с высоким уровнем риска](high-risk-delivery-pool-for-outbound-messages.md) , чтобы обеспечить защиту репутации службы (то есть, храните исходные почтовые серверы Microsoft 365 из списков заблокированных IP-адресов).</span><span class="sxs-lookup"><span data-stu-id="69ee5-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="69ee5-107">Администраторы автоматически получают уведомление о подозрительных действиях с исходящей электронной почтой и заблокированных пользователях с помощью [политик оповещений](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="69ee5-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="69ee5-108">EOP использует политики исходящей нежелательной почты в рамках общей защиты Организации от спама.</span><span class="sxs-lookup"><span data-stu-id="69ee5-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="69ee5-109">Дополнительные сведения см. в статье [Защита от нежелательной почты](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="69ee5-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="69ee5-110">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику исходящей нежелательной почты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="69ee5-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="69ee5-111">Для большей детализации можно также создать настраиваемые политики исходящей почты, которые применяются к определенным пользователям, группам или доменам в Организации.</span><span class="sxs-lookup"><span data-stu-id="69ee5-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="69ee5-112">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="69ee5-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="69ee5-113">Политики исходящей нежелательной почты можно настроить в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для Microsoft 365 организации с почтовыми ящиками в Exchange Online; изолированная оболочка EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="69ee5-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="69ee5-114">Основными элементами политики исходящей нежелательной почты в EOP являются:</span><span class="sxs-lookup"><span data-stu-id="69ee5-114">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="69ee5-115">**Политика фильтрации исходящей нежелательной почты**определяет действия для фильтрации исходящих нежелательной почты вердиктс и параметры уведомлений.</span><span class="sxs-lookup"><span data-stu-id="69ee5-115">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="69ee5-116">**Правило фильтрации нежелательной почты**определяет приоритет и фильтры получателей (к которым применяется политика) для политики фильтрации исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="69ee5-116">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="69ee5-117">Различия между этими двумя элементами не очевидны при управлении политиками исходящей нежелательной почты в центре безопасности & соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="69ee5-117">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="69ee5-118">При создании политики вы фактически создаете правило фильтрации нежелательной почты и связанную политику фильтрации нежелательной почты одновременно с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="69ee5-118">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="69ee5-119">При изменении политики параметры, связанные с фильтрами имен, приоритетов, включенных или отключенных и получателей, изменяют правило фильтрации исходящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="69ee5-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="69ee5-120">Все остальные параметры изменяют соответствующую политику фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="69ee5-120">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="69ee5-121">При удалении политики удаляются правила фильтрации исходящей нежелательной почты и связанная политика фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="69ee5-121">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="69ee5-122">В Exchange Online PowerShell или автономном EOP PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="69ee5-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="69ee5-123">Для получения дополнительных сведений обратитесь к разделу [использование Exchange Online PowerShell или изолированной EOP PowerShell для настройки политик нежелательной почты](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) , описанных далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="69ee5-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this topic.</span></span>

<span data-ttu-id="69ee5-124">Каждая организация имеет встроенную политику исходящей почты с именем Default, которая имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="69ee5-124">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="69ee5-125">Политика применяется ко всем получателям в Организации, несмотря на то, что отсутствует правило фильтрации исходящих сообщений (фильтры получателей), связанное с политикой.</span><span class="sxs-lookup"><span data-stu-id="69ee5-125">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="69ee5-126">Для политики задано специальное значение приоритета **Самый низкий**, которое невозможно изменить (эта политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="69ee5-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="69ee5-127">Все созданные специальные политики всегда имеют более высокий приоритет, чем политика с именем "По умолчанию".</span><span class="sxs-lookup"><span data-stu-id="69ee5-127">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="69ee5-128">Эта политика является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.</span><span class="sxs-lookup"><span data-stu-id="69ee5-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="69ee5-129">Чтобы повысить эффективность фильтрации исходящей нежелательной почты, можно создать настраиваемые политики нежелательной почты с более жесткими параметрами, которые применяются к определенным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="69ee5-129">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="69ee5-130">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="69ee5-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="69ee5-131">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="69ee5-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="69ee5-132">Чтобы сразу перейти к странице **Параметры защиты от нежелательной почты**, используйте ссылку <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="69ee5-132">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="69ee5-133">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="69ee5-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="69ee5-134">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="69ee5-134">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="69ee5-135">Чтобы вы могли выполнить процедуры, упомянутые в этой теме, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="69ee5-135">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="69ee5-136">Для добавления, изменения и удаления политик исходящей нежелательной почты необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="69ee5-136">To add, modify, and delete outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="69ee5-137">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="69ee5-137">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="69ee5-138">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="69ee5-138">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="69ee5-139">Для доступа только для чтения к политикам исходящей нежелательной почты необходимо быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="69ee5-139">For read-only access to outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="69ee5-140">**Средство считывания сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="69ee5-140">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="69ee5-141">**Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="69ee5-141">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="69ee5-142">Наши Рекомендуемые параметры политик нежелательной почты приведены в разделе [Параметры политики фильтрации исходящих сообщений EOP](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="69ee5-142">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="69ee5-143">[Политики оповещений](../../compliance/alert-policies.md) по умолчанию с именем " **лимит отправки электронной почты" превышены**, **обнаружены подозрительные шаблоны отправки электронной почты**, а пользователь, использующий **отправку сообщений** электронной почты, уже отправит уведомления участникам группы **тенантадминс** (**Глобальные администраторы**) о необычных действиях с исходящей электронной почтой и заблокированных пользователях</span><span class="sxs-lookup"><span data-stu-id="69ee5-143">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="69ee5-144">Дополнительные сведения см. [в статье Проверка параметров оповещений для пользователей с ограниченным доступом](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="69ee5-144">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="69ee5-145">Рекомендуется использовать эти политики оповещений вместо параметров уведомлений в политиках исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="69ee5-145">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="69ee5-146">Использование центра безопасности & соответствия требованиям для создания политик исходящей нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="69ee5-146">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="69ee5-147">Создание настраиваемой политики нежелательной почты в центре безопасности & соответствия требованиям создает правило фильтрации нежелательной почты и связанную политику фильтрации нежелательной почты одновременно с одним и тем же именем.</span><span class="sxs-lookup"><span data-stu-id="69ee5-147">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="69ee5-148">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="69ee5-149">На странице **Параметры защиты от нежелательной почты** нажмите кнопку **создать политику исходящей**почты.</span><span class="sxs-lookup"><span data-stu-id="69ee5-149">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="69ee5-150">В открывшемся диалоговом окне **Политика фильтрации нежелательной почты** настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="69ee5-150">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="69ee5-151">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="69ee5-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="69ee5-152">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="69ee5-152">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="69ee5-153">Необязательно Разверните раздел **уведомления** , чтобы настроить дополнительных пользователей, которые должны получать копии и уведомления о подозрительных исходящих сообщениях электронной почты:</span><span class="sxs-lookup"><span data-stu-id="69ee5-153">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="69ee5-154">**Отправлять копии подозрительных исходящих сообщений электронной почты определенным людям**: этот параметр добавляет указанных пользователей в качестве получателей скрытой копии в подозрительные исходящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="69ee5-154">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="69ee5-155">Этот параметр работает только в политике исходящей нежелательной почты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="69ee5-155">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="69ee5-156">Она не работает в настраиваемых политиках исходящей почты.</span><span class="sxs-lookup"><span data-stu-id="69ee5-156">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="69ee5-157">Чтобы включить этот параметр, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="69ee5-157">To enable this setting:</span></span>

     1. <span data-ttu-id="69ee5-158">Установите этот флажок, чтобы включить параметр.</span><span class="sxs-lookup"><span data-stu-id="69ee5-158">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="69ee5-159">Нажмите кнопку **Добавить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-159">Click **Add people**.</span></span> <span data-ttu-id="69ee5-160">В появившемся всплывающем окне **Добавление или удаление получателей** :</span><span class="sxs-lookup"><span data-stu-id="69ee5-160">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="69ee5-161">Введите электронный адрес отправителя.</span><span class="sxs-lookup"><span data-stu-id="69ee5-161">Enter the sender's email address.</span></span> <span data-ttu-id="69ee5-162">Можно указать несколько адресов электронной почты, разделенных точкой с запятой (;) или по одному получателю в строке.</span><span class="sxs-lookup"><span data-stu-id="69ee5-162">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="69ee5-163">Щелкните</span><span class="sxs-lookup"><span data-stu-id="69ee5-163">Click</span></span> ![Значок добавления](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="69ee5-165">для добавления получателей.</span><span class="sxs-lookup"><span data-stu-id="69ee5-165">to add the recipients.</span></span>

        <span data-ttu-id="69ee5-166">Повторите эти действия необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="69ee5-166">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="69ee5-167">Добавленные получатели отображаются в разделе **список получателей** в всплывающем меню.</span><span class="sxs-lookup"><span data-stu-id="69ee5-167">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="69ee5-168">Чтобы удалить получателя, нажмите кнопку ![ удалить кнопку ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="69ee5-168">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="69ee5-169">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-169">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="69ee5-170">Чтобы отключить этот параметр, снимите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="69ee5-170">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="69ee5-171">**Уведомлять определенных людей, если отправитель блокируется из-за отправки нежелательной почты**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-171">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="69ee5-172">Этот параметр находится в процессе использования устаревших политик нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="69ee5-172">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="69ee5-173">[Политика оповещений](../../compliance/alert-policies.md) по умолчанию с именем "пользователь", которая **ограничена отправкой электронной почты** , уже отправляет уведомления по электронной почте членам группы **тенантадминс** (**Глобальные администраторы**), когда пользователи блокируются из-за превышения ограничений в разделе **ограничения получателей** .</span><span class="sxs-lookup"><span data-stu-id="69ee5-173">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="69ee5-174">**Мы настоятельно рекомендуем использовать политику оповещений, а не этот параметр в политике исходящей нежелательной почты для уведомления администраторов и других пользователей**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-174">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="69ee5-175">Инструкции приведены в разделе [Проверка параметров оповещений для пользователей с ограниченным доступом](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="69ee5-175">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="69ee5-176">Необязательно Разверните раздел **ограничения получателей** , чтобы настроить ограничения и действия для подозрительных исходящих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="69ee5-176">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="69ee5-177">Эти параметры применяются только к облачным почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="69ee5-177">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="69ee5-178">**Максимальное количество получателей на одного пользователя**</span><span class="sxs-lookup"><span data-stu-id="69ee5-178">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="69ee5-179">Допустимые значения: от 0 до 10000.</span><span class="sxs-lookup"><span data-stu-id="69ee5-179">A valid value is 0 to 10000.</span></span> <span data-ttu-id="69ee5-180">Значение по умолчанию — 0, что означает, что используются значения по умолчанию для службы.</span><span class="sxs-lookup"><span data-stu-id="69ee5-180">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="69ee5-181">Более подробную информацию можно узнать в статье [limiting Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span><span class="sxs-lookup"><span data-stu-id="69ee5-181">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="69ee5-182">**Внешнее почасовое ограничение**: максимальное число внешних получателей в час.</span><span class="sxs-lookup"><span data-stu-id="69ee5-182">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="69ee5-183">**Внутреннее почасовое ограничение**: максимальное число внутренних получателей в час.</span><span class="sxs-lookup"><span data-stu-id="69ee5-183">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="69ee5-184">**Ежедневное ограничение**: максимальное общее количество получателей в день.</span><span class="sxs-lookup"><span data-stu-id="69ee5-184">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="69ee5-185">**Действие, когда пользователь превышает указанные выше пределы**: Настройте действие, которое будет выполняться при превышении одного из **пределов получателей** .</span><span class="sxs-lookup"><span data-stu-id="69ee5-185">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="69ee5-186">Для всех действий получатели, указанные в **учетной записи пользователя, имеют ограниченную отправку политики оповещений по электронной почте** (и в разделе теперь избыточность **уведомлять определенных людей, если отправитель заблокирован из-за отправки параметра нежелательной почты** в политике нежелательной почты получать уведомления по электронной почте</span><span class="sxs-lookup"><span data-stu-id="69ee5-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="69ee5-187">**Запретить пользователю отправлять почту до следующего дня**: это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="69ee5-187">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="69ee5-188">Уведомления по электронной почте отправляются, и пользователь не сможет отправлять больше сообщений до следующего дня, исходя из времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="69ee5-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="69ee5-189">Администратор не может переопределить этот блок.</span><span class="sxs-lookup"><span data-stu-id="69ee5-189">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="69ee5-190">Оповещение об активности с именем **User Restricted from Send e-mail** уведомляет администраторов (через электронную почту и на странице " **Просмотр оповещений** ").</span><span class="sxs-lookup"><span data-stu-id="69ee5-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="69ee5-191">Все получатели, указанные в поле **уведомлять определенных людей, если отправитель заблокирован из-за отправки настройки исходящей нежелательной почты** в политике, также получают уведомления.</span><span class="sxs-lookup"><span data-stu-id="69ee5-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="69ee5-192">Пользователь не сможет отправлять больше сообщений до следующего дня, основываясь на времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="69ee5-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="69ee5-193">Администратор не может переопределить этот блок.</span><span class="sxs-lookup"><span data-stu-id="69ee5-193">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="69ee5-194">**Запретить пользователю отправлять почту**: отправляются уведомления по электронной почте, пользователь добавляется на портал \*\*[пользователи с ограниченными правами] <https://sip.protection.office.com/restrictedusers> \*\* в центре безопасности & соответствия требованиям, и пользователь не может отправлять электронную почту до тех пор, пока администратор не удалит их из портала **ограниченных пользователей** . После того как администратор удалит пользователя из списка, он не будет снова ограничен в течение этого дня.</span><span class="sxs-lookup"><span data-stu-id="69ee5-194">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="69ee5-195">Инструкции приведены в статье [Удаление пользователя с портала ограниченных пользователей после отправки нежелательной почты](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="69ee5-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="69ee5-196">**Без действия, только оповещение**: отправляются уведомления по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="69ee5-196">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="69ee5-197">Необязательно Разверните раздел **Автоматическая переадресация** , чтобы управлять автоматическим перенаправлением электронной почты пользователями внешними отправителями.</span><span class="sxs-lookup"><span data-stu-id="69ee5-197">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="69ee5-198">Дополнительные сведения об автоматической переадресации приведены в разделе [Настройка переадресации электронной почты](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding).</span><span class="sxs-lookup"><span data-stu-id="69ee5-198">For more information about automatic forwarding, see [Configure email forwarding](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="69ee5-199">До сентября 2020 эти параметры доступны, но не применяются.</span><span class="sxs-lookup"><span data-stu-id="69ee5-199">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="69ee5-200">Эти параметры применяются только к облачным почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="69ee5-200">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="69ee5-201">Эти параметры не влияют на автоматическую пересылку на внутренние получатели.</span><span class="sxs-lookup"><span data-stu-id="69ee5-201">Automatic forwarding to internal recipients is not affected by these setting.</span></span>

   <span data-ttu-id="69ee5-202">Ниже представлены возможные значения.</span><span class="sxs-lookup"><span data-stu-id="69ee5-202">The available values are:</span></span>

   - <span data-ttu-id="69ee5-203">**Система управляется системой**: разрешает фильтрацию исходящих нежелательных сообщений для управления автоматической переадресации внешних сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="69ee5-203">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="69ee5-204">Это значение используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="69ee5-204">This is the default value.</span></span>

   - <span data-ttu-id="69ee5-205">**On**: автоматическая переадресация внешних сообщений электронной почты не отключена политикой.</span><span class="sxs-lookup"><span data-stu-id="69ee5-205">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>

   - <span data-ttu-id="69ee5-206">Disabled **(отключено). Эта**политика отключена для всех автоматических внешних переадресаций электронной почты.</span><span class="sxs-lookup"><span data-stu-id="69ee5-206">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="69ee5-207">Потребоваться Разверните раздел **применено** , чтобы определить внутренних отправителей, к которым применяется политика.</span><span class="sxs-lookup"><span data-stu-id="69ee5-207">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="69ee5-208">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="69ee5-208">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="69ee5-209">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<sender1\>_ or _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="69ee5-209">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="69ee5-210">Между разными условиями и исключениями используется оператор AND (например, _\<sender1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="69ee5-210">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="69ee5-211">Проще всего нажать кнопку **Добавить условие** три раза, чтобы увидеть все доступные условия.</span><span class="sxs-lookup"><span data-stu-id="69ee5-211">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="69ee5-212">Чтобы удалить условия, которые не нужно настраивать, можно щелкнуть ![Кнопка удаления](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="69ee5-212">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="69ee5-213">**Домен отправителя**: указывает отправители из одного или нескольких настроенных обслуживаемых доменов в Организации.</span><span class="sxs-lookup"><span data-stu-id="69ee5-213">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="69ee5-214">Щелкните поле **Добавить тег**, чтобы просмотреть и выбрать домен.</span><span class="sxs-lookup"><span data-stu-id="69ee5-214">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="69ee5-215">Еще раз щелкните поле **Добавить тег**, чтобы выбрать дополнительные домены, если доступно несколько доменов.</span><span class="sxs-lookup"><span data-stu-id="69ee5-215">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="69ee5-216">**Отправитель**: указывает одного или нескольких пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="69ee5-216">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="69ee5-217">Щелкните в поле **Добавить тег** и начните вводить текст, чтобы отфильтровать список.</span><span class="sxs-lookup"><span data-stu-id="69ee5-217">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="69ee5-218">Еще раз щелкните поле **Добавить тег** , чтобы выбрать дополнительных отправители.</span><span class="sxs-lookup"><span data-stu-id="69ee5-218">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="69ee5-219">**Отправитель является участником**: указывает одну или несколько групп в Организации.</span><span class="sxs-lookup"><span data-stu-id="69ee5-219">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="69ee5-220">Щелкните в поле **Добавить тег** и начните вводить текст, чтобы отфильтровать список.</span><span class="sxs-lookup"><span data-stu-id="69ee5-220">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="69ee5-221">Еще раз щелкните поле **Добавить тег** , чтобы выбрать дополнительных отправители.</span><span class="sxs-lookup"><span data-stu-id="69ee5-221">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="69ee5-222">**За исключением случаев, когда**. Чтобы добавить исключение из правила, щелкните **Добавьте условие** три раза, чтобы увидеть все доступные исключения.</span><span class="sxs-lookup"><span data-stu-id="69ee5-222">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="69ee5-223">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="69ee5-223">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="69ee5-224">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-224">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="69ee5-225">Использование центра безопасности & соответствия требованиям для просмотра политик нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="69ee5-225">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="69ee5-226">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="69ee5-227">На странице **Параметры защиты от нежелательной почты** нажмите ![ развернуть значок, ](../../media/scc-expand-icon.png) чтобы развернуть политику нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="69ee5-227">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="69ee5-228">Политика по умолчанию с именем **Исходящая политика фильтрации нежелательной почты**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-228">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="69ee5-229">Создана настраиваемая политика, где значение в столбце **тип** является **настраиваемой политикой исходящих сообщений о нежелательной почте**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-229">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="69ee5-230">Параметры политики отображаются в отображаемых сведениях расширенной политики или можно щелкнуть **изменить политику**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-230">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="69ee5-231">Использование центра безопасности & соответствия требованиям для изменения политик исходящей нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="69ee5-231">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="69ee5-232">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-232">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="69ee5-233">На странице **Параметры защиты от нежелательной почты** нажмите ![ развернуть значок, ](../../media/scc-expand-icon.png) чтобы развернуть политику нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="69ee5-233">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="69ee5-234">Политика по умолчанию с именем **Исходящая политика фильтрации нежелательной почты**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-234">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="69ee5-235">Создана настраиваемая политика, где значение в столбце **тип** является **настраиваемой политикой исходящих сообщений о нежелательной почте**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-235">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="69ee5-236">Щелкните **Изменение политики**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-236">Click **Edit policy**.</span></span>

<span data-ttu-id="69ee5-237">Для настраиваемых политик нежелательной почты доступные параметры в всплывающем меню идентичны тем, которые описаны в разделе [использование & безопасности центра соответствия требованиям для создания раздела политики исходящих сообщений о нежелательной почте](#use-the-security--compliance-center-to-create-outbound-spam-policies) .</span><span class="sxs-lookup"><span data-stu-id="69ee5-237">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="69ee5-238">Для политики исходящих сообщений по умолчанию с именем " **Политика фильтрации нежелательной почты**" раздел **применено к** (политика применяется для всех), и вы не можете переименовать политику.</span><span class="sxs-lookup"><span data-stu-id="69ee5-238">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="69ee5-239">Сведения о включении или отключении политики, настройке приоритета политики или настройке уведомлений пользователей о карантине см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="69ee5-239">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="69ee5-240">Включение и отключение политик исходящей нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="69ee5-240">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="69ee5-241">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-241">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="69ee5-242">На странице **Параметры защиты от нежелательной почты** нажмите ![ развернуть значок, ](../../media/scc-expand-icon.png) чтобы развернуть созданную настраиваемую политику (значение в столбце **тип** — **настраиваемая политика исходящей почты**).</span><span class="sxs-lookup"><span data-stu-id="69ee5-242">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="69ee5-243">В развернутых сведениях политики обратите внимание на значение в столбце **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-243">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="69ee5-244">Чтобы отключить политику, переместите переключатель влево:</span><span class="sxs-lookup"><span data-stu-id="69ee5-244">Move the toggle to the left to disable the policy:</span></span> ![Выключенный переключатель](../../media/scc-toggle-off.png)

   <span data-ttu-id="69ee5-246">Чтобы включить политику, переместите переключатель вправо:</span><span class="sxs-lookup"><span data-stu-id="69ee5-246">Move the toggle to the right to enable the policy:</span></span> ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="69ee5-248">Отключить политику исходящей почты по умолчанию невозможно.</span><span class="sxs-lookup"><span data-stu-id="69ee5-248">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="69ee5-249">Установка приоритета настраиваемых политик нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="69ee5-249">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="69ee5-250">По умолчанию политикам исходящих сообщений по умолчанию назначен приоритет, основанный на порядке, в котором они были созданы (более новые политики имеют более высокий приоритет, чем старые политики).</span><span class="sxs-lookup"><span data-stu-id="69ee5-250">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="69ee5-251">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="69ee5-251">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="69ee5-252">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="69ee5-252">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="69ee5-253">Настраиваемые политики исходящей почты отображаются в порядке их обработки (первая политика имеет значение **приоритета** 0).</span><span class="sxs-lookup"><span data-stu-id="69ee5-253">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="69ee5-254">По умолчанию политика **фильтрации** нежелательной почты имеет значение Priority **наименьшее**, и вы не можете изменить его.</span><span class="sxs-lookup"><span data-stu-id="69ee5-254">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="69ee5-255">Чтобы изменить приоритет политики, переместите ее вверх или вниз в списке (в Центре безопасности и соответствия требованиям невозможно напрямую изменить значение свойства **Приоритет**).</span><span class="sxs-lookup"><span data-stu-id="69ee5-255">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="69ee5-256">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-256">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="69ee5-257">На странице **Параметры защиты от нежелательной почты** найдите политики, в которых значение столбца **тип** является **настраиваемой политикой исходящих сообщений**о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="69ee5-257">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="69ee5-258">Обратите внимание на значения в столбце **Приоритет**:</span><span class="sxs-lookup"><span data-stu-id="69ee5-258">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="69ee5-259">Настраиваемая политика нежелательной почты с наивысшим приоритетом имеет ![ значок стрелки вниз ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-259">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="69ee5-260">Настраиваемая политика нежелательной почты с наименьшим приоритетом имеет ![ значок стрелки вверх ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (например, ![ значок со стрелкой вверх ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="69ee5-260">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="69ee5-261">Если у вас есть три или более настраиваемых политик нежелательной почты, политики между самым высоким и самым низким приоритетом имеют значок стрелка ![ вверх со ](../../media/ITPro-EAC-UpArrowIcon.png)![ стрелкой вниз ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (например, значок ![ со стрелкой вверх ](../../media/ITPro-EAC-UpArrowIcon.png)![ вниз значок ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="69ee5-261">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="69ee5-262">Щелкните</span><span class="sxs-lookup"><span data-stu-id="69ee5-262">Click</span></span> ![Значок "Стрелка вверх"](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="69ee5-264">или</span><span class="sxs-lookup"><span data-stu-id="69ee5-264">or</span></span> ![Значок "Стрелка вниз"](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="69ee5-266">Перемещение настраиваемой политики нежелательной почты в списке приоритет.</span><span class="sxs-lookup"><span data-stu-id="69ee5-266">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="69ee5-267">Использование центра безопасности & соответствия требованиям для удаления политик нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="69ee5-267">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="69ee5-268">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-268">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="69ee5-269">На странице **параметров защиты от нежелательной почты** нажмите ![ развернуть значок, ](../../media/scc-expand-icon.png) чтобы развернуть пользовательскую политику, которую нужно удалить (в столбце **тип** — **настраиваемая политика нежелательной почты**).</span><span class="sxs-lookup"><span data-stu-id="69ee5-269">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="69ee5-270">В развернутых сведениях политики щелкните **Удалить политику**.</span><span class="sxs-lookup"><span data-stu-id="69ee5-270">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="69ee5-271">Нажмите **Да** в появившемся предупреждающем диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="69ee5-271">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="69ee5-272">Политику по умолчанию удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="69ee5-272">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="69ee5-273">Настройка политик нежелательной почты с помощью Exchange Online PowerShell или изолированной EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="69ee5-273">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="69ee5-274">Как описывалось ранее, политика исходящей нежелательной почты состоит из политики фильтрации исходящей нежелательной почты и правила фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="69ee5-274">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="69ee5-275">В Exchange Online PowerShell или отдельном EOP PowerShell разница между политиками фильтрации исходящей спама и правилом фильтрации нежелательной почты очевидна.</span><span class="sxs-lookup"><span data-stu-id="69ee5-275">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="69ee5-276">Управление политиками фильтрации нежелательной почты осуществляется с помощью командлетов \*\* \* – хостедаутбаундспамфилтерполици\*\* и управление правилами фильтрации нежелательной почты с помощью командлетов \*\* \* – хостедаутбаундспамфилтерруле\*\* .</span><span class="sxs-lookup"><span data-stu-id="69ee5-276">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="69ee5-277">В PowerShell сначала создается политика фильтрации исходящей нежелательной почты, а затем создается правило фильтрации исходящих сообщений, определяющее политику, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="69ee5-277">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="69ee5-278">В PowerShell параметры политики фильтрации исходящей нежелательной почты и фильтрации исходящих сообщений можно изменить отдельно.</span><span class="sxs-lookup"><span data-stu-id="69ee5-278">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="69ee5-279">При удалении политики фильтрации исходящей нежелательной почты из PowerShell соответствующее правило фильтрации нежелательной почты не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="69ee5-279">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="69ee5-280">Создание политик нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="69ee5-280">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="69ee5-281">Процесс создания политики нежелательной почты в PowerShell состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="69ee5-281">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="69ee5-282">Создайте политику фильтрации исходящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="69ee5-282">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="69ee5-283">Создайте правило фильтрации исходящих сообщений о нежелательной почте, которое указывает политику фильтрации исходящих сообщений, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="69ee5-283">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="69ee5-284">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="69ee5-284">**Notes**:</span></span>

- <span data-ttu-id="69ee5-285">Вы можете создать новое правило фильтрации нежелательной почты и назначить для него существующую, не связанную с ней политику фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="69ee5-285">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="69ee5-286">Правило фильтрации исходящих сообщений не может быть связано с несколькими политиками фильтрации исходящей почты.</span><span class="sxs-lookup"><span data-stu-id="69ee5-286">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="69ee5-287">Вы можете настроить следующие параметры для новых политик фильтрации нежелательной почты в PowerShell, которые недоступны в центре безопасности & соответствия требованиям, пока не будет создана политика:</span><span class="sxs-lookup"><span data-stu-id="69ee5-287">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="69ee5-288">Создайте новую политику как отключенную (_включена_ `$false` в командлете **New-хостедаутбаундспамфилтерруле** ).</span><span class="sxs-lookup"><span data-stu-id="69ee5-288">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="69ee5-289">Задайте приоритет политики при создании (_приоритет_ _\<Number\>_ ) для командлета **New-хостедаутбаундспамфилтерруле** .</span><span class="sxs-lookup"><span data-stu-id="69ee5-289">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="69ee5-290">Новая политика фильтрации исходящих сообщений, созданная в PowerShell, не отображается в центре безопасности &, пока политика не будет назначена правилу фильтрации спама.</span><span class="sxs-lookup"><span data-stu-id="69ee5-290">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="69ee5-291">Шаг 1: использование PowerShell для создания политики фильтрации исходящей нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="69ee5-291">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="69ee5-292">Чтобы создать политику фильтрации нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="69ee5-292">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="69ee5-293">В этом примере создается политика фильтрации исходящих сообщений с именем Contoso Executives со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="69ee5-293">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="69ee5-294">Ограничения скорости получателя ограничены меньшими значениями, используемыми по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="69ee5-294">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="69ee5-295">Для получения дополнительных сведений [365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)см.</span><span class="sxs-lookup"><span data-stu-id="69ee5-295">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="69ee5-296">По истечении одного из этих пределов пользователю запрещено отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="69ee5-296">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="69ee5-297">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – хостедаутбаундспамфилтерполици](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="69ee5-297">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="69ee5-298">Шаг 2: использование PowerShell для создания правила фильтрации исходящей нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="69ee5-298">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="69ee5-299">Чтобы создать правило фильтрации исходящих сообщений, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="69ee5-299">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="69ee5-300">В этом примере создается правило фильтрации исходящих сообщений с именем Contoso Executives с этими параметрами:</span><span class="sxs-lookup"><span data-stu-id="69ee5-300">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="69ee5-301">Политика фильтрации исходящей нежелательной почты с именем Contoso Executives связана с правилом.</span><span class="sxs-lookup"><span data-stu-id="69ee5-301">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="69ee5-302">Правило применяется к участникам группы Contoso Executives (Руководители Contoso).</span><span class="sxs-lookup"><span data-stu-id="69ee5-302">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="69ee5-303">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="69ee5-303">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="69ee5-304">Просмотр политик фильтрации исходящей нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="69ee5-304">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="69ee5-305">Чтобы получить сводный список всех политик фильтрации нежелательной почты, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="69ee5-305">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="69ee5-306">Чтобы получить подробные сведения о конкретной политике фильтрации нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="69ee5-306">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="69ee5-307">В этом примере возвращаются все значения свойств для политики фильтрации исходящей нежелательной почты с именем Executives.</span><span class="sxs-lookup"><span data-stu-id="69ee5-307">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="69ee5-308">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – хостедаутбаундспамфилтерполици](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="69ee5-308">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="69ee5-309">Просмотр правил фильтрации исходящей нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="69ee5-309">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="69ee5-310">Чтобы просмотреть существующие правила фильтрации нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="69ee5-310">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="69ee5-311">Чтобы получить сводный список всех правил фильтрации нежелательной почты, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="69ee5-311">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="69ee5-312">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="69ee5-312">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="69ee5-313">Чтобы получить подробные сведения об определенном правиле фильтрации нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="69ee5-313">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="69ee5-314">В этом примере возвращаются все значения свойств для правила фильтрации нежелательной почты Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="69ee5-314">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="69ee5-315">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="69ee5-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="69ee5-316">Использование PowerShell для изменения политик фильтрации исходящей нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="69ee5-316">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="69ee5-317">Те же параметры доступны при изменении политики фильтрации вредоносных программ в PowerShell так же, как и при создании политики, как описано в [шаге 1: с помощью PowerShell создайте в этой статье раздел Политика фильтрации исходящей нежелательной почты](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) .</span><span class="sxs-lookup"><span data-stu-id="69ee5-317">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="69ee5-318">Невозможно переименовать политику фильтра нежелательной почты (командлет **Set-хостедаутбаундспамфилтерполици** не имеет параметра _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="69ee5-318">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="69ee5-319">При переименовании политики исходящей нежелательной почты в центре безопасности & соответствия требованиям Вы переименовываете только _правило_фильтрации исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="69ee5-319">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="69ee5-320">Чтобы изменить политику фильтрации нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="69ee5-320">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="69ee5-321">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – хостедаутбаундспамфилтерполици](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="69ee5-321">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="69ee5-322">Использование PowerShell для изменения правил фильтрации исходящей нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="69ee5-322">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="69ee5-323">Единственный параметр, недоступный при изменении правила фильтрации нежелательной почты в PowerShell, это параметр _Enabled_ , позволяющий создать отключенное правило.</span><span class="sxs-lookup"><span data-stu-id="69ee5-323">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="69ee5-324">Чтобы включить или отключить существующие правила фильтрации нежелательной почты, ознакомьтесь со статьей, приведенным в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="69ee5-324">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="69ee5-325">В противном случае дополнительные параметры не будут доступны при изменении правила фильтрации нежелательной почты в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69ee5-325">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="69ee5-326">Те же параметры доступны при создании правила, как описано в [шаге 2: используйте PowerShell, чтобы создать раздел правил фильтрации нежелательной почты](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) , приведенный ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="69ee5-326">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="69ee5-327">Чтобы изменить правило фильтрации исходящих сообщений, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="69ee5-327">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="69ee5-328">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="69ee5-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="69ee5-329">Включение и отключение правил фильтрации исходящих сообщений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="69ee5-329">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="69ee5-330">Включение или отключение правила фильтрации исходящей нежелательной почты в PowerShell включает или отключает полную политику исходящей нежелательной почты (правило фильтрации нежелательной почты и назначенную политику фильтрации нежелательной почты).</span><span class="sxs-lookup"><span data-stu-id="69ee5-330">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="69ee5-331">Вы не можете включить или отключить политику исходящей почты по умолчанию (она всегда применяется ко всем получателям).</span><span class="sxs-lookup"><span data-stu-id="69ee5-331">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="69ee5-332">Чтобы включить или отключить правило фильтрации исходящих сообщений в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="69ee5-332">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="69ee5-333">В этом примере отключается правило фильтрации исходящих сообщений с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="69ee5-333">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="69ee5-334">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="69ee5-334">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="69ee5-335">Подробные сведения о синтаксисе и параметрах можно найти в статье [Enable – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="69ee5-335">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="69ee5-336">Установка приоритета правил фильтрации исходящих сообщений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="69ee5-336">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="69ee5-337">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="69ee5-337">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="69ee5-338">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="69ee5-338">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="69ee5-339">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="69ee5-339">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="69ee5-340">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="69ee5-340">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="69ee5-341">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="69ee5-341">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="69ee5-342">Чтобы задать приоритет правила фильтрации исходящей нежелательной почты в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="69ee5-342">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="69ee5-p139">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="69ee5-p139">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="69ee5-345">Чтобы задать приоритет нового правила при его создании, используйте параметр _Priority_ в командлете **New – хостедаутбаундспамфилтерруле** .</span><span class="sxs-lookup"><span data-stu-id="69ee5-345">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="69ee5-346">Исходящая политика фильтрации нежелательной почты по умолчанию не имеет соответствующего правила фильтрации нежелательной почты и всегда имеет неизменяемое значение приоритета **.**</span><span class="sxs-lookup"><span data-stu-id="69ee5-346">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="69ee5-347">Удаление политик фильтрации нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="69ee5-347">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="69ee5-348">При использовании PowerShell для удаления политики фильтрации исходящей нежелательной почты соответствующее правило фильтрации нежелательной почты не удаляется.</span><span class="sxs-lookup"><span data-stu-id="69ee5-348">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="69ee5-349">Чтобы удалить политику фильтрации нежелательной почты в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="69ee5-349">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="69ee5-350">В этом примере удаляется политика фильтрации исходящей нежелательной почты с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="69ee5-350">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="69ee5-351">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – хостедаутбаундспамфилтерполици](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="69ee5-351">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="69ee5-352">Удаление правил фильтрации нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="69ee5-352">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="69ee5-353">При использовании PowerShell для удаления правила фильтрации нежелательной почты соответствующая политика фильтрации исходящих сообщений не удаляется.</span><span class="sxs-lookup"><span data-stu-id="69ee5-353">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="69ee5-354">Чтобы удалить правило фильтрации нежелательной почты в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="69ee5-354">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="69ee5-355">В этом примере удаляется правило фильтрации исходящих сообщений с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="69ee5-355">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="69ee5-356">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="69ee5-356">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="69ee5-357">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="69ee5-357">For more information</span></span>

[<span data-ttu-id="69ee5-358">Удаление заблокированных пользователей с портала "Пользователи с ограниченным доступом"</span><span class="sxs-lookup"><span data-stu-id="69ee5-358">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="69ee5-359">Пул доставки сообщений с высоким уровнем опасности</span><span class="sxs-lookup"><span data-stu-id="69ee5-359">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="69ee5-360">Вопросы и ответы по защите от нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="69ee5-360">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="69ee5-361">Отчет по автоматически пересылаемым сообщениям</span><span class="sxs-lookup"><span data-stu-id="69ee5-361">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
