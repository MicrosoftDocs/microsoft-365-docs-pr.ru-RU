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
ms.openlocfilehash: f074596f0391e98735b07d17390cd058fd6fcafe
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793020"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="28c07-103">Настройка политик защиты от фишинга в EOP</span><span class="sxs-lookup"><span data-stu-id="28c07-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="28c07-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="28c07-104">**Applies to**</span></span>
- [<span data-ttu-id="28c07-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="28c07-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="28c07-106">В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без Exchange Online почтовых ящиков по умолчанию существует политика защиты от фишинга, которая содержит ограниченное количество функций защиты от спуфинга, которые включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="28c07-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="28c07-107">Дополнительные сведения см. в статье [Параметры фишинга в политиках защиты от фишинга](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="28c07-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="28c07-108">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="28c07-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="28c07-109">Для большей детализации можно также создать настраиваемые политики защиты от фишинга, применимые к определенным пользователям, группам или доменам в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="28c07-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="28c07-110">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="28c07-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="28c07-111">Организации с Exchange Online почтовыми ящиками могут настраивать политики защиты от фишинга в центре Microsoft 365 безопасности или Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28c07-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Microsoft 365 security center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="28c07-112">Автономные организации EOP могут использовать только центр безопасности.</span><span class="sxs-lookup"><span data-stu-id="28c07-112">Standalone EOP organizations can only use the security center.</span></span>

<span data-ttu-id="28c07-113">Сведения о создании и изменении более продвинутых политик защиты от фишинга, доступных в Microsoft Defender для Office 365, см. в руб. Настройка политик защиты от фишинга в [Microsoft Defender](configure-atp-anti-phishing-policies.md)для Office 365 .</span><span class="sxs-lookup"><span data-stu-id="28c07-113">For information about creating and modifying the more advanced anti-phishing policies that are available in Microsoft Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="28c07-114">Основные элементы политики защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="28c07-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="28c07-115">**Политика защиты от фишинга:** указывает средства защиты от фишинга, чтобы включить или отключить, а также действия по применении параметров.</span><span class="sxs-lookup"><span data-stu-id="28c07-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="28c07-116">**Правило защиты от фишинга:** указывает фильтры приоритета и получателей (к кому применяется политика) для политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="28c07-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="28c07-117">Разница между этими двумя элементами не очевидна при управлении политиками защиты от фишинга в центре безопасности:</span><span class="sxs-lookup"><span data-stu-id="28c07-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the security center:</span></span>

- <span data-ttu-id="28c07-118">При создании политики защиты от фишинга создается правило защиты от фишинга и связанная с ним политика защиты от фишинга, используя одно и то же имя для обоих.</span><span class="sxs-lookup"><span data-stu-id="28c07-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="28c07-119">При изменении политики защиты от фишинга параметры, связанные с именем, приоритетом, включенной или отключенной, а также фильтры получателей изменяют правило защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="28c07-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="28c07-120">Все остальные параметры изменяют связанную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="28c07-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="28c07-121">При удалении политики защиты от фишинга правило защиты от фишинга и связанная с ним политика защиты от фишинга удаляются.</span><span class="sxs-lookup"><span data-stu-id="28c07-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="28c07-122">В Exchange Online PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="28c07-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="28c07-123">Дополнительные сведения см. в [разделе Использование Exchange Online PowerShell для](#use-exchange-online-powershell-to-configure-anti-phishing-policies) настройки политики защиты от фишинга в этой статье.</span><span class="sxs-lookup"><span data-stu-id="28c07-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="28c07-124">Каждая организация имеет встроенную политику защиты от фишинга с именем Office365 AntiPhish Default, которая имеет эти свойства:</span><span class="sxs-lookup"><span data-stu-id="28c07-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="28c07-125">Политика применяется к всем получателям в организации, несмотря на отсутствие правила защиты от фишинга (фильтры получателей), связанного с политикой.</span><span class="sxs-lookup"><span data-stu-id="28c07-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="28c07-126">Для политики задано специальное значение приоритета **Самый низкий**, которое невозможно изменить (эта политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="28c07-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="28c07-127">Все созданные специальные политики всегда имеют более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="28c07-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="28c07-128">Эта политика является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.</span><span class="sxs-lookup"><span data-stu-id="28c07-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="28c07-129">Чтобы повысить эффективность защиты от фишинга, можно создать настраиваемые политики защиты от фишинга с более строгими настройками, которые применяются к конкретным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="28c07-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="28c07-130">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="28c07-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="28c07-131">Открытие Центра безопасности производится в <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="28c07-131">You open the security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="28c07-132">Чтобы перейти непосредственно на страницу **anti-phishing,** используйте <https://security.microsoft.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="28c07-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="28c07-133">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="28c07-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="28c07-134">Вы не можете управлять политиками защиты от фишинга в автономных EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28c07-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="28c07-135">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="28c07-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="28c07-136">Чтобы добавить, изменить и удалить политики защиты от фишинга, необходимо  быть членом групп ролей администратора организации или **администратора** безопасности.</span><span class="sxs-lookup"><span data-stu-id="28c07-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="28c07-137">Для доступа только для чтения к политикам защиты от фишинга необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="28c07-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="28c07-138">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="28c07-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="28c07-139">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="28c07-139">**Notes**:</span></span>

  - <span data-ttu-id="28c07-140">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="28c07-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="28c07-141">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="28c07-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="28c07-142">Группа **ролей только** для организации просмотра в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой <sup>\*</sup> функции.</span><span class="sxs-lookup"><span data-stu-id="28c07-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>

- <span data-ttu-id="28c07-143">Рекомендуемые параметры для политик защиты от фишинга см. в рекомендациях EOP по борьбе [с фишингом.](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="28c07-143">For our recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="28c07-144">Разрешить до 30 минут для обновленной политики, которая будет применяться.</span><span class="sxs-lookup"><span data-stu-id="28c07-144">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="28c07-145">Сведения о том, где политики защиты от фишинга применяются в конвейере фильтрации, см. в рублях [Order и precedence of email protection.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="28c07-145">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security-center-to-create-anti-phishing-policies"></a><span data-ttu-id="28c07-146">Используйте центр безопасности для создания политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-146">Use the security center to create anti-phishing policies</span></span>

<span data-ttu-id="28c07-147">Создание настраиваемой политики защиты от фишинга в центре безопасности создает правило защиты от фишинга и связанную политику защиты от фишинга, одновременно используя одно и то же имя для обоих.</span><span class="sxs-lookup"><span data-stu-id="28c07-147">Creating a custom anti-phishing policy in the security center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="28c07-148">В центре безопасности перейдите в раздел Политики **совместной** & электронной почты & политики угрозы правил \>  \>  \>  раздела \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="28c07-148">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="28c07-149">На странице **Anti-phishing** нажмите кнопку ![ Создать значок ](../../media/m365-cc-sc-create-icon.png) **Создать**.</span><span class="sxs-lookup"><span data-stu-id="28c07-149">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="28c07-150">Откроется мастер политик.</span><span class="sxs-lookup"><span data-stu-id="28c07-150">The policy wizard opens.</span></span> <span data-ttu-id="28c07-151">На странице **Имя политики** настройте эти параметры:</span><span class="sxs-lookup"><span data-stu-id="28c07-151">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="28c07-152">**Имя**. Укажите уникальное, описательное имя политики.</span><span class="sxs-lookup"><span data-stu-id="28c07-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="28c07-153">**Описание**. По желанию введите описание политики.</span><span class="sxs-lookup"><span data-stu-id="28c07-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="28c07-154">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="28c07-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="28c07-155">На открывшейся странице **Пользователи, группы и домены** определите внутренних получателей, к которым применяется политика (условия получателей):</span><span class="sxs-lookup"><span data-stu-id="28c07-155">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="28c07-156">**Пользователи**: указывает один или несколько почтовых ящиков, пользователей почты или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="28c07-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="28c07-157">**Группы**: указывает группы рассылки, группы безопасности с поддержкой почты или группы Microsoft 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="28c07-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="28c07-158">**Домены**: все получатели в указанных [обслуживаемых доменах](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="28c07-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="28c07-159">Щелкните соответствующее поле, начните вводить значение и выберите нужное значение в результатах.</span><span class="sxs-lookup"><span data-stu-id="28c07-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="28c07-160">Повторите эти действия необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="28c07-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="28c07-161">Чтобы удалить существующее значение, нажмите "Удалить".</span><span class="sxs-lookup"><span data-stu-id="28c07-161">To remove an existing value, click remove</span></span> ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="28c07-163">рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="28c07-163">next to the value.</span></span>

   <span data-ttu-id="28c07-164">Для пользователей и групп можно использовать большинство идентификаторов (имя, отображаемое имя, псевдоним, адрес электронной почты, имя учетной записи и т. д.), но в результатах будет выведено отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="28c07-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="28c07-165">Для получения списка всех пользователей введите звездочку (\*) без добавлений, чтобы увидеть все доступные значения.</span><span class="sxs-lookup"><span data-stu-id="28c07-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="28c07-166">Указать несколько значений в одном условии можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="28c07-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="28c07-167">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="28c07-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="28c07-168">**Исключить этих пользователей, группы и домены**. Чтобы добавить исключения для внутренних получателей, к которым применяется политика (исключение получателей), выберите этот параметр и настройте исключения.</span><span class="sxs-lookup"><span data-stu-id="28c07-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="28c07-169">Настройки и поведение такие же, как в разделе условий.</span><span class="sxs-lookup"><span data-stu-id="28c07-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="28c07-170">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="28c07-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="28c07-171">На странице **защиты &** фишинга, чтобы включить  или отключить подмену сведений, используйте поле Включить подмену сведений.</span><span class="sxs-lookup"><span data-stu-id="28c07-171">On the **Phishing threshold & protection** page that appears, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="28c07-172">Значение по умолчанию находится на (выбранном), и мы рекомендуем оставить его.</span><span class="sxs-lookup"><span data-stu-id="28c07-172">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="28c07-173">Вы настраиваете действие для принятия заблокированных поддельных сообщений на следующей странице.</span><span class="sxs-lookup"><span data-stu-id="28c07-173">You configure the action to take on blocked spoofed messages on the next page.</span></span>

   <span data-ttu-id="28c07-174">Чтобы отключить подмену сведений, очистить поле.</span><span class="sxs-lookup"><span data-stu-id="28c07-174">To turn off spoof intelligence, clear the check box.</span></span>

   > [!NOTE]
   > <span data-ttu-id="28c07-175">Вам не нужно отключать защиту от подмены, если запись MX не означает Microsoft 365; Вместо этого вы включаете усиленную фильтрацию соединителя.</span><span class="sxs-lookup"><span data-stu-id="28c07-175">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="28c07-176">Инструкции см. в [расширенной фильтрации соединители в Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="28c07-176">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="28c07-177">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="28c07-177">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="28c07-178">В открывшемся окне **Действия** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="28c07-178">On the **Actions** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="28c07-179">**Если сообщение обнаружено как поддельный:** этот параметр доступен только в том случае, если вы выбрали **сведения о** подмене на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="28c07-179">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="28c07-180">Выберите одно из следующих действий в списке выпадения для сообщений от заблокированных поддельных отправителей:</span><span class="sxs-lookup"><span data-stu-id="28c07-180">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
     - <span data-ttu-id="28c07-181">**Перемещение сообщения в папки нежелательной почты получателей**</span><span class="sxs-lookup"><span data-stu-id="28c07-181">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="28c07-182">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="28c07-182">**Quarantine the message**</span></span>

   - <span data-ttu-id="28c07-183">**Советы по &** безопасности: этот параметр доступен только в том случае, если вы выбрали **сведения о** подмене на предыдущей странице:</span><span class="sxs-lookup"><span data-stu-id="28c07-183">**Safety tips & indicators**: This setting is available only if you selected **Enable spoof intelligence** on the previous page:</span></span>
     - <span data-ttu-id="28c07-184">**Показать (?)** для неавентированных отправителей для подмены: добавляет знак вопроса на фотографию отправителей в поле From в Outlook, если сообщение  не проходит проверки SPF или DKIM и сообщение не проходит DMARC или композитную проверку подлинности [.](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="28c07-184">**Show (?) for unauthenticated senders for spoof**: Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="28c07-185">**Показать тег "via":** добавляет тег chris@contoso.com через fabrikam.com) в адрес From, если он отличается от домена в подписи DKIM или адреса **MAIL FROM.**</span><span class="sxs-lookup"><span data-stu-id="28c07-185">**Show "via" tag**: Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span>

       > [!NOTE]
       > <span data-ttu-id="28c07-186">В настоящее **время параметр тега Show "via"** доступен не во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="28c07-186">Currently, the **Show "via" tag** setting is not available in all organizations.</span></span> <span data-ttu-id="28c07-187">Если у вас нет параметра тега **Show "via",** знак вопроса и тег через контролируются командой **Show (?)** для неавентированных отправителей для настройки подмены в организации. </span><span class="sxs-lookup"><span data-stu-id="28c07-187">If you don't have the **Show "via" tag** setting, the the question mark **and** the via tag are both controlled by the **Show (?) for unauthenticated senders for spoof** setting in your organization.</span></span>

     <span data-ttu-id="28c07-188">Чтобы включить параметр, выберите поле для проверки.</span><span class="sxs-lookup"><span data-stu-id="28c07-188">To turn on a setting, select the check box.</span></span> <span data-ttu-id="28c07-189">Чтобы отключить его, зачистите контрольный ящик.</span><span class="sxs-lookup"><span data-stu-id="28c07-189">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="28c07-190">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="28c07-190">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="28c07-191">На странице **Просмотр** просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="28c07-191">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="28c07-192">Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="28c07-192">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="28c07-193">Или вы можете щелкнуть **кнопку Назад** или выбрать определенную страницу в мастере.</span><span class="sxs-lookup"><span data-stu-id="28c07-193">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="28c07-194">По завершению нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="28c07-194">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="28c07-195">На странице подтверждения, которая откроется, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="28c07-195">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-security-center-to-view-anti-phishing-policies"></a><span data-ttu-id="28c07-196">Используйте центр безопасности для просмотра политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-196">Use the security center to view anti-phishing policies</span></span>

1. <span data-ttu-id="28c07-197">В центре безопасности перейдите в раздел Политики **совместной** & электронной почты & политики угрозы правил \>  \>  \>  раздела \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="28c07-197">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="28c07-198">На странице **Anti-phishing** в списке политик защиты от фишинга отображаются следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="28c07-198">On the **Anti-phishing** page, the following properties are displayed in the list of anti-phishing policies:</span></span>

   - <span data-ttu-id="28c07-199">**Имя**</span><span class="sxs-lookup"><span data-stu-id="28c07-199">**Name**</span></span>
   - <span data-ttu-id="28c07-200">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="28c07-200">**Status**</span></span>
   - <span data-ttu-id="28c07-201">**Приоритет**</span><span class="sxs-lookup"><span data-stu-id="28c07-201">**Priority**</span></span>
   - <span data-ttu-id="28c07-202">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="28c07-202">**Last modified**</span></span>

3. <span data-ttu-id="28c07-203">При выборе политики, щелкнув имя, параметры политики отображаются в вылете.</span><span class="sxs-lookup"><span data-stu-id="28c07-203">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-security-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="28c07-204">Используйте центр безопасности для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-204">Use the security center to modify anti-phishing policies</span></span>

1. <span data-ttu-id="28c07-205">В центре безопасности перейдите в раздел Политики **совместной** & электронной почты & политики угрозы правил \>  \>  \>  раздела \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="28c07-205">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="28c07-206">На странице **Anti-phishing** выберите политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="28c07-206">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="28c07-207">Параметры политики будут показаны во всплывающем окне. Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="28c07-207">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="28c07-208">Дополнительные сведения о параметрах см. в разделе [Использование](#use-the-security-center-to-create-anti-phishing-policies) центра безопасности для создания разделов политики защиты от фишинга в этой статье.</span><span class="sxs-lookup"><span data-stu-id="28c07-208">For more information about the settings, see the [Use the security center to create anti-phishing policies](#use-the-security-center-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="28c07-209">Для политики защиты от фишинга по умолчанию раздел **Пользователи,** группы и домены недоступны (политика применяется ко всем), и переименовать политику нельзя.</span><span class="sxs-lookup"><span data-stu-id="28c07-209">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="28c07-210">Чтобы включить или отключить политику или установить порядок приоритета политики, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="28c07-210">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="28c07-211">Включить или отключить настраиваемые политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-211">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="28c07-212">Вы не можете отключить политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="28c07-212">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="28c07-213">В центре безопасности перейдите в раздел Политики **совместной** & электронной почты & политики угрозы правил \>  \>  \>  раздела \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="28c07-213">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="28c07-214">На странице **Anti-phishing** выберите настраиваемую политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="28c07-214">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="28c07-215">Появится всплывающее окно со сведениями о политике. В верхней его части вы увидите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="28c07-215">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="28c07-216">**Политика отключена**. Чтобы включить политику, щелкните значок !["Включить"](../../media/m365-cc-sc-turn-on-off-icon.png) **Включить** .</span><span class="sxs-lookup"><span data-stu-id="28c07-216">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="28c07-217">**Политика включена**. Чтобы выключить политику, щелкните значок !["Отключить"](../../media/m365-cc-sc-turn-on-off-icon.png) **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="28c07-217">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="28c07-218">В диалоговом окне подтверждения нажмите кнопку **Включить** или **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="28c07-218">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="28c07-219">Во всплывающем окне сведений о политике нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="28c07-219">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="28c07-220">Когда вы вернетесь на главную страницу политики, значение параметра **Состояние** этой политики будет **Включена** или **Выключена**.</span><span class="sxs-lookup"><span data-stu-id="28c07-220">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="28c07-221">Установите приоритет настраиваемой политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-221">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="28c07-222">По умолчанию политикам защиты от фишинга предоставляется приоритет, основанный на порядке, в который они были созданы (более новые политики имеют более низкий приоритет по сравнению с более старыми политиками).</span><span class="sxs-lookup"><span data-stu-id="28c07-222">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="28c07-223">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="28c07-223">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="28c07-224">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="28c07-224">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="28c07-225">Чтобы изменить приоритет политики, нажмите кнопку **Увеличить приоритет** или **Уменьшить приоритет** в свойствах политики (вы не можете напрямую изменить числовое значение параметра **Приоритет** в центре безопасности).</span><span class="sxs-lookup"><span data-stu-id="28c07-225">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the security center).</span></span> <span data-ttu-id="28c07-226">Изменение приоритета политики имеет смысл, только если у вас несколько политик.</span><span class="sxs-lookup"><span data-stu-id="28c07-226">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="28c07-227">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="28c07-227">**Notes**:</span></span>

- <span data-ttu-id="28c07-228">В центре безопасности можно изменить приоритет политики защиты от фишинга только после ее создания.</span><span class="sxs-lookup"><span data-stu-id="28c07-228">In the security center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="28c07-229">В PowerShell можно переопредить приоритет по умолчанию при создании правила защиты от фишинга (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="28c07-229">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="28c07-230">Политики защиты от фишинга обрабатываются в порядке отображения (первая политика имеет значение **Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="28c07-230">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="28c07-231">Политика защиты от фишинга по умолчанию имеет приоритетное значение **Самое** низкое, и изменить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="28c07-231">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="28c07-232">В центре безопасности перейдите в раздел Политики **совместной** & электронной почты & политики угрозы правил \>  \>  \>  раздела \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="28c07-232">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="28c07-233">На странице **Anti-phishing** выберите настраиваемую политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="28c07-233">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="28c07-234">Появится всплывающее окно со сведениями о политике. В верхней его части вы увидите одно из следующих значений: **Увеличить приоритет** или **Уменьшить приоритет** в зависимости от текущего значения приоритета и количества настраиваемых политик:</span><span class="sxs-lookup"><span data-stu-id="28c07-234">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="28c07-235">Политика защиты от фишинга со значением **Priority** **0** имеет только доступный параметр **Decrease priority.**</span><span class="sxs-lookup"><span data-stu-id="28c07-235">The anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="28c07-236">Политика защиты от фишинга  с наименьшим значением Приоритет (например, **3)** имеет только доступный параметр **Increase priority.**</span><span class="sxs-lookup"><span data-stu-id="28c07-236">The anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="28c07-237">Если у вас есть три или более политик защиты от фишинга, политики между самыми высокими и самыми низкими значениями приоритетов имеют доступные параметры **приоритета Increase** и **Decrease.**</span><span class="sxs-lookup"><span data-stu-id="28c07-237">If you have three or more anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="28c07-238">Щелкните ![Значок увеличения приоритета](../../media/m365-cc-sc-increase-icon.png) **Увеличить приоритет** или ![Значок уменьшения приоритета](../../media/m365-cc-sc-decrease-icon.png) **Уменьшить приоритет** чтобы изменить значение параметра **Приоритет**.</span><span class="sxs-lookup"><span data-stu-id="28c07-238">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="28c07-239">Закончив, нажмите **Закрыть** во всплывающем окне сведений о политике.</span><span class="sxs-lookup"><span data-stu-id="28c07-239">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-security-center-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="28c07-240">Используйте центр безопасности для удаления настраиваемой политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-240">Use the security center to remove custom anti-phishing policies</span></span>

<span data-ttu-id="28c07-241">При удалении настраиваемой политики защиты от фишинга с помощью центра безопасности правило защиты от фишинга и соответствующая политика защиты от фишинга удаляются.</span><span class="sxs-lookup"><span data-stu-id="28c07-241">When you use the security center to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="28c07-242">Вы не можете удалить политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="28c07-242">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="28c07-243">В центре безопасности перейдите в раздел Политики **совместной** & электронной почты & политики угрозы правил \>  \>  \>  раздела \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="28c07-243">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="28c07-244">Выберите настраиваемую политику из списка, щелкнув имя политики.</span><span class="sxs-lookup"><span data-stu-id="28c07-244">Select a custom policy from the list by clicking on the name of the policy.</span></span> <span data-ttu-id="28c07-245">В открывшемся всплывающем окне сведений о политике щелкните ![значок "Дополнительные действия"](../../media/m365-cc-sc-more-actions-icon.png) **Дополнительные действия** \> ![значок "Удалить политику"](../../media/m365-cc-sc-delete-icon.png) **Удалить политику**.</span><span class="sxs-lookup"><span data-stu-id="28c07-245">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="28c07-246">В диалоговом окне подтверждения нажмите **Да**.</span><span class="sxs-lookup"><span data-stu-id="28c07-246">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="28c07-247">Используйте Exchange Online PowerShell для настройки политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-247">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="28c07-248">Как описано выше, политика защиты от фишинга состоит из политики защиты от фишинга и правила защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="28c07-248">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="28c07-249">В Exchange Online PowerShell разница между политиками защиты от фишинга и правилами защиты от фишинга очевидна.</span><span class="sxs-lookup"><span data-stu-id="28c07-249">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="28c07-250">Вы управляете политиками защиты от фишинга с помощью кодлетов **\* -AntiPhishPolicy** и управляете правилами защиты от фишинга с помощью cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="28c07-250">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="28c07-251">В PowerShell сначала создается политика защиты от фишинга, а затем создается правило защиты от фишинга, которое определяет политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="28c07-251">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="28c07-252">В PowerShell параметры политики защиты от фишинга и правила защиты от фишинга изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="28c07-252">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="28c07-253">При удалении политики защиты от фишинга из PowerShell соответствующее правило не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="28c07-253">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="28c07-254">Следующие процедуры PowerShell недоступны в автономных организациях EOP с Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28c07-254">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="28c07-255">Использование PowerShell для создания политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-255">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="28c07-256">Создание политики защиты от фишинга в PowerShell — это двухшаговый процесс:</span><span class="sxs-lookup"><span data-stu-id="28c07-256">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="28c07-257">Создание политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="28c07-257">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="28c07-258">Создайте правило защиты от фишинга, которое указывает политику защиты от фишинга, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="28c07-258">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="28c07-259">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="28c07-259">**Notes**:</span></span>

- <span data-ttu-id="28c07-260">Вы можете создать новое правило защиты от фишинга и назначить ему существующую, неассоциированную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="28c07-260">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="28c07-261">Правило защиты от фишинга не может быть связано с одной политикой защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="28c07-261">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="28c07-262">Вы можете настроить следующие параметры для новых политик защиты от фишинга в PowerShell, которые недоступны в центре безопасности до момента создания политики:</span><span class="sxs-lookup"><span data-stu-id="28c07-262">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the security center until after you create the policy:</span></span>

  - <span data-ttu-id="28c07-263">Создайте новую политику как отключенную _(включена_ `$false` в **кодлете New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="28c07-263">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="28c07-264">Задай приоритет политики во время создания _(приоритет)_ в _\<Number\>_ **комлете New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="28c07-264">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="28c07-265">Новая политика защиты от фишинга, которую вы создаете в PowerShell, не отображается в центре безопасности, пока не назначите политику правилу защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="28c07-265">A new anti-phish policy that you create in PowerShell isn't visible in the security center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="28c07-266">Шаг 1. Использование PowerShell для создания политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-266">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="28c07-267">Чтобы создать политику защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="28c07-267">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

<span data-ttu-id="28c07-268">В этом примере создается политика защиты от фишинга с именем Research Quarantine со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="28c07-268">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="28c07-269">Описание: Политика отдела исследований.</span><span class="sxs-lookup"><span data-stu-id="28c07-269">The description is: Research department policy.</span></span>
- <span data-ttu-id="28c07-270">Изменяет действие по умолчанию для подмены на карантин.</span><span class="sxs-lookup"><span data-stu-id="28c07-270">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="28c07-271">Подробные сведения о синтаксисе и параметрах см. в [обзоре New-AntiPhishPolicy.](/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="28c07-271">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="28c07-272">Шаг 2. Использование PowerShell для создания правила защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-272">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="28c07-273">Чтобы создать правило защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="28c07-273">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="28c07-274">В этом примере создается правило защиты от фишинга с именем Research Department со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="28c07-274">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="28c07-275">Это правило связано с политикой защиты от фишинга с именем Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="28c07-275">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="28c07-276">Правило применяется к членам группы "Research Department".</span><span class="sxs-lookup"><span data-stu-id="28c07-276">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="28c07-277">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="28c07-277">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="28c07-278">Подробные сведения о синтаксисе и параметрах см. [в обзоре New-AntiPhishRule.](/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="28c07-278">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="28c07-279">Использование PowerShell для просмотра политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-279">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="28c07-280">Чтобы просмотреть существующие политики защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="28c07-280">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="28c07-281">В этом примере возвращается сводный список всех политик защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="28c07-281">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="28c07-282">В этом примере возвращаются все значения свойств для политики защиты от фишинга с именем Executives.</span><span class="sxs-lookup"><span data-stu-id="28c07-282">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="28c07-283">Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-AntiPhishPolicy.](/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="28c07-283">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="28c07-284">Использование PowerShell для просмотра правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-284">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="28c07-285">Чтобы просмотреть существующие правила защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="28c07-285">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="28c07-286">В этом примере возвращается сводный список всех правил по борьбе с фишингом вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="28c07-286">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="28c07-287">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="28c07-287">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="28c07-288">В этом примере возвращаются все значения свойств для правила защиты от фишинга с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="28c07-288">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="28c07-289">Подробные сведения о синтаксисе и параметрах см. в [ссылке Get-AntiPhishRule.](/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="28c07-289">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="28c07-290">Использование PowerShell для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-290">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="28c07-291">Кроме следующих элементов, при изменении политики защиты от фишинга в PowerShell доступны те же параметры, что и при создании политики, описанной в шаге [1: Использование PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) для создания политики защиты от фишинга ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="28c07-291">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="28c07-292">Переключатель _MakeDefault,_ который превращает указанную политику в политику по  умолчанию (применяется для всех, всегда самый низкий приоритет, и вы не можете удалить ее) доступен только при изменении политики защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28c07-292">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>
- <span data-ttu-id="28c07-293">Нельзя переименовать политику защиты от фишинга (в **кодлете Set-AntiPhishPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="28c07-293">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="28c07-294">При переименовании политики защиты от фишинга в центре безопасности можно только переименовать правило защиты от _фишинга._</span><span class="sxs-lookup"><span data-stu-id="28c07-294">When you rename an anti-phishing policy in the security center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="28c07-295">Чтобы изменить политику защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="28c07-295">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="28c07-296">Подробные сведения о синтаксисе и параметрах см. в [инструкции Set-AntiPhishPolicy.](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="28c07-296">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="28c07-297">Использование PowerShell для изменения правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-297">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="28c07-298">Единственным параметром, недоступным при изменении правила защиты от фишинга в PowerShell, является параметр _Включен,_ который позволяет создать правило отключения.</span><span class="sxs-lookup"><span data-stu-id="28c07-298">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="28c07-299">Чтобы включить или отключить существующие правила защиты от фишинга, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="28c07-299">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="28c07-300">В противном случае те же параметры доступны при создании правила, описанного в разделе [Шаг 2: Использование PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) для создания раздела правил по борьбе с фишингом ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="28c07-300">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="28c07-301">Чтобы изменить правило защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="28c07-301">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="28c07-302">Подробные сведения о синтаксисе и параметрах см. в [инструкции Set-AntiPhishRule.](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="28c07-302">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="28c07-303">Использование PowerShell, чтобы включить или отключить правила защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-303">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="28c07-304">Включение или отключение правила защиты от фишинга в PowerShell включает или отключает всю политику защиты от фишинга (правило защиты от фишинга и назначенную политику защиты от фишинга).</span><span class="sxs-lookup"><span data-stu-id="28c07-304">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="28c07-305">Вы не можете включить или отключить политику защиты от фишинга по умолчанию (она всегда применяется к всем получателям).</span><span class="sxs-lookup"><span data-stu-id="28c07-305">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="28c07-306">Чтобы включить или отключить правило защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="28c07-306">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="28c07-307">В этом примере отключает правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="28c07-307">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="28c07-308">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="28c07-308">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="28c07-309">Подробные сведения о синтаксисе и параметрах см. в [сводке Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) и [Disable-AntiPhishRule.](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="28c07-309">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="28c07-310">Использование PowerShell для набора приоритета правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-310">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="28c07-p132">Максимальный приоритет, который можно задать для правила, — 0. Минимальное значение зависит от количества правил. Например, если у вас есть пять правил, вы можете использовать значения 0-4. Изменение приоритета существующего правила оказывает каскадное влияние на другие правила. Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="28c07-p132">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="28c07-316">Чтобы установить приоритет правила защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="28c07-316">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="28c07-p133">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="28c07-p133">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="28c07-319">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="28c07-319">**Notes**:</span></span>

- <span data-ttu-id="28c07-320">Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в **комлете New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="28c07-320">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>
- <span data-ttu-id="28c07-321">Политика защиты от фишинга по умолчанию не имеет соответствующего правила по борьбе с фишингом, и всегда имеет неоплаченное значение приоритета **Самое низкое.**</span><span class="sxs-lookup"><span data-stu-id="28c07-321">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="28c07-322">Использование PowerShell для удаления политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-322">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="28c07-323">При удалении политики защиты от фишинга с помощью PowerShell соответствующее правило по борьбе с фишингом не удаляется.</span><span class="sxs-lookup"><span data-stu-id="28c07-323">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="28c07-324">Чтобы удалить политику защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="28c07-324">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="28c07-325">В этом примере удаляется политика защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="28c07-325">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="28c07-326">Подробные сведения о синтаксисе и параметрах см. в [обзоре Remove-AntiPhishPolicy.](/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="28c07-326">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="28c07-327">Использование PowerShell для удаления правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="28c07-327">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="28c07-328">При удалении правила защиты от фишинга с помощью PowerShell соответствующая политика защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="28c07-328">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="28c07-329">Чтобы удалить правило защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="28c07-329">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="28c07-330">В этом примере удаляется правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="28c07-330">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="28c07-331">Подробные сведения о синтаксисе и параметрах см. в [инструкции Remove-AntiPhishRule.](/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="28c07-331">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="28c07-332">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="28c07-332">How do you know these procedures worked?</span></span>

<span data-ttu-id="28c07-333">Чтобы убедиться, что вы успешно настроены политики защиты от фишинга в EOP, сделайте все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="28c07-333">To verify that you've successfully configured anti-phishing policies in EOP, do any of the following steps:</span></span>

- <span data-ttu-id="28c07-334">В центре безопасности перейдите в раздел Политики **совместной** & электронной почты & политики угрозы правил \>  \>  \>  раздела \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="28c07-334">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="28c07-335">Проверка списка политик, их значений **состояния** и **их значений приоритета.**</span><span class="sxs-lookup"><span data-stu-id="28c07-335">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="28c07-336">Чтобы просмотреть дополнительные сведения, выберите политику из списка, нажав на имя и просмотрев сведения в вылете, который появится.</span><span class="sxs-lookup"><span data-stu-id="28c07-336">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="28c07-337">В Exchange Online PowerShell замените имя политики или правила, запустите следующую команду и проверьте \<Name\> параметры:</span><span class="sxs-lookup"><span data-stu-id="28c07-337">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
