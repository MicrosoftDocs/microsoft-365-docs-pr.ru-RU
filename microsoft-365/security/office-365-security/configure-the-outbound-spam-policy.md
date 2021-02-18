---
title: Настройка фильтрации исходящего спама
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как просматривать, создавать, изменять и удалять политики нежелательной почты для исходящие сообщений в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 742c58a8a94938c5896382a6d53acac127974f02
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288937"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="359b1-103">Настройка фильтрации исходящие спама в EOP</span><span class="sxs-lookup"><span data-stu-id="359b1-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="359b1-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="359b1-104">**Applies to**</span></span>
- [<span data-ttu-id="359b1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="359b1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="359b1-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="359b1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="359b1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="359b1-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="359b1-108">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online исходящие сообщения электронной почты, отправляемые через EOP, автоматически проверяются на наличие нежелательной почты и необычных действий при отправке.</span><span class="sxs-lookup"><span data-stu-id="359b1-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="359b1-109">Исходящие нежелательные сообщения от пользователя в организации обычно указывают на компрометации учетной записи.</span><span class="sxs-lookup"><span data-stu-id="359b1-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="359b1-110">Подозрительные исходящие сообщения помечается как нежелательная почта (независимо от уровня уверенности в нежелательной почте или SCL) и маршрутются через пул доставки сообщений с высоким уровнем риска, чтобы защитить репутацию службы (то есть, не выключать исходные почтовые серверы Microsoft 365 из списков заблокированных [IP-адресов).](high-risk-delivery-pool-for-outbound-messages.md)</span><span class="sxs-lookup"><span data-stu-id="359b1-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="359b1-111">Администраторы автоматически получают уведомления о подозрительной активности исходящие сообщения электронной почты и блокируют пользователей с помощью [политик оповещений.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="359b1-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="359b1-112">EOP использует политики защиты от нежелательной почты исходящие сообщения в рамках общей защиты организации от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="359b1-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="359b1-113">Дополнительные сведения см. в статье [Защита от нежелательной почты](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="359b1-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="359b1-114">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику нежелательной почты для исходящие сообщения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="359b1-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="359b1-115">Для большей детализации можно также создать настраиваемые политики нежелательной почты исходящие, которые применяются к определенным пользователям, группам или доменам в организации.</span><span class="sxs-lookup"><span data-stu-id="359b1-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="359b1-116">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="359b1-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="359b1-117">Политики защиты от нежелательной почты для исходящие сообщений можно настроить в Центре безопасности и & соответствия требованиям или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="359b1-117">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="359b1-118">Основные элементы политики нежелательной почты для исходящие сообщений в EOP:</span><span class="sxs-lookup"><span data-stu-id="359b1-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="359b1-119">**Политика фильтрации исходящие нежелательной** почты : определяет действия для решения фильтрации исходящие нежелательной почты и параметры уведомлений.</span><span class="sxs-lookup"><span data-stu-id="359b1-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="359b1-120">**Правило фильтрации исходящие нежелательной** почты : указывает приоритет и фильтры получателей (к кому применяется политика) для политики фильтрации исходящие нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="359b1-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="359b1-121">Разница между этими двумя элементами не очевидна при управлении политиками нежелательной почты для исходящие сообщения в Центре безопасности & соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="359b1-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="359b1-122">При создании политики фактически создается правило фильтрации исходящие нежелательной почты и связанная с ней политика фильтрации исходящие нежелательной почты одновременно с использованием одного и того же имени для обоих этих правил.</span><span class="sxs-lookup"><span data-stu-id="359b1-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="359b1-123">При изменении политики параметры, связанные с именем, приоритетом, включенным или отключенным фильтрами получателей, изменяют правило фильтрации исходящие спама.</span><span class="sxs-lookup"><span data-stu-id="359b1-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="359b1-124">Все остальные параметры изменяют связанную политику фильтрации исходящие нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="359b1-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="359b1-125">При удалении политики удаляются правило фильтрации исходящие нежелательной почты и связанная с ней политика фильтрации исходящие нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="359b1-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="359b1-126">В Exchange Online PowerShell или автономном EOP PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="359b1-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="359b1-127">Дополнительные сведения см. в разделе "Использование Exchange Online PowerShell или автономный [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) для настройки политик исходящие нежелательной почты" далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="359b1-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="359b1-128">В каждой организации имеется встроенная политика нежелательной почты для исходящие сообщений с именем Default, которая имеет указанные здесь свойства.</span><span class="sxs-lookup"><span data-stu-id="359b1-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="359b1-129">Политика применяется к всем получателям в организации, даже если с политикой не связано ни одно правило фильтрации исходящие нежелательной почты (фильтры получателей).</span><span class="sxs-lookup"><span data-stu-id="359b1-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="359b1-130">Для политики задано специальное значение приоритета **Самый низкий**, которое невозможно изменить (эта политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="359b1-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="359b1-131">Все созданные специальные политики всегда имеют более высокий приоритет, чем политика с именем "По умолчанию".</span><span class="sxs-lookup"><span data-stu-id="359b1-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="359b1-132">Эта политика является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.</span><span class="sxs-lookup"><span data-stu-id="359b1-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="359b1-133">Чтобы повысить эффективность фильтрации исходящие нежелательные сообщения, можно создать настраиваемые политики исходящие нежелательной почты с более строгими настройками, которые применяются к определенным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="359b1-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="359b1-134">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="359b1-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="359b1-135">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="359b1-135">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="359b1-136">Чтобы сразу перейти к странице **Параметры защиты от нежелательной почты**, используйте ссылку <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="359b1-136">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="359b1-137">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="359b1-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="359b1-138">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="359b1-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="359b1-139">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="359b1-139">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="359b1-140">Для добавления, изменения и удаления политик нежелательной почты для  исходящие сообщения необходимо быть членом группы ролей "Управление организацией" или "Администратор **безопасности".**</span><span class="sxs-lookup"><span data-stu-id="359b1-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="359b1-141">Для доступа только для чтения к политикам нежелательной почты исходящие  сообщения необходимо быть членом группы ролей **"Глобальный** читатель" или "Читатель безопасности".</span><span class="sxs-lookup"><span data-stu-id="359b1-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="359b1-142">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="359b1-142">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="359b1-143">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="359b1-143">**Notes**:</span></span>

  - <span data-ttu-id="359b1-144">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="359b1-144">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="359b1-145">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="359b1-145">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="359b1-146">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="359b1-146">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="359b1-147">Рекомендуемые параметры политик фильтрации исходящие нежелательной почты см. в параметрах политики фильтрации исходящие [нежелательных сообщений EOP.](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="359b1-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="359b1-148">Политики [](../../compliance/alert-policies.md) оповещений по умолчанию с именем **"Ограничение**  на отправку электронной почты" превышены, обнаружены подозрительные шаблоны отправки электронной почты, а пользователи, которые не могут отправлять сообщения электронной почты, уже отправляют уведомления членам группы **TenantAdmins** **(глобальные** администраторы) о необычных действиях с электронной почтой и заблокированных пользователях из-за нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="359b1-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="359b1-149">Дополнительные сведения [см. в подсети "Проверка параметров оповещений для пользователей с ограниченным доступом".](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="359b1-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="359b1-150">Мы рекомендуем использовать эти политики оповещений вместо параметров уведомлений в политиках нежелательной почты для исходящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="359b1-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="359b1-151">Использование Центра безопасности & соответствия требованиям для создания политик защиты от нежелательной почты для исходящие сообщения</span><span class="sxs-lookup"><span data-stu-id="359b1-151">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="359b1-152">При создании настраиваемой политики нежелательной почты исходящие сообщения в Центре безопасности & соответствия требованиям одновременно создаются правило фильтрации нежелательной почты и связанная с ней политика фильтрации нежелательной почты с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="359b1-152">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="359b1-153">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="359b1-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="359b1-154">На странице **"Параметры нежелательной почты"** щелкните **"Создать политику исходящие сообщения".**</span><span class="sxs-lookup"><span data-stu-id="359b1-154">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="359b1-155">В **открываемой** политике фильтрации исходящие нежелательной почты настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="359b1-155">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="359b1-156">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="359b1-156">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="359b1-157">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="359b1-157">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="359b1-158">(Необязательно) **Расширьте раздел** "Уведомления", чтобы настроить дополнительных пользователей, которые должны получать копии и уведомления о подозрительных исходящие сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="359b1-158">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="359b1-159">**Отправка копии подозрительных** исходящие сообщения электронной почты определенным пользователям: этот параметр добавляет указанных пользователей в качестве получателей "СК" в подозрительные исходящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="359b1-159">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="359b1-160">Этот параметр работает только в политике нежелательной почты для исходящие сообщения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="359b1-160">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="359b1-161">Он не работает с настраиваемой политикой нежелательной почты для исходящие сообщения, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="359b1-161">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="359b1-162">Чтобы включить этот параметр, с помощью этого параметра:</span><span class="sxs-lookup"><span data-stu-id="359b1-162">To enable this setting:</span></span>

     1. <span data-ttu-id="359b1-163">Чтобы включить параметр, выберите этот параметр.</span><span class="sxs-lookup"><span data-stu-id="359b1-163">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="359b1-164">Нажмите **кнопку "Добавить людей".**</span><span class="sxs-lookup"><span data-stu-id="359b1-164">Click **Add people**.</span></span> <span data-ttu-id="359b1-165">В **окле "Добавление или удаление получателей"** появится:</span><span class="sxs-lookup"><span data-stu-id="359b1-165">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="359b1-166">Введите электронный адрес отправителя.</span><span class="sxs-lookup"><span data-stu-id="359b1-166">Enter the sender's email address.</span></span> <span data-ttu-id="359b1-167">Можно указать несколько адресов электронной почты, разделенных точками с за ;) или один получатель на строку.</span><span class="sxs-lookup"><span data-stu-id="359b1-167">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="359b1-168">Щелкните</span><span class="sxs-lookup"><span data-stu-id="359b1-168">Click</span></span> ![Значок добавления](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="359b1-170">для добавления получателей.</span><span class="sxs-lookup"><span data-stu-id="359b1-170">to add the recipients.</span></span>

        <span data-ttu-id="359b1-171">Повторите эти действия необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="359b1-171">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="359b1-172">Добавленные получатели отображаются в **разделе** списка получателей во flyout.</span><span class="sxs-lookup"><span data-stu-id="359b1-172">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="359b1-173">Чтобы удалить получателя, нажмите ![ кнопку "Удалить". ](../../media/scc-remove-icon.png)</span><span class="sxs-lookup"><span data-stu-id="359b1-173">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="359b1-174">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="359b1-174">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="359b1-175">Чтобы отключить этот параметр, необходимо установить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="359b1-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="359b1-176">**Уведомлять определенных пользователей, если отправитель заблокирован из-за отправки исходящие нежелательные сообщения:**</span><span class="sxs-lookup"><span data-stu-id="359b1-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="359b1-177">Этот параметр не является частью политик нежелательной почты для исходящие сообщений.</span><span class="sxs-lookup"><span data-stu-id="359b1-177">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="359b1-178">Политика [](../../compliance/alert-policies.md) оповещений по умолчанию User **restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins)** group when users are blocked due to exceeding the limits in the Recipient **Limits** section.</span><span class="sxs-lookup"><span data-stu-id="359b1-178">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="359b1-179">Мы настоятельно рекомендуем использовать политику оповещений, а не этот параметр в политике нежелательной почты для исходящие сообщения для уведомления администраторов **и других пользователей.**</span><span class="sxs-lookup"><span data-stu-id="359b1-179">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="359b1-180">Инструкции см. в [подсети "Проверка параметров оповещений для пользователей с ограниченным доступом".](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="359b1-180">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="359b1-181">(Необязательно) **Расширьте раздел "Ограничения** получателей", чтобы настроить ограничения и действия для подозрительных исходящие сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="359b1-181">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="359b1-182">Эти параметры применимы только к облачным почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="359b1-182">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="359b1-183">**Максимальное количество получателей на пользователя**</span><span class="sxs-lookup"><span data-stu-id="359b1-183">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="359b1-184">Допустимые значения— от 0 до 10 000.</span><span class="sxs-lookup"><span data-stu-id="359b1-184">A valid value is 0 to 10000.</span></span> <span data-ttu-id="359b1-185">Значение по умолчанию — 0, то есть используются значения по умолчанию для службы.</span><span class="sxs-lookup"><span data-stu-id="359b1-185">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="359b1-186">Дополнительные сведения см. в [ограничениях на отправку.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)</span><span class="sxs-lookup"><span data-stu-id="359b1-186">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="359b1-187">**Внешнее почасовая ограничение:** максимальное количество внешних получателей в час.</span><span class="sxs-lookup"><span data-stu-id="359b1-187">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="359b1-188">**Внутреннее почасовая ограничение:** максимальное количество внутренних получателей в час.</span><span class="sxs-lookup"><span data-stu-id="359b1-188">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="359b1-189">**Ежедневный предел:** максимальное общее число получателей в день.</span><span class="sxs-lookup"><span data-stu-id="359b1-189">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="359b1-190">**Действие, когда пользователь превышает** вышеперечисленные ограничения: настройте действие, если превышено одно из ограничений получателей. </span><span class="sxs-lookup"><span data-stu-id="359b1-190">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="359b1-191">Для всех действий получатели,  указанные в политике предупреждений пользователя,  не могут отправлять сообщения электронной почты (а в теперь избыточном уведомлении определенных пользователей, если отправитель заблокирован из-за того, что в политике нежелательной почты для исходящие сообщения отправлены исходящие сообщения нежелательной почты, получают уведомления по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="359b1-191">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="359b1-192">**Запретить пользователю отправлять почту до следующего дня:** это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="359b1-192">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="359b1-193">Уведомления отправляются по электронной почте, и пользователь не сможет отправлять больше сообщений до следующего дня в зависимости от времени в UTC.</span><span class="sxs-lookup"><span data-stu-id="359b1-193">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="359b1-194">Администратор не может переопредить этот блок.</span><span class="sxs-lookup"><span data-stu-id="359b1-194">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="359b1-195">Оповещение об активности **с именем User restricted от** отправки электронной почты оповещает администраторов (по электронной почте и на странице просмотра **оповещений).**</span><span class="sxs-lookup"><span data-stu-id="359b1-195">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="359b1-196">Все получатели, указанные в уведомлении определенных пользователей, если отправитель заблокирован из-за параметра исходящие нежелательные сообщения в политике также уведомляются. </span><span class="sxs-lookup"><span data-stu-id="359b1-196">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="359b1-197">Пользователь не сможет отправлять больше сообщений до следующего дня в зависимости от времени в UTC.</span><span class="sxs-lookup"><span data-stu-id="359b1-197">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="359b1-198">Администратор не может переопредить этот блок.</span><span class="sxs-lookup"><span data-stu-id="359b1-198">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="359b1-199">Запретить пользователю отправлять **почту:** отправка уведомлений электронной почты, пользователь добавляется на портал [Пользователи с ограниченным доступом **&] <https://sip.protection.office.com/restrictedusers>** в  Центре безопасности и соответствия требованиям, и пользователь не может отправлять электронную почту, пока администратор не будет удален с портала "Пользователи с ограниченным доступом". После того как администратор удалит пользователя из списка, он не будет снова ограничен в течение этого дня.</span><span class="sxs-lookup"><span data-stu-id="359b1-199">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="359b1-200">Инструкции см. в удалении пользователя с портала "Пользователи с ограниченным [доступом" после отправки нежелательной почты.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="359b1-200">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="359b1-201">**Никаких действий, только оповещение:** отправка уведомлений по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="359b1-201">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="359b1-202">(Необязательно) Раздел **"Автоматическая переадружение"** позволяет контролировать автоматическую переадружение электронной почты пользователями внешним отправителям.</span><span class="sxs-lookup"><span data-stu-id="359b1-202">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="359b1-203">Дополнительные сведения см. в поддоме "Управление автоматической переадружаемой внешней электронной [почтой" в Microsoft 365.](external-email-forwarding.md)</span><span class="sxs-lookup"><span data-stu-id="359b1-203">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="359b1-204">До сентября 2020 г. эти параметры доступны, но не применяются.</span><span class="sxs-lookup"><span data-stu-id="359b1-204">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="359b1-205">Эти параметры применяются только к облачным почтовым ящикам.</span><span class="sxs-lookup"><span data-stu-id="359b1-205">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="359b1-206">Если автоматическая пересылаемая почта отключена, получатель получает отчет о неотвечаемой доставке (также известный как сообщение о возврате), если внешние отправитые отправляют сообщения электронной почты в почтовый ящик, в который была отправлена пересылаемая почта.</span><span class="sxs-lookup"><span data-stu-id="359b1-206">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="359b1-207">Если сообщение отправлено внутренним отправищиком, а методом пересылки является пересылание почтовых ящиков [(также](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) известное как пересылание _SMTP),_ внутренний отправитель получит этот запрос. </span><span class="sxs-lookup"><span data-stu-id="359b1-207">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="359b1-208">Внутренний отправитель не получит сообщение о задержанной отправке, если она произошла из-за правила для почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="359b1-208">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

   <span data-ttu-id="359b1-209">Ниже представлены возможные значения.</span><span class="sxs-lookup"><span data-stu-id="359b1-209">The available values are:</span></span>

   - <span data-ttu-id="359b1-210">**Автоматическое управление системой:** позволяет фильтровать исходящие нежелательные сообщения для управления автоматической внешней переадружаемой электронной почтой.</span><span class="sxs-lookup"><span data-stu-id="359b1-210">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="359b1-211">Это значение используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="359b1-211">This is the default value.</span></span>
   - <span data-ttu-id="359b1-212">**On**: Automatic external email forwarding is not disabled by the policy.</span><span class="sxs-lookup"><span data-stu-id="359b1-212">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
   - <span data-ttu-id="359b1-213">**Выключите:** политика отключит автоматическую переадружение внешней электронной почты.</span><span class="sxs-lookup"><span data-stu-id="359b1-213">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="359b1-214">(Обязательно) **Разослать раздел "Применено",** чтобы определить внутренних отправителей, к которые применяется политика.</span><span class="sxs-lookup"><span data-stu-id="359b1-214">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="359b1-215">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="359b1-215">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="359b1-216">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<sender1\>_ or _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="359b1-216">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="359b1-217">Между разными условиями и исключениями используется оператор AND (например, _\<sender1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="359b1-217">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="359b1-218">Проще всего нажать кнопку **Добавить условие** три раза, чтобы увидеть все доступные условия.</span><span class="sxs-lookup"><span data-stu-id="359b1-218">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="359b1-219">Чтобы удалить условия, которые не нужно настраивать, можно щелкнуть ![Кнопка удаления](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="359b1-219">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="359b1-220">**Домен отправителей:** указывает отправителей в одном или более настроенных принятых доменах в организации.</span><span class="sxs-lookup"><span data-stu-id="359b1-220">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="359b1-221">Щелкните поле **Добавить тег**, чтобы просмотреть и выбрать домен.</span><span class="sxs-lookup"><span data-stu-id="359b1-221">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="359b1-222">Еще раз щелкните поле **Добавить тег**, чтобы выбрать дополнительные домены, если доступно несколько доменов.</span><span class="sxs-lookup"><span data-stu-id="359b1-222">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="359b1-223">**Отправитель:** указывает одного или несколько пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="359b1-223">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="359b1-224">Щелкните в поле **Добавить тег** и начните вводить текст, чтобы отфильтровать список.</span><span class="sxs-lookup"><span data-stu-id="359b1-224">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="359b1-225">Щелкните еще **раз в поле "Добавить тег",** чтобы выбрать дополнительных отправителей.</span><span class="sxs-lookup"><span data-stu-id="359b1-225">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="359b1-226">**Sender is a member of**: Specifies one or more groups in your organization.</span><span class="sxs-lookup"><span data-stu-id="359b1-226">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="359b1-227">Щелкните в поле **Добавить тег** и начните вводить текст, чтобы отфильтровать список.</span><span class="sxs-lookup"><span data-stu-id="359b1-227">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="359b1-228">Щелкните еще **раз в поле "Добавить тег",** чтобы выбрать дополнительных отправителей.</span><span class="sxs-lookup"><span data-stu-id="359b1-228">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="359b1-229">**За исключением случаев, когда**. Чтобы добавить исключение из правила, щелкните **Добавьте условие** три раза, чтобы увидеть все доступные исключения.</span><span class="sxs-lookup"><span data-stu-id="359b1-229">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="359b1-230">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="359b1-230">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="359b1-231">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="359b1-231">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="359b1-232">Просмотр политик защиты от & безопасности с помощью Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="359b1-232">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="359b1-233">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="359b1-233">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="359b1-234">На странице **"Параметры нежелательной почты"** щелкните значок "Развернуть", чтобы развернуть политику ![ ](../../media/scc-expand-icon.png) нежелательной почты для исходящие сообщения:</span><span class="sxs-lookup"><span data-stu-id="359b1-234">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="359b1-235">Политика по умолчанию с **именем "Политика фильтрации исходящие нежелательной почты".**</span><span class="sxs-lookup"><span data-stu-id="359b1-235">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="359b1-236">Настраиваемая политика, которую вы создали, где значение в столбце **"Тип"** — **настраиваемая политика нежелательной почты для исходящие сообщения.**</span><span class="sxs-lookup"><span data-stu-id="359b1-236">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="359b1-237">Параметры политики отображаются в появились в расширенных сведениях политики, или вы можете нажать кнопку **"Изменить политику".**</span><span class="sxs-lookup"><span data-stu-id="359b1-237">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="359b1-238">Использование Центра безопасности & соответствия требованиям для изменения политик защиты от нежелательной почты для исходящие сообщения</span><span class="sxs-lookup"><span data-stu-id="359b1-238">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="359b1-239">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="359b1-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="359b1-240">На странице **"Параметры нежелательной почты"** щелкните значок "Развернуть", чтобы развернуть политику ![ ](../../media/scc-expand-icon.png) нежелательной почты для исходящие сообщения:</span><span class="sxs-lookup"><span data-stu-id="359b1-240">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="359b1-241">Политика по умолчанию с **именем "Политика фильтрации исходящие нежелательной почты".**</span><span class="sxs-lookup"><span data-stu-id="359b1-241">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="359b1-242">Настраиваемая политика, которую вы создали, где значение в столбце **"Тип"** — **настраиваемая политика нежелательной почты для исходящие сообщения.**</span><span class="sxs-lookup"><span data-stu-id="359b1-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="359b1-243">Щелкните **Изменение политики**.</span><span class="sxs-lookup"><span data-stu-id="359b1-243">Click **Edit policy**.</span></span>

<span data-ttu-id="359b1-244">Для настраиваемой политики защиты от нежелательной почты исходящие сообщения доступные параметры во flyout идентичны тем, которые описаны в разделе "Использование Центра безопасности [и](#use-the-security--compliance-center-to-create-outbound-spam-policies) соответствия требованиям & для создания политик защиты от нежелательной почты для исходящие сообщения".</span><span class="sxs-lookup"><span data-stu-id="359b1-244">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="359b1-245">Для политики исходящие нежелательные сообщения по умолчанию  с именем "Политика фильтрации исходящие нежелательной почты" раздел "Применено к" не доступен (политика применяется ко всем), и переименовать политику нельзя. </span><span class="sxs-lookup"><span data-stu-id="359b1-245">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="359b1-246">Сведения о включении или отключении политики, настройке приоритета политики или настройке уведомлений пользователей о карантине см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="359b1-246">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="359b1-247">Enable or disable outbound spam policies</span><span class="sxs-lookup"><span data-stu-id="359b1-247">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="359b1-248">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="359b1-248">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="359b1-249">На странице **"Параметры** нежелательной почты" щелкните значок "Развернуть", чтобы развернуть созданную настраиваемую политику (значение в столбце "Тип" — настраиваемая политика нежелательной почты для исходящие ![ ](../../media/scc-expand-icon.png) **сообщения).** </span><span class="sxs-lookup"><span data-stu-id="359b1-249">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="359b1-250">В развернутых сведениях политики обратите внимание на значение в столбце **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="359b1-250">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="359b1-251">Чтобы отключить политику, переместите переключатель влево:</span><span class="sxs-lookup"><span data-stu-id="359b1-251">Move the toggle to the left to disable the policy:</span></span> ![Выключенный переключатель](../../media/scc-toggle-off.png)

   <span data-ttu-id="359b1-253">Чтобы включить политику, переместите переключатель вправо:</span><span class="sxs-lookup"><span data-stu-id="359b1-253">Move the toggle to the right to enable the policy:</span></span> ![Включенный переключатель](../../media/scc-toggle-on.png)

<span data-ttu-id="359b1-255">Вы не можете отключить политику нежелательной почты для исходящие сообщения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="359b1-255">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="359b1-256">Настройка приоритета настраиваемой политики нежелательной почты для исходящие сообщения</span><span class="sxs-lookup"><span data-stu-id="359b1-256">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="359b1-257">По умолчанию политикам нежелательной почты исходящие сообщения дается приоритет, основанный на порядке их создания (приоритет новых политик ниже, чем у старых политик).</span><span class="sxs-lookup"><span data-stu-id="359b1-257">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="359b1-258">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="359b1-258">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="359b1-259">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="359b1-259">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="359b1-260">Настраиваемые политики нежелательной почты для исходящие сообщений отображаются в порядке их обработки (первая политика имеет значение **приоритета** 0).</span><span class="sxs-lookup"><span data-stu-id="359b1-260">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="359b1-261">Политика фильтрации исходяшей нежелательной почты по умолчанию с именем **"Политика** фильтрации исходяшей нежелательной почты" имеет значение приоритета **"Самый** низкий", и изменить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="359b1-261">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="359b1-262">Чтобы изменить приоритет политики, переместите ее вверх или вниз в списке (в Центре безопасности и соответствия требованиям невозможно напрямую изменить значение свойства **Приоритет**).</span><span class="sxs-lookup"><span data-stu-id="359b1-262">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="359b1-263">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="359b1-263">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="359b1-264">На странице **"Параметры нежелательной** почты" найдите политики, значением которых в столбце **"Тип"** является настраиваемая **политика нежелательной почты для исходящие сообщения.**</span><span class="sxs-lookup"><span data-stu-id="359b1-264">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="359b1-265">Обратите внимание на значения в столбце **Приоритет**:</span><span class="sxs-lookup"><span data-stu-id="359b1-265">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="359b1-266">Настраиваемая политика нежелательной почты исходящие сообщения с наивысшим приоритетом имеет значение значок стрелки ![ вниз ](../../media/ITPro-EAC-DownArrowIcon.png) **0.**</span><span class="sxs-lookup"><span data-stu-id="359b1-266">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="359b1-267">Настраиваемая политика нежелательной почты исходящие сообщения с наименьшим приоритетом имеет значение "Стрелка вверх" n (например, значок "Стрелка ![ ](../../media/ITPro-EAC-UpArrowIcon.png)  ![ ](../../media/ITPro-EAC-UpArrowIcon.png) **вверх" 3).**</span><span class="sxs-lookup"><span data-stu-id="359b1-267">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="359b1-268">Если у вас есть три или более пользовательских политик нежелательной почты для исходящие сообщения, политики между самым высоким и низким приоритетом имеют значения значок стрелки вверх и вниз n (например, значок стрелки вверх ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png)  ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2).**</span><span class="sxs-lookup"><span data-stu-id="359b1-268">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="359b1-269">Щелкните</span><span class="sxs-lookup"><span data-stu-id="359b1-269">Click</span></span> ![Значок "Стрелка вверх"](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="359b1-271">или</span><span class="sxs-lookup"><span data-stu-id="359b1-271">or</span></span> ![Значок "Стрелка вниз"](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="359b1-273">для перемещения настраиваемой политики нежелательной почты исходящие сообщения вверх или вниз в списке приоритетов.</span><span class="sxs-lookup"><span data-stu-id="359b1-273">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="359b1-274">Использование Центра безопасности & соответствия требованиям для удаления политик нежелательной почты для исходящие сообщения</span><span class="sxs-lookup"><span data-stu-id="359b1-274">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="359b1-275">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="359b1-275">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="359b1-276">На странице **"Параметры** нежелательной почты" щелкните значок "Развернуть", чтобы развернуть настраиваемую политику, которую необходимо удалить (столбец "Тип" — это настраиваемая политика нежелательной почты для исходящие ![ ](../../media/scc-expand-icon.png) **сообщения).** </span><span class="sxs-lookup"><span data-stu-id="359b1-276">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="359b1-277">В развернутых сведениях политики щелкните **Удалить политику**.</span><span class="sxs-lookup"><span data-stu-id="359b1-277">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="359b1-278">Нажмите **Да** в появившемся предупреждающем диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="359b1-278">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="359b1-279">Политику по умолчанию удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="359b1-279">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="359b1-280">Использование Exchange Online PowerShell или автономный EOP PowerShell для настройки политик исходящие спама</span><span class="sxs-lookup"><span data-stu-id="359b1-280">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="359b1-281">Как было описано выше, политика нежелательной почты исходящие сообщения состоит из политики фильтрации исходящие нежелательной почты и правила фильтрации исходящие нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="359b1-281">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="359b1-282">В Exchange Online PowerShell или в автономных EOP PowerShell разница между политиками фильтрации исходящие нежелательной почты и правилами фильтрации исходящие нежелательной почты очевидна.</span><span class="sxs-lookup"><span data-stu-id="359b1-282">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="359b1-283">Управление политиками фильтрации исходящей нежелательной почты можно управлять с помощью **\* cmdlets -HostedOutboundSpamFilterPolicy,** а управление правилами фильтрации исходящей нежелательной почты с помощью cmdlets **\* -HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="359b1-283">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="359b1-284">В PowerShell сначала создается политика фильтрации исходящие нежелательной почты, а затем правило фильтрации исходящие нежелательной почты, определяя политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="359b1-284">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="359b1-285">В PowerShell параметры политики фильтрации исходящие нежелательной почты и правила фильтрации исходящие нежелательной почты изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="359b1-285">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="359b1-286">При удалении политики фильтрации исходящие нежелательной почты из PowerShell соответствующее правило фильтрации исходящие нежелательной почты не удаляется автоматически и наоборот.</span><span class="sxs-lookup"><span data-stu-id="359b1-286">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="359b1-287">Создание политик нежелательной почты для исходящие сообщения с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="359b1-287">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="359b1-288">Создание политики нежелательной почты для исходящие сообщений в PowerShell — это двухшаговая процедура:</span><span class="sxs-lookup"><span data-stu-id="359b1-288">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="359b1-289">Создайте политику фильтрации исходящие нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="359b1-289">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="359b1-290">Создайте правило фильтрации исходящие нежелательной почты, которое определяет политику фильтрации исходящие нежелательной почты, к которую оно применяется.</span><span class="sxs-lookup"><span data-stu-id="359b1-290">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="359b1-291">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="359b1-291">**Notes**:</span></span>

- <span data-ttu-id="359b1-292">Вы можете создать новое правило фильтрации исходящие нежелательной почты и назначить ему существующую несвязаную политику фильтрации исходящие нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="359b1-292">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="359b1-293">Правило фильтрации исходящие нежелательной почты не может быть связано с более чем одной политикой фильтрации исходящие нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="359b1-293">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="359b1-294">Вы можете настроить следующие параметры для новых политик фильтрации исходящие нежелательной почты в PowerShell, которые недоступны в Центре безопасности & соответствия требованиям, пока не создайте политику:</span><span class="sxs-lookup"><span data-stu-id="359b1-294">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="359b1-295">Создайте новую политику как отключенную (включена в `$false` **cmdlet New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="359b1-295">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="359b1-296">Установите приоритет политики во время создания _(priority)_ в _\<Number\>_ **cmdlet New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="359b1-296">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="359b1-297">Новая политика фильтрации исходящие нежелательной почты, которую вы создаете в PowerShell, не отображается в Центре безопасности & соответствия требованиям, пока вы не назначите политику правилу фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="359b1-297">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="359b1-298">Шаг 1. Создание политики фильтрации исходящие нежелательной почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="359b1-298">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="359b1-299">Чтобы создать политику фильтрации исходящие спама, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="359b1-299">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="359b1-300">В этом примере создается новая политика фильтрации исходящие нежелательной почты с именем Contoso Executives со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="359b1-300">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="359b1-301">Ограничения на количество получателей ограничены небольшими значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="359b1-301">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="359b1-302">Дополнительные сведения [см. в ограничениях на отправку в параметрах Microsoft 365.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)</span><span class="sxs-lookup"><span data-stu-id="359b1-302">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="359b1-303">После того как достигнуто одно из ограничений, пользователю не будет отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="359b1-303">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="359b1-304">Подробные сведения о синтаксисах и параметрах см. в описании [New-HostedOutboundSpamFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="359b1-304">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="359b1-305">Шаг 2. Создание правила фильтрации исходящие нежелательных сообщений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="359b1-305">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="359b1-306">Чтобы создать правило фильтрации исходящие нежелательные сообщения, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="359b1-306">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="359b1-307">В этом примере создается новое правило фильтрации нежелательной почты для исходящие сообщений с именем Contoso Executives с такими настройками:</span><span class="sxs-lookup"><span data-stu-id="359b1-307">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="359b1-308">Политика фильтрации исходящие нежелательной почты с именем Contoso Executives связана с правилом.</span><span class="sxs-lookup"><span data-stu-id="359b1-308">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="359b1-309">Правило применяется к участникам группы Contoso Executives (Руководители Contoso).</span><span class="sxs-lookup"><span data-stu-id="359b1-309">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="359b1-310">Подробные сведения о синтаксисах и параметрах см. в описании [new-HostedOutboundSpamFilterRule.](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="359b1-310">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="359b1-311">Просмотр политик фильтрации исходящие нежелательных сообщений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="359b1-311">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="359b1-312">Чтобы получить сводный список всех политик фильтрации исходящие нежелательной почты, запустите команду:</span><span class="sxs-lookup"><span data-stu-id="359b1-312">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="359b1-313">Чтобы получить подробные сведения об определенной политике фильтрации исходящие нежелательных сообщений, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="359b1-313">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="359b1-314">В этом примере возвращаются все значения свойств политики фильтрации исходящие нежелательной почты с именем Executives.</span><span class="sxs-lookup"><span data-stu-id="359b1-314">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="359b1-315">Подробные сведения о синтаксисах и параметрах см. в описании [get-HostedOutboundSpamFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="359b1-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="359b1-316">Просмотр правил фильтрации исходящие нежелательных сообщений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="359b1-316">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="359b1-317">Чтобы просмотреть существующие правила фильтрации исходящие спама, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="359b1-317">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="359b1-318">Чтобы получить сводный список всех правил фильтрации исходящие нежелательной почты, запустите команду:</span><span class="sxs-lookup"><span data-stu-id="359b1-318">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="359b1-319">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="359b1-319">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="359b1-320">Чтобы получить подробные сведения об определенном правиле фильтрации исходящие спама, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="359b1-320">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="359b1-321">В этом примере возвращаются все значения свойств правила фильтрации исходящие нежелательной почты с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="359b1-321">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="359b1-322">Подробные сведения о синтаксисах и параметрах см. в описании [get-HostedOutboundSpamFilterRule.](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="359b1-322">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="359b1-323">Использование PowerShell для изменения политик фильтрации исходящие нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="359b1-323">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="359b1-324">При изменении политики фильтрации вредоносных программ в PowerShell доступны те же параметры, что и при создании политики, описанной в шаге [1.1. Использование PowerShell](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) для создания раздела политики фильтрации исходящие нежелательной почты ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="359b1-324">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="359b1-325">Политику фильтрации исходящей нежелательной почты переименовать нельзя (у cmdlet **Set-HostedOutboundSpamFilterPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="359b1-325">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="359b1-326">При переименовании политики защиты от нежелательной почты исходящие сообщения в Центре безопасности & соответствия требованиям переименовывать можно только правило фильтрации исходящие нежелательной _почты._</span><span class="sxs-lookup"><span data-stu-id="359b1-326">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="359b1-327">Чтобы изменить политику фильтрации исходящие спама, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="359b1-327">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="359b1-328">Подробные сведения о синтаксисах и параметрах см. в описании [Set-HostedOutboundSpamFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="359b1-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="359b1-329">Изменение правил фильтрации исходящие нежелательных сообщений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="359b1-329">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="359b1-330">Единственный параметр, который не доступен при изменении правила фильтрации исходящие нежелательной почты в PowerShell, — это параметр _Enabled,_ который позволяет создать отключенное правило.</span><span class="sxs-lookup"><span data-stu-id="359b1-330">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="359b1-331">Чтобы включить или отключить существующие правила фильтрации исходящие спама, см. следующий раздел.</span><span class="sxs-lookup"><span data-stu-id="359b1-331">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="359b1-332">В противном случае при изменении правила фильтрации исходящие нежелательной почты в PowerShell дополнительные параметры недоступны.</span><span class="sxs-lookup"><span data-stu-id="359b1-332">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="359b1-333">Эти же параметры доступны при создании правила, как описано в разделе "Шаг 2. Создание правила фильтрации исходящие нежелательных сообщений с помощью [PowerShell"](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="359b1-333">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="359b1-334">Чтобы изменить правило фильтрации исходящие нежелательные сообщения, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="359b1-334">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="359b1-335">Подробные сведения о синтаксисах и параметрах см. в описании [set-HostedOutboundSpamFilterRule.](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="359b1-335">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="359b1-336">Использование PowerShell для отключения правил фильтрации исходящие нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="359b1-336">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="359b1-337">Включение или отключение правила фильтрации исходящие нежелательной почты в PowerShell включает или отключает всю политику исходящие нежелательной почты (правило фильтрации исходящие нежелательной почты и назначенная политика фильтрации исходящие нежелательной почты).</span><span class="sxs-lookup"><span data-stu-id="359b1-337">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="359b1-338">Вы не можете включить или отключить политику нежелательной почты для исходящие сообщения по умолчанию (она всегда применяется к всем получателям).</span><span class="sxs-lookup"><span data-stu-id="359b1-338">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="359b1-339">Чтобы включить или отключить правило фильтрации исходящие спама в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="359b1-339">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="359b1-340">В этом примере отключается правило фильтрации нежелательной почты исходящие сообщения с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="359b1-340">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="359b1-341">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="359b1-341">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="359b1-342">Подробные сведения о синтаксисах и параметрах см. в описании [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) и [Disable-HostedOutboundSpamFilterRule.](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="359b1-342">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="359b1-343">Настройка приоритета правил фильтрации исходящие нежелательных сообщений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="359b1-343">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="359b1-344">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="359b1-344">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="359b1-345">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="359b1-345">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="359b1-346">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="359b1-346">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="359b1-347">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="359b1-347">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="359b1-348">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="359b1-348">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="359b1-349">Чтобы установить приоритет правила фильтрации исходящие спама в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="359b1-349">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="359b1-p141">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="359b1-p141">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="359b1-352">Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в параметре **New-HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="359b1-352">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="359b1-353">Политика фильтрации нежелательной почты по умолчанию для исходящие сообщения не имеет соответствующего правила фильтрации нежелательной почты и всегда имеет немодифимируемый приоритет **"Самый низкий".**</span><span class="sxs-lookup"><span data-stu-id="359b1-353">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="359b1-354">Удаление политик фильтрации исходящие нежелательных сообщений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="359b1-354">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="359b1-355">При удалении политики фильтрации исходящие нежелательной почты с помощью PowerShell соответствующее правило фильтрации исходящие нежелательной почты не удаляется.</span><span class="sxs-lookup"><span data-stu-id="359b1-355">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="359b1-356">Чтобы удалить политику фильтрации исходящие спама в PowerShell, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="359b1-356">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="359b1-357">В этом примере удаляется политика фильтрации исходящие нежелательной почты с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="359b1-357">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="359b1-358">Подробные сведения о синтаксисах и параметрах см. в описании [remove-HostedOutboundSpamFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="359b1-358">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="359b1-359">Удаление правил фильтрации исходящие нежелательных сообщений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="359b1-359">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="359b1-360">При удалении правила фильтрации исходящие нежелательной почты с помощью PowerShell соответствующая политика фильтрации исходящие нежелательной почты не удаляется.</span><span class="sxs-lookup"><span data-stu-id="359b1-360">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="359b1-361">Чтобы удалить правило фильтрации исходящие нежелательной почты в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="359b1-361">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="359b1-362">В этом примере удаляется правило фильтрации нежелательной почты исходящие сообщения с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="359b1-362">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="359b1-363">Подробные сведения о синтаксисах и параметрах см. в описании [remove-HostedOutboundSpamFilterRule.](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="359b1-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="359b1-364">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="359b1-364">For more information</span></span>

[<span data-ttu-id="359b1-365">Удаление заблокированных пользователей с портала "Пользователи с ограниченным доступом"</span><span class="sxs-lookup"><span data-stu-id="359b1-365">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="359b1-366">Пул доставки сообщений с высоким уровнем опасности</span><span class="sxs-lookup"><span data-stu-id="359b1-366">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="359b1-367">Вопросы и ответы по защите от нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="359b1-367">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="359b1-368">Отчет по автоматически пересылаемым сообщениям</span><span class="sxs-lookup"><span data-stu-id="359b1-368">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
