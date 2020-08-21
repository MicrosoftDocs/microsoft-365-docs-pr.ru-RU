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
ms.openlocfilehash: 530c1af9b7802be6073f19331ce7f6a20bdb2668
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845982"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="90366-103">Настройка фильтрации исходящей нежелательной почты в EOP</span><span class="sxs-lookup"><span data-stu-id="90366-103">Configure outbound spam filtering in EOP</span></span>

<span data-ttu-id="90366-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online для исходящих сообщений электронной почты, отправленных через EOP, автоматически проверяется спам и необычная отправка.</span><span class="sxs-lookup"><span data-stu-id="90366-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="90366-105">Как правило, в исходящем спаме от пользователя в вашей организации возникает компрометация учетной записи.</span><span class="sxs-lookup"><span data-stu-id="90366-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="90366-106">Подозрительные исходящие сообщения помечаются как спам (независимо от вероятности нежелательной почты) и направляются через [пул доставки сообщений](high-risk-delivery-pool-for-outbound-messages.md) с высоким уровнем опасности для защиты репутации службы (то поднимайте, оставляйте исходные почтовые серверы Microsoft 365 от списков заблокированных IP-адресов).</span><span class="sxs-lookup"><span data-stu-id="90366-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="90366-107">Администраторы автоматически уведомляются о подозрительных действиях с исходящим электронной почтой и заблокированных пользователей с [помощью политик оповещений.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="90366-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="90366-108">Служба EOP использует политики исходящей нежелательной почты в рамках общей защиты от нежелательной почты в организации.</span><span class="sxs-lookup"><span data-stu-id="90366-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="90366-109">Дополнительные сведения см. в статье [Защита от нежелательной почты](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="90366-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="90366-110">Администраторы могут просматривать, изменять и настраивать (но не удалять) политики защиты от нежелательной почты для исходящих сообщений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="90366-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="90366-111">Для большей детализации можно также создать настраиваемые политики защиты от нежелательной почты для исходящих сообщений, которые применяются к определенным пользователям, группам и доменам в организации.</span><span class="sxs-lookup"><span data-stu-id="90366-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="90366-112">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="90366-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="90366-113">Вы можете настроить политики исходящей нежелательной почты в Центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; отдельный PowerShell EOP для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="90366-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="90366-114">Основные элементы политики защиты от исходящей нежелательной почты в EOP:</span><span class="sxs-lookup"><span data-stu-id="90366-114">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="90366-115">**Политика фильтрации исходящей нежелательной**почты: указывает действия, предусмание которых необходимо предусмотреть в фильтрах исходящей нежелательной почты, и параметры уведомлений.</span><span class="sxs-lookup"><span data-stu-id="90366-115">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="90366-116">**Правило фильтрации исходящей нежелательной**почты. Указывает приоритет и фильтры получателей (к кому применяется политика) для политики фильтрации исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="90366-116">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="90366-117">Разница между этими двумя элементами не так очевидна, если вы управляете политиками исходящей нежелательной почты в Центре безопасности & безопасности:</span><span class="sxs-lookup"><span data-stu-id="90366-117">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="90366-118">При создании политики в действительности вы одновременно создаете правило фильтрации исходящей нежелательной почты и связанную с ним политику с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="90366-118">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="90366-119">При изменении политики параметры, связанные с именем, приоритетом, включенным или отключенным, и фильтрами получателей, изменяют правило фильтрации исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="90366-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="90366-120">Все остальные параметры меняют связанную политику фильтрации исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="90366-120">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="90366-121">При удалении политики удаляются правило фильтрации исходящей нежелательной почты и связанная с ними политика фильтрации исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="90366-121">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="90366-122">В Exchange Online PowerShell или автономном EOP PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="90366-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="90366-123">Дополнительные сведения см. в разделе "Настройка политик спама для исходящей нежелательной почты" далее в этой статье в разделе ["Использование Exchange Online PowerShell" или автономной службы EOP PowerShell.](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="90366-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this topic.</span></span>

<span data-ttu-id="90366-124">В каждой организации есть встроенная политика защиты от нежелательной почты для исходящих сообщений с именем "По умолчанию" с указанными ниже свойствами.</span><span class="sxs-lookup"><span data-stu-id="90366-124">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="90366-125">Политика применяется ко всем получателям в организации, даже если с ней не связано никакого правила фильтрации исходящей нежелательной почты (фильтрации получателей).</span><span class="sxs-lookup"><span data-stu-id="90366-125">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="90366-126">Для политики задано специальное значение приоритета **Самый низкий**, которое невозможно изменить (эта политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="90366-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="90366-127">Все созданные специальные политики всегда имеют более высокий приоритет, чем политика с именем "По умолчанию".</span><span class="sxs-lookup"><span data-stu-id="90366-127">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="90366-128">Эта политика является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.</span><span class="sxs-lookup"><span data-stu-id="90366-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="90366-129">Чтобы повысить эффективность фильтрации исходящей нежелательной почты, можно создать настраиваемые политики защиты от нежелательной почты для исходящих сообщений с более строгими параметрами, которые применяются к определенным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="90366-129">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="90366-130">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="90366-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="90366-131">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="90366-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="90366-132">Чтобы сразу перейти к странице **Параметры защиты от нежелательной почты**, используйте ссылку <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="90366-132">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="90366-133">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="90366-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="90366-134">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="90366-134">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="90366-135">Чтобы вы могли выполнить процедуры, упомянутые в этой теме, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="90366-135">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="90366-136">Чтобы добавлять, изменять и удалять политики исходящей нежелательной почты, необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="90366-136">To add, modify, and delete outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="90366-137">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="90366-137">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="90366-138">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="90366-138">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="90366-139">Чтобы политики исходящей нежелательной почты полю получить доступ только для чтения, вы должны быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="90366-139">For read-only access to outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="90366-140">**Средство считывания сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="90366-140">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="90366-141">**Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="90366-141">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="90366-142">Рекомендуемые параметры политик исходящей нежелательной почты см. в разделе ["Параметры политики фильтрации исходящей нежелательной почты eop".](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="90366-142">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="90366-143">[Превышен](../../compliance/alert-policies.md) предел **предусмотренных**по умолчанию **для**политик отправки сообщений по умолчанию подозрительный предел доставки сообщений , обнаружен шаблон вредоносных сообщений и **пользователь запрещал** отправлять электронные уведомления **участникам группы TenantAdmins** **(глобальные администраторы)** о необычных действиях с электронной почтой и заблокированных пользователях из-за нежелательной почты для исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="90366-143">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="90366-144">Дополнительные сведения см. в разделе ["Проверка параметров оповещений для пользователей с ограниченным доступом".](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="90366-144">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="90366-145">Рекомендуем использовать эти политики вместо параметров уведомлений в политиках исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="90366-145">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="90366-146">Создание политик исходящ &ей нежелательной почты с помощью Центра безопасности почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="90366-146">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="90366-147">При создании настраиваемой политики защиты от нежелательной почты в Центре соответствия требованиям & создаются правило фильтрации нежелательной почты и связанная с ним политика фильтрации нежелательной почты одновременно, используя одинаковые для этих элементов одно и то же название.</span><span class="sxs-lookup"><span data-stu-id="90366-147">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="90366-148">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="90366-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="90366-149">На странице **"Параметры защиты от нежелательной** почты" нажмите **кнопку "Создать политику исходящей почты".**</span><span class="sxs-lookup"><span data-stu-id="90366-149">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="90366-150">В **открывшемся всплывающем** окне политики фильтрации исходящей нежелательной почты настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="90366-150">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="90366-151">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="90366-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="90366-152">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="90366-152">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="90366-153">(Необязательно) Разверните раздел **"Уведомления"** для настройки дополнительных пользователей, которые должны получать копии и уведомления о подозрительных исходящих сообщениях электронной почты:</span><span class="sxs-lookup"><span data-stu-id="90366-153">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="90366-154">**Отправка копии подозрительных**исходящих сообщений определенным пользователям: этот параметр добавляет указанных пользователей в поле "СК" подозрительных исходящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="90366-154">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="90366-155">Этот параметр применяется только к политике защиты от нежелательной почты для исходящих сообщений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="90366-155">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="90366-156">Он не работает в настраиваемых политиках защиты от нежелательной почты для исходящих сообщений, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="90366-156">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="90366-157">Чтобы включить этот параметр,</span><span class="sxs-lookup"><span data-stu-id="90366-157">To enable this setting:</span></span>

     1. <span data-ttu-id="90366-158">Установите флажок, чтобы включить параметр.</span><span class="sxs-lookup"><span data-stu-id="90366-158">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="90366-159">Нажмите **кнопку Добавить пользователей.**</span><span class="sxs-lookup"><span data-stu-id="90366-159">Click **Add people**.</span></span> <span data-ttu-id="90366-160">Во **всплывающем элементе** "Добавление и удаление получателей" отобразится следующее:</span><span class="sxs-lookup"><span data-stu-id="90366-160">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="90366-161">Введите электронный адрес отправителя.</span><span class="sxs-lookup"><span data-stu-id="90366-161">Enter the sender's email address.</span></span> <span data-ttu-id="90366-162">Можно указать несколько адресов электронной почты, разделив их точками с запятой (;) одного получателя в строке.</span><span class="sxs-lookup"><span data-stu-id="90366-162">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="90366-163">Щелкните</span><span class="sxs-lookup"><span data-stu-id="90366-163">Click</span></span> ![Значок добавления](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="90366-165">для добавления получателей.</span><span class="sxs-lookup"><span data-stu-id="90366-165">to add the recipients.</span></span>

        <span data-ttu-id="90366-166">Повторите эти действия необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="90366-166">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="90366-167">Добавленные получатели отображаются в разделе **"Список получателей"** во всплывающем окне.</span><span class="sxs-lookup"><span data-stu-id="90366-167">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="90366-168">Чтобы удалить получателя, нажмите кнопку ![ ](../../media/scc-remove-icon.png) "Удалить".</span><span class="sxs-lookup"><span data-stu-id="90366-168">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="90366-169">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="90366-169">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="90366-170">Чтобы отключить этот параметр, снимите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="90366-170">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="90366-171">**Уведомляйте конкретных людей, если отправитель заблокирован из-за отправки спама:**</span><span class="sxs-lookup"><span data-stu-id="90366-171">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="90366-172">Этот параметр находится в процессе прекращения поддержки политик исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="90366-172">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="90366-173">[Стандартная политика оповещений](../../compliance/alert-policies.md) **по умолчанию User limited from sending email** already sends email notifications to members of the **TenantAdmins** **(Global admins)** group when users are blocked ed the limits in the **Recipient Limits** section.</span><span class="sxs-lookup"><span data-stu-id="90366-173">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="90366-174">**Мы настоятельно рекомендуем использовать политику**предупреждений вместо этого параметра в политике исходящей нежелательной почты для уведомления администраторов и других пользователей.</span><span class="sxs-lookup"><span data-stu-id="90366-174">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="90366-175">Инструкции см. в статье ["Проверка параметров оповещений для пользователей с ограниченным доступом".](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="90366-175">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="90366-176">(Необязательно) Разверните **раздел "Ограничения получателей",** чтобы настроить ограничения и действия для подозрительных исходящих сообщений электронной почты:</span><span class="sxs-lookup"><span data-stu-id="90366-176">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="90366-177">Эти параметры применимы только к облачным почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="90366-177">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="90366-178">**Максимальное количество получателей на пользователя**</span><span class="sxs-lookup"><span data-stu-id="90366-178">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="90366-179">Допустимые значения — от 0 до 10 000.</span><span class="sxs-lookup"><span data-stu-id="90366-179">A valid value is 0 to 10000.</span></span> <span data-ttu-id="90366-180">Значение по умолчанию равно 0, что означает, что используются значения по умолчанию для службы.</span><span class="sxs-lookup"><span data-stu-id="90366-180">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="90366-181">Дополнительные сведения см. в разделе ["Ограничения на отправку".](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)</span><span class="sxs-lookup"><span data-stu-id="90366-181">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="90366-182">**Ограничение внешнего часа**— максимальное количество внешних получателей в час.</span><span class="sxs-lookup"><span data-stu-id="90366-182">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="90366-183">**Внутреннее ограничение в час:** максимальное количество внутренних получателей в час.</span><span class="sxs-lookup"><span data-stu-id="90366-183">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="90366-184">**Ежедневный**лимит: максимальное общее количество получателей в день.</span><span class="sxs-lookup"><span data-stu-id="90366-184">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="90366-185">**При превышении пользователем указанных**выше ограничений: настройте действие, при превышении любого **из ограничений** получателей.</span><span class="sxs-lookup"><span data-stu-id="90366-185">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="90366-186">Во всех действиях получателям, указанным в **политике пользователя,** разрешена отправка политики предупреждений электронной почты (и в этом случае теперь в этом случае уведомления отправляются отправителю из-за отправки параметра исходящей нежелательной почты в политике защиты от нежелательной почты для исходящей почты. **Notify specific people if a sender is blocked due to sending outbound spam**</span><span class="sxs-lookup"><span data-stu-id="90366-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="90366-187">**Ограничьте отправку сообщений для указанного списка в следующем день:** Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="90366-187">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="90366-188">Уведомления отправляются, и пользователь больше не сможет отправлять сообщения до следующего дня в зависимости от времени UTC.</span><span class="sxs-lookup"><span data-stu-id="90366-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="90366-189">Администратор не может переопределить этот блок.</span><span class="sxs-lookup"><span data-stu-id="90366-189">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="90366-190">Предупреждение о действии **с именем "Пользователь уничтожен" запретил** отправку уведомлений администраторам электронной почты (по электронной почте и на **странице просмотра оповещений).**</span><span class="sxs-lookup"><span data-stu-id="90366-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="90366-191">Все получатели, указанные в **уведомлении конкретных людей,** если отправитель заблокирован из-за того, что отправка исходящей нежелательной почты в политике, также уведомляется.</span><span class="sxs-lookup"><span data-stu-id="90366-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="90366-192">Отправка сообщений пользователем в зависимости от времени в формате UTC будет недоступна для отправки сообщений до следующего дня.</span><span class="sxs-lookup"><span data-stu-id="90366-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="90366-193">Администратор не может переопределить этот блок.</span><span class="sxs-lookup"><span data-stu-id="90366-193">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="90366-194">**Запретить пользователю отправлять почту:** уведомления по электронной почте отправляются, он добавляется на \*\*портал [Пользователи <https://sip.protection.office.com/restrictedusers> \*\* с ограниченным доступом] в Центре безопасности & соответствия требованиям и не может отправлять электронную почту до удаления его из портала **"Пользователи с** ограниченным доступом" администратором. После того как администратор удалит пользователя из списка, этот день снова будет ограничен.</span><span class="sxs-lookup"><span data-stu-id="90366-194">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="90366-195">Инструкции см. в статье ["Удаление пользователя с портала "Пользователи с ограниченным доступом" после отправки нежелательной почты.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="90366-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="90366-196">**Нет никаких действий, только**оповещения: уведомления по электронной почте отправляются.</span><span class="sxs-lookup"><span data-stu-id="90366-196">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="90366-197">(Необязательно) Разверните **раздел "Автоматическая переадресация",** чтобы управлять автоматической переадресацией почты пользователями внешним отправителям.</span><span class="sxs-lookup"><span data-stu-id="90366-197">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="90366-198">Дополнительные сведения об автоматической переадресации см. в статье ["Настройка переадресации электронной почты".](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding)</span><span class="sxs-lookup"><span data-stu-id="90366-198">For more information about automatic forwarding, see [Configure email forwarding](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="90366-199">До сентября 2020 г. эти параметры доступны, но не используются.</span><span class="sxs-lookup"><span data-stu-id="90366-199">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="90366-200">Эти параметры применяются только к облачным почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="90366-200">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="90366-201">Этот параметр не влияет на автоматическую переадресацию внутренним получателям.</span><span class="sxs-lookup"><span data-stu-id="90366-201">Automatic forwarding to internal recipients is not affected by these setting.</span></span>

   <span data-ttu-id="90366-202">Ниже представлены возможные значения.</span><span class="sxs-lookup"><span data-stu-id="90366-202">The available values are:</span></span>

   - <span data-ttu-id="90366-203">**Автоматически контролируемый системой:** позволяет фильтру исходящей нежелательной почты управлять автоматической переадресацией внешней почты.</span><span class="sxs-lookup"><span data-stu-id="90366-203">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="90366-204">Это значение используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="90366-204">This is the default value.</span></span>

   - <span data-ttu-id="90366-205">**В меню**"Автоматическая внешняя переадресация" не отключена политикой.</span><span class="sxs-lookup"><span data-stu-id="90366-205">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>

   - <span data-ttu-id="90366-206">**Выкл.:** политика отключила автоматическую автоматическую переадресацию по внешней адресе электронной почты.</span><span class="sxs-lookup"><span data-stu-id="90366-206">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="90366-207">(Обязательный) Разверните **раздел, чтобы** указать внутренних отправителей, к которым применяется политика.</span><span class="sxs-lookup"><span data-stu-id="90366-207">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="90366-208">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="90366-208">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="90366-209">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<sender1\>_ or _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="90366-209">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="90366-210">Между разными условиями и исключениями используется оператор AND (например, _\<sender1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="90366-210">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="90366-211">Проще всего нажать кнопку **Добавить условие** три раза, чтобы увидеть все доступные условия.</span><span class="sxs-lookup"><span data-stu-id="90366-211">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="90366-212">Чтобы удалить условия, которые не нужно настраивать, можно щелкнуть ![Кнопка удаления](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="90366-212">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="90366-213">**Домен отправителя:** указывает отправителей в одном или нескольких настроенных обслуживаемых доменах в организации.</span><span class="sxs-lookup"><span data-stu-id="90366-213">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="90366-214">Щелкните поле **Добавить тег**, чтобы просмотреть и выбрать домен.</span><span class="sxs-lookup"><span data-stu-id="90366-214">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="90366-215">Еще раз щелкните поле **Добавить тег**, чтобы выбрать дополнительные домены, если доступно несколько доменов.</span><span class="sxs-lookup"><span data-stu-id="90366-215">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="90366-216">**Sender is:** Указывает одного или нескольких пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="90366-216">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="90366-217">Щелкните в поле **Добавить тег** и начните вводить текст, чтобы отфильтровать список.</span><span class="sxs-lookup"><span data-stu-id="90366-217">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="90366-218">Снова **нажмите кнопку "Добавить тег",** чтобы выбрать других отправителей.</span><span class="sxs-lookup"><span data-stu-id="90366-218">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="90366-219">**Отправитель входит в группу:** указывает одну или несколько групп в организации.</span><span class="sxs-lookup"><span data-stu-id="90366-219">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="90366-220">Щелкните в поле **Добавить тег** и начните вводить текст, чтобы отфильтровать список.</span><span class="sxs-lookup"><span data-stu-id="90366-220">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="90366-221">Снова **нажмите кнопку "Добавить тег",** чтобы выбрать других отправителей.</span><span class="sxs-lookup"><span data-stu-id="90366-221">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="90366-222">**За исключением случаев, когда**. Чтобы добавить исключение из правила, щелкните **Добавьте условие** три раза, чтобы увидеть все доступные исключения.</span><span class="sxs-lookup"><span data-stu-id="90366-222">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="90366-223">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="90366-223">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="90366-224">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="90366-224">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="90366-225">Просмотр политик исходящ &ей нежелательной почты с помощью Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="90366-225">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="90366-226">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="90366-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="90366-227">На странице параметров **защиты от нежелательной почты нажмите** значок ![ "Развернуть", ](../../media/scc-expand-icon.png) чтобы развернуть политику исходящей нежелательной почты:</span><span class="sxs-lookup"><span data-stu-id="90366-227">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="90366-228">Стандартная политика фильтрации спама для **исходящей нежелательной почты.**</span><span class="sxs-lookup"><span data-stu-id="90366-228">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="90366-229">Созданная настраиваемая политика, где в столбце **"Тип"** используется настраиваемая политика защиты **от нежелательной почты для исходящих сообщений.**</span><span class="sxs-lookup"><span data-stu-id="90366-229">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="90366-230">Параметры политики отображаются в развернутых сведениях политики, которые отображаются, либо нажмите кнопку **"Изменить политику".**</span><span class="sxs-lookup"><span data-stu-id="90366-230">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="90366-231">Изменение политик исходящей нежелательной почты с помощью Центра безопасности &</span><span class="sxs-lookup"><span data-stu-id="90366-231">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="90366-232">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="90366-232">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="90366-233">На странице параметров **защиты от нежелательной почты нажмите** значок ![ "Развернуть", ](../../media/scc-expand-icon.png) чтобы развернуть политику исходящей нежелательной почты:</span><span class="sxs-lookup"><span data-stu-id="90366-233">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="90366-234">Стандартная политика фильтрации спама для **исходящей нежелательной почты.**</span><span class="sxs-lookup"><span data-stu-id="90366-234">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="90366-235">Созданная настраиваемая политика, где в столбце **"Тип"** используется настраиваемая политика защиты **от нежелательной почты для исходящих сообщений.**</span><span class="sxs-lookup"><span data-stu-id="90366-235">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="90366-236">Щелкните **Изменение политики**.</span><span class="sxs-lookup"><span data-stu-id="90366-236">Click **Edit policy**.</span></span>

<span data-ttu-id="90366-237">Для настраиваемых политик защиты от нежелательной почты доступные параметры во всплывающем элементе идентичны параметрам, описанным в разделе ["Безопасность & Соответствия требованиям" для создания политик исходящей нежелательной почты.](#use-the-security--compliance-center-to-create-outbound-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="90366-237">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="90366-238">Для политики фильтрации исходящей **Applied to** нежелательной почты по умолчанию с именем **"Политика фильтрации исходящей**нежелательной почты" раздел "Применяется к разделу" (политика применяется ко всем пользователям), и вы не можете переименовать политику.</span><span class="sxs-lookup"><span data-stu-id="90366-238">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="90366-239">Сведения о включении или отключении политики, настройке приоритета политики или настройке уведомлений пользователей о карантине см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="90366-239">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="90366-240">Включение и отключение политик исходящей нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="90366-240">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="90366-241">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="90366-241">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="90366-242">На странице параметров **защиты от нежелательной почты** нажмите ![ значок "Развернуть", чтобы развернуть созданную ](../../media/scc-expand-icon.png) настраиваемую политику (в столбце **"Тип"** указана настраиваемая политика **защиты от нежелательной почты).**</span><span class="sxs-lookup"><span data-stu-id="90366-242">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="90366-243">В развернутых сведениях политики обратите внимание на значение в столбце **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="90366-243">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="90366-244">Чтобы отключить политику, переместите переключатель влево:</span><span class="sxs-lookup"><span data-stu-id="90366-244">Move the toggle to the left to disable the policy:</span></span> ![Выключенный переключатель](../../media/scc-toggle-off.png)

   <span data-ttu-id="90366-246">Чтобы включить политику, переместите переключатель вправо:</span><span class="sxs-lookup"><span data-stu-id="90366-246">Move the toggle to the right to enable the policy:</span></span> ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="90366-248">Политику защиты от нежелательной почты для исходящих сообщений по умолчанию невозможно отключить.</span><span class="sxs-lookup"><span data-stu-id="90366-248">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="90366-249">Настройка приоритета настраиваемых политик защиты от нежелательной почты для исходящих сообщений</span><span class="sxs-lookup"><span data-stu-id="90366-249">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="90366-250">По умолчанию политикам исходящей нежелательной почты задается приоритет, основанный на том, в каком порядке они были созданы (приоритет новых политик ниже, чем у старых).</span><span class="sxs-lookup"><span data-stu-id="90366-250">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="90366-251">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="90366-251">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="90366-252">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="90366-252">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="90366-253">Настраиваемые политики защиты от нежелательной почты для исходящих сообщений отображаются в порядке их обработки (для первой **политики установленприоритет** 0).</span><span class="sxs-lookup"><span data-stu-id="90366-253">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="90366-254">Для защиты политики фильтрации исходящей нежелательной почты с именем **"Rout spam"** (Политика фильтрации исходящей нежелательной почты) по умолчанию имеет значение **приоритета "Наименьший",** его невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="90366-254">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="90366-255">Чтобы изменить приоритет политики, переместите ее вверх или вниз в списке (в Центре безопасности и соответствия требованиям невозможно напрямую изменить значение свойства **Приоритет**).</span><span class="sxs-lookup"><span data-stu-id="90366-255">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="90366-256">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="90366-256">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="90366-257">На странице параметров **защиты от нежелательной почты** найдите политики, в столбце "Тип" которых в столбце **"Тип"** указана **настраиваемая политика защиты от нежелательной почты для исходящей нежелательной почты.**</span><span class="sxs-lookup"><span data-stu-id="90366-257">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="90366-258">Обратите внимание на значения в столбце **Приоритет**:</span><span class="sxs-lookup"><span data-stu-id="90366-258">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="90366-259">Настраиваемой политике защиты от нежелательной почты для исходящих сообщений с наивысшим приоритетом соответствует значок ![ стрелки вниз ](../../media/ITPro-EAC-DownArrowIcon.png) **0.**</span><span class="sxs-lookup"><span data-stu-id="90366-259">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="90366-260">Для настраиваемой политики защиты от нежелательной почты для исходящих сообщений с наименьшим приоритетом используется значение значка стрелки вверх ![ ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (например, ![ значок стрелки ](../../media/ITPro-EAC-UpArrowIcon.png) **вверх 3).**</span><span class="sxs-lookup"><span data-stu-id="90366-260">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="90366-261">Если вы используете три и более настраиваемых политик защиты от нежелательной почты для исходящих сообщений, политики между наивысшим и низким приоритетом будут иметь стрелку вверх ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ и ](../../media/ITPro-EAC-DownArrowIcon.png) **вниз** (например, ![ значок стрелки вверх ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2)**</span><span class="sxs-lookup"><span data-stu-id="90366-261">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="90366-262">Щелкните</span><span class="sxs-lookup"><span data-stu-id="90366-262">Click</span></span> ![Значок "Стрелка вверх"](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="90366-264">или</span><span class="sxs-lookup"><span data-stu-id="90366-264">or</span></span> ![Значок "Стрелка вниз"](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="90366-266">для перемещения настраиваемой политики защиты от нежелательной почты вверх или вниз в списке приоритетов.</span><span class="sxs-lookup"><span data-stu-id="90366-266">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="90366-267">Удаление политик исходя &щей нежелательной исходящей нежелательной почты с помощью Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="90366-267">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="90366-268">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="90366-268">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="90366-269">На странице **"Параметры защиты от нежелательной почты"** нажмите значок "Развернуть", чтобы развернуть настраиваемую политику, ![ ](../../media/scc-expand-icon.png) которую нужно удалить (в **столбце "Тип" указана** настраиваемая политика **защиты от нежелательной почты).**</span><span class="sxs-lookup"><span data-stu-id="90366-269">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="90366-270">В развернутых сведениях политики щелкните **Удалить политику**.</span><span class="sxs-lookup"><span data-stu-id="90366-270">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="90366-271">Нажмите **Да** в появившемся предупреждающем диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="90366-271">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="90366-272">Политику по умолчанию удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="90366-272">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="90366-273">Настройка политик спама для исходящей нежелательной почты с помощью Exchange Online PowerShell или автономной службы EOP</span><span class="sxs-lookup"><span data-stu-id="90366-273">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="90366-274">Как описано выше, политика фильтрации исходящей нежелательной почты состоит из политики фильтрации исходящей нежелательной почты и правила фильтрации исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="90366-274">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="90366-275">В Exchange Online PowerShell или автономной службе EOP PowerShell разница между политиками фильтрации исходящей нежелательной почты очевидна.</span><span class="sxs-lookup"><span data-stu-id="90366-275">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="90366-276">Для управления политиками фильтрации исходящей нежелательной почты \*\* \* используются командлеты -HostedOutboundSpamFilterPolicy,\*\* а правила фильтрации исходящей нежелательной почты для управления исходящей нежелательной почты можно управлять с \*\* \* помощью командлетов -HostedOutboundSpamFilterRule.\*\*</span><span class="sxs-lookup"><span data-stu-id="90366-276">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="90366-277">В PowerShell сначала создается политика фильтрации исходящей нежелательной почты, а затем — правило фильтрации исходящей нежелательной почты, указывающее политику, к которой правило применяется.</span><span class="sxs-lookup"><span data-stu-id="90366-277">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="90366-278">В PowerShell параметры политики фильтрации исходящей нежелательной почты и правила фильтрации исходящей нежелательной почты наменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="90366-278">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="90366-279">При удалении политики фильтрации исходящей нежелательной почты с помощью PowerShell соответствующее правило не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="90366-279">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="90366-280">Создание политик исходящей нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="90366-280">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="90366-281">Процесс создания политики исходящей нежелательной почты в PowerShell выполняется в два этапа.</span><span class="sxs-lookup"><span data-stu-id="90366-281">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="90366-282">Создание политики фильтрации исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="90366-282">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="90366-283">Создание правила фильтрации исходящей нежелательной почты, указывающего политику фильтрации исходящей нежелательной почты, к которой правило применяется.</span><span class="sxs-lookup"><span data-stu-id="90366-283">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="90366-284">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="90366-284">**Notes**:</span></span>

- <span data-ttu-id="90366-285">Вы можете создать новое правило фильтрации исходящей нежелательной почты и назначить ему существующие несвязанные политики фильтрации нежелательной почты для исходящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="90366-285">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="90366-286">Правила фильтрации исходящей нежелательной почты нельзя связать с несколькими политиками фильтрации исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="90366-286">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="90366-287">Вы можете настроить следующие параметры для новых политик фильтрации исходящей нежелательной почты в PowerShell, которые будут доступны в Центре безопасности &, пока не будет создана политика:</span><span class="sxs-lookup"><span data-stu-id="90366-287">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="90366-288">Новая политика отключена _(активирована_ `$false` для командлета **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="90366-288">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="90366-289">Задайте приоритет политики во время создания _(приоритет)_ _\<Number\>_ в **командлете New-HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="90366-289">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="90366-290">Новая политика фильтрации исходящей нежелательной почты, созданная в PowerShell, не будет отображаться в Центре безопасности & соответствия требованиям, пока вы не назначите ее правилу фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="90366-290">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="90366-291">Шаг 1. Создание политики фильтрации исходящей нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="90366-291">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="90366-292">Чтобы создать политику фильтрации исходящей нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90366-292">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="90366-293">В этом примере создается политика фильтрации исходящей нежелательной почты Contoso Executives (Руководители Contoso) со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="90366-293">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="90366-294">Предельное количество получателей ограничено значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="90366-294">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="90366-295">Дополнительные сведения см. в статье [об ограничениях на отправку в планах Microsoft 365.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)</span><span class="sxs-lookup"><span data-stu-id="90366-295">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="90366-296">После достижения одного из этих ограничений отправка сообщений для пользователя отключена.</span><span class="sxs-lookup"><span data-stu-id="90366-296">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="90366-297">Дополнительные сведения о синтаксисе и параметрах см. в [описании New-HostedOutboundSpamFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="90366-297">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="90366-298">Шаг 2. Создание правила фильтрации исходящей нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="90366-298">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="90366-299">Чтобы создать правило фильтрации исходящей нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90366-299">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="90366-300">В этом примере создается новое правило фильтрации исходящей нежелательной почты contoso, используя следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="90366-300">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="90366-301">С правилом связана политика фильтрации исходящей нежелательной почты с именем Contoso Executives (Руководители Contoso).</span><span class="sxs-lookup"><span data-stu-id="90366-301">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="90366-302">Правило применяется к участникам группы Contoso Executives (Руководители Contoso).</span><span class="sxs-lookup"><span data-stu-id="90366-302">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="90366-303">Дополнительные сведения о синтаксисе и параметрах см. в [описании метода New-HostedOutboundSpamFilterRule.](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="90366-303">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="90366-304">Просмотр политик фильтрации исходящей нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="90366-304">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="90366-305">Чтобы получить сводный список всех политик фильтрации нежелательной почты для исходящих сообщений, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="90366-305">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="90366-306">Чтобы получить подробные сведения об определенной политике фильтрации исходящей нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90366-306">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="90366-307">В этом примере возвращаются значения всех свойств политики фильтрации исходящей нежелательной почты с именем Executives (Руководители).</span><span class="sxs-lookup"><span data-stu-id="90366-307">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="90366-308">Дополнительные сведения о синтаксисе и параметрах см. в [статье Get-HostedOutboundSpamFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="90366-308">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="90366-309">Просмотр правил фильтрации исходящей нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="90366-309">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="90366-310">Чтобы просмотреть существующие правила фильтрации исходящей нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90366-310">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="90366-311">Чтобы получить сводный список всех правил фильтрации нежелательной почты для исходящих сообщений, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="90366-311">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="90366-312">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="90366-312">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="90366-313">Чтобы получить подробные сведения об определенном правиле фильтрации исходящей нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90366-313">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="90366-314">В этом примере возвращаются значения всех свойств правила фильтрации исходящей нежелательной почты с именем Contoso Executives (Руководители Contoso).</span><span class="sxs-lookup"><span data-stu-id="90366-314">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="90366-315">Дополнительные сведения о синтаксисе и параметрах см. в [статье Get-HostedOutboundSpamFilterRule.](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="90366-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="90366-316">Изменение политик фильтрации исходящей нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="90366-316">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="90366-317">Такие же параметры доступны при изменении политики фильтрации вредоносных программ в PowerShell, как и в [разделе "Шаг 1. Создание политики фильтрации исходящей нежелательной почты"](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) с помощью PowerShell выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="90366-317">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="90366-318">Политику фильтрации исходящей нежелательной почты переименовать невозможно **(у командлета Set-HostedOutboundSpamFilterPolicy** нет _параметра_ Name).</span><span class="sxs-lookup"><span data-stu-id="90366-318">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="90366-319">При переименовании политики защиты от нежелательной почты в Центре соответствия требованиям безопасности &, правило фильтрации нежелательной почты для исходящей _нежелательной почты переименовывается._</span><span class="sxs-lookup"><span data-stu-id="90366-319">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="90366-320">Чтобы изменить политику фильтрации исходящей нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90366-320">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="90366-321">Дополнительные сведения о синтаксисе и параметрах см. в [статье Set-HostedOutboundSpamFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="90366-321">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="90366-322">Изменение правил фильтрации исходящей нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="90366-322">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="90366-323">При изменении правила фильтрации исходящей нежелательной почты в PowerShell недоступен только параметр _Enabled,_ позволяющий создать отключенное правило.</span><span class="sxs-lookup"><span data-stu-id="90366-323">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="90366-324">Сведения о включении и отключении существующих правил фильтрации исходящей нежелательной почты см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="90366-324">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="90366-325">В противном случае при изменении правила фильтрации исходящей нежелательной почты в PowerShell никакие дополнительные параметры не используются.</span><span class="sxs-lookup"><span data-stu-id="90366-325">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="90366-326">Такие же параметры доступны при создании правила, как описано в [действии 2. Создание правила фильтрации исходящей нежелательной почты](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) описано выше в этой статье с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90366-326">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="90366-327">Чтобы изменить правило фильтрации исходящей нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90366-327">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="90366-328">Дополнительные сведения о синтаксисе и параметрах см. в [описании Set-HostedOutboundSpamFilterRule.](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="90366-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="90366-329">Включение и отключение правил фильтрации исходящей нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="90366-329">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="90366-330">При включении или отключении правила фильтрации исходящей нежелательной почты в PowerShell включается или отключается вся политика фильтрации исходящей нежелательной почты (правило фильтрации исходящей нежелательной почты и назначенная политика фильтрации исходящей нежелательной почты).</span><span class="sxs-lookup"><span data-stu-id="90366-330">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="90366-331">Вы не можете включить или отключить политику защиты от нежелательной почты для исходящих сообщений по умолчанию (она всегда применяется ко всем получателям).</span><span class="sxs-lookup"><span data-stu-id="90366-331">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="90366-332">Чтобы включить или отключить правило фильтрации исходящей нежелательной почты в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90366-332">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="90366-333">В этом примере отключается правило фильтрации исходящей нежелательной почты с именем Marketing Department (Отдел маркетинга).</span><span class="sxs-lookup"><span data-stu-id="90366-333">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="90366-334">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="90366-334">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="90366-335">Дополнительные сведения о синтаксисе и параметрах см. в [описании команд Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) [и Disable-HostedOutboundSpamFilterRule.](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="90366-335">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="90366-336">Установка приоритета правил фильтрации исходящей нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="90366-336">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="90366-337">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="90366-337">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="90366-338">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="90366-338">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="90366-339">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="90366-339">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="90366-340">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="90366-340">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="90366-341">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="90366-341">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="90366-342">Чтобы задать приоритет правила фильтрации исходящей нежелательной почты в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90366-342">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="90366-p139">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="90366-p139">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="90366-345">Чтобы задать приоритет нового правила при его создании, используйте параметр _Priority_ командлета **New-HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="90366-345">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="90366-346">Политика фильтрации спама для исходящих сообщений, выбранная по умолчанию, не имеет соответствующего правила фильтрации нежелательной почты и всегда имеет неизменяемое **значение приоритета.**</span><span class="sxs-lookup"><span data-stu-id="90366-346">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="90366-347">Удаление политик фильтрации исходящей нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="90366-347">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="90366-348">Если вы используете PowerShell для удаления политики фильтрации исходящей нежелательной почты, соответствующее правило фильтрации исходящей нежелательной почты не удаляется.</span><span class="sxs-lookup"><span data-stu-id="90366-348">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="90366-349">Чтобы удалить политику фильтрации исходящей нежелательной почты в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90366-349">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="90366-350">В этом примере удаляется политика фильтрации исходящей нежелательной почты с именем Marketing Department (Отдел маркетинга).</span><span class="sxs-lookup"><span data-stu-id="90366-350">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="90366-351">Дополнительные сведения о синтаксисе и параметрах см. в [статье Remove-HostedOutboundSpamFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="90366-351">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="90366-352">Удаление правил фильтрации исходящей нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="90366-352">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="90366-353">Если вы используете PowerShell для удаления правила фильтрации исходящей нежелательной почты, соответствующая политика фильтрации исходящей нежелательной почты не удаляется.</span><span class="sxs-lookup"><span data-stu-id="90366-353">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="90366-354">Чтобы удалить правило фильтрации исходящей нежелательной почты в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90366-354">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="90366-355">В этом примере удаляется правило фильтрации исходящей нежелательной почты с именем Marketing Department (Отдел маркетинга).</span><span class="sxs-lookup"><span data-stu-id="90366-355">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="90366-356">Дополнительные сведения о синтаксисе и параметрах см. в [статье Remove-HostedOutboundSpamFilterRule.](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="90366-356">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="90366-357">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="90366-357">For more information</span></span>

[<span data-ttu-id="90366-358">Удаление заблокированных пользователей с портала "Пользователи с ограниченным доступом"</span><span class="sxs-lookup"><span data-stu-id="90366-358">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="90366-359">Пул доставки сообщений с высоким уровнем опасности</span><span class="sxs-lookup"><span data-stu-id="90366-359">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="90366-360">Вопросы и ответы по защите от нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="90366-360">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="90366-361">Отчет по автоматически пересылаемым сообщениям</span><span class="sxs-lookup"><span data-stu-id="90366-361">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
