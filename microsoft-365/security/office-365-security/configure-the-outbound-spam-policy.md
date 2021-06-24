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
description: Администраторы могут научиться просматривать, создавать, изменять и удалять исходящие политики нежелательной почты в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 97b429584371dbe49778163a7f1bbe6f36aea54c
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108419"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="5ceb2-103">Настройка фильтрации исходящие нежелательной почты в EOP</span><span class="sxs-lookup"><span data-stu-id="5ceb2-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5ceb2-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-104">**Applies to**</span></span>
- [<span data-ttu-id="5ceb2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5ceb2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5ceb2-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5ceb2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ceb2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="5ceb2-108">В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без Exchange Online почтовых ящиков исходящие сообщения электронной почты, отправляемые через EOP, автоматически проверяются на наличие нежелательной почты и необычную отправку.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="5ceb2-109">Исходящие нежелательные сообщения от пользователя в организации обычно указывают на скомпрометированную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="5ceb2-110">Подозрительные исходящие сообщения помечены как нежелательной почты (независимо от уровня [](high-risk-delivery-pool-for-outbound-messages.md) доверия к нежелательной почте или SCL) и проходят через пул доставки с высоким уровнем риска, чтобы защитить репутацию службы (то есть сохранить Microsoft 365 исходные серверы электронной почты вне списков блоков IP).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="5ceb2-111">Администраторы автоматически оповещаются о подозрительных исходящие действия электронной почты и блокируют пользователей с помощью политик [оповещения.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="5ceb2-112">EOP использует исходящие политики нежелательной почты в рамках общей защиты организации от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="5ceb2-113">Дополнительные сведения см. в статье [Защита от нежелательной почты](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="5ceb2-114">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику исходящие спама по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="5ceb2-115">Для большей детализации можно также создавать настраиваемые политики исходящие нежелательной почты, применимые к определенным пользователям, группам или доменам в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="5ceb2-116">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="5ceb2-117">Вы можете настроить исходящие политики нежелательной почты на портале Microsoft 365 Microsoft 365 Defender или в PowerShell (Exchange Online PowerShell для Microsoft 365 организаций с почтовыми ящиками в Exchange Online; автономные EOP PowerShell для организаций без Exchange Online почтовых ящиков).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-117">You can configure outbound spam policies in the Microsoft 365 Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="5ceb2-118">Основные элементы политики исходящие нежелательной почты в EOP:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="5ceb2-119">**Политика фильтра исходящие** спама: указывает действия для исходящие решения фильтрации нежелательной почты и параметры уведомлений.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="5ceb2-120">**Правило исходящие фильтры** нежелательной почты: указывает фильтры приоритета и получателя (к кому применяется политика) для политики фильтра исходящие нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="5ceb2-121">Разница между этими двумя элементами не очевидна при управлении исходящие службы нежелательной почты на портале Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="5ceb2-122">При создании политики создается правило фильтра исходящие нежелательной почты и связанная политика фильтра исходящие нежелательной почты одновременно с использованием одного и того же имени для обоих.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="5ceb2-123">При изменении политики параметры, связанные с именем, приоритетом, включенной или отключенной, и фильтры получателей изменяют правило исходящие фильтры нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="5ceb2-124">Все остальные параметры изменяют связанную политику фильтрации исходящие спама.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="5ceb2-125">При удалении политики удаляется правило исходящие фильтры нежелательной почты и связанная политика фильтра исходящие нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="5ceb2-126">В Exchange Online PowerShell или автономном EOP PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="5ceb2-127">Дополнительные сведения см. в разделе Использование Exchange Online PowerShell или автономный [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) для настройки исходящие политики нежелательной почты в этой статье.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="5ceb2-128">Каждая организация имеет встроенную политику исходящие нежелательной почты с именем Default, которая имеет эти свойства:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="5ceb2-129">Политика применяется к всем получателям в организации, несмотря на отсутствие правила исходящие фильтры нежелательной почты (фильтры получателей), связанные с политикой.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="5ceb2-130">Для политики задано специальное значение приоритета **Самый низкий**, которое невозможно изменить (эта политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="5ceb2-131">Все созданные специальные политики всегда имеют более высокий приоритет, чем политика с именем "По умолчанию".</span><span class="sxs-lookup"><span data-stu-id="5ceb2-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="5ceb2-132">Эта политика является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="5ceb2-133">Чтобы повысить эффективность фильтрации исходящие нежелательной почты, можно создать настраиваемые политики исходящие нежелательной почты с более строгими настройками, которые применяются к конкретным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5ceb2-134">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="5ceb2-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5ceb2-135">Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-135">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="5ceb2-136">Чтобы сразу перейти к странице **Параметры защиты от нежелательной почты**, используйте ссылку <https://security.microsoft.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-136">To go directly to the **Anti-spam settings** page, use <https://security.microsoft.com/antispam>.</span></span>

- <span data-ttu-id="5ceb2-137">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="5ceb2-138">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="5ceb2-139">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-139">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="5ceb2-140">Чтобы добавить, изменить и удалить исходящие политики нежелательной почты, необходимо быть членом группы ролей **администратора** организации или **администратора** безопасности.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="5ceb2-141">Для доступа только для чтения к исходящие политики нежелательной почты необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="5ceb2-142">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-142">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="5ceb2-143">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-143">**Notes**:</span></span>

  - <span data-ttu-id="5ceb2-144">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-144">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="5ceb2-145">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-145">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="5ceb2-146">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-146">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="5ceb2-147">Рекомендуемые параметры для политик исходящие нежелательной почты см. в подборке параметров политики фильтрации исходящие нежелательной [почты EOP.](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="5ceb2-148">Политики [](../../compliance/alert-policies.md) оповещения по умолчанию с именем предел отправки электронной  почты превысили, подозрительные шаблоны отправки электронной почты **обнаружены,** и пользователь ограничен от отправки электронной почты уже отправлять уведомления электронной почты членам группы **TenantAdmins** **(Глобальные** администраторы) о необычных исходящие действия электронной почты и заблокированных пользователей из-за исходящие нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="5ceb2-149">Дополнительные сведения см. в [дополнительных сведениях: Проверка параметров оповещений для пользователей с ограниченным доступом.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="5ceb2-150">Мы рекомендуем использовать эти политики оповещения, а не параметры уведомлений в исходящие политики нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies"></a><span data-ttu-id="5ceb2-151">Использование портала Microsoft 365 Defender для создания исходящие политики нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-151">Use the Microsoft 365 Defender portal to create outbound spam policies</span></span>

<span data-ttu-id="5ceb2-152">Создание настраиваемой политики исходящие нежелательной почты на портале Microsoft 365 Defender создает правило фильтра нежелательной почты и связанную политику фильтра нежелательной почты одновременно с использованием одного и того же имени для обоих.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-152">Creating a custom outbound spam policy in the Microsoft 365 Defender portal creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="5ceb2-153">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики борьбы \>  \>  \>  \> **со спамом**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-153">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="5ceb2-154">На странице **Политики борьбы со спамом** нажмите кнопку Создать значок Создать политику, а затем выберите исходящие из ![ ](../../media/m365-cc-sc-create-icon.png)  выпадаемого списка. </span><span class="sxs-lookup"><span data-stu-id="5ceb2-154">On the **Anti-spam policies** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create policy** and then select **Outbound** from the drop down list.</span></span>

3. <span data-ttu-id="5ceb2-155">Откроется мастер политик.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-155">The policy wizard opens.</span></span> <span data-ttu-id="5ceb2-156">На странице **Имя новой политики** настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-156">On the **Name your policy page**, configure these settings:</span></span>
   - <span data-ttu-id="5ceb2-157">**Имя**. Укажите уникальное, описательное имя политики.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-157">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="5ceb2-158">**Описание**. По желанию введите описание политики.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-158">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="5ceb2-159">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-159">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="5ceb2-160">На открывшейся странице **Пользователи, группы и домены** определите внутренних получателей, к которым применяется политика (условия получателей):</span><span class="sxs-lookup"><span data-stu-id="5ceb2-160">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="5ceb2-161">**Пользователи**: указывает один или несколько почтовых ящиков, пользователей почты или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-161">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="5ceb2-162">**Группы**: указывает группы рассылки, группы безопасности с поддержкой почты или группы Microsoft 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-162">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="5ceb2-163">**Домены**: все получатели в указанных [обслуживаемых доменах](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-163">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="5ceb2-164">Щелкните соответствующее поле, начните вводить значение и выберите нужное значение в результатах.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-164">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="5ceb2-165">Повторите эти действия необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-165">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="5ceb2-166">Чтобы удалить существующее значение, нажмите "Удалить".</span><span class="sxs-lookup"><span data-stu-id="5ceb2-166">To remove an existing value, click remove</span></span> ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="5ceb2-168">рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-168">next to the value.</span></span>

   <span data-ttu-id="5ceb2-169">Для пользователей и групп можно использовать большинство идентификаторов (имя, отображаемое имя, псевдоним, адрес электронной почты, имя учетной записи и т. д.), но в результатах будет выведено отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-169">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="5ceb2-170">Для получения списка всех пользователей введите звездочку (\*) без добавлений, чтобы увидеть все доступные значения.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-170">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="5ceb2-171">Указать несколько значений в одном условии можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-171">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="5ceb2-172">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-172">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="5ceb2-173">**Исключить этих пользователей, группы и домены**. Чтобы добавить исключения для внутренних получателей, к которым применяется политика (исключение получателей), выберите этот параметр и настройте исключения.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-173">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="5ceb2-174">Настройки и поведение такие же, как в разделе условий.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-174">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="5ceb2-175">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-175">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="5ceb2-176">На **открываемой странице Параметры** защиты настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-176">On the **Protection settings** page that opens, configure the following settings:</span></span>
   - <span data-ttu-id="5ceb2-177">**Ограничения сообщений.** Параметры в этом разделе настраивают ограничения для исходящие сообщения электронной почты из Exchange Online **почтовых** ящиков:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-177">**Message limits**: The settings in this section configure the limits for outbound email messages from **Exchange Online** mailboxes:</span></span>
     - <span data-ttu-id="5ceb2-178">**Установите ограничение внешнего сообщения:** максимальное число внешних получателей в час.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-178">**Set an external message limit**: The maximum number of external recipients per hour.</span></span>
     - <span data-ttu-id="5ceb2-179">**Установите внутреннее ограничение сообщений:** максимальное число внутренних получателей в час.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-179">**Set an internal message limit**: The maximum number of internal recipients per hour.</span></span>
     - <span data-ttu-id="5ceb2-180">**Установите дневное ограничение сообщений:** максимальное общее число получателей в день.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-180">**Set a daily message limit**: The maximum total number of recipients per day.</span></span>

     <span data-ttu-id="5ceb2-181">Допустимо значение от 0 до 10000.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-181">A valid value is 0 to 10000.</span></span> <span data-ttu-id="5ceb2-182">Значение по умолчанию — 0, что означает, что используются по умолчанию службы.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-182">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="5ceb2-183">Дополнительные сведения см. в [рублях Отправка ограничений.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-183">For more information, see [Sending limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

    <span data-ttu-id="5ceb2-184">Введите значение в поле или используйте стрелки увеличения и уменьшения на поле.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-184">Enter a value in the box, or use the increase/decrease arrows on the box.</span></span>

   - <span data-ttu-id="5ceb2-185">**Ограничение для пользователей,** достигавших предела сообщений: Выберите действие из списка  выпаданий при превышении ограничений в разделе Параметры защиты.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-185">**Restriction placed on users who reach the message limit**: Select an action from the drop down list when any of the limits in the **Protection settings** section are exceeded.</span></span>

     <span data-ttu-id="5ceb2-186">Для всех действий получатели,  указанные в пользовательском сообщении, не  могут отправлять политику оповещений по электронной почте (а в теперь избыточном уведомлении об этом пользователи и группы, если отправитель заблокирован из-за отправки параметров исходящие нежелательной почты позднее на этой странице), получают уведомления электронной почты.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify these users and groups if a sender is blocked due to sending outbound spam** setting later on this page) receive email notifications.</span></span>

     - <span data-ttu-id="5ceb2-187">**Ограничить отправку почты** пользователем до следующего дня. Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-187">**Restrict the user from sending mail until the following day**: This is the default value.</span></span> <span data-ttu-id="5ceb2-188">Уведомления электронной почты отправляются, и пользователь не сможет отправлять больше сообщений до следующего дня, в зависимости от времени UTC.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="5ceb2-189">Администратор не может переопределять этот блок.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-189">There is no way for the admin to override this block.</span></span>
       - <span data-ttu-id="5ceb2-190">Оповещение о действии с именем User, ограниченное **отправкой** электронной почты, оповещает администраторов (по электронной почте и на странице **Оповещений Просмотра).**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>
       - <span data-ttu-id="5ceb2-191">Все получатели, указанные в уведомлении определенных людей, если отправитель заблокирован из-за отправки исходящие параметры нежелательной почты в политике, также уведомлены. </span><span class="sxs-lookup"><span data-stu-id="5ceb2-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>
       - <span data-ttu-id="5ceb2-192">Пользователь не сможет отправлять больше сообщений до следующего дня, в зависимости от времени UTC.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="5ceb2-193">Администратор не может переопределять этот блок.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-193">There is no way for the admin to override this block.</span></span>
     - <span data-ttu-id="5ceb2-194">**Ограничить** отправку почты пользователем. Уведомления электронной почты отправляются, пользователь добавляется пользователям с ограниченным доступом на портале Microsoft 365 Defender, и пользователь не может отправлять электронную почту, пока администратор не удалит их из пользователей с ограниченным  <https://security.microsoft.com/restrictedusers>  доступом. После удаления пользователя из списка администратор снова не будет ограничен в течение этого дня.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-194">**Restrict the user from sending mail**: Email notifications are sent, the user is added to **Restricted users** <https://security.microsoft.com/restrictedusers> in the Microsoft 365 Defender portal, and the user can't send email until they're removed from **Restricted users** by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="5ceb2-195">Инструкции см. в сообщении Удаление пользователя с портала Ограниченные пользователи [после отправки нежелательной почты.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>
     - <span data-ttu-id="5ceb2-196">**Нет действий, только** оповещений: уведомления электронной почты отправляются.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-196">**No action, alert only**: Email notifications are sent.</span></span>

   - <span data-ttu-id="5ceb2-197">**Правила пересылания.** Используйте параметры в этом разделе для управления автоматической пересылке электронной почты Exchange Online почтовых ящиков **внешним** отправителям.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-197">**Forwarding rules**: Use the settings in this section to control automatic email forwarding by **Exchange Online mailboxes** to external senders.</span></span> <span data-ttu-id="5ceb2-198">Дополнительные сведения см. в сообщении [Control automatic external email forwarding in Microsoft 365.](external-email-forwarding.md)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-198">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="5ceb2-199">При отключении автоматической пересылки получатель получает отчет о невывозе (также известном как сообщение NDR или отказов), если внешние отправители отправляют сообщение электронной почты в почтовый ящик, который имеет отправление на месте.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-199">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="5ceb2-200">Если сообщение отправляет внутренний отправитель, а методом пересылания является пересылание почтовых ящиков [(также](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) известное как отправка _SMTP),_ внутренний отправитель получит NDR. </span><span class="sxs-lookup"><span data-stu-id="5ceb2-200">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="5ceb2-201">Внутренний отправитель не получит NDR, если отправка произошла из-за правила входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-201">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

     <span data-ttu-id="5ceb2-202">Выберите одно из следующих действий из выпадающего списка правил **автоматической** переададки:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-202">Select one of the following actions from the **Automatic forwarding rules** drop down list:</span></span>

     - <span data-ttu-id="5ceb2-203">**Автоматическая — система управления:** позволяет фильтрацию исходящие нежелательной почты для управления автоматической внешней отправкой электронной почты.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-203">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="5ceb2-204">Это значение используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-204">This is the default value.</span></span>
     - <span data-ttu-id="5ceb2-205">**О. Автоматическая** внешняя переадружение электронной почты не отключена политикой.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-205">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
     - <span data-ttu-id="5ceb2-206">**Отключено.** Вся автоматическая внешняя переадружение электронной почты отключена политикой.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-206">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

   - <span data-ttu-id="5ceb2-207">**Уведомления.** Используйте параметры в разделе для настройки дополнительных получателей, которые должны получать копии и уведомления о подозрительных исходящие сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-207">**Notifications**: Use the settings in the section to configure additional recipients who should receive copies and notifications of suspicious outbound email messages:</span></span>

     - <span data-ttu-id="5ceb2-208">**Отправьте копию** подозрительного исходящие, которые превышают эти ограничения для этих пользователей и групп. Этот параметр добавляет указанных получателей в поле BCC подозрительных исходящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-208">**Send a copy of suspicious outbound that exceed these limits to these users and groups**: This setting adds the specified recipients to the Bcc field of suspicious outbound messages.</span></span>

       > [!NOTE]
       > <span data-ttu-id="5ceb2-209">Этот параметр работает только в политике исходящие нежелательной почты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-209">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="5ceb2-210">Он не работает в настраиваемой исходящие политики нежелательной почты, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-210">It doesn't work in custom outbound spam policies that you create.</span></span>

       <span data-ttu-id="5ceb2-211">Чтобы включить этот параметр, выберите поле для проверки.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-211">To enable this setting, select the check box.</span></span> <span data-ttu-id="5ceb2-212">В отображаемом поле нажмите кнопку в поле, введите допустимый адрес электронной почты, а затем нажмите кнопку Введите или выберите полное значение, отображаемую ниже окна.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-212">In the box that appears, click in the box, enter a valid email address, and then press Enter or select the complete value that's displayed below the box.</span></span>

       <span data-ttu-id="5ceb2-213">Повторите этот шаг нужное количество раз.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="5ceb2-214">Чтобы удалить существующее значение, нажмите "Удалить".</span><span class="sxs-lookup"><span data-stu-id="5ceb2-214">To remove an existing value, click remove</span></span> ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="5ceb2-216">рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-216">next to the value.</span></span>

   - <span data-ttu-id="5ceb2-217">**Уведомление этих пользователей и групп, если отправитель заблокирован из-за отправки исходячего спама**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-217">**Notify these users and groups if a sender is blocked due to sending outbound spam**</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="5ceb2-218">Этот параметр находится в процессе отмывки от исходящие политики нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-218">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="5ceb2-219">Политика [](../../compliance/alert-policies.md) оповещений по умолчанию с именем **User,** ограниченная отправкой электронной почты, уже отправляет уведомления электронной почты членам группы **TenantAdmins** **(Глобальные** администраторы), когда пользователи заблокированы из-за превышения ограничений в разделе Ограничения **получателей.**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-219">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="5ceb2-220">Мы настоятельно рекомендуем использовать политику оповещения, а не этот параметр в исходящие политики нежелательной почты, чтобы уведомить **администраторов и других пользователей**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-220">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="5ceb2-221">Инструкции см. в [инструкции Verify the alert settings for restricted users.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-221">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

   <span data-ttu-id="5ceb2-222">По завершении нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-222">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="5ceb2-223">На странице **Просмотр** просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-223">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="5ceb2-224">Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-224">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="5ceb2-225">Вы также можете щелкнуть **Назад** или выбрать определенную страницу в мастере.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-225">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="5ceb2-226">Когда закончите, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-226">When you're finished, click **Create**.</span></span>

7. <span data-ttu-id="5ceb2-227">На странице подтверждения, которая откроется, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-227">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-outbound-spam-policies"></a><span data-ttu-id="5ceb2-228">Использование портала Microsoft 365 Defender для просмотра исходящие политики нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-228">Use the Microsoft 365 Defender portal to view outbound spam policies</span></span>

1. <span data-ttu-id="5ceb2-229">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики борьбы \>  \>  \>  \> **со спамом**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-229">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="5ceb2-230">На странице **Политики защиты от спама** найдите одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-230">On the **Anti-spam policies** page, look for one of the following values:</span></span>
   - <span data-ttu-id="5ceb2-231">Значение **Type** — **настраиваемая политика исходящие нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-231">The **Type** value is **Custom outbound spam policy**</span></span>
   - <span data-ttu-id="5ceb2-232">Значение **Name** — политика исходящие от **нежелательной почты (по умолчанию)**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-232">The **Name** value is **Anti-spam outbound policy (Default)**</span></span>

   <span data-ttu-id="5ceb2-233">В списке политик для борьбы с нежелательной почтой можно увидеть следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-233">The following properties are displayed in the list of anti-spam policies:</span></span>

   - <span data-ttu-id="5ceb2-234">**Имя**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-234">**Name**</span></span>
   - <span data-ttu-id="5ceb2-235">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-235">**Status**</span></span>
   - <span data-ttu-id="5ceb2-236">**Приоритет**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-236">**Priority**</span></span>
   - <span data-ttu-id="5ceb2-237">**Тип**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-237">**Type**</span></span>

3. <span data-ttu-id="5ceb2-238">Когда вы выбираете исходящие политики нежелательной почты, нажав на имя, параметры политики отображаются в вылете.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-238">When you select an outbound spam policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-outbound-spam-policies"></a><span data-ttu-id="5ceb2-239">Использование портала Microsoft 365 Defender для изменения исходящие политики нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-239">Use the Microsoft 365 Defender portal to modify outbound spam policies</span></span>

1. <span data-ttu-id="5ceb2-240">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики борьбы \>  \>  \>  \> **со спамом**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-240">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="5ceb2-241">На странице **Политики борьбы со спамом** выберите исходящие политики нежелательной почты из списка, нажав на имя:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-241">On the **Anti-spam policies** page, select an outbound spam policy from the list by clicking on the name:</span></span>
   - <span data-ttu-id="5ceb2-242">Настраиваемая политика, созданная в столбце **Тип,** — **это настраиваемая политика исходящие спама.**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>
   - <span data-ttu-id="5ceb2-243">Политика по умолчанию, названная политикой исходящие от нежелательной почты **(по умолчанию).**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-243">The default policy named **Anti-spam outbound policy (Default)**.</span></span>

3. <span data-ttu-id="5ceb2-244">Параметры политики будут показаны во всплывающем окне. Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-244">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="5ceb2-245">Дополнительные сведения о параметрах см. в предыдущем разделе Использование портала [Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies) для создания исходящие политики нежелательной почты в этой статье.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-245">For more information about the settings, see the previous [Use the Microsoft 365 Defender portal to create outbound spam policies](#use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies) section in this article.</span></span>

   <span data-ttu-id="5ceb2-246">Политика исходящие нежелательной почты по умолчанию недоступна (политика применяется ко всем), и переименовать политику нельзя. </span><span class="sxs-lookup"><span data-stu-id="5ceb2-246">For the default outbound spam policy, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="5ceb2-247">Сведения о включении или отключении политики, настройке приоритета политики или настройке уведомлений пользователей о карантине см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-247">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-custom-outbound-spam-policies"></a><span data-ttu-id="5ceb2-248">Включить или отключить настраиваемые политики исходящие нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-248">Enable or disable custom outbound spam policies</span></span>

<span data-ttu-id="5ceb2-249">Вы не можете отключить политику исходящие нежелательной почты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-249">You can't disable the default outbound spam policy.</span></span>

1. <span data-ttu-id="5ceb2-250">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики борьбы \>  \>  \>  \> **со спамом**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-250">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="5ceb2-251">На странице **Политики борьбы со спамом** выберите политику со значением **Type** of **Custom outbound spam policy** from the list, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-251">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom  outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="5ceb2-252">Появится всплывающее окно со сведениями о политике. В верхней его части вы увидите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-252">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="5ceb2-253">**Политика отключена**. Чтобы включить политику, щелкните значок !["Включить"](../../media/m365-cc-sc-turn-on-off-icon.png) **Включить** .</span><span class="sxs-lookup"><span data-stu-id="5ceb2-253">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="5ceb2-254">**Политика включена**. Чтобы выключить политику, щелкните значок !["Отключить"](../../media/m365-cc-sc-turn-on-off-icon.png) **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-254">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="5ceb2-255">В диалоговом окне подтверждения нажмите кнопку **Включить** или **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-255">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="5ceb2-256">Во всплывающем окне сведений о политике нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-256">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="5ceb2-257">Когда вы вернетесь на главную страницу политики, значение параметра **Состояние** этой политики будет **Включена** или **Выключена**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-257">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="5ceb2-258">Установите приоритет пользовательских политик исходящие нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-258">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="5ceb2-259">По умолчанию политикам исходящие нежелательной почты дается приоритет, основанный на порядке, в который они были созданы (более новые политики имеют более низкий приоритет по сравнению с более старыми политиками).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-259">By default, outbound spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="5ceb2-260">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-260">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="5ceb2-261">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-261">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="5ceb2-262">Чтобы изменить приоритет политики, нажмите кнопку **Увеличить приоритет** или **Уменьшить приоритет** в свойствах политики (вы не можете напрямую изменить числовое значение параметра **Приоритет** на портале Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-262">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="5ceb2-263">Изменение приоритета политики имеет смысл, только если у вас несколько политик.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-263">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="5ceb2-264">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-264">**Notes**:</span></span>

- <span data-ttu-id="5ceb2-265">На портале Microsoft 365 Defender можно изменить приоритет исходящие политики нежелательной почты только после ее создания.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-265">In the Microsoft 365 Defender portal, you can only change the priority of the outbound spam policy after you create it.</span></span> <span data-ttu-id="5ceb2-266">В PowerShell можно переопределить заданный по умолчанию приоритет при создании правила фильтрации нежелательной почты (это может повлиять на приоритеты существующих правил).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-266">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="5ceb2-267">Исходящие политики нежелательной почты обрабатываются в порядке отображения (первая политика имеет значение **Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-267">Outbound spam policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="5ceb2-268">Политика исходящие нежелательной почты по умолчанию имеет приоритетное значение **Самое** низкое, и изменить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-268">The default outbound spam policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="5ceb2-269">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики борьбы \>  \>  \>  \> **со спамом**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-269">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="5ceb2-270">На странице **Политики борьбы со спамом** выберите политику со  значением **Тип** пользовательской политики исходящие нежелательной почты из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-270">On the **Anti-spam policies** page, select a select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="5ceb2-271">Появится всплывающее окно со сведениями о политике. В верхней его части вы увидите одно из следующих значений: **Увеличить приоритет** или **Уменьшить приоритет** в зависимости от текущего значения приоритета и количества настраиваемых политик:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-271">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="5ceb2-272">Политика исходящие нежелательной почты со **значением Priority** **0** имеет только доступный параметр **"Уменьшение приоритета".**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-272">The outbound spam policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="5ceb2-273">Политика исходящие нежелательной  почты с наименьшим значением Приоритет (например, **3)** имеет только доступный параметр **Increase priority.**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-273">The outbound spam policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="5ceb2-274">Если у вас есть три или более исходящие политики нежелательной почты, политики между самыми высокими и самыми низкими значениями приоритетов имеют доступные параметры приоритета **Increase** и **Decrease.**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-274">If you have three or more outbound spam policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="5ceb2-275">Щелкните ![Значок увеличения приоритета](../../media/m365-cc-sc-increase-icon.png) **Увеличить приоритет** или ![Значок уменьшения приоритета](../../media/m365-cc-sc-decrease-icon.png) **Уменьшить приоритет** чтобы изменить значение параметра **Приоритет**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-275">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="5ceb2-276">Закончив, нажмите **Закрыть** во всплывающем окне сведений о политике.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-276">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-outbound-spam-policies"></a><span data-ttu-id="5ceb2-277">Использование портала Microsoft 365 Defender для удаления настраиваемой политики исходящие нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-277">Use the Microsoft 365 Defender portal to remove custom outbound spam policies</span></span>

<span data-ttu-id="5ceb2-278">При использовании портала Microsoft 365 Defender для удаления настраиваемой политики исходящие нежелательной почты правило фильтра нежелательной почты и соответствующая политика фильтра нежелательной почты удаляются.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-278">When you use the Microsoft 365 Defender portal to remove a custom outbound spam policy, the spam filter rule and the corresponding spam filter policy are both deleted.</span></span> <span data-ttu-id="5ceb2-279">Вы не можете удалить политику исходящие нежелательной почты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-279">You can't remove the default outbound spam policy.</span></span>

1. <span data-ttu-id="5ceb2-280">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики борьбы \>  \>  \>  \> **со спамом**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-280">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="5ceb2-281">На странице **Политики борьбы со спамом** выберите политику со значением **Type** of **Custom outbound spam policy** from the list, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-281">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span> <span data-ttu-id="5ceb2-282">В открывшемся всплывающем окне сведений о политике щелкните ![значок "Дополнительные действия"](../../media/m365-cc-sc-more-actions-icon.png) **Дополнительные действия** \> ![значок "Удалить политику"](../../media/m365-cc-sc-delete-icon.png) **Удалить политику**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-282">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="5ceb2-283">В диалоговом окне подтверждения нажмите **Да**.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-283">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="5ceb2-284">Используйте Exchange Online PowerShell или автономный EOP PowerShell для настройки исходящие политики нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-284">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="5ceb2-285">Как описано ранее, политика исходящие спама состоит из политики фильтра исходящие спама и правила исходящие фильтры нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-285">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="5ceb2-286">В Exchange Online PowerShell или автономных EOP PowerShell разница между политиками исходящие фильтры нежелательной почты и исходящие правила фильтра нежелательной почты очевидна.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-286">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="5ceb2-287">Вы управляете политиками фильтрации исходящего нежелательной почты с помощью кодлетов **\* -HostedOutboundSpamFilterPolicy** и управляете правилами фильтра исходящего нежелательной почты с помощью кодлетов **\* -HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-287">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="5ceb2-288">В PowerShell сначала создается политика исходящие фильтры нежелательной почты, а затем создается правило исходящие фильтры нежелательной почты, определяя политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-288">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="5ceb2-289">В PowerShell параметры политики исходящие фильтры нежелательной почты и правила исходящие фильтры нежелательной почты изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-289">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="5ceb2-290">При удалении политики исходящие фильтры нежелательной почты из PowerShell соответствующее правило фильтра исходящие нежелательной почты автоматически не удаляется, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-290">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="5ceb2-291">Использование PowerShell для создания исходящие политики нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-291">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="5ceb2-292">Создание исходящие политики нежелательной почты в PowerShell — это двухшаговая процедура:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-292">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="5ceb2-293">Создание политики исходящие фильтры нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-293">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="5ceb2-294">Создайте правило исходящие фильтры нежелательной почты, которое указывает политику исходящие фильтры нежелательной почты, которая применяется к этому правилу.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-294">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

   <span data-ttu-id="5ceb2-295">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-295">**Notes**:</span></span>

   - <span data-ttu-id="5ceb2-296">Вы можете создать новое правило фильтра исходящие нежелательной почты и назначить ему существующую политику фильтра исходящие нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-296">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="5ceb2-297">Правило исходящие фильтры нежелательной почты не может быть связано с более чем одной политикой фильтрации исходящие нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-297">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>
   - <span data-ttu-id="5ceb2-298">Вы можете настроить следующие параметры для новых политик фильтра от нежелательной почты в PowerShell, недоступных на портале Microsoft 365 Defender до создания политики:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-298">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
     - <span data-ttu-id="5ceb2-299">Создайте новую политику как отключенную _(включена_ `$false` в комлете **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-299">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
     - <span data-ttu-id="5ceb2-300">Задай приоритет политики во время создания _(приоритет)_ в _\<Number\>_ **комлете New-HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-300">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
   - <span data-ttu-id="5ceb2-301">Новая политика фильтра исходящие нежелательной почты, которую вы создаете в PowerShell, не отображается на портале Microsoft 365 Defender, пока не назначите политику правилу исходящие фильтры нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-301">A new outbound spam filter policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an outbound spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="5ceb2-302">Шаг 1. Использование PowerShell для создания политики исходящие фильтры нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-302">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="5ceb2-303">Чтобы создать политику исходящие фильтры нежелательной почты, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-303">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="5ceb2-304">В этом примере создается новая политика фильтра от нежелательной почты с именем Contoso Executives со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-304">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="5ceb2-305">Ограничения скорости получателей ограничены небольшими значениями, которые по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-305">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="5ceb2-306">Дополнительные сведения см. в [рублях Отправка](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)ограничений по Microsoft 365 параметров.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-306">For more information, see [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="5ceb2-307">После того, как один из ограничений будет достигнут, пользователю не будет отправляем сообщения.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-307">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="5ceb2-308">Подробные сведения о синтаксисах и параметрах см. в [обзоре New-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-308">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="5ceb2-309">Шаг 2. Использование PowerShell для создания правила исходящие фильтры нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-309">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="5ceb2-310">Чтобы создать правило фильтра от нежелательной почты, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-310">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="5ceb2-311">В этом примере создается новое правило фильтра от нежелательной почты с именем Contoso Executives с этими настройками:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-311">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="5ceb2-312">Политика исходящие фильтры нежелательной почты с именем Contoso Executives связана с правилом.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-312">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="5ceb2-313">Правило применяется к участникам группы Contoso Executives (Руководители Contoso).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-313">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

<span data-ttu-id="5ceb2-314">Подробные сведения о синтаксисах и параметрах см. в [обзоре New-HostedOutboundSpamFilterRule.](/powershell/module/exchange/new-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-314">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="5ceb2-315">Использование PowerShell для просмотра исходящие политики фильтра нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-315">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="5ceb2-316">Чтобы вернуть сводный список всех исходящие политики фильтрации нежелательной почты, запустите эту команду:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-316">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="5ceb2-317">Чтобы вернуть подробные сведения о конкретной политике фильтра от нежелательной почты, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-317">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="5ceb2-318">В этом примере возвращаются все значения свойств для политики исходящие фильтры нежелательной почты с именем Executives.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-318">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="5ceb2-319">Подробные сведения о синтаксисах и параметрах см. в [ссылке Get-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-319">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="5ceb2-320">Использование PowerShell для просмотра правил исходящие фильтры нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-320">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="5ceb2-321">Чтобы просмотреть существующие правила фильтра от нежелательной почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-321">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="5ceb2-322">Чтобы вернуть сводный список всех правил фильтра от нежелательной почты, запустите эту команду:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-322">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="5ceb2-323">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-323">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="5ceb2-324">Чтобы вернуть подробные сведения о конкретном правиле фильтра от нежелательной почты, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-324">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="5ceb2-325">В этом примере возвращаются все значения свойств для правила фильтра исходящие нежелательной почты с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-325">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="5ceb2-326">Подробные сведения о синтаксисах и параметрах см. в [ссылке Get-HostedOutboundSpamFilterRule.](/powershell/module/exchange/get-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-326">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="5ceb2-327">Использование PowerShell для изменения политик исходящие фильтры нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-327">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="5ceb2-328">Те же параметры доступны при изменении политики фильтрации вредоносных программ в PowerShell, как и при создании политики, описанной в шаге [1. Использование PowerShell](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) для создания исходящие политики фильтрации нежелательной почты в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-328">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="5ceb2-329">Нельзя переименовать политику исходящего фильтра нежелательной почты (в **кодлете Set-HostedOutboundSpamFilterPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="5ceb2-329">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="5ceb2-330">При переименовании политики исходящие нежелательной почты на портале Microsoft 365 Defender вы только переименуете правило исходящие фильтры нежелательной _почты._</span><span class="sxs-lookup"><span data-stu-id="5ceb2-330">When you rename an outbound spam policy in the Microsoft 365 Defender portal, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="5ceb2-331">Чтобы изменить политику исходящие фильтры нежелательной почты, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-331">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="5ceb2-332">Подробные сведения о синтаксисах и параметрах см. в [ссылке Set-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-332">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="5ceb2-333">Использование PowerShell для изменения правил фильтрации исходящие нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-333">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="5ceb2-334">Единственный параметр, недоступный при изменении правила фильтра от нежелательной  почты в PowerShell, — это параметр Включен, который позволяет создать правило отключения.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-334">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="5ceb2-335">Чтобы включить или отключить существующие правила фильтра от нежелательной почты, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-335">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="5ceb2-336">В противном случае при изменении правила фильтра от нежелательной почты в PowerShell дополнительные параметры недоступны.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-336">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="5ceb2-337">Эти же параметры доступны при создании правила, описанного в шаге [2. Использование PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) для создания раздела правила фильтра исходящие нежелательной почты ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-337">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="5ceb2-338">Чтобы изменить правило фильтра от нежелательной почты, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-338">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="5ceb2-339">Подробные сведения о синтаксисах и параметрах см. в [ссылке Set-HostedOutboundSpamFilterRule.](/powershell/module/exchange/set-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-339">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="5ceb2-340">Использование PowerShell, чтобы включить или отключить правила фильтрации исходящие спама</span><span class="sxs-lookup"><span data-stu-id="5ceb2-340">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="5ceb2-341">Включение или отключение правила фильтра исходящие нежелательной почты в PowerShell включает или отключает всю политику исходящие нежелательной почты (правило исходящие фильтры нежелательной почты и назначенная политика фильтра исходящие нежелательной почты).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-341">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="5ceb2-342">Вы не можете включить или отключить политику исходящие нежелательной почты по умолчанию (она всегда применяется к всем получателям).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-342">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="5ceb2-343">Чтобы включить или отключить правило фильтра исходящие нежелательной почты в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-343">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="5ceb2-344">В этом примере отключает правило фильтра исходящие нежелательной почты с именем Отдел маркетинга.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-344">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="5ceb2-345">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-345">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="5ceb2-346">Подробные сведения о синтаксисах и параметрах см. в сведениях [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) и [Disable-HostedOutboundSpamFilterRule.](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-346">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="5ceb2-347">Использование PowerShell для набора приоритета правил исходящие фильтры нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-347">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="5ceb2-p142">Максимальный приоритет, который можно задать для правила, — 0. Минимальное значение зависит от количества правил. Например, если у вас есть пять правил, вы можете использовать значения 0-4. Изменение приоритета существующего правила оказывает каскадное влияние на другие правила. Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-p142">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="5ceb2-353">Чтобы установить приоритет правила фильтра исходящие нежелательной почты в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-353">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="5ceb2-p143">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="5ceb2-p143">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="5ceb2-356">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-356">**Notes**:</span></span>

- <span data-ttu-id="5ceb2-357">Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в **комлете New-HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-357">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
- <span data-ttu-id="5ceb2-358">Политика фильтра фильтра нежелательной почты по умолчанию по умолчанию не имеет соответствующего правила фильтра нежелательной почты, и всегда имеет неограничимое значение приоритета **Самое низкое.**</span><span class="sxs-lookup"><span data-stu-id="5ceb2-358">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="5ceb2-359">Использование PowerShell для удаления исходящие политики фильтра нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-359">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="5ceb2-360">При удалении политики исходящие фильтры нежелательной почты с помощью PowerShell соответствующее правило фильтра исходящие нежелательной почты не удаляется.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-360">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="5ceb2-361">Чтобы удалить политику исходящие фильтры нежелательной почты в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-361">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="5ceb2-362">В этом примере удаляется политика исходящие фильтры нежелательной почты с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-362">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="5ceb2-363">Подробные сведения о синтаксисах и параметрах см. в [ссылке Remove-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="5ceb2-364">Использование PowerShell для удаления исходящие правила фильтрации нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-364">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="5ceb2-365">При удалении правила фильтра от нежелательной почты с помощью PowerShell соответствующая политика исходящие фильтры нежелательной почты не удаляется.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-365">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="5ceb2-366">Чтобы удалить правило фильтра исходящие нежелательной почты в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5ceb2-366">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="5ceb2-367">В этом примере удаляется правило фильтра исходящие нежелательной почты с именем Отдел маркетинга.</span><span class="sxs-lookup"><span data-stu-id="5ceb2-367">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="5ceb2-368">Подробные сведения о синтаксисах и параметрах см. в [ссылке Remove-HostedOutboundSpamFilterRule.](/powershell/module/exchange/remove-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-368">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="5ceb2-369">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="5ceb2-369">For more information</span></span>

[<span data-ttu-id="5ceb2-370">Удаление заблокированных пользователей с портала Ограниченные пользователи</span><span class="sxs-lookup"><span data-stu-id="5ceb2-370">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="5ceb2-371">Пул доставки сообщений с высоким уровнем опасности</span><span class="sxs-lookup"><span data-stu-id="5ceb2-371">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="5ceb2-372">Вопросы и ответы по защите от нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="5ceb2-372">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.yml)

[<span data-ttu-id="5ceb2-373">Отчет по автоматически пересылаемым сообщениям</span><span class="sxs-lookup"><span data-stu-id="5ceb2-373">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
