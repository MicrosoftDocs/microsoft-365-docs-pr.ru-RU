---
title: Настройка политик защиты от фишинга в EOP
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
description: Администраторы могут научиться создавать, изменять и удалять политики защиты от фишинга, доступные в Exchange Online Protection организациях с Exchange Online почтовыми ящиками.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e56e1b5d91b74d2ffcf9cccc897962b915c6e83c
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108071"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="95856-103">Настройка политик защиты от фишинга в EOP</span><span class="sxs-lookup"><span data-stu-id="95856-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="95856-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="95856-104">**Applies to**</span></span>
- [<span data-ttu-id="95856-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="95856-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="95856-106">В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без Exchange Online почтовых ящиков по умолчанию существует политика защиты от фишинга, которая содержит ограниченное количество функций защиты от спуфинга, которые включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="95856-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="95856-107">Дополнительные сведения см. в статье [Параметры фишинга в политиках защиты от фишинга](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="95856-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="95856-108">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="95856-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="95856-109">Для большей детализации можно также создать настраиваемые политики защиты от фишинга, применимые к определенным пользователям, группам или доменам в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="95856-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="95856-110">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="95856-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="95856-111">Организации с Exchange Online почтовыми ящиками могут настраивать политики защиты от фишинга на портале Microsoft 365 Defender или в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95856-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Microsoft 365 Defender portal or in Exchange Online PowerShell.</span></span> <span data-ttu-id="95856-112">Автономные организации EOP могут использовать только Microsoft 365 Defender портал.</span><span class="sxs-lookup"><span data-stu-id="95856-112">Standalone EOP organizations can only use the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="95856-113">Сведения о создании и изменении более продвинутых политик защиты от фишинга, доступных в Microsoft Defender для Office 365, см. в руб. Настройка политик защиты от фишинга в [Microsoft Defender](configure-mdo-anti-phishing-policies.md)для Office 365 .</span><span class="sxs-lookup"><span data-stu-id="95856-113">For information about creating and modifying the more advanced anti-phishing policies that are available in Microsoft Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span></span>

<span data-ttu-id="95856-114">Основные элементы политики защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="95856-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="95856-115">**Политика защиты от фишинга:** указывает средства защиты от фишинга, чтобы включить или отключить, а также действия по применении параметров.</span><span class="sxs-lookup"><span data-stu-id="95856-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="95856-116">**Правило защиты от фишинга:** указывает фильтры приоритета и получателей (к кому применяется политика) для политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="95856-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="95856-117">Разница между этими двумя элементами не очевидна при управлении политиками защиты от фишинга на Microsoft 365 Defender портале:</span><span class="sxs-lookup"><span data-stu-id="95856-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="95856-118">При создании политики защиты от фишинга создается правило защиты от фишинга и связанная с ним политика защиты от фишинга, используя одно и то же имя для обоих.</span><span class="sxs-lookup"><span data-stu-id="95856-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="95856-119">При изменении политики защиты от фишинга параметры, связанные с именем, приоритетом, включенной или отключенной, а также фильтры получателей изменяют правило защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="95856-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="95856-120">Все остальные параметры изменяют связанную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="95856-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="95856-121">При удалении политики защиты от фишинга правило защиты от фишинга и связанная с ним политика защиты от фишинга удаляются.</span><span class="sxs-lookup"><span data-stu-id="95856-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="95856-122">В Exchange Online PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="95856-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="95856-123">Дополнительные сведения см. в [разделе Использование Exchange Online PowerShell для](#use-exchange-online-powershell-to-configure-anti-phishing-policies) настройки политики защиты от фишинга в этой статье.</span><span class="sxs-lookup"><span data-stu-id="95856-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="95856-124">Каждая организация имеет встроенную политику защиты от фишинга с именем Office365 AntiPhish Default, которая имеет эти свойства:</span><span class="sxs-lookup"><span data-stu-id="95856-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="95856-125">Политика применяется к всем получателям в организации, несмотря на отсутствие правила защиты от фишинга (фильтры получателей), связанного с политикой.</span><span class="sxs-lookup"><span data-stu-id="95856-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="95856-126">Для политики задано специальное значение приоритета **Самый низкий**, которое невозможно изменить (эта политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="95856-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="95856-127">Все созданные специальные политики всегда имеют более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="95856-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="95856-128">Эта политика является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.</span><span class="sxs-lookup"><span data-stu-id="95856-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="95856-129">Чтобы повысить эффективность защиты от фишинга, можно создать настраиваемые политики защиты от фишинга с более строгими настройками, которые применяются к конкретным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="95856-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="95856-130">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="95856-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="95856-131">Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="95856-131">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="95856-132">Чтобы перейти непосредственно на страницу **anti-phishing,** используйте <https://security.microsoft.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="95856-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="95856-133">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="95856-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="95856-134">Вы не можете управлять политиками защиты от фишинга в автономных EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95856-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="95856-135">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="95856-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="95856-136">Чтобы добавить, изменить и удалить политики защиты от фишинга, необходимо  быть членом групп ролей администратора организации или **администратора** безопасности.</span><span class="sxs-lookup"><span data-stu-id="95856-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="95856-137">Для доступа только для чтения к политикам защиты от фишинга необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="95856-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="95856-138">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="95856-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="95856-139">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="95856-139">**Notes**:</span></span>

  - <span data-ttu-id="95856-140">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="95856-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="95856-141">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="95856-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="95856-142">Группа **ролей только** для организации просмотра в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой <sup>\*</sup> функции.</span><span class="sxs-lookup"><span data-stu-id="95856-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>

- <span data-ttu-id="95856-143">Рекомендуемые параметры для политик защиты от фишинга см. в рекомендациях EOP по борьбе [с фишингом.](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="95856-143">For our recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="95856-144">Разрешить до 30 минут для обновленной политики, которая будет применяться.</span><span class="sxs-lookup"><span data-stu-id="95856-144">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="95856-145">Сведения о том, где политики защиты от фишинга применяются в конвейере фильтрации, см. в рублях [Order и precedence of email protection.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="95856-145">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a><span data-ttu-id="95856-146">Используйте портал Microsoft 365 Defender для создания политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-146">Use the Microsoft 365 Defender portal to create anti-phishing policies</span></span>

<span data-ttu-id="95856-147">Создание настраиваемой политики защиты от фишинга на портале Microsoft 365 Defender создает правило защиты от фишинга и связанную политику защиты от фишинга, используя одно и то же имя для обоих.</span><span class="sxs-lookup"><span data-stu-id="95856-147">Creating a custom anti-phishing policy in the Microsoft 365 Defender portal creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="95856-148">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики защиты от \>  \>  \>  \> **фишинга**.</span><span class="sxs-lookup"><span data-stu-id="95856-148">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="95856-149">На странице **Anti-phishing** нажмите кнопку ![ Создать значок ](../../media/m365-cc-sc-create-icon.png) **Создать**.</span><span class="sxs-lookup"><span data-stu-id="95856-149">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="95856-150">Откроется мастер политик.</span><span class="sxs-lookup"><span data-stu-id="95856-150">The policy wizard opens.</span></span> <span data-ttu-id="95856-151">На странице **Имя политики** настройте эти параметры:</span><span class="sxs-lookup"><span data-stu-id="95856-151">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="95856-152">**Имя**. Укажите уникальное, описательное имя политики.</span><span class="sxs-lookup"><span data-stu-id="95856-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="95856-153">**Описание**. По желанию введите описание политики.</span><span class="sxs-lookup"><span data-stu-id="95856-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="95856-154">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95856-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="95856-155">На открывшейся странице **Пользователи, группы и домены** определите внутренних получателей, к которым применяется политика (условия получателей):</span><span class="sxs-lookup"><span data-stu-id="95856-155">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="95856-156">**Пользователи**: указывает один или несколько почтовых ящиков, пользователей почты или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="95856-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="95856-157">**Группы**: указывает группы рассылки, группы безопасности с поддержкой почты или группы Microsoft 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="95856-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="95856-158">**Домены**: все получатели в указанных [обслуживаемых доменах](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="95856-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="95856-159">Щелкните соответствующее поле, начните вводить значение и выберите нужное значение в результатах.</span><span class="sxs-lookup"><span data-stu-id="95856-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="95856-160">Повторите эти действия необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="95856-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="95856-161">Чтобы удалить существующее значение, нажмите "Удалить".</span><span class="sxs-lookup"><span data-stu-id="95856-161">To remove an existing value, click remove</span></span> ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="95856-163">рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="95856-163">next to the value.</span></span>

   <span data-ttu-id="95856-164">Для пользователей и групп можно использовать большинство идентификаторов (имя, отображаемое имя, псевдоним, адрес электронной почты, имя учетной записи и т. д.), но в результатах будет выведено отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="95856-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="95856-165">Для получения списка всех пользователей введите звездочку (\*) без добавлений, чтобы увидеть все доступные значения.</span><span class="sxs-lookup"><span data-stu-id="95856-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="95856-166">Указать несколько значений в одном условии можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="95856-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="95856-167">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="95856-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="95856-168">**Исключить этих пользователей, группы и домены**. Чтобы добавить исключения для внутренних получателей, к которым применяется политика (исключение получателей), выберите этот параметр и настройте исключения.</span><span class="sxs-lookup"><span data-stu-id="95856-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="95856-169">Настройки и поведение такие же, как в разделе условий.</span><span class="sxs-lookup"><span data-stu-id="95856-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="95856-170">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95856-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="95856-171">На странице **защиты &** фишинга, чтобы включить  или отключить подмену сведений, используйте поле Включить подмену сведений.</span><span class="sxs-lookup"><span data-stu-id="95856-171">On the **Phishing threshold & protection** page that appears, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="95856-172">Значение по умолчанию находится на (выбранном), и мы рекомендуем оставить его.</span><span class="sxs-lookup"><span data-stu-id="95856-172">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="95856-173">Вы настраиваете действие для принятия заблокированных поддельных сообщений на следующей странице.</span><span class="sxs-lookup"><span data-stu-id="95856-173">You configure the action to take on blocked spoofed messages on the next page.</span></span>

   <span data-ttu-id="95856-174">Чтобы отключить подмену сведений, очистить поле.</span><span class="sxs-lookup"><span data-stu-id="95856-174">To turn off spoof intelligence, clear the check box.</span></span>

   > [!NOTE]
   > <span data-ttu-id="95856-175">Вам не нужно отключать защиту от подмены, если запись MX не означает Microsoft 365; Вместо этого вы включаете усиленную фильтрацию соединителя.</span><span class="sxs-lookup"><span data-stu-id="95856-175">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="95856-176">Инструкции см. в [расширенной фильтрации соединители в Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="95856-176">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="95856-177">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95856-177">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="95856-178">В открывшемся окне **Действия** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="95856-178">On the **Actions** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="95856-179">**Если сообщение обнаружено как поддельный:** этот параметр доступен только в том случае, если вы выбрали **сведения о** подмене на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="95856-179">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="95856-180">Выберите одно из следующих действий в списке выпадения для сообщений от заблокированных поддельных отправителей:</span><span class="sxs-lookup"><span data-stu-id="95856-180">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
     - <span data-ttu-id="95856-181">**Перемещение сообщения в папки нежелательной почты получателей**</span><span class="sxs-lookup"><span data-stu-id="95856-181">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="95856-182">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="95856-182">**Quarantine the message**</span></span>

   - <span data-ttu-id="95856-183">**Советы по & безопасности:**</span><span class="sxs-lookup"><span data-stu-id="95856-183">**Safety tips & indicators**:</span></span>
     - <span data-ttu-id="95856-184">**Показать первые контактные совет по безопасности:** Дополнительные сведения см. в [совет по безопасности.](set-up-anti-phishing-policies.md#first-contact-safety-tip)</span><span class="sxs-lookup"><span data-stu-id="95856-184">**Show first contact safety tip**: For more information, see [First contact safety tip](set-up-anti-phishing-policies.md#first-contact-safety-tip).</span></span>
     - <span data-ttu-id="95856-185">**Показать (?)** для неавентированных отправителей для подмены: добавляет знак вопроса к фотографии отправителей в поле From в Outlook, если сообщение не проходит проверки SPF или DKIM и сообщение не передает <sup>\*</sup> DMARC  или композитную проверку подлинности . [](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="95856-185">**Show (?) for unauthenticated senders for spoof**<sup>\*</sup>: Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="95856-186">**Показать тег "via":** Добавляет тег via (chris@contoso.com fabrikam.com) на адрес From, если он отличается от домена в подписи <sup>\*</sup> DKIM или адреса MAIL **FROM.**</span><span class="sxs-lookup"><span data-stu-id="95856-186">**Show "via" tag**<sup>\*</sup>: Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span>

     <span data-ttu-id="95856-187">Чтобы включить параметр, выберите поле для проверки.</span><span class="sxs-lookup"><span data-stu-id="95856-187">To turn on a setting, select the check box.</span></span> <span data-ttu-id="95856-188">Чтобы отключить его, зачистите контрольный ящик.</span><span class="sxs-lookup"><span data-stu-id="95856-188">To turn it off, clear the check box.</span></span>

     <span data-ttu-id="95856-189"><sup>\*</sup> Этот параметр доступен только в том случае, если вы выбрали сведения о подмене **подмены на** предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="95856-189"><sup>\*</sup> This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="95856-190">Дополнительные сведения см. в [перенаправщике, неавентированном.](set-up-anti-phishing-policies.md#unauthenticated-sender)</span><span class="sxs-lookup"><span data-stu-id="95856-190">For more information, see [Unauthenticated sender](set-up-anti-phishing-policies.md#unauthenticated-sender).</span></span>

   <span data-ttu-id="95856-191">По завершении нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95856-191">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="95856-192">На странице **Просмотр** просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="95856-192">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="95856-193">Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="95856-193">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="95856-194">Вы также можете щелкнуть **Назад** или выбрать определенную страницу в мастере.</span><span class="sxs-lookup"><span data-stu-id="95856-194">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="95856-195">По завершении нажмите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="95856-195">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="95856-196">На странице подтверждения, которая откроется, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="95856-196">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a><span data-ttu-id="95856-197">Используйте портал Microsoft 365 Defender для просмотра политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-197">Use the Microsoft 365 Defender portal to view anti-phishing policies</span></span>

1. <span data-ttu-id="95856-198">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики защиты от \>  \>  \>  \> **фишинга**.</span><span class="sxs-lookup"><span data-stu-id="95856-198">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="95856-199">На **странице Anti-phishing** в списке политик отображаются следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="95856-199">On the **Anti-phishing** page, the following properties are displayed in the list of policies:</span></span>

   - <span data-ttu-id="95856-200">**Имя**</span><span class="sxs-lookup"><span data-stu-id="95856-200">**Name**</span></span>
   - <span data-ttu-id="95856-201">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="95856-201">**Status**</span></span>
   - <span data-ttu-id="95856-202">**Приоритет**</span><span class="sxs-lookup"><span data-stu-id="95856-202">**Priority**</span></span>
   - <span data-ttu-id="95856-203">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="95856-203">**Last modified**</span></span>

3. <span data-ttu-id="95856-204">При выборе политики, щелкнув имя, параметры политики отображаются в вылете.</span><span class="sxs-lookup"><span data-stu-id="95856-204">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a><span data-ttu-id="95856-205">Использование портала Microsoft 365 Defender для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-205">Use the Microsoft 365 Defender portal to modify anti-phishing policies</span></span>

1. <span data-ttu-id="95856-206">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики защиты от \>  \>  \>  \> **фишинга**.</span><span class="sxs-lookup"><span data-stu-id="95856-206">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="95856-207">На странице **Anti-phishing** выберите политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="95856-207">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="95856-208">Параметры политики будут показаны во всплывающем окне. Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="95856-208">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="95856-209">Дополнительные сведения о параметрах см. в разделе Использование портала [Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) для создания разделов политики защиты от фишинга в этой статье.</span><span class="sxs-lookup"><span data-stu-id="95856-209">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create anti-phishing policies](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="95856-210">Для политики защиты от фишинга по умолчанию раздел **Пользователи,** группы и домены недоступны (политика применяется ко всем), и переименовать политику нельзя.</span><span class="sxs-lookup"><span data-stu-id="95856-210">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="95856-211">Чтобы включить или отключить политику или установить порядок приоритета политики, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="95856-211">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="95856-212">Включить или отключить настраиваемые политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-212">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="95856-213">Вы не можете отключить политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="95856-213">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="95856-214">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики защиты от \>  \>  \>  \> **фишинга**.</span><span class="sxs-lookup"><span data-stu-id="95856-214">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="95856-215">На странице **Anti-phishing** выберите настраиваемую политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="95856-215">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="95856-216">Появится всплывающее окно со сведениями о политике. В верхней его части вы увидите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="95856-216">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="95856-217">**Политика отключена**. Чтобы включить политику, щелкните значок !["Включить"](../../media/m365-cc-sc-turn-on-off-icon.png) **Включить** .</span><span class="sxs-lookup"><span data-stu-id="95856-217">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="95856-218">**Политика включена**. Чтобы выключить политику, щелкните значок !["Отключить"](../../media/m365-cc-sc-turn-on-off-icon.png) **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="95856-218">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="95856-219">В диалоговом окне подтверждения нажмите кнопку **Включить** или **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="95856-219">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="95856-220">Во всплывающем окне сведений о политике нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="95856-220">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="95856-221">Когда вы вернетесь на главную страницу политики, значение параметра **Состояние** этой политики будет **Включена** или **Выключена**.</span><span class="sxs-lookup"><span data-stu-id="95856-221">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="95856-222">Установите приоритет настраиваемой политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-222">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="95856-223">По умолчанию политикам защиты от фишинга предоставляется приоритет, основанный на порядке, в который они были созданы (более новые политики имеют более низкий приоритет по сравнению с более старыми политиками).</span><span class="sxs-lookup"><span data-stu-id="95856-223">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="95856-224">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="95856-224">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="95856-225">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="95856-225">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="95856-226">Чтобы изменить приоритет политики, нажмите кнопку **Увеличить приоритет** или **Уменьшить приоритет** в свойствах политики (вы не можете напрямую изменить числовое значение параметра **Приоритет** на портале Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="95856-226">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="95856-227">Изменение приоритета политики имеет смысл, только если у вас несколько политик.</span><span class="sxs-lookup"><span data-stu-id="95856-227">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="95856-228">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="95856-228">**Notes**:</span></span>

- <span data-ttu-id="95856-229">На Microsoft 365 Defender вы можете изменить приоритет политики защиты от фишинга только после ее создания.</span><span class="sxs-lookup"><span data-stu-id="95856-229">In the Microsoft 365 Defender portal, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="95856-230">В PowerShell можно переопредить приоритет по умолчанию при создании правила защиты от фишинга (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="95856-230">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="95856-231">Политики защиты от фишинга обрабатываются в порядке отображения (первая политика имеет значение **Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="95856-231">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="95856-232">Политика защиты от фишинга по умолчанию имеет приоритетное значение **Самое** низкое, и изменить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="95856-232">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="95856-233">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики защиты от \>  \>  \>  \> **фишинга**.</span><span class="sxs-lookup"><span data-stu-id="95856-233">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="95856-234">На странице **Anti-phishing** выберите настраиваемую политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="95856-234">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="95856-235">Появится всплывающее окно со сведениями о политике. В верхней его части вы увидите одно из следующих значений: **Увеличить приоритет** или **Уменьшить приоритет** в зависимости от текущего значения приоритета и количества настраиваемых политик:</span><span class="sxs-lookup"><span data-stu-id="95856-235">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="95856-236">Политика со **значением Приоритет** **0** имеет только доступный параметр **Приоритет уменьшения.**</span><span class="sxs-lookup"><span data-stu-id="95856-236">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="95856-237">Политика с наименьшим **значением** Приоритет (например, **3)** имеет только доступный параметр **Increase priority.**</span><span class="sxs-lookup"><span data-stu-id="95856-237">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="95856-238">Если у вас есть три или более политик, политики между самыми высокими и самыми низкими значениями приоритетов имеют доступные параметры **приоритета Increase** и **Decrease.**</span><span class="sxs-lookup"><span data-stu-id="95856-238">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="95856-239">Щелкните ![Значок увеличения приоритета](../../media/m365-cc-sc-increase-icon.png) **Увеличить приоритет** или ![Значок уменьшения приоритета](../../media/m365-cc-sc-decrease-icon.png) **Уменьшить приоритет** чтобы изменить значение параметра **Приоритет**.</span><span class="sxs-lookup"><span data-stu-id="95856-239">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="95856-240">Закончив, нажмите **Закрыть** во всплывающем окне сведений о политике.</span><span class="sxs-lookup"><span data-stu-id="95856-240">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="95856-241">Использование портала Microsoft 365 Defender для удаления настраиваемой политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-241">Use the Microsoft 365 Defender portal to remove custom anti-phishing policies</span></span>

<span data-ttu-id="95856-242">При использовании портала Microsoft 365 Defender для удаления настраиваемой политики защиты от фишинга правило защиты от фишинга и соответствующая политика защиты от фишинга удаляются.</span><span class="sxs-lookup"><span data-stu-id="95856-242">When you use the Microsoft 365 Defender portal to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="95856-243">Вы не можете удалить политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="95856-243">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="95856-244">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики защиты от \>  \>  \>  \> **фишинга**.</span><span class="sxs-lookup"><span data-stu-id="95856-244">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="95856-245">На странице **Anti-phishing** выберите настраиваемую политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="95856-245">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="95856-246">В открывшемся всплывающем окне сведений о политике щелкните ![значок "Дополнительные действия"](../../media/m365-cc-sc-more-actions-icon.png) **Дополнительные действия** \> ![значок "Удалить политику"](../../media/m365-cc-sc-delete-icon.png) **Удалить политику**.</span><span class="sxs-lookup"><span data-stu-id="95856-246">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="95856-247">В диалоговом окне подтверждения нажмите **Да**.</span><span class="sxs-lookup"><span data-stu-id="95856-247">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="95856-248">Используйте Exchange Online PowerShell для настройки политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-248">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="95856-249">Как описано выше, политика защиты от фишинга состоит из политики защиты от фишинга и правила защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="95856-249">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="95856-250">В Exchange Online PowerShell разница между политиками защиты от фишинга и правилами защиты от фишинга очевидна.</span><span class="sxs-lookup"><span data-stu-id="95856-250">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="95856-251">Вы управляете политиками защиты от фишинга с помощью кодлетов **\* -AntiPhishPolicy** и управляете правилами защиты от фишинга с помощью cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="95856-251">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="95856-252">В PowerShell сначала создается политика защиты от фишинга, а затем создается правило защиты от фишинга, которое определяет политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="95856-252">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="95856-253">В PowerShell параметры политики защиты от фишинга и правила защиты от фишинга изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="95856-253">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="95856-254">При удалении политики защиты от фишинга из PowerShell соответствующее правило не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="95856-254">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="95856-255">Следующие процедуры PowerShell недоступны в автономных организациях EOP с Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95856-255">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="95856-256">Использование PowerShell для создания политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-256">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="95856-257">Создание политики защиты от фишинга в PowerShell — это двухшаговый процесс:</span><span class="sxs-lookup"><span data-stu-id="95856-257">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="95856-258">Создание политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="95856-258">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="95856-259">Создайте правило защиты от фишинга, которое указывает политику защиты от фишинга, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="95856-259">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="95856-260">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="95856-260">**Notes**:</span></span>

- <span data-ttu-id="95856-261">Вы можете создать новое правило защиты от фишинга и назначить ему существующую, неассоциированную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="95856-261">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="95856-262">Правило защиты от фишинга не может быть связано с одной политикой защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="95856-262">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="95856-263">Вы можете настроить следующие параметры для новых политик защиты от фишинга в PowerShell, недоступных на портале Microsoft 365 Defender до создания политики:</span><span class="sxs-lookup"><span data-stu-id="95856-263">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>

  - <span data-ttu-id="95856-264">Создайте новую политику как отключенную _(включена_ `$false` в **кодлете New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="95856-264">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="95856-265">Задай приоритет политики во время создания _(приоритет)_ в _\<Number\>_ **комлете New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="95856-265">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="95856-266">Новая политика защиты от фишинга, которую вы создаете в PowerShell, не отображается на портале Microsoft 365 Defender, пока не назначите политику правилу защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="95856-266">A new anti-phish policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="95856-267">Шаг 1. Использование PowerShell для создания политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-267">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="95856-268">Чтобы создать политику защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="95856-268">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

<span data-ttu-id="95856-269">В этом примере создается политика защиты от фишинга с именем Research Quarantine со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="95856-269">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="95856-270">Описание: Политика отдела исследований.</span><span class="sxs-lookup"><span data-stu-id="95856-270">The description is: Research department policy.</span></span>
- <span data-ttu-id="95856-271">Изменяет действие по умолчанию для подмены на карантин.</span><span class="sxs-lookup"><span data-stu-id="95856-271">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="95856-272">Подробные сведения о синтаксисе и параметрах см. в [обзоре New-AntiPhishPolicy.](/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="95856-272">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="95856-273">Шаг 2. Использование PowerShell для создания правила защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-273">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="95856-274">Чтобы создать правило защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="95856-274">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="95856-275">В этом примере создается правило защиты от фишинга с именем Research Department со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="95856-275">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="95856-276">Это правило связано с политикой защиты от фишинга с именем Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="95856-276">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="95856-277">Правило применяется к членам группы "Research Department".</span><span class="sxs-lookup"><span data-stu-id="95856-277">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="95856-278">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="95856-278">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="95856-279">Подробные сведения о синтаксисе и параметрах см. [в обзоре New-AntiPhishRule.](/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="95856-279">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="95856-280">Использование PowerShell для просмотра политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-280">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="95856-281">Чтобы просмотреть существующие политики защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="95856-281">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="95856-282">В этом примере возвращается сводный список всех политик защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="95856-282">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="95856-283">В этом примере возвращаются все значения свойств для политики защиты от фишинга с именем Executives.</span><span class="sxs-lookup"><span data-stu-id="95856-283">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="95856-284">Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-AntiPhishPolicy.](/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="95856-284">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="95856-285">Использование PowerShell для просмотра правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-285">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="95856-286">Чтобы просмотреть существующие правила защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="95856-286">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="95856-287">В этом примере возвращается сводный список всех правил по борьбе с фишингом вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="95856-287">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="95856-288">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="95856-288">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="95856-289">В этом примере возвращаются все значения свойств для правила защиты от фишинга с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="95856-289">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="95856-290">Подробные сведения о синтаксисе и параметрах см. в [ссылке Get-AntiPhishRule.](/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="95856-290">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="95856-291">Использование PowerShell для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-291">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="95856-292">Кроме следующих элементов, при изменении политики защиты от фишинга в PowerShell доступны те же параметры, что и при создании политики, описанной в шаге [1: Использование PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) для создания политики защиты от фишинга ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="95856-292">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="95856-293">Переключатель _MakeDefault,_ который превращает указанную политику в политику по  умолчанию (применяется для всех, всегда самый низкий приоритет, и вы не можете удалить ее) доступен только при изменении политики защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95856-293">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>
- <span data-ttu-id="95856-294">Нельзя переименовать политику защиты от фишинга (в **кодлете Set-AntiPhishPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="95856-294">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="95856-295">При переименовании политики защиты от фишинга на портале Microsoft 365 Defender вы только переименовывать правило защиты от _фишинга._</span><span class="sxs-lookup"><span data-stu-id="95856-295">When you rename an anti-phishing policy in the Microsoft 365 Defender portal, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="95856-296">Чтобы изменить политику защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="95856-296">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="95856-297">Подробные сведения о синтаксисе и параметрах см. в [инструкции Set-AntiPhishPolicy.](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="95856-297">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="95856-298">Использование PowerShell для изменения правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-298">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="95856-299">Единственным параметром, недоступным при изменении правила защиты от фишинга в PowerShell, является параметр _Включен,_ который позволяет создать правило отключения.</span><span class="sxs-lookup"><span data-stu-id="95856-299">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="95856-300">Чтобы включить или отключить существующие правила защиты от фишинга, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="95856-300">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="95856-301">В противном случае те же параметры доступны при создании правила, описанного в разделе [Шаг 2: Использование PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) для создания раздела правил по борьбе с фишингом ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="95856-301">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="95856-302">Чтобы изменить правило защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="95856-302">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="95856-303">Подробные сведения о синтаксисе и параметрах см. в [инструкции Set-AntiPhishRule.](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="95856-303">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="95856-304">Использование PowerShell, чтобы включить или отключить правила защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-304">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="95856-305">Включение или отключение правила защиты от фишинга в PowerShell включает или отключает всю политику защиты от фишинга (правило защиты от фишинга и назначенную политику защиты от фишинга).</span><span class="sxs-lookup"><span data-stu-id="95856-305">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="95856-306">Вы не можете включить или отключить политику защиты от фишинга по умолчанию (она всегда применяется к всем получателям).</span><span class="sxs-lookup"><span data-stu-id="95856-306">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="95856-307">Чтобы включить или отключить правило защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="95856-307">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="95856-308">В этом примере отключает правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="95856-308">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="95856-309">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="95856-309">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="95856-310">Подробные сведения о синтаксисе и параметрах см. в [сводке Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) и [Disable-AntiPhishRule.](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="95856-310">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="95856-311">Использование PowerShell для набора приоритета правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-311">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="95856-p131">Максимальный приоритет, который можно задать для правила, — 0. Минимальное значение зависит от количества правил. Например, если у вас есть пять правил, вы можете использовать значения 0-4. Изменение приоритета существующего правила оказывает каскадное влияние на другие правила. Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="95856-p131">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="95856-317">Чтобы установить приоритет правила защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="95856-317">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="95856-p132">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="95856-p132">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="95856-320">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="95856-320">**Notes**:</span></span>

- <span data-ttu-id="95856-321">Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в **комлете New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="95856-321">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>
- <span data-ttu-id="95856-322">Политика защиты от фишинга по умолчанию не имеет соответствующего правила по борьбе с фишингом, и всегда имеет неоплаченное значение приоритета **Самое низкое.**</span><span class="sxs-lookup"><span data-stu-id="95856-322">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="95856-323">Использование PowerShell для удаления политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-323">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="95856-324">При удалении политики защиты от фишинга с помощью PowerShell соответствующее правило по борьбе с фишингом не удаляется.</span><span class="sxs-lookup"><span data-stu-id="95856-324">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="95856-325">Чтобы удалить политику защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="95856-325">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="95856-326">В этом примере удаляется политика защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="95856-326">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="95856-327">Подробные сведения о синтаксисе и параметрах см. в [обзоре Remove-AntiPhishPolicy.](/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="95856-327">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="95856-328">Использование PowerShell для удаления правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="95856-328">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="95856-329">При удалении правила защиты от фишинга с помощью PowerShell соответствующая политика защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="95856-329">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="95856-330">Чтобы удалить правило защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="95856-330">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="95856-331">В этом примере удаляется правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="95856-331">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="95856-332">Подробные сведения о синтаксисе и параметрах см. в [инструкции Remove-AntiPhishRule.](/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="95856-332">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="95856-333">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="95856-333">How do you know these procedures worked?</span></span>

<span data-ttu-id="95856-334">Чтобы убедиться, что вы успешно настроены политики защиты от фишинга в EOP, сделайте все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="95856-334">To verify that you've successfully configured anti-phishing policies in EOP, do any of the following steps:</span></span>

- <span data-ttu-id="95856-335">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики защиты от \>  \>  \>  \> **фишинга**.</span><span class="sxs-lookup"><span data-stu-id="95856-335">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="95856-336">Проверка списка политик, их значений **состояния** и **их значений приоритета.**</span><span class="sxs-lookup"><span data-stu-id="95856-336">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="95856-337">Чтобы просмотреть дополнительные сведения, выберите политику из списка, нажав на имя и просмотрев сведения в вылете, который появится.</span><span class="sxs-lookup"><span data-stu-id="95856-337">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="95856-338">В Exchange Online PowerShell замените имя политики или правила, запустите следующую команду и проверьте \<Name\> параметры:</span><span class="sxs-lookup"><span data-stu-id="95856-338">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
