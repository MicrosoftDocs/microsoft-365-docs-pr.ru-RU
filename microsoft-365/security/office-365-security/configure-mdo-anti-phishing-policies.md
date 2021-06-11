---
title: Настройка политик защиты от фишинга в Microsoft Defender для Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Администраторы могут научиться создавать, изменять и удалять расширенные политики защиты от фишинга, доступные в организациях с Microsoft Defender для Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8337e25fb6328a2492e2e033e80efcdee8352f6f
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878932"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ece1a-103">Настройка политик защиты от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="ece1a-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ece1a-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="ece1a-104">**Applies to**</span></span>
- [<span data-ttu-id="ece1a-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="ece1a-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ece1a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ece1a-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ece1a-107">Политики защиты от фишинга в [Microsoft Defender для](defender-for-office-365.md) Office 365 могут защитить организацию от вредоносных фишинговых атак на основе обезличения и других типов фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="ece1a-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="ece1a-108">Дополнительные сведения о различиях между политиками защиты от фишинга в Exchange Online Protection (EOP) и антифишинговыми политиками в Microsoft Defender для Office 365 см. в этой [записи.](anti-phishing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="ece1a-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="ece1a-109">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ece1a-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="ece1a-110">Для большей детализации можно также создать настраиваемые политики защиты от фишинга, применимые к определенным пользователям, группам или доменам в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ece1a-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="ece1a-111">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="ece1a-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="ece1a-112">Вы можете настроить политики защиты от фишинга в Defender для Office 365 на портале Microsoft 365 Defender или в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ece1a-112">You can configure anti-phishing policies in Defender for Office 365 in the Microsoft 365 Defender portal or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="ece1a-113">Сведения о настройке более ограниченных в антифишинговых политиках, доступных в Exchange Online Protection (то есть организациях без Defender для Office 365), см. в [веб-сайте Configure anti-phishing policies in EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="ece1a-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection (that is, organizations without Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="ece1a-114">Основные элементы политики защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="ece1a-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="ece1a-115">**Политика защиты от фишинга:** указывает средства защиты от фишинга, чтобы включить или отключить, а также действия по применении параметров.</span><span class="sxs-lookup"><span data-stu-id="ece1a-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="ece1a-116">**Правило защиты от фишинга:** указывает фильтры приоритета и получателей (к кому применяется политика) для политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="ece1a-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="ece1a-117">Разница между этими двумя элементами не очевидна при управлении политиками защиты от фишинга на портале Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="ece1a-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="ece1a-118">При создании политики создается правило защиты от фишинга и связанная с ним политика защиты от фишинга, используя одно и то же имя для обоих.</span><span class="sxs-lookup"><span data-stu-id="ece1a-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="ece1a-119">При изменении политики параметры, связанные с именем, приоритетом, включенной или отключенной, а также фильтры получателей изменяют правило защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="ece1a-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="ece1a-120">Все остальные параметры изменяют связанную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="ece1a-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="ece1a-121">При удалении политики удаляется правило защиты от фишинга и связанная с ним политика защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="ece1a-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="ece1a-122">В Exchange Online PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="ece1a-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="ece1a-123">Дополнительные сведения см. в [разделе Использование Exchange Online PowerShell для](#use-exchange-online-powershell-to-configure-anti-phishing-policies) настройки политики защиты от фишинга в этой статье.</span><span class="sxs-lookup"><span data-stu-id="ece1a-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="ece1a-124">Каждая организация Defender для Office 365 имеет встроенную политику защиты от фишинга с именем Office365 AntiPhish Default, которая имеет эти свойства:</span><span class="sxs-lookup"><span data-stu-id="ece1a-124">Every Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="ece1a-125">Политика применяется к всем получателям в организации, несмотря на отсутствие правила защиты от фишинга (фильтры получателей), связанного с политикой.</span><span class="sxs-lookup"><span data-stu-id="ece1a-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="ece1a-126">Для политики задано специальное значение приоритета **Самый низкий**, которое невозможно изменить (эта политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="ece1a-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="ece1a-127">Все созданные специальные политики всегда имеют более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="ece1a-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="ece1a-128">Эта политика является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.</span><span class="sxs-lookup"><span data-stu-id="ece1a-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="ece1a-129">Чтобы повысить эффективность защиты от фишинга в Defender для Office 365, можно создать настраиваемые политики защиты от фишинга с более строгими настройками, которые применяются к конкретным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="ece1a-129">To increase the effectiveness of anti-phishing protection in Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ece1a-130">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="ece1a-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ece1a-131">Вы открываете портал Microsoft 365 Defender по <https://security.microsoft.com> ссылке .</span><span class="sxs-lookup"><span data-stu-id="ece1a-131">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="ece1a-132">Чтобы перейти непосредственно на страницу **anti-phishing,** используйте <https://security.microsoft.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="ece1a-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="ece1a-133">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ece1a-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="ece1a-134">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="ece1a-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ece1a-135">Чтобы добавить, изменить и удалить политики защиты от фишинга, необходимо  быть членом групп ролей администратора организации или **администратора** безопасности.</span><span class="sxs-lookup"><span data-stu-id="ece1a-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="ece1a-136">Для доступа только для чтения к политикам защиты от фишинга необходимо быть членом групп ролей **Global Reader** или **Security Reader.** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ece1a-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="ece1a-137">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="ece1a-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="ece1a-138">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-138">**Notes**:</span></span>

  - <span data-ttu-id="ece1a-139">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ece1a-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ece1a-140">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ece1a-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="ece1a-141">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="ece1a-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="ece1a-142">Рекомендуемые параметры для политик защиты от фишинга в Defender для Office 365 см. в Office 365 правила защиты от [фишинга.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="ece1a-142">For our recommended settings for anti-phishing policies in Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="ece1a-143">Разрешить до 30 минут для новой или обновленной политики, которая будет применяться.</span><span class="sxs-lookup"><span data-stu-id="ece1a-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="ece1a-144">Сведения о том, где политики защиты от фишинга применяются в конвейере фильтрации, см. в рублях [Order и precedence of email protection.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="ece1a-144">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a><span data-ttu-id="ece1a-145">Используйте портал Microsoft 365 Defender для создания политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-145">Use the Microsoft 365 Defender portal to create anti-phishing policies</span></span>

<span data-ttu-id="ece1a-146">Создание настраиваемой политики защиты от фишинга на портале Microsoft 365 Defender создает правило защиты от фишинга и связанную с ним политику одновременно с использованием одного и того же имени для обоих.</span><span class="sxs-lookup"><span data-stu-id="ece1a-146">Creating a custom anti-phishing policy in the Microsoft 365 Defender portal creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="ece1a-147">На портале Microsoft 365 Defender перейдите в раздел Политики **совместной** & электронной почты & политики угрозы \>  \>  \>  \> правил.</span><span class="sxs-lookup"><span data-stu-id="ece1a-147">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ece1a-148">На странице **Anti-phishing** нажмите кнопку ![ Создать значок ](../../media/m365-cc-sc-create-icon.png) **Создать**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-148">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="ece1a-149">Откроется мастер политик.</span><span class="sxs-lookup"><span data-stu-id="ece1a-149">The policy wizard opens.</span></span> <span data-ttu-id="ece1a-150">На странице **Имя политики** настройте эти параметры:</span><span class="sxs-lookup"><span data-stu-id="ece1a-150">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="ece1a-151">**Имя**. Укажите уникальное, описательное имя политики.</span><span class="sxs-lookup"><span data-stu-id="ece1a-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="ece1a-152">**Описание**. По желанию введите описание политики.</span><span class="sxs-lookup"><span data-stu-id="ece1a-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="ece1a-153">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="ece1a-154">На открывшейся странице **Пользователи, группы и домены** определите внутренних получателей, к которым применяется политика (условия получателей):</span><span class="sxs-lookup"><span data-stu-id="ece1a-154">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="ece1a-155">**Пользователи**: указывает один или несколько почтовых ящиков, пользователей почты или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="ece1a-155">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="ece1a-156">**Группы**: указывает группы рассылки, группы безопасности с поддержкой почты или группы Microsoft 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ece1a-156">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="ece1a-157">**Домены**: все получатели в указанных [обслуживаемых доменах](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ece1a-157">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="ece1a-158">Щелкните соответствующее поле, начните вводить значение и выберите нужное значение в результатах.</span><span class="sxs-lookup"><span data-stu-id="ece1a-158">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="ece1a-159">Повторите эти действия необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="ece1a-159">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="ece1a-160">Чтобы удалить существующее значение, нажмите "Удалить".</span><span class="sxs-lookup"><span data-stu-id="ece1a-160">To remove an existing value, click remove</span></span> ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="ece1a-162">рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="ece1a-162">next to the value.</span></span>

   <span data-ttu-id="ece1a-163">Для пользователей и групп можно использовать большинство идентификаторов (имя, отображаемое имя, псевдоним, адрес электронной почты, имя учетной записи и т. д.), но в результатах будет выведено отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="ece1a-163">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="ece1a-164">Для получения списка всех пользователей введите звездочку (\*) без добавлений, чтобы увидеть все доступные значения.</span><span class="sxs-lookup"><span data-stu-id="ece1a-164">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="ece1a-165">Указать несколько значений в одном условии можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="ece1a-165">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="ece1a-166">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="ece1a-166">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="ece1a-167">**Исключить этих пользователей, группы и домены**. Чтобы добавить исключения для внутренних получателей, к которым применяется политика (исключение получателей), выберите этот параметр и настройте исключения.</span><span class="sxs-lookup"><span data-stu-id="ece1a-167">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="ece1a-168">Настройки и поведение такие же, как в разделе условий.</span><span class="sxs-lookup"><span data-stu-id="ece1a-168">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="ece1a-169">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-169">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="ece1a-170">На странице **защиты &** фишинга настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ece1a-170">On the **Phishing threshold & protection** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ece1a-171">**Порог фишинговой электронной** почты: используйте ползунок, чтобы выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="ece1a-171">**Phishing email threshold**: Use the slider to select one of the following values:</span></span>
     - <span data-ttu-id="ece1a-172">**1 . Стандартный** (это значение по умолчанию.)</span><span class="sxs-lookup"><span data-stu-id="ece1a-172">**1 - Standard** (This is the default value.)</span></span>
     - <span data-ttu-id="ece1a-173">**2 . Агрессивная**</span><span class="sxs-lookup"><span data-stu-id="ece1a-173">**2 - Aggressive**</span></span>
     - <span data-ttu-id="ece1a-174">**3 . Более агрессивная**</span><span class="sxs-lookup"><span data-stu-id="ece1a-174">**3 - More aggressive**</span></span>
     - <span data-ttu-id="ece1a-175">**4 . Наиболее агрессивный**</span><span class="sxs-lookup"><span data-stu-id="ece1a-175">**4 - Most aggressive**</span></span>

     <span data-ttu-id="ece1a-176">Дополнительные сведения см. в расширенных пороговых значениях фишинга в политиках по борьбе с фишингом в [Microsoft Defender для](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)Office 365.</span><span class="sxs-lookup"><span data-stu-id="ece1a-176">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="ece1a-177">**Обезличение.** Эти параметры являются условием для политики, определяющей конкретных отправителей, которые необходимо искать (по отдельности или по домену) в Адресе входящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="ece1a-177">**Impersonation**: These settings are a condition for the policy that identifies specific senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="ece1a-178">Дополнительные сведения см. в сведениях о параметрах [Impersonation в](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)политиках защиты от фишинга в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="ece1a-178">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="ece1a-179">В каждой политике защиты от фишинга можно указать не более 60 защищенных пользователей (адреса электронной почты отправитель).</span><span class="sxs-lookup"><span data-stu-id="ece1a-179">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="ece1a-180">В нескольких политиках нельзя указать одного и того же защищенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="ece1a-180">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="ece1a-181">Защита от обезличения пользователя не работает, если отправитель и получатель ранее связывались по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="ece1a-181">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="ece1a-182">Если отправитель и получатель никогда не связывались по электронной почте, сообщение будет определено как попытка обезличения.</span><span class="sxs-lookup"><span data-stu-id="ece1a-182">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

     - <span data-ttu-id="ece1a-183">**Включить пользователей для защиты:** значение по умолчанию отключено (не выбрано).</span><span class="sxs-lookup"><span data-stu-id="ece1a-183">**Enable users to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="ece1a-184">Чтобы включить его, выберите шажок, а затем нажмите кнопку **Управление (nn) отправитель(ы)** ссылку, которая появляется.</span><span class="sxs-lookup"><span data-stu-id="ece1a-184">To turn it on, select the check box, and then click the **Manage (nn) sender(s)** link that appears.</span></span>

       <span data-ttu-id="ece1a-185">В поле **Управление отправительами для вылетов** защиты от обезличения, которые появляются, сделайте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ece1a-185">In the **Manage senders for impersonation protection** flyout that appears, do the following steps:</span></span>

       - <span data-ttu-id="ece1a-186">**Внутренние отправители:** ![ Щелкните Добавить внутренний значок ](../../media/m365-cc-sc-add-internal-icon.png) **Выберите внутренний**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-186">**Internal senders**: Click ![Add internal icon](../../media/m365-cc-sc-add-internal-icon.png) **Select internal**.</span></span> <span data-ttu-id="ece1a-187">В **появится флажок Добавить** внутренние отправители, щелкните в поле и выберите внутреннего пользователя из списка.</span><span class="sxs-lookup"><span data-stu-id="ece1a-187">In the **Add internal senders** flyout that appears, click in the box and select an internal user from the list.</span></span> <span data-ttu-id="ece1a-188">Список можно фильтровать, введя пользователя, а затем выбрав его из результатов.</span><span class="sxs-lookup"><span data-stu-id="ece1a-188">You can filter the list by typing the user, and then selecting the user from the results.</span></span> <span data-ttu-id="ece1a-189">Вы можете использовать большинство идентификаторов (имя, имя отображения, псевдоним, адрес электронной почты, имя учетной записи и т.д.), но соответствующее имя отображения отображается в результатах.</span><span class="sxs-lookup"><span data-stu-id="ece1a-189">You can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span>

         <span data-ttu-id="ece1a-190">Повторите этот шаг нужное количество раз.</span><span class="sxs-lookup"><span data-stu-id="ece1a-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="ece1a-191">Чтобы удалить существующее значение, нажмите "Удалить".</span><span class="sxs-lookup"><span data-stu-id="ece1a-191">To remove an existing value, click remove</span></span> ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="ece1a-193">рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="ece1a-193">next to the value.</span></span>

         <span data-ttu-id="ece1a-194">По завершению щелкните **Добавить**</span><span class="sxs-lookup"><span data-stu-id="ece1a-194">When you're finished, click **Add**</span></span>

       - <span data-ttu-id="ece1a-195">**Внешние отправители:** ![ Щелкните Добавить внешний значок ](../../media/m365-cc-sc-create-icon.png) **Выберите внешний**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-195">**External senders**: Click ![Add external icon](../../media/m365-cc-sc-create-icon.png) **Select external**.</span></span> <span data-ttu-id="ece1a-196">В **вылете** Добавить внешние отправители, который  появляется, введите имя отображения в поле Добавить имя и адрес электронной почты в поле **Добавить vaild** электронной почты, а затем нажмите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-196">In the **Add external senders** flyout that appears, enter a display name in the **Add a name** box and an email address in the **Add a vaild email** box, and then click **Add**.</span></span>

         <span data-ttu-id="ece1a-197">Повторите этот шаг нужное количество раз.</span><span class="sxs-lookup"><span data-stu-id="ece1a-197">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="ece1a-198">Чтобы удалить существующее значение, нажмите "Удалить".</span><span class="sxs-lookup"><span data-stu-id="ece1a-198">To remove an existing value, click remove</span></span> ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="ece1a-200">рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="ece1a-200">next to the value.</span></span>

         <span data-ttu-id="ece1a-201">По завершению щелкните **Добавить**</span><span class="sxs-lookup"><span data-stu-id="ece1a-201">When you're finished, click **Add**</span></span>

       <span data-ttu-id="ece1a-202">Возвращаясь к **вылету "Управление** отправительами" для вылетов, вы можете удалить записи, выбрав одну или несколько записей из списка.</span><span class="sxs-lookup"><span data-stu-id="ece1a-202">Back on the **Manage senders for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="ece1a-203">Вы можете искать записи с помощью окна ![ поиска ](../../media/m365-cc-sc-create-icon.png) **значков** поиска.</span><span class="sxs-lookup"><span data-stu-id="ece1a-203">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="ece1a-204">После выбора хотя бы одной записи появится значок ![ Remove selected users ](../../media/m365-cc-sc-remove-selected-users-icon.png) Remove selected users icon Remove **selected users,** который можно использовать для удаления выбранных записей.</span><span class="sxs-lookup"><span data-stu-id="ece1a-204">After you select at least one entry, the ![Remove selected users icon](../../media/m365-cc-sc-remove-selected-users-icon.png) **Remove selected users** icon appears, which you can use to remove the selected entries.</span></span>

       <span data-ttu-id="ece1a-205">По завершении нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-205">When you're finished, click **Done**.</span></span>

     - <span data-ttu-id="ece1a-206">**Включить домены для защиты:** значение по умолчанию отключено (не выбрано).</span><span class="sxs-lookup"><span data-stu-id="ece1a-206">**Enable domains to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="ece1a-207">Чтобы включить его, выберите шажок, а затем настройте один или оба следующих параметра, которые отображаются:</span><span class="sxs-lookup"><span data-stu-id="ece1a-207">To turn it on, select the check box, and then configure one or both of the following settings that appear:</span></span>
       - <span data-ttu-id="ece1a-208">**Включи домены, которые у меня** есть: Чтобы включить этот параметр, выберите поле.</span><span class="sxs-lookup"><span data-stu-id="ece1a-208">**Include the domains I own**: To turn this setting on, select the check box.</span></span> <span data-ttu-id="ece1a-209">Чтобы просмотреть домены, которые у вас есть, **щелкните Просмотреть мои домены**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-209">To view the domains that you own, click **View my domains**.</span></span>
       - <span data-ttu-id="ece1a-210">**Включайте настраиваемые** домены. Чтобы включить этот параметр, выберите поле и нажмите ссылку Управление пользовательским доменом **(nn).**</span><span class="sxs-lookup"><span data-stu-id="ece1a-210">**Include custom domains**: To turn this setting on, select the check box, and then click the **Manage (nn) custom domain(s)** link that appears.</span></span> <span data-ttu-id="ece1a-211">В поле **Управление пользовательскими доменами для вылетов** защиты от обезличения, которые появляются, нажмите кнопку Добавить значок доменов ![ Добавить ](../../media/m365-cc-sc-create-icon.png) **домены**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-211">In the **Manage custom domains for impersonation protection** flyout that appears, click ![Add domains icon](../../media/m365-cc-sc-create-icon.png) **Add domains**.</span></span>

         <span data-ttu-id="ece1a-212">В **вылете Добавить** пользовательские домены, который появляется, нажмите в поле **Домен,** введите значение, а затем нажмите введите или выберите значение, которое отображается ниже окна.</span><span class="sxs-lookup"><span data-stu-id="ece1a-212">In the **Add custom domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="ece1a-213">Повторите этот шаг нужное количество раз.</span><span class="sxs-lookup"><span data-stu-id="ece1a-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="ece1a-214">Чтобы удалить существующее значение, нажмите кнопку ![Удалить](../../media/m365-cc-sc-remove-selection-icon.png) рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="ece1a-214">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

         <span data-ttu-id="ece1a-215">По завершению щелкните **Добавить домены**</span><span class="sxs-lookup"><span data-stu-id="ece1a-215">When you're finished, click **Add domains**</span></span>

         > [!NOTE]
         > <span data-ttu-id="ece1a-216">Во всех политиках защиты от фишинга можно использовать не более 50 доменов.</span><span class="sxs-lookup"><span data-stu-id="ece1a-216">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

       <span data-ttu-id="ece1a-217">Возвращаясь к **настраиваемой** области управления пользовательскими доменами для вылетов для обезличения, вы можете удалить записи, выбрав одну или несколько записей из списка.</span><span class="sxs-lookup"><span data-stu-id="ece1a-217">Back on the **Manage custom domains for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="ece1a-218">Вы можете искать записи с помощью окна ![ поиска ](../../media/m365-cc-sc-create-icon.png) **значков** поиска.</span><span class="sxs-lookup"><span data-stu-id="ece1a-218">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="ece1a-219">После выбора хотя бы одной записи появится значок Delete domains Delete, который можно использовать для удаления ![ ](../../media/m365-cc-sc-delete-icon.png)  выбранных записей.</span><span class="sxs-lookup"><span data-stu-id="ece1a-219">After you select at least one entry, the ![Delete domains icon](../../media/m365-cc-sc-delete-icon.png) **Delete** icon appears, which you can use to remove the selected entries.</span></span>

   - <span data-ttu-id="ece1a-220">**Добавление надежных** отправителей и доменов: : Укажите исключения для защиты от обезличения для политики, нажав на Управление **(nn) доверенным отправителям (ы) и доменом (s)**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-220">**Add trusted senders and domains**: : Specify impersonation protection exceptions for the policy by clicking on **Manage (nn) trusted sender(s) and domain(s)**.</span></span> <span data-ttu-id="ece1a-221">В поле **Управление настраиваемых доменов для вылетов** защиты от обезличения, которые появляются, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ece1a-221">In the **Manage custom domains for impersonation protection** flyout that appears, configure the following settings:</span></span>
      - <span data-ttu-id="ece1a-222">**Отправители.** Убедитесь, **что** выбрана вкладка Отправитель, и ![ щелкните значок Добавить ](../../media/m365-cc-sc-create-icon.png) отправителей.</span><span class="sxs-lookup"><span data-stu-id="ece1a-222">**Senders**: Verify the **Sender** tab is selected and click ![Add senders icon](../../media/m365-cc-sc-create-icon.png).</span></span> <span data-ttu-id="ece1a-223">В **вылете Добавлены** надежные отправители, которые появляются, введите адрес электронной почты в поле и нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-223">In the **Add trusted senders** flyout that appears, enter an email address in the box and then click **Add**.</span></span> <span data-ttu-id="ece1a-224">Повторите этот шаг нужное количество раз.</span><span class="sxs-lookup"><span data-stu-id="ece1a-224">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="ece1a-225">Чтобы удалить существующую запись, нажмите ![ кнопку Удалить значок Удалить ](../../media/m365-cc-sc-close-icon.png) для записи.</span><span class="sxs-lookup"><span data-stu-id="ece1a-225">To remove an existing entry, click ![Delete icon](../../media/m365-cc-sc-close-icon.png) for the entry.</span></span>

        <span data-ttu-id="ece1a-226">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-226">When you're finished, click **Add**.</span></span>

      - <span data-ttu-id="ece1a-227">**Домены.** Выберите **вкладку Домен** и нажмите ![ кнопку Добавить значок доменов ](../../media/m365-cc-sc-create-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="ece1a-227">**Domains**: Select the **Domain** tab and click ![Add domains icon](../../media/m365-cc-sc-create-icon.png).</span></span>
  
        <span data-ttu-id="ece1a-228">В **вылете Добавить** доверенные домены, который появляется, нажмите в поле **Домен,** введите значение, а затем нажмите введите или выберите значение, которое отображается ниже окна.</span><span class="sxs-lookup"><span data-stu-id="ece1a-228">In the **Add trusted domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="ece1a-229">Повторите этот шаг нужное количество раз.</span><span class="sxs-lookup"><span data-stu-id="ece1a-229">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="ece1a-230">Чтобы удалить существующее значение, нажмите кнопку ![Удалить](../../media/m365-cc-sc-remove-selection-icon.png) рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="ece1a-230">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

        <span data-ttu-id="ece1a-231">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-231">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="ece1a-232">Возвращаясь к **настраиваемой** области управления пользовательскими доменами для вылетов, вы можете удалить записи из вкладок **Отправитель** и Домен, выбрав одну или несколько записей из списка. </span><span class="sxs-lookup"><span data-stu-id="ece1a-232">Back on the **Manage custom domains for impersonation** flyout, you can remove entries from the **Sender** and **Domain** tabs by selecting one or more entries from the list.</span></span> <span data-ttu-id="ece1a-233">Вы можете искать записи с помощью окна ![ поиска ](../../media/m365-cc-sc-create-icon.png) **значков** поиска.</span><span class="sxs-lookup"><span data-stu-id="ece1a-233">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

     <span data-ttu-id="ece1a-234">После выбора хотя бы одной записи появится значок **Delete,** который можно использовать для удаления выбранных записей.</span><span class="sxs-lookup"><span data-stu-id="ece1a-234">After you select at least one entry, the **Delete** icon appears, which you can use to remove the selected entries.</span></span>

     <span data-ttu-id="ece1a-235">По завершении нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-235">When you're finished, click **Done**.</span></span>

   - <span data-ttu-id="ece1a-236">**Включить разведданные почтовых ящиков:** значение по умолчанию включается (выбрано), и мы рекомендуем оставить его.</span><span class="sxs-lookup"><span data-stu-id="ece1a-236">**Enable mailbox intelligence**: The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="ece1a-237">Чтобы отключить его, зачистите контрольный ящик.</span><span class="sxs-lookup"><span data-stu-id="ece1a-237">To turn it off, clear the check box.</span></span>

     - <span data-ttu-id="ece1a-238">**Включить защиту от обезличения** на основе разведданных. Этот параметр доступен только в том случае, если включается (выбрана) разведка почтовых ящиков. </span><span class="sxs-lookup"><span data-stu-id="ece1a-238">**Enable intelligence based impersonation protection**: This setting is available only if **Enable mailbox intelligence** is on (selected).</span></span> <span data-ttu-id="ece1a-239">Этот параметр позволяет аналитике почтовых ящиков принимать меры в отношении сообщений, которые определены как попытки обезличения.</span><span class="sxs-lookup"><span data-stu-id="ece1a-239">This setting allows mailbox intelligence to take action on messages that are identified as impersonation attempts.</span></span> <span data-ttu-id="ece1a-240">Вы указываете действие, необходимое для разведки почтовых ящиков **If,** обнаруживаемую вами на следующей странице.</span><span class="sxs-lookup"><span data-stu-id="ece1a-240">You specify the action to take in the **If mailbox intelligence detects an impersonated user** setting on the next page.</span></span>

       <span data-ttu-id="ece1a-241">Рекомендуется включить этот параметр, выбрав поле.</span><span class="sxs-lookup"><span data-stu-id="ece1a-241">We recommend that you turn this setting on by selecting the check box.</span></span> <span data-ttu-id="ece1a-242">Чтобы отключить этот параметр, зачистите контрольный ящик.</span><span class="sxs-lookup"><span data-stu-id="ece1a-242">To turn this setting off, clear the check box.</span></span>

   - <span data-ttu-id="ece1a-243">**Spoof**. В этом разделе используйте поле **Включить** подмену сведении, чтобы включить или отключить подмену сведений.</span><span class="sxs-lookup"><span data-stu-id="ece1a-243">**Spoof**: In this section, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="ece1a-244">Значение по умолчанию находится на (выбранном), и мы рекомендуем оставить его.</span><span class="sxs-lookup"><span data-stu-id="ece1a-244">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="ece1a-245">Вы указываете действие для принятия сообщений от заблокированных поддельных отправителей в сообщении If обнаружено в качестве параметра **spoof** на следующей странице.</span><span class="sxs-lookup"><span data-stu-id="ece1a-245">You specify the action to take on messages from blocked spoofed senders in the **If message is detected as spoof** setting on the next page.</span></span>

     <span data-ttu-id="ece1a-246">Чтобы отключить подмену сведений, очистить поле.</span><span class="sxs-lookup"><span data-stu-id="ece1a-246">To turn off spoof intelligence, clear the check box.</span></span>

     > [!NOTE]
     > <span data-ttu-id="ece1a-247">Вам не нужно отключать защиту от подмены, если запись MX не означает Microsoft 365; Вместо этого вы включаете усиленную фильтрацию соединителя.</span><span class="sxs-lookup"><span data-stu-id="ece1a-247">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="ece1a-248">Инструкции см. в [расширенной фильтрации соединители в Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="ece1a-248">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="ece1a-249">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-249">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="ece1a-250">В открывшемся окне **Действия** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ece1a-250">On the **Actions** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ece1a-251">**Действия сообщения:** Настройка следующих действий в этом разделе:</span><span class="sxs-lookup"><span data-stu-id="ece1a-251">**Message actions**: Configure the following actions in this section:</span></span>
     - <span data-ttu-id="ece1a-252">**Если сообщение обнаружено** как обезличенный пользователь: этот параметр доступен только в том случае, если вы выбрали **Включить** пользователей для защиты на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="ece1a-252">**If message is detected as an impersonated user**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span> <span data-ttu-id="ece1a-253">Выберите одно из следующих действий в списке выпаданий для сообщений, в которых отправитель является одним из защищенных пользователей, указанных на предыдущей странице:</span><span class="sxs-lookup"><span data-stu-id="ece1a-253">Select one of the following actions in the drop down list for messages where the sender is one of the protected users that you specified on the previous page:</span></span>
       - <span data-ttu-id="ece1a-254">**Не применяйте никаких действий**</span><span class="sxs-lookup"><span data-stu-id="ece1a-254">**Don't apply any action**</span></span>
       - <span data-ttu-id="ece1a-255">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="ece1a-255">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="ece1a-256">**Перемещение сообщения в папки нежелательной почты получателей**</span><span class="sxs-lookup"><span data-stu-id="ece1a-256">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="ece1a-257">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="ece1a-257">**Quarantine the message**</span></span>
       - <span data-ttu-id="ece1a-258">**Доставка сообщения и добавление других адресов в строку Bcc**</span><span class="sxs-lookup"><span data-stu-id="ece1a-258">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="ece1a-259">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="ece1a-259">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="ece1a-260">**Если сообщение обнаружено** как обезличенный домен: этот параметр доступен только в том случае, если вы выбрали домены **Enable для** защиты на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="ece1a-260">**If the message is detected as an impersonated domain**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span> <span data-ttu-id="ece1a-261">Выберите одно из следующих действий в списке drop down для сообщений, в которых адрес электронной почты отправитель находится в одном из защищенных доменов, указанных на предыдущей странице:</span><span class="sxs-lookup"><span data-stu-id="ece1a-261">Select one of the following actions in the drop down list for messages where the sender's email address is in one of the protected domains that you specified on the previous page:</span></span>
       - <span data-ttu-id="ece1a-262">**Не применяйте никаких действий**</span><span class="sxs-lookup"><span data-stu-id="ece1a-262">**Don't apply any action**</span></span>
       - <span data-ttu-id="ece1a-263">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="ece1a-263">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="ece1a-264">**Перемещение сообщения в папки нежелательной почты получателей**</span><span class="sxs-lookup"><span data-stu-id="ece1a-264">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="ece1a-265">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="ece1a-265">**Quarantine the message**</span></span>
       - <span data-ttu-id="ece1a-266">**Доставка сообщения и добавление других адресов в строку Bcc**</span><span class="sxs-lookup"><span data-stu-id="ece1a-266">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="ece1a-267">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="ece1a-267">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="ece1a-268">**Если разведка почтовых ящиков** обнаруживает обезличенных пользователей: этот параметр доступен только в том случае, если вы выбрали **включить** разведку для защиты от обезличения на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="ece1a-268">**If mailbox intelligence detects an impersonated user**: This setting is available only if you selected **Enable intelligence for impersonation protection** on the previous page.</span></span> <span data-ttu-id="ece1a-269">Выберите одно из следующих действий в списке drop down для сообщений, которые были определены как попытки обезличения с помощью разведки почтовых ящиков:</span><span class="sxs-lookup"><span data-stu-id="ece1a-269">Select one of the following actions in the drop down list for messages that were identified as impersonation attempts by mailbox intelligence:</span></span>
       - <span data-ttu-id="ece1a-270">**Не применяйте никаких действий**</span><span class="sxs-lookup"><span data-stu-id="ece1a-270">**Don't apply any action**</span></span>
       - <span data-ttu-id="ece1a-271">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="ece1a-271">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="ece1a-272">**Перемещение сообщения в папки нежелательной почты получателей**</span><span class="sxs-lookup"><span data-stu-id="ece1a-272">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="ece1a-273">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="ece1a-273">**Quarantine the message**</span></span>
       - <span data-ttu-id="ece1a-274">**Доставка сообщения и добавление других адресов в строку Bcc**</span><span class="sxs-lookup"><span data-stu-id="ece1a-274">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="ece1a-275">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="ece1a-275">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="ece1a-276">**Если сообщение обнаружено как поддельный:** этот параметр доступен только в том случае, если вы выбрали **сведения о** подмене на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="ece1a-276">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="ece1a-277">Выберите одно из следующих действий в списке выпадения для сообщений от заблокированных поддельных отправителей:</span><span class="sxs-lookup"><span data-stu-id="ece1a-277">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
       - <span data-ttu-id="ece1a-278">**Перемещение сообщения в папки нежелательной почты получателей**</span><span class="sxs-lookup"><span data-stu-id="ece1a-278">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="ece1a-279">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="ece1a-279">**Quarantine the message**</span></span>

   - <span data-ttu-id="ece1a-280">**Советы по &** безопасности: Настройка следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="ece1a-280">**Safety tips & indicators**: Configure the following settings:</span></span>
     - <span data-ttu-id="ece1a-281">**Показать имя пользователя совет по безопасности:** Этот параметр доступен только в том случае, если выбрана возможность защиты пользователей **на** предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="ece1a-281">**Show user impersonation safety tip**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span>
     - <span data-ttu-id="ece1a-282">**Показать имя домена совет по безопасности.** Этот параметр доступен только в том случае, если вы выбрали **домены Enable для** защиты на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="ece1a-282">**Show domain impersonation safety tip**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="ece1a-283">**Показать пользователю вымысление необычных символов совет по безопасности** Этот параметр доступен только в том случае, если вы выбрали **Включить** пользователей для защиты или включить домены **для защиты** на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="ece1a-283">**Show user impersonation unusual characters safety tip** This setting is available only if you selected **Enable users to protect** or **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="ece1a-284">**Показать (?)** для неавентированных отправителей для подмены: Этот параметр доступен только в том случае, если вы выбрали **включить** подмену сведений на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="ece1a-284">**Show (?) for unauthenticated senders for spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="ece1a-285">Добавляет знак вопроса на фотографию отправитель в поле From в Outlook, если сообщение не проходит проверки SPF или DKIM и сообщение не передает DMARC или композитную проверку  подлинности. [](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="ece1a-285">Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="ece1a-286">**Показать тег "via".** Этот параметр доступен только в том случае, если вы выбрали **сведения о** подмене подмены на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="ece1a-286">**Show "via" tag**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="ece1a-287">Добавляет тег via (chris@contoso.com через fabrikam.com) на адрес From, если он отличается от домена в подписи DKIM или **адресЕ MAIL FROM.**</span><span class="sxs-lookup"><span data-stu-id="ece1a-287">Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="ece1a-288">Значение по умолчанию находится (выбрано).</span><span class="sxs-lookup"><span data-stu-id="ece1a-288">The default value is on (selected).</span></span> <span data-ttu-id="ece1a-289">Чтобы отключить его, зачистите контрольный ящик.</span><span class="sxs-lookup"><span data-stu-id="ece1a-289">To turn it off, clear the check box.</span></span>

       > [!NOTE]
       > <span data-ttu-id="ece1a-290">В настоящее **время параметр тега Show "via"** доступен не во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="ece1a-290">Currently, the **Show "via" tag** setting is not available in all organizations.</span></span> <span data-ttu-id="ece1a-291">Если у вас нет параметра тега **Show "via",** знак вопроса и тег через контролируются командой **Show (?)** для неавентированных отправителей для настройки подмены в организации. </span><span class="sxs-lookup"><span data-stu-id="ece1a-291">If you don't have the **Show "via" tag** setting, the question mark **and** the via tag are both controlled by the **Show (?) for unauthenticated senders for spoof** setting in your organization.</span></span>

     <span data-ttu-id="ece1a-292">Чтобы включить параметр, выберите поле для проверки.</span><span class="sxs-lookup"><span data-stu-id="ece1a-292">To turn on a setting, select the check box.</span></span> <span data-ttu-id="ece1a-293">Чтобы отключить его, зачистите контрольный ящик.</span><span class="sxs-lookup"><span data-stu-id="ece1a-293">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="ece1a-294">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-294">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="ece1a-295">На странице **Просмотр** просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="ece1a-295">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="ece1a-296">Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="ece1a-296">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="ece1a-297">Вы также можете щелкнуть **Назад** или выбрать определенную страницу в мастере.</span><span class="sxs-lookup"><span data-stu-id="ece1a-297">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="ece1a-298">По завершению нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-298">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="ece1a-299">На странице подтверждения, которая откроется, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-299">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a><span data-ttu-id="ece1a-300">Используйте портал Microsoft 365 Defender для просмотра политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-300">Use the Microsoft 365 Defender portal to view anti-phishing policies</span></span>

1. <span data-ttu-id="ece1a-301">На портале Microsoft 365 Defender перейдите в раздел Политики **совместной** & электронной почты & политики угрозы \>  \>  \>  \> правил.</span><span class="sxs-lookup"><span data-stu-id="ece1a-301">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ece1a-302">На странице **Anti-phishing** в списке политик защиты от фишинга отображаются следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="ece1a-302">On the **Anti-phishing** page, the following properties are displayed in the list of anti-phishing policies:</span></span>

   - <span data-ttu-id="ece1a-303">**Имя**</span><span class="sxs-lookup"><span data-stu-id="ece1a-303">**Name**</span></span>
   - <span data-ttu-id="ece1a-304">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="ece1a-304">**Status**</span></span>
   - <span data-ttu-id="ece1a-305">**Приоритет**</span><span class="sxs-lookup"><span data-stu-id="ece1a-305">**Priority**</span></span>
   - <span data-ttu-id="ece1a-306">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="ece1a-306">**Last modified**</span></span>

3. <span data-ttu-id="ece1a-307">При выборе политики, щелкнув имя, параметры политики отображаются в вылете.</span><span class="sxs-lookup"><span data-stu-id="ece1a-307">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a><span data-ttu-id="ece1a-308">Используйте портал Microsoft 365 Defender для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-308">Use the Microsoft 365 Defender portal to modify anti-phishing policies</span></span>

1. <span data-ttu-id="ece1a-309">На портале Microsoft 365 Defender перейдите в раздел Политики **совместной** & электронной почты & политики угрозы \>  \>  \>  \> правил.</span><span class="sxs-lookup"><span data-stu-id="ece1a-309">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ece1a-310">На странице **Anti-phishing** выберите политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="ece1a-310">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="ece1a-311">Параметры политики будут показаны во всплывающем окне. Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="ece1a-311">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="ece1a-312">Дополнительные сведения о параметрах см. в разделе Использование портала [Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) для создания раздела политики защиты от фишинга в этой статье.</span><span class="sxs-lookup"><span data-stu-id="ece1a-312">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create anti-phishing policies](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="ece1a-313">Для политики защиты от фишинга по умолчанию раздел **Пользователи,** группы и домены недоступны (политика применяется ко всем), и переименовать политику нельзя.</span><span class="sxs-lookup"><span data-stu-id="ece1a-313">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="ece1a-314">Чтобы включить или отключить политику или установить порядок приоритета политики, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="ece1a-314">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="ece1a-315">Включить или отключить настраиваемые политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-315">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="ece1a-316">Вы не можете отключить политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ece1a-316">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="ece1a-317">На портале Microsoft 365 Defender перейдите в раздел Политики **совместной** & электронной почты & политики угрозы \>  \>  \>  \> правил.</span><span class="sxs-lookup"><span data-stu-id="ece1a-317">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ece1a-318">На странице **Anti-phishing** выберите настраиваемую политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="ece1a-318">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="ece1a-319">Появится всплывающее окно со сведениями о политике. В верхней его части вы увидите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="ece1a-319">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="ece1a-320">**Политика отключена**. Чтобы включить политику, щелкните значок !["Включить"](../../media/m365-cc-sc-turn-on-off-icon.png) **Включить** .</span><span class="sxs-lookup"><span data-stu-id="ece1a-320">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="ece1a-321">**Политика включена**. Чтобы выключить политику, щелкните значок !["Отключить"](../../media/m365-cc-sc-turn-on-off-icon.png) **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-321">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="ece1a-322">В диалоговом окне подтверждения нажмите кнопку **Включить** или **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-322">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="ece1a-323">Во всплывающем окне сведений о политике нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-323">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="ece1a-324">Когда вы вернетесь на главную страницу политики, значение параметра **Состояние** этой политики будет **Включена** или **Выключена**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-324">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="ece1a-325">Установите приоритет настраиваемой политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-325">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="ece1a-326">По умолчанию политикам защиты от фишинга предоставляется приоритет, основанный на порядке, в который они были созданы (более новые политики имеют более низкий приоритет по сравнению с более старыми политиками).</span><span class="sxs-lookup"><span data-stu-id="ece1a-326">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="ece1a-327">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="ece1a-327">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="ece1a-328">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="ece1a-328">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="ece1a-329">Чтобы изменить приоритет политики, нажмите кнопку Увеличение  приоритета или Уменьшение приоритета в свойствах политики  (вы не можете напрямую изменить номер приоритета на портале Microsoft 365 Defender). </span><span class="sxs-lookup"><span data-stu-id="ece1a-329">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="ece1a-330">Изменение приоритета политики имеет смысл, только если у вас несколько политик.</span><span class="sxs-lookup"><span data-stu-id="ece1a-330">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="ece1a-331">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-331">**Notes**:</span></span>

- <span data-ttu-id="ece1a-332">На портале Microsoft 365 Defender можно изменить приоритет политики защиты от фишинга только после ее создания.</span><span class="sxs-lookup"><span data-stu-id="ece1a-332">In the Microsoft 365 Defender portal, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="ece1a-333">В PowerShell можно переопредить приоритет по умолчанию при создании правила защиты от фишинга (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="ece1a-333">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="ece1a-334">Политики защиты от фишинга обрабатываются в порядке отображения (первая политика имеет значение **Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="ece1a-334">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="ece1a-335">Политика защиты от фишинга по умолчанию имеет приоритетное значение **Самое** низкое, и изменить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="ece1a-335">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="ece1a-336">На портале Microsoft 365 Defender перейдите в раздел Политики **совместной** & электронной почты & политики угрозы \>  \>  \>  \> правил.</span><span class="sxs-lookup"><span data-stu-id="ece1a-336">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ece1a-337">На странице **Anti-phishing** выберите настраиваемую политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="ece1a-337">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="ece1a-338">Появится всплывающее окно со сведениями о политике. В верхней его части вы увидите одно из следующих значений: **Увеличить приоритет** или **Уменьшить приоритет** в зависимости от текущего значения приоритета и количества настраиваемых политик:</span><span class="sxs-lookup"><span data-stu-id="ece1a-338">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="ece1a-339">Политика защиты от фишинга со значением **Priority** **0** имеет только доступный параметр **Decrease priority.**</span><span class="sxs-lookup"><span data-stu-id="ece1a-339">The anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="ece1a-340">Политика защиты от фишинга  с наименьшим значением Приоритет (например, **3)** имеет только доступный параметр **Increase priority.**</span><span class="sxs-lookup"><span data-stu-id="ece1a-340">The anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="ece1a-341">Если у вас есть три или более политик защиты от фишинга, политики между самыми высокими и самыми низкими значениями приоритетов имеют доступные параметры **приоритета Increase** и **Decrease.**</span><span class="sxs-lookup"><span data-stu-id="ece1a-341">If you have three or more anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="ece1a-342">Щелкните ![Значок увеличения приоритета](../../media/m365-cc-sc-increase-icon.png) **Увеличить приоритет** или ![Значок уменьшения приоритета](../../media/m365-cc-sc-decrease-icon.png) **Уменьшить приоритет** чтобы изменить значение параметра **Приоритет**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-342">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="ece1a-343">Закончив, нажмите **Закрыть** во всплывающем окне сведений о политике.</span><span class="sxs-lookup"><span data-stu-id="ece1a-343">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="ece1a-344">Использование портала Microsoft 365 Defender для удаления настраиваемой политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-344">Use the Microsoft 365 Defender portal to remove custom anti-phishing policies</span></span>

<span data-ttu-id="ece1a-345">При использовании портала Microsoft 365 Defender для удаления настраиваемой политики защиты от фишинга правило защиты от фишинга и соответствующая политика защиты от фишинга удаляются.</span><span class="sxs-lookup"><span data-stu-id="ece1a-345">When you use the Microsoft 365 Defender portal to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="ece1a-346">Вы не можете удалить политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ece1a-346">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="ece1a-347">На портале Microsoft 365 Defender перейдите в раздел Политики **совместной** & электронной почты & политики угрозы \>  \>  \>  \> правил.</span><span class="sxs-lookup"><span data-stu-id="ece1a-347">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ece1a-348">Выберите настраиваемую политику из списка, щелкнув имя политики.</span><span class="sxs-lookup"><span data-stu-id="ece1a-348">Select a custom policy from the list by clicking on the name of the policy.</span></span> <span data-ttu-id="ece1a-349">В открывшемся всплывающем окне сведений о политике щелкните ![значок "Дополнительные действия"](../../media/m365-cc-sc-more-actions-icon.png) **Дополнительные действия** \> ![значок "Удалить политику"](../../media/m365-cc-sc-delete-icon.png) **Удалить политику**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-349">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="ece1a-350">В диалоговом окне подтверждения нажмите **Да**.</span><span class="sxs-lookup"><span data-stu-id="ece1a-350">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="ece1a-351">Используйте Exchange Online PowerShell для настройки политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-351">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="ece1a-352">Как описано выше, политика защиты от нежелательной почты состоит из политики защиты от фишинга и правила защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="ece1a-352">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="ece1a-353">В Exchange Online PowerShell разница между политиками защиты от фишинга и правилами защиты от фишинга очевидна.</span><span class="sxs-lookup"><span data-stu-id="ece1a-353">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="ece1a-354">Вы управляете политиками защиты от фишинга с помощью кодлетов **\* -AntiPhishPolicy** и управляете правилами защиты от фишинга с помощью cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="ece1a-354">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="ece1a-355">В PowerShell сначала создается политика защиты от фишинга, а затем создается правило защиты от фишинга, которое определяет политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="ece1a-355">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="ece1a-356">В PowerShell параметры политики защиты от фишинга и правила защиты от фишинга изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="ece1a-356">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="ece1a-357">При удалении политики защиты от фишинга из PowerShell соответствующее правило не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="ece1a-357">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="ece1a-358">Использование PowerShell для создания политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-358">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="ece1a-359">Создание политики защиты от фишинга в PowerShell — это двухшаговый процесс:</span><span class="sxs-lookup"><span data-stu-id="ece1a-359">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="ece1a-360">Создание политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="ece1a-360">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="ece1a-361">Создайте правило защиты от фишинга, которое указывает политику защиты от фишинга, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="ece1a-361">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="ece1a-362">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="ece1a-362">**Notes**:</span></span>

- <span data-ttu-id="ece1a-363">Вы можете создать новое правило защиты от фишинга и назначить ему существующую, неассоциированную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="ece1a-363">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="ece1a-364">Правило защиты от фишинга не может быть связано с одной политикой защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="ece1a-364">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>
- <span data-ttu-id="ece1a-365">Вы можете настроить следующие параметры для новых политик защиты от фишинга в PowerShell, которые недоступны на портале Microsoft 365 Defender до момента создания политики:</span><span class="sxs-lookup"><span data-stu-id="ece1a-365">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="ece1a-366">Создайте новую политику как отключенную _(включена_ `$false` в **кодлете New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="ece1a-366">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="ece1a-367">Задай приоритет политики во время создания _(приоритет)_ в _\<Number\>_ **комлете New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="ece1a-367">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>
- <span data-ttu-id="ece1a-368">Новая политика защиты от фишинга, которую вы создаете в PowerShell, не отображается на портале Microsoft 365 Defender, пока не назначите политику правилу защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="ece1a-368">A new anti-phish policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="ece1a-369">Шаг 1. Использование PowerShell для создания политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-369">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="ece1a-370">Чтобы создать политику защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ece1a-370">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="ece1a-371">В этом примере создается политика защиты от фишинга с именем Research Quarantine со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="ece1a-371">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="ece1a-372">Политика включена (мы не используем параметр _Включен,_ а значение по `$true` умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ece1a-372">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="ece1a-373">Описание: Политика отдела исследований.</span><span class="sxs-lookup"><span data-stu-id="ece1a-373">The description is: Research department policy.</span></span>
- <span data-ttu-id="ece1a-374">Включает защиту доменов организации для всех принятых доменов и адресную защиту доменов для fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="ece1a-374">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="ece1a-375">Указывает, что защищать от имитации нужно пользователя Mai Fujito (mfujito@fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="ece1a-375">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="ece1a-376">Включает аналитику почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="ece1a-376">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="ece1a-377">Включает защиту разведданных почтовых ящиков и указывает действие карантина.</span><span class="sxs-lookup"><span data-stu-id="ece1a-377">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="ece1a-378">Включает советы по безопасности.</span><span class="sxs-lookup"><span data-stu-id="ece1a-378">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="ece1a-379">Подробные сведения о синтаксисе и параметрах см. в [обзоре New-AntiPhishPolicy.](/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="ece1a-379">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="ece1a-380">Шаг 2. Использование PowerShell для создания правила защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-380">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="ece1a-381">Чтобы создать правило защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ece1a-381">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="ece1a-382">В этом примере создается правило защиты от фишинга с именем Research Department со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="ece1a-382">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="ece1a-383">Это правило связано с политикой защиты от фишинга с именем Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="ece1a-383">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="ece1a-384">Правило применяется к членам группы "Research Department".</span><span class="sxs-lookup"><span data-stu-id="ece1a-384">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="ece1a-385">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ece1a-385">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="ece1a-386">Подробные сведения о синтаксисе и параметрах см. [в обзоре New-AntiPhishRule.](/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="ece1a-386">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="ece1a-387">Использование PowerShell для просмотра политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-387">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="ece1a-388">Чтобы просмотреть существующие политики защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ece1a-388">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ece1a-389">В этом примере возвращается сводный список всех политик защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="ece1a-389">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="ece1a-390">В этом примере возвращаются все значения свойств для политики защиты от фишинга с именем Executives.</span><span class="sxs-lookup"><span data-stu-id="ece1a-390">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="ece1a-391">Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-AntiPhishPolicy.](/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="ece1a-391">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="ece1a-392">Использование PowerShell для просмотра правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-392">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="ece1a-393">Чтобы просмотреть существующие правила защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ece1a-393">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ece1a-394">В этом примере возвращается сводный список всех правил по борьбе с фишингом вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="ece1a-394">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="ece1a-395">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="ece1a-395">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="ece1a-396">В этом примере возвращаются все значения свойств для правила защиты от фишинга с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="ece1a-396">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="ece1a-397">Подробные сведения о синтаксисе и параметрах см. в [ссылке Get-AntiPhishRule.](/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="ece1a-397">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="ece1a-398">Использование PowerShell для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-398">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="ece1a-399">Кроме следующих элементов, при изменении политики защиты от фишинга в PowerShell доступны те же параметры, что и при создании политики, описанной в разделе [Шаг 1. Использование PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) для создания раздела политики защиты от фишинга в этой статье.</span><span class="sxs-lookup"><span data-stu-id="ece1a-399">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="ece1a-400">Переключатель _MakeDefault,_ который превращает указанную политику в политику по  умолчанию (применяется для всех, всегда самый низкий приоритет, и вы не можете удалить ее) доступен только при изменении политики защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ece1a-400">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="ece1a-401">Нельзя переименовать политику защиты от фишинга (в **кодлете Set-AntiPhishPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="ece1a-401">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="ece1a-402">При переименовании политики защиты от фишинга на портале Microsoft 365 Defender можно только переименовать правило защиты от _фишинга._</span><span class="sxs-lookup"><span data-stu-id="ece1a-402">When you rename an anti-phishing policy in the Microsoft 365 Defender portal, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="ece1a-403">Чтобы изменить политику защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ece1a-403">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="ece1a-404">Подробные сведения о синтаксисе и параметрах см. в [инструкции Set-AntiPhishPolicy.](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="ece1a-404">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="ece1a-405">Использование PowerShell для изменения правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-405">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="ece1a-406">Единственным параметром, недоступным при изменении правила защиты от фишинга  в PowerShell, является параметр Включен, который позволяет создать правило отключено.</span><span class="sxs-lookup"><span data-stu-id="ece1a-406">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="ece1a-407">Чтобы включить или отключить существующие правила защиты от фишинга, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="ece1a-407">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="ece1a-408">В противном случае дополнительные параметры не доступны при изменении правила защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ece1a-408">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="ece1a-409">Эти же параметры доступны при создании правила, описанного в разделе Шаг [2. Использование PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) для создания раздела правил для защиты от фишинга в этой статье.</span><span class="sxs-lookup"><span data-stu-id="ece1a-409">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="ece1a-410">Чтобы изменить правило защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ece1a-410">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="ece1a-411">Подробные сведения о синтаксисе и параметрах см. в [инструкции Set-AntiPhishRule.](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="ece1a-411">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="ece1a-412">Использование PowerShell, чтобы включить или отключить правила защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-412">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="ece1a-413">Включение или отключение правила защиты от фишинга в PowerShell включает или отключает всю политику защиты от фишинга (правило защиты от фишинга и назначенную политику защиты от фишинга).</span><span class="sxs-lookup"><span data-stu-id="ece1a-413">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="ece1a-414">Вы не можете включить или отключить политику защиты от фишинга по умолчанию (она всегда применяется к всем получателям).</span><span class="sxs-lookup"><span data-stu-id="ece1a-414">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="ece1a-415">Чтобы включить или отключить правило защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ece1a-415">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="ece1a-416">В этом примере отключает правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="ece1a-416">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ece1a-417">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="ece1a-417">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ece1a-418">Подробные сведения о синтаксисе и параметрах см. в [сводке Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) и [Disable-AntiPhishRule.](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="ece1a-418">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="ece1a-419">Использование PowerShell для набора приоритета правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-419">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="ece1a-p158">Максимальный приоритет, который можно задать для правила, — 0. Минимальное значение зависит от количества правил. Например, если у вас есть пять правил, вы можете использовать значения 0-4. Изменение приоритета существующего правила оказывает каскадное влияние на другие правила. Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="ece1a-p158">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="ece1a-425">Чтобы установить приоритет правила защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ece1a-425">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="ece1a-p159">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="ece1a-p159">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="ece1a-428">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="ece1a-428">**Notes**:</span></span>

- <span data-ttu-id="ece1a-429">Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в **комлете New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="ece1a-429">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="ece1a-430">Политика защиты от фишинга по умолчанию не имеет соответствующего правила по борьбе с фишингом, и всегда имеет неоплаченное значение приоритета **Самое низкое.**</span><span class="sxs-lookup"><span data-stu-id="ece1a-430">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="ece1a-431">Использование PowerShell для удаления политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-431">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="ece1a-432">При удалении политики защиты от фишинга с помощью PowerShell соответствующее правило по борьбе с фишингом не удаляется.</span><span class="sxs-lookup"><span data-stu-id="ece1a-432">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="ece1a-433">Чтобы удалить политику защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ece1a-433">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="ece1a-434">В этом примере удаляется политика защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="ece1a-434">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="ece1a-435">Подробные сведения о синтаксисе и параметрах см. в [обзоре Remove-AntiPhishPolicy.](/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="ece1a-435">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="ece1a-436">Использование PowerShell для удаления правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="ece1a-436">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="ece1a-437">При удалении правила защиты от фишинга с помощью PowerShell соответствующая политика защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="ece1a-437">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="ece1a-438">Чтобы удалить правило защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ece1a-438">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="ece1a-439">В этом примере удаляется правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="ece1a-439">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ece1a-440">Подробные сведения о синтаксисе и параметрах см. в [инструкции Remove-AntiPhishRule.](/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="ece1a-440">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="ece1a-441">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="ece1a-441">How do you know these procedures worked?</span></span>

<span data-ttu-id="ece1a-442">Чтобы убедиться в успешной настройке политик защиты от фишинга в Defender для Office 365, необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ece1a-442">To verify that you've successfully configured anti-phishing policies in Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="ece1a-443">На портале Microsoft 365 Defender перейдите в раздел Политики **совместной** & электронной почты & политики угрозы \>  \>  \>  \> правил.</span><span class="sxs-lookup"><span data-stu-id="ece1a-443">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="ece1a-444">Проверка списка политик, их значений **состояния** и **их значений приоритета.**</span><span class="sxs-lookup"><span data-stu-id="ece1a-444">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="ece1a-445">Чтобы просмотреть дополнительные сведения, выберите политику из списка, нажав на имя и просмотрев сведения в вылете, который появится.</span><span class="sxs-lookup"><span data-stu-id="ece1a-445">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="ece1a-446">В Exchange Online PowerShell замените имя политики или правила и запустите следующую команду и проверьте \<Name\> параметры:</span><span class="sxs-lookup"><span data-stu-id="ece1a-446">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
