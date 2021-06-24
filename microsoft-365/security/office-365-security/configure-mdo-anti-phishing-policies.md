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
ms.openlocfilehash: 1a948604f11064f2c1fefcc441adc4a9792ac918
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108443"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8eb8f-103">Настройка политик защиты от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="8eb8f-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8eb8f-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-104">**Applies to**</span></span>
- [<span data-ttu-id="8eb8f-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="8eb8f-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8eb8f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8eb8f-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8eb8f-107">Политики защиты от фишинга в [Microsoft Defender для](defender-for-office-365.md) Office 365 могут защитить организацию от вредоносных фишинговых атак на основе обезличения и других типов фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="8eb8f-108">Дополнительные сведения о различиях между политиками защиты от фишинга в Exchange Online Protection (EOP) и антифишинговыми политиками в Microsoft Defender для Office 365 см. в этой [записи.](anti-phishing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="8eb8f-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="8eb8f-109">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="8eb8f-110">Для большей детализации можно также создать настраиваемые политики защиты от фишинга, применимые к определенным пользователям, группам или доменам в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="8eb8f-111">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="8eb8f-112">Вы можете настроить политики защиты от фишинга в Defender для Office 365 на портале Microsoft 365 Defender или в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-112">You can configure anti-phishing policies in Defender for Office 365 in the Microsoft 365 Defender portal or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="8eb8f-113">Сведения о настройке более ограниченных в антифишинговых политиках, доступных в Exchange Online Protection (то есть организациях без Defender для Office 365), см. в [веб-сайте Configure anti-phishing policies in EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="8eb8f-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection (that is, organizations without Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="8eb8f-114">Основные элементы политики защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="8eb8f-115">**Политика защиты от фишинга:** указывает средства защиты от фишинга, чтобы включить или отключить, а также действия по применении параметров.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="8eb8f-116">**Правило защиты от фишинга:** указывает фильтры приоритета и получателей (к кому применяется политика) для политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="8eb8f-117">Разница между этими двумя элементами не очевидна при управлении политиками защиты от фишинга на Microsoft 365 Defender портале:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="8eb8f-118">При создании политики создается правило защиты от фишинга и связанная с ним политика защиты от фишинга, используя одно и то же имя для обоих.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="8eb8f-119">При изменении политики параметры, связанные с именем, приоритетом, включенной или отключенной, а также фильтры получателей изменяют правило защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="8eb8f-120">Все остальные параметры изменяют связанную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="8eb8f-121">При удалении политики удаляется правило защиты от фишинга и связанная с ним политика защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="8eb8f-122">В Exchange Online PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="8eb8f-123">Дополнительные сведения см. в [разделе Использование Exchange Online PowerShell для](#use-exchange-online-powershell-to-configure-anti-phishing-policies) настройки политики защиты от фишинга в этой статье.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="8eb8f-124">Каждая организация Defender для Office 365 имеет встроенную политику защиты от фишинга с именем Office365 AntiPhish Default, которая имеет эти свойства:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-124">Every Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="8eb8f-125">Политика применяется к всем получателям в организации, несмотря на отсутствие правила защиты от фишинга (фильтры получателей), связанного с политикой.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="8eb8f-126">Для политики задано специальное значение приоритета **Самый низкий**, которое невозможно изменить (эта политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="8eb8f-127">Все созданные специальные политики всегда имеют более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="8eb8f-128">Эта политика является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="8eb8f-129">Чтобы повысить эффективность защиты от фишинга в Defender для Office 365, можно создать настраиваемые политики защиты от фишинга с более строгими настройками, которые применяются к конкретным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-129">To increase the effectiveness of anti-phishing protection in Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8eb8f-130">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="8eb8f-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8eb8f-131">Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-131">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="8eb8f-132">Чтобы перейти непосредственно на страницу **anti-phishing,** используйте <https://security.microsoft.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="8eb8f-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="8eb8f-133">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="8eb8f-134">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="8eb8f-135">Чтобы добавить, изменить и удалить политики защиты от фишинга, необходимо  быть членом групп ролей администратора организации или **администратора** безопасности.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="8eb8f-136">Для доступа только для чтения к политикам защиты от фишинга необходимо быть членом групп ролей **Global Reader** или **Security Reader.** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8eb8f-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="8eb8f-137">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="8eb8f-138">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-138">**Notes**:</span></span>

  - <span data-ttu-id="8eb8f-139">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="8eb8f-140">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="8eb8f-141">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="8eb8f-142">Рекомендуемые параметры для политик защиты от фишинга в Defender для Office 365 см. в Office 365 правила защиты от [фишинга.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="8eb8f-142">For our recommended settings for anti-phishing policies in Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="8eb8f-143">Разрешить до 30 минут для новой или обновленной политики, которая будет применяться.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="8eb8f-144">Сведения о том, где политики защиты от фишинга применяются в конвейере фильтрации, см. в рублях [Order и precedence of email protection.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="8eb8f-144">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a><span data-ttu-id="8eb8f-145">Используйте портал Microsoft 365 Defender для создания политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-145">Use the Microsoft 365 Defender portal to create anti-phishing policies</span></span>

<span data-ttu-id="8eb8f-146">Создание настраиваемой политики защиты от фишинга на портале Microsoft 365 Defender создает правило защиты от фишинга и связанную политику защиты от фишинга, используя одно и то же имя для обоих.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-146">Creating a custom anti-phishing policy in the Microsoft 365 Defender portal creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="8eb8f-147">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики защиты от \>  \>  \>  \> **фишинга**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-147">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="8eb8f-148">На странице **Anti-phishing** нажмите кнопку ![ Создать значок ](../../media/m365-cc-sc-create-icon.png) **Создать**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-148">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="8eb8f-149">Откроется мастер политик.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-149">The policy wizard opens.</span></span> <span data-ttu-id="8eb8f-150">На странице **Имя политики** настройте эти параметры:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-150">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="8eb8f-151">**Имя**. Укажите уникальное, описательное имя политики.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="8eb8f-152">**Описание**. По желанию введите описание политики.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="8eb8f-153">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="8eb8f-154">На открывшейся странице **Пользователи, группы и домены** определите внутренних получателей, к которым применяется политика (условия получателей):</span><span class="sxs-lookup"><span data-stu-id="8eb8f-154">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="8eb8f-155">**Пользователи**: указывает один или несколько почтовых ящиков, пользователей почты или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-155">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="8eb8f-156">**Группы**: указывает группы рассылки, группы безопасности с поддержкой почты или группы Microsoft 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-156">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="8eb8f-157">**Домены**: все получатели в указанных [обслуживаемых доменах](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-157">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="8eb8f-158">Щелкните соответствующее поле, начните вводить значение и выберите нужное значение в результатах.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-158">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="8eb8f-159">Повторите эти действия необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-159">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="8eb8f-160">Чтобы удалить существующее значение, нажмите "Удалить".</span><span class="sxs-lookup"><span data-stu-id="8eb8f-160">To remove an existing value, click remove</span></span> ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="8eb8f-162">рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-162">next to the value.</span></span>

   <span data-ttu-id="8eb8f-163">Для пользователей и групп можно использовать большинство идентификаторов (имя, отображаемое имя, псевдоним, адрес электронной почты, имя учетной записи и т. д.), но в результатах будет выведено отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-163">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="8eb8f-164">Для получения списка всех пользователей введите звездочку (\*) без добавлений, чтобы увидеть все доступные значения.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-164">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="8eb8f-165">Указать несколько значений в одном условии можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-165">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="8eb8f-166">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-166">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="8eb8f-167">**Исключить этих пользователей, группы и домены**. Чтобы добавить исключения для внутренних получателей, к которым применяется политика (исключение получателей), выберите этот параметр и настройте исключения.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-167">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="8eb8f-168">Настройки и поведение такие же, как в разделе условий.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-168">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="8eb8f-169">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-169">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="8eb8f-170">На странице **защиты &** фишинга настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-170">On the **Phishing threshold & protection** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8eb8f-171">**Порог фишинговой электронной** почты: используйте ползунок, чтобы выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-171">**Phishing email threshold**: Use the slider to select one of the following values:</span></span>
     - <span data-ttu-id="8eb8f-172">**1 . Стандартный** (это значение по умолчанию.)</span><span class="sxs-lookup"><span data-stu-id="8eb8f-172">**1 - Standard** (This is the default value.)</span></span>
     - <span data-ttu-id="8eb8f-173">**2 . Агрессивная**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-173">**2 - Aggressive**</span></span>
     - <span data-ttu-id="8eb8f-174">**3 . Более агрессивная**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-174">**3 - More aggressive**</span></span>
     - <span data-ttu-id="8eb8f-175">**4 . Наиболее агрессивный**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-175">**4 - Most aggressive**</span></span>

     <span data-ttu-id="8eb8f-176">Дополнительные сведения см. в расширенных пороговых значениях фишинга в политиках по борьбе с фишингом в [Microsoft Defender для](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)Office 365.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-176">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="8eb8f-177">**Обезличение.** Эти параметры являются условием для политики, определяющей конкретных отправителей, которые необходимо искать (по отдельности или по домену) в Адресе входящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-177">**Impersonation**: These settings are a condition for the policy that identifies specific senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="8eb8f-178">Дополнительные сведения см. в сведениях о параметрах [Impersonation в](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)политиках защиты от фишинга в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-178">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="8eb8f-179">В каждой политике защиты от фишинга можно указать не более 60 защищенных пользователей (адреса электронной почты отправитель).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-179">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="8eb8f-180">В нескольких политиках нельзя указать одного и того же защищенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-180">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="8eb8f-181">Защита от обезличения пользователя не работает, если отправитель и получатель ранее связывались по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-181">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="8eb8f-182">Если отправитель и получатель никогда не связывались по электронной почте, сообщение будет определено как попытка обезличения.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-182">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

     - <span data-ttu-id="8eb8f-183">**Включить пользователей для защиты:** значение по умолчанию отключено (не выбрано).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-183">**Enable users to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="8eb8f-184">Чтобы включить его, выберите шажок, а затем нажмите кнопку **Управление (nn) отправитель(ы)** ссылку, которая появляется.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-184">To turn it on, select the check box, and then click the **Manage (nn) sender(s)** link that appears.</span></span>

       <span data-ttu-id="8eb8f-185">В поле **Управление отправительами для вылетов** защиты от обезличения, которые появляются, сделайте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-185">In the **Manage senders for impersonation protection** flyout that appears, do the following steps:</span></span>

       - <span data-ttu-id="8eb8f-186">**Внутренние отправители:** ![ Щелкните Добавить внутренний значок ](../../media/m365-cc-sc-add-internal-icon.png) **Выберите внутренний**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-186">**Internal senders**: Click ![Add internal icon](../../media/m365-cc-sc-add-internal-icon.png) **Select internal**.</span></span> <span data-ttu-id="8eb8f-187">В **появится флажок Добавить** внутренние отправители, щелкните в поле и выберите внутреннего пользователя из списка.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-187">In the **Add internal senders** flyout that appears, click in the box and select an internal user from the list.</span></span> <span data-ttu-id="8eb8f-188">Список можно фильтровать, введя пользователя, а затем выбрав его из результатов.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-188">You can filter the list by typing the user, and then selecting the user from the results.</span></span> <span data-ttu-id="8eb8f-189">Вы можете использовать большинство идентификаторов (имя, имя отображения, псевдоним, адрес электронной почты, имя учетной записи и т.д.), но соответствующее имя отображения отображается в результатах.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-189">You can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span>

         <span data-ttu-id="8eb8f-190">Повторите этот шаг нужное количество раз.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="8eb8f-191">Чтобы удалить существующее значение, нажмите "Удалить".</span><span class="sxs-lookup"><span data-stu-id="8eb8f-191">To remove an existing value, click remove</span></span> ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="8eb8f-193">рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-193">next to the value.</span></span>

         <span data-ttu-id="8eb8f-194">По завершению щелкните **Добавить**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-194">When you're finished, click **Add**</span></span>

       - <span data-ttu-id="8eb8f-195">**Внешние отправители:** ![ Щелкните Добавить внешний значок ](../../media/m365-cc-sc-create-icon.png) **Выберите внешний**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-195">**External senders**: Click ![Add external icon](../../media/m365-cc-sc-create-icon.png) **Select external**.</span></span> <span data-ttu-id="8eb8f-196">В **вылете** Добавить внешние отправители, который  появляется, введите имя отображения в поле Добавить имя и адрес электронной почты в поле **Добавить vaild** электронной почты, а затем нажмите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-196">In the **Add external senders** flyout that appears, enter a display name in the **Add a name** box and an email address in the **Add a vaild email** box, and then click **Add**.</span></span>

         <span data-ttu-id="8eb8f-197">Повторите этот шаг нужное количество раз.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-197">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="8eb8f-198">Чтобы удалить существующее значение, нажмите "Удалить".</span><span class="sxs-lookup"><span data-stu-id="8eb8f-198">To remove an existing value, click remove</span></span> ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="8eb8f-200">рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-200">next to the value.</span></span>

         <span data-ttu-id="8eb8f-201">По завершению щелкните **Добавить**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-201">When you're finished, click **Add**</span></span>

       <span data-ttu-id="8eb8f-202">Возвращаясь к **вылету "Управление** отправительами" для вылетов, вы можете удалить записи, выбрав одну или несколько записей из списка.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-202">Back on the **Manage senders for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="8eb8f-203">Вы можете искать записи с помощью окна ![ поиска ](../../media/m365-cc-sc-create-icon.png) **значков** поиска.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-203">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="8eb8f-204">После выбора хотя бы одной записи появится значок ![ Remove selected users ](../../media/m365-cc-sc-remove-selected-users-icon.png) Remove selected users icon Remove **selected users,** который можно использовать для удаления выбранных записей.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-204">After you select at least one entry, the ![Remove selected users icon](../../media/m365-cc-sc-remove-selected-users-icon.png) **Remove selected users** icon appears, which you can use to remove the selected entries.</span></span>

       <span data-ttu-id="8eb8f-205">По завершении нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-205">When you're finished, click **Done**.</span></span>

     - <span data-ttu-id="8eb8f-206">**Включить домены для защиты:** значение по умолчанию отключено (не выбрано).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-206">**Enable domains to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="8eb8f-207">Чтобы включить его, выберите шажок, а затем настройте один или оба следующих параметра, которые отображаются:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-207">To turn it on, select the check box, and then configure one or both of the following settings that appear:</span></span>
       - <span data-ttu-id="8eb8f-208">**Включи домены, которые у меня** есть: Чтобы включить этот параметр, выберите поле.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-208">**Include the domains I own**: To turn this setting on, select the check box.</span></span> <span data-ttu-id="8eb8f-209">Чтобы просмотреть домены, которые у вас есть, **щелкните Просмотреть мои домены**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-209">To view the domains that you own, click **View my domains**.</span></span>
       - <span data-ttu-id="8eb8f-210">**Включайте настраиваемые** домены. Чтобы включить этот параметр, выберите поле и нажмите ссылку Управление пользовательским доменом **(nn).**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-210">**Include custom domains**: To turn this setting on, select the check box, and then click the **Manage (nn) custom domain(s)** link that appears.</span></span> <span data-ttu-id="8eb8f-211">В поле **Управление пользовательскими доменами для вылетов** защиты от обезличения, которые появляются, нажмите кнопку Добавить значок доменов ![ Добавить ](../../media/m365-cc-sc-create-icon.png) **домены**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-211">In the **Manage custom domains for impersonation protection** flyout that appears, click ![Add domains icon](../../media/m365-cc-sc-create-icon.png) **Add domains**.</span></span>

         <span data-ttu-id="8eb8f-212">В **вылете Добавить** пользовательские домены, который появляется, нажмите в поле **Домен,** введите значение, а затем нажмите введите или выберите значение, которое отображается ниже окна.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-212">In the **Add custom domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="8eb8f-213">Повторите этот шаг нужное количество раз.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="8eb8f-214">Чтобы удалить существующее значение, нажмите кнопку ![Удалить](../../media/m365-cc-sc-remove-selection-icon.png) рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-214">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

         <span data-ttu-id="8eb8f-215">По завершению щелкните **Добавить домены**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-215">When you're finished, click **Add domains**</span></span>

         > [!NOTE]
         > <span data-ttu-id="8eb8f-216">Во всех политиках защиты от фишинга можно использовать не более 50 доменов.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-216">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

       <span data-ttu-id="8eb8f-217">Возвращаясь к **настраиваемой** области управления пользовательскими доменами для вылетов для обезличения, вы можете удалить записи, выбрав одну или несколько записей из списка.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-217">Back on the **Manage custom domains for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="8eb8f-218">Вы можете искать записи с помощью окна ![ поиска ](../../media/m365-cc-sc-create-icon.png) **значков** поиска.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-218">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="8eb8f-219">После выбора хотя бы одной записи появится значок Delete domains Delete, который можно использовать для удаления ![ ](../../media/m365-cc-sc-delete-icon.png)  выбранных записей.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-219">After you select at least one entry, the ![Delete domains icon](../../media/m365-cc-sc-delete-icon.png) **Delete** icon appears, which you can use to remove the selected entries.</span></span>

   - <span data-ttu-id="8eb8f-220">**Добавление надежных** отправителей и доменов: : Укажите исключения для защиты от обезличения для политики, нажав на Управление **(nn) доверенным отправителям (ы) и доменом (s)**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-220">**Add trusted senders and domains**: : Specify impersonation protection exceptions for the policy by clicking on **Manage (nn) trusted sender(s) and domain(s)**.</span></span> <span data-ttu-id="8eb8f-221">В поле **Управление настраиваемых доменов для вылетов** защиты от обезличения, которые появляются, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-221">In the **Manage custom domains for impersonation protection** flyout that appears, configure the following settings:</span></span>
      - <span data-ttu-id="8eb8f-222">**Отправители.** Убедитесь, **что** выбрана вкладка Отправитель, и ![ щелкните значок Добавить ](../../media/m365-cc-sc-create-icon.png) отправителей.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-222">**Senders**: Verify the **Sender** tab is selected and click ![Add senders icon](../../media/m365-cc-sc-create-icon.png).</span></span> <span data-ttu-id="8eb8f-223">В **вылете Добавлены** надежные отправители, которые появляются, введите адрес электронной почты в поле и нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-223">In the **Add trusted senders** flyout that appears, enter an email address in the box and then click **Add**.</span></span> <span data-ttu-id="8eb8f-224">Повторите этот шаг нужное количество раз.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-224">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="8eb8f-225">Чтобы удалить существующую запись, нажмите ![ кнопку Удалить значок Удалить ](../../media/m365-cc-sc-close-icon.png) для записи.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-225">To remove an existing entry, click ![Delete icon](../../media/m365-cc-sc-close-icon.png) for the entry.</span></span>

        <span data-ttu-id="8eb8f-226">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-226">When you're finished, click **Add**.</span></span>

      - <span data-ttu-id="8eb8f-227">**Домены.** Выберите **вкладку Домен** и нажмите ![ кнопку Добавить значок доменов ](../../media/m365-cc-sc-create-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="8eb8f-227">**Domains**: Select the **Domain** tab and click ![Add domains icon](../../media/m365-cc-sc-create-icon.png).</span></span>
  
        <span data-ttu-id="8eb8f-228">В **вылете Добавить** доверенные домены, который появляется, нажмите в поле **Домен,** введите значение, а затем нажмите введите или выберите значение, которое отображается ниже окна.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-228">In the **Add trusted domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="8eb8f-229">Повторите этот шаг нужное количество раз.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-229">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="8eb8f-230">Чтобы удалить существующее значение, нажмите кнопку ![Удалить](../../media/m365-cc-sc-remove-selection-icon.png) рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-230">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

        <span data-ttu-id="8eb8f-231">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-231">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="8eb8f-232">Возвращаясь к **настраиваемой** области управления пользовательскими доменами для вылетов, вы можете удалить записи из вкладок **Отправитель** и Домен, выбрав одну или несколько записей из списка. </span><span class="sxs-lookup"><span data-stu-id="8eb8f-232">Back on the **Manage custom domains for impersonation** flyout, you can remove entries from the **Sender** and **Domain** tabs by selecting one or more entries from the list.</span></span> <span data-ttu-id="8eb8f-233">Вы можете искать записи с помощью окна ![ поиска ](../../media/m365-cc-sc-create-icon.png) **значков** поиска.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-233">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

     <span data-ttu-id="8eb8f-234">После выбора хотя бы одной записи появится значок **Delete,** который можно использовать для удаления выбранных записей.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-234">After you select at least one entry, the **Delete** icon appears, which you can use to remove the selected entries.</span></span>

     <span data-ttu-id="8eb8f-235">По завершении нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-235">When you're finished, click **Done**.</span></span>

   - <span data-ttu-id="8eb8f-236">**Включить разведданные почтовых ящиков:** значение по умолчанию включается (выбрано), и мы рекомендуем оставить его.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-236">**Enable mailbox intelligence**: The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="8eb8f-237">Чтобы отключить его, зачистите контрольный ящик.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-237">To turn it off, clear the check box.</span></span>

     - <span data-ttu-id="8eb8f-238">**Включить защиту от обезличения** на основе разведданных. Этот параметр доступен только в том случае, если включается (выбрана) разведка почтовых ящиков. </span><span class="sxs-lookup"><span data-stu-id="8eb8f-238">**Enable intelligence based impersonation protection**: This setting is available only if **Enable mailbox intelligence** is on (selected).</span></span> <span data-ttu-id="8eb8f-239">Этот параметр позволяет аналитике почтовых ящиков принимать меры в отношении сообщений, которые определены как попытки обезличения.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-239">This setting allows mailbox intelligence to take action on messages that are identified as impersonation attempts.</span></span> <span data-ttu-id="8eb8f-240">Вы указываете действие, необходимое для разведки почтовых ящиков **If,** обнаруживаемую вами на следующей странице.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-240">You specify the action to take in the **If mailbox intelligence detects an impersonated user** setting on the next page.</span></span>

       <span data-ttu-id="8eb8f-241">Рекомендуется включить этот параметр, выбрав поле.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-241">We recommend that you turn this setting on by selecting the check box.</span></span> <span data-ttu-id="8eb8f-242">Чтобы отключить этот параметр, зачистите контрольный ящик.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-242">To turn this setting off, clear the check box.</span></span>

   - <span data-ttu-id="8eb8f-243">**Spoof**. В этом разделе используйте поле **Включить** подмену сведении, чтобы включить или отключить подмену сведений.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-243">**Spoof**: In this section, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="8eb8f-244">Значение по умолчанию находится на (выбранном), и мы рекомендуем оставить его.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-244">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="8eb8f-245">Вы указываете действие для принятия сообщений от заблокированных поддельных отправителей в сообщении If обнаружено в качестве параметра **spoof** на следующей странице.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-245">You specify the action to take on messages from blocked spoofed senders in the **If message is detected as spoof** setting on the next page.</span></span>

     <span data-ttu-id="8eb8f-246">Чтобы отключить подмену сведений, очистить поле.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-246">To turn off spoof intelligence, clear the check box.</span></span>

     > [!NOTE]
     > <span data-ttu-id="8eb8f-247">Вам не нужно отключать защиту от подмены, если запись MX не означает Microsoft 365; Вместо этого вы включаете усиленную фильтрацию соединителя.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-247">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="8eb8f-248">Инструкции см. в [расширенной фильтрации соединители в Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-248">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="8eb8f-249">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-249">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="8eb8f-250">В открывшемся окне **Действия** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-250">On the **Actions** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8eb8f-251">**Действия сообщения:** Настройка следующих действий в этом разделе:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-251">**Message actions**: Configure the following actions in this section:</span></span>
     - <span data-ttu-id="8eb8f-252">**Если сообщение обнаружено** как обезличенный пользователь: этот параметр доступен только в том случае, если вы выбрали **Включить** пользователей для защиты на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-252">**If message is detected as an impersonated user**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span> <span data-ttu-id="8eb8f-253">Выберите одно из следующих действий в списке выпаданий для сообщений, в которых отправитель является одним из защищенных пользователей, указанных на предыдущей странице:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-253">Select one of the following actions in the drop down list for messages where the sender is one of the protected users that you specified on the previous page:</span></span>
       - <span data-ttu-id="8eb8f-254">**Не применяйте никаких действий**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-254">**Don't apply any action**</span></span>
       - <span data-ttu-id="8eb8f-255">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-255">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="8eb8f-256">**Перемещение сообщения в папки нежелательной почты получателей**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-256">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="8eb8f-257">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-257">**Quarantine the message**</span></span>
       - <span data-ttu-id="8eb8f-258">**Доставка сообщения и добавление других адресов в строку Bcc**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-258">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="8eb8f-259">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-259">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="8eb8f-260">**Если сообщение обнаружено** как обезличенный домен: этот параметр доступен только в том случае, если вы выбрали домены **Enable для** защиты на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-260">**If the message is detected as an impersonated domain**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span> <span data-ttu-id="8eb8f-261">Выберите одно из следующих действий в списке drop down для сообщений, в которых адрес электронной почты отправитель находится в одном из защищенных доменов, указанных на предыдущей странице:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-261">Select one of the following actions in the drop down list for messages where the sender's email address is in one of the protected domains that you specified on the previous page:</span></span>
       - <span data-ttu-id="8eb8f-262">**Не применяйте никаких действий**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-262">**Don't apply any action**</span></span>
       - <span data-ttu-id="8eb8f-263">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-263">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="8eb8f-264">**Перемещение сообщения в папки нежелательной почты получателей**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-264">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="8eb8f-265">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-265">**Quarantine the message**</span></span>
       - <span data-ttu-id="8eb8f-266">**Доставка сообщения и добавление других адресов в строку Bcc**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-266">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="8eb8f-267">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-267">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="8eb8f-268">**Если разведка почтовых ящиков** обнаруживает обезличенных пользователей: этот параметр доступен только в том случае, если вы выбрали **включить** разведку для защиты от обезличения на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-268">**If mailbox intelligence detects an impersonated user**: This setting is available only if you selected **Enable intelligence for impersonation protection** on the previous page.</span></span> <span data-ttu-id="8eb8f-269">Выберите одно из следующих действий в списке drop down для сообщений, которые были определены как попытки обезличения с помощью разведки почтовых ящиков:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-269">Select one of the following actions in the drop down list for messages that were identified as impersonation attempts by mailbox intelligence:</span></span>
       - <span data-ttu-id="8eb8f-270">**Не применяйте никаких действий**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-270">**Don't apply any action**</span></span>
       - <span data-ttu-id="8eb8f-271">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-271">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="8eb8f-272">**Перемещение сообщения в папки нежелательной почты получателей**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-272">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="8eb8f-273">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-273">**Quarantine the message**</span></span>
       - <span data-ttu-id="8eb8f-274">**Доставка сообщения и добавление других адресов в строку Bcc**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-274">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="8eb8f-275">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-275">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="8eb8f-276">**Если сообщение обнаружено как поддельный:** этот параметр доступен только в том случае, если вы выбрали **сведения о** подмене на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-276">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="8eb8f-277">Выберите одно из следующих действий в списке выпадения для сообщений от заблокированных поддельных отправителей:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-277">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
       - <span data-ttu-id="8eb8f-278">**Перемещение сообщения в папки нежелательной почты получателей**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-278">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="8eb8f-279">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-279">**Quarantine the message**</span></span>

   - <span data-ttu-id="8eb8f-280">**Советы по &** безопасности: Настройка следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-280">**Safety tips & indicators**: Configure the following settings:</span></span>
     - <span data-ttu-id="8eb8f-281">**Показать первые контактные совет по безопасности:** Дополнительные сведения см. в [совет по безопасности.](set-up-anti-phishing-policies.md#first-contact-safety-tip)</span><span class="sxs-lookup"><span data-stu-id="8eb8f-281">**Show first contact safety tip**: For more information, see [First contact safety tip](set-up-anti-phishing-policies.md#first-contact-safety-tip).</span></span>
     - <span data-ttu-id="8eb8f-282">**Показать имя пользователя совет по безопасности:** Этот параметр доступен только в том случае, если выбрана возможность защиты пользователей **на** предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-282">**Show user impersonation safety tip**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span>
     - <span data-ttu-id="8eb8f-283">**Показать имя домена совет по безопасности.** Этот параметр доступен только в том случае, если вы выбрали **домены Enable для** защиты на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-283">**Show domain impersonation safety tip**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="8eb8f-284">**Показать пользователю вымысление необычных символов совет по безопасности** Этот параметр доступен только в том случае, если вы выбрали **Включить** пользователей для защиты или включить домены **для защиты** на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-284">**Show user impersonation unusual characters safety tip** This setting is available only if you selected **Enable users to protect** or **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="8eb8f-285">**Показать (?)** для неавентированных отправителей для подмены: Этот параметр доступен только в том случае, если вы выбрали **включить** подмену сведений на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-285">**Show (?) for unauthenticated senders for spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="8eb8f-286">Добавляет знак вопроса на фотографию отправитель в поле From в Outlook, если сообщение не проходит проверки SPF или DKIM и сообщение не передает DMARC или композитную проверку  подлинности. [](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="8eb8f-286">Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="8eb8f-287">**Показать тег "via".** Этот параметр доступен только в том случае, если вы выбрали **сведения о** подмене подмены на предыдущей странице.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-287">**Show "via" tag**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="8eb8f-288">Добавляет тег via (chris@contoso.com через fabrikam.com) на адрес From, если он отличается от домена в подписи DKIM или **адресЕ MAIL FROM.**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-288">Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="8eb8f-289">Значение по умолчанию находится (выбрано).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-289">The default value is on (selected).</span></span> <span data-ttu-id="8eb8f-290">Чтобы отключить его, зачистите контрольный ящик.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-290">To turn it off, clear the check box.</span></span>

       > [!NOTE]
       > <span data-ttu-id="8eb8f-291">Если у вас нет параметра тега **Show "via",** знак вопроса и тег через контролируются командой **Show (?)** для неавентированных отправителей для настройки подмены в организации. </span><span class="sxs-lookup"><span data-stu-id="8eb8f-291">If you don't have the **Show "via" tag** setting, the question mark **and** the via tag are both controlled by the **Show (?) for unauthenticated senders for spoof** setting in your organization.</span></span>

     <span data-ttu-id="8eb8f-292">Чтобы включить параметр, выберите поле для проверки.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-292">To turn on a setting, select the check box.</span></span> <span data-ttu-id="8eb8f-293">Чтобы отключить его, зачистите контрольный ящик.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-293">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="8eb8f-294">По завершении нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-294">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="8eb8f-295">На странице **Просмотр** просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-295">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="8eb8f-296">Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-296">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="8eb8f-297">Вы также можете щелкнуть **Назад** или выбрать определенную страницу в мастере.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-297">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="8eb8f-298">По завершении нажмите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-298">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="8eb8f-299">На странице подтверждения, которая откроется, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-299">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a><span data-ttu-id="8eb8f-300">Используйте портал Microsoft 365 Defender для просмотра политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-300">Use the Microsoft 365 Defender portal to view anti-phishing policies</span></span>

1. <span data-ttu-id="8eb8f-301">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики защиты от \>  \>  \>  \> **фишинга**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-301">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="8eb8f-302">На странице **Anti-phishing** в списке политик защиты от фишинга отображаются следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-302">On the **Anti-phishing** page, the following properties are displayed in the list of anti-phishing policies:</span></span>

   - <span data-ttu-id="8eb8f-303">**Имя**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-303">**Name**</span></span>
   - <span data-ttu-id="8eb8f-304">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-304">**Status**</span></span>
   - <span data-ttu-id="8eb8f-305">**Приоритет**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-305">**Priority**</span></span>
   - <span data-ttu-id="8eb8f-306">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-306">**Last modified**</span></span>

3. <span data-ttu-id="8eb8f-307">При выборе политики, щелкнув имя, параметры политики отображаются в вылете.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-307">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a><span data-ttu-id="8eb8f-308">Использование портала Microsoft 365 Defender для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-308">Use the Microsoft 365 Defender portal to modify anti-phishing policies</span></span>

1. <span data-ttu-id="8eb8f-309">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики защиты от \>  \>  \>  \> **фишинга**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-309">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="8eb8f-310">На странице **Anti-phishing** выберите политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-310">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="8eb8f-311">Параметры политики будут показаны во всплывающем окне. Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-311">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="8eb8f-312">Дополнительные сведения о параметрах см. в разделе Использование портала [Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) для создания разделов политики защиты от фишинга в этой статье.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-312">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create anti-phishing policies](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="8eb8f-313">Для политики защиты от фишинга по умолчанию раздел **Пользователи,** группы и домены недоступны (политика применяется ко всем), и переименовать политику нельзя.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-313">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="8eb8f-314">Чтобы включить или отключить политику или установить порядок приоритета политики, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-314">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="8eb8f-315">Включить или отключить настраиваемые политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-315">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="8eb8f-316">Вы не можете отключить политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-316">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="8eb8f-317">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики защиты от \>  \>  \>  \> **фишинга**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-317">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="8eb8f-318">На странице **Anti-phishing** выберите настраиваемую политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-318">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="8eb8f-319">Появится всплывающее окно со сведениями о политике. В верхней его части вы увидите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-319">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="8eb8f-320">**Политика отключена**. Чтобы включить политику, щелкните значок !["Включить"](../../media/m365-cc-sc-turn-on-off-icon.png) **Включить** .</span><span class="sxs-lookup"><span data-stu-id="8eb8f-320">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="8eb8f-321">**Политика включена**. Чтобы выключить политику, щелкните значок !["Отключить"](../../media/m365-cc-sc-turn-on-off-icon.png) **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-321">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="8eb8f-322">В диалоговом окне подтверждения нажмите кнопку **Включить** или **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-322">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="8eb8f-323">Во всплывающем окне сведений о политике нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-323">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="8eb8f-324">Когда вы вернетесь на главную страницу политики, значение параметра **Состояние** этой политики будет **Включена** или **Выключена**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-324">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="8eb8f-325">Установите приоритет настраиваемой политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-325">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="8eb8f-326">По умолчанию политикам защиты от фишинга предоставляется приоритет, основанный на порядке, в который они были созданы (более новые политики имеют более низкий приоритет по сравнению с более старыми политиками).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-326">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="8eb8f-327">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-327">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="8eb8f-328">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-328">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="8eb8f-329">Чтобы изменить приоритет политики, нажмите кнопку **Увеличить приоритет** или **Уменьшить приоритет** в свойствах политики (вы не можете напрямую изменить числовое значение параметра **Приоритет** на портале Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-329">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="8eb8f-330">Изменение приоритета политики имеет смысл, только если у вас несколько политик.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-330">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="8eb8f-331">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-331">**Notes**:</span></span>

- <span data-ttu-id="8eb8f-332">На Microsoft 365 Defender вы можете изменить приоритет политики защиты от фишинга только после ее создания.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-332">In the Microsoft 365 Defender portal, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="8eb8f-333">В PowerShell можно переопредить приоритет по умолчанию при создании правила защиты от фишинга (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-333">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="8eb8f-334">Политики защиты от фишинга обрабатываются в порядке отображения (первая политика имеет значение **Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-334">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="8eb8f-335">Политика защиты от фишинга по умолчанию имеет приоритетное значение **Самое** низкое, и изменить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-335">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="8eb8f-336">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики защиты от \>  \>  \>  \> **фишинга**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-336">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="8eb8f-337">На странице **Anti-phishing** выберите настраиваемую политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-337">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="8eb8f-338">Появится всплывающее окно со сведениями о политике. В верхней его части вы увидите одно из следующих значений: **Увеличить приоритет** или **Уменьшить приоритет** в зависимости от текущего значения приоритета и количества настраиваемых политик:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-338">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="8eb8f-339">Политика со **значением Приоритет** **0** имеет только доступный параметр **Приоритет уменьшения.**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-339">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="8eb8f-340">Политика с наименьшим **значением** Приоритет (например, **3)** имеет только доступный параметр **Increase priority.**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-340">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="8eb8f-341">Если у вас есть три или более политик, политики между самыми высокими и самыми низкими значениями приоритетов имеют доступные параметры **приоритета Increase** и **Decrease.**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-341">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="8eb8f-342">Щелкните ![Значок увеличения приоритета](../../media/m365-cc-sc-increase-icon.png) **Увеличить приоритет** или ![Значок уменьшения приоритета](../../media/m365-cc-sc-decrease-icon.png) **Уменьшить приоритет** чтобы изменить значение параметра **Приоритет**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-342">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="8eb8f-343">Закончив, нажмите **Закрыть** во всплывающем окне сведений о политике.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-343">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="8eb8f-344">Использование портала Microsoft 365 Defender для удаления настраиваемой политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-344">Use the Microsoft 365 Defender portal to remove custom anti-phishing policies</span></span>

<span data-ttu-id="8eb8f-345">При использовании портала Microsoft 365 Defender для удаления настраиваемой политики защиты от фишинга правило защиты от фишинга и соответствующая политика защиты от фишинга удаляются.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-345">When you use the Microsoft 365 Defender portal to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="8eb8f-346">Вы не можете удалить политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-346">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="8eb8f-347">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики защиты от \>  \>  \>  \> **фишинга**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-347">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="8eb8f-348">На странице **Anti-phishing** выберите настраиваемую политику из списка, нажав на имя политики.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-348">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="8eb8f-349">В открывшемся всплывающем окне сведений о политике щелкните ![значок "Дополнительные действия"](../../media/m365-cc-sc-more-actions-icon.png) **Дополнительные действия** \> ![значок "Удалить политику"](../../media/m365-cc-sc-delete-icon.png) **Удалить политику**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-349">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="8eb8f-350">В диалоговом окне подтверждения нажмите **Да**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-350">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="8eb8f-351">Используйте Exchange Online PowerShell для настройки политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-351">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="8eb8f-352">Как описано выше, политика защиты от нежелательной почты состоит из политики защиты от фишинга и правила защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-352">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="8eb8f-353">В Exchange Online PowerShell разница между политиками защиты от фишинга и правилами защиты от фишинга очевидна.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-353">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="8eb8f-354">Вы управляете политиками защиты от фишинга с помощью кодлетов **\* -AntiPhishPolicy** и управляете правилами защиты от фишинга с помощью cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-354">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="8eb8f-355">В PowerShell сначала создается политика защиты от фишинга, а затем создается правило защиты от фишинга, которое определяет политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-355">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="8eb8f-356">В PowerShell параметры политики защиты от фишинга и правила защиты от фишинга изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-356">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="8eb8f-357">При удалении политики защиты от фишинга из PowerShell соответствующее правило не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-357">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="8eb8f-358">Использование PowerShell для создания политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-358">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="8eb8f-359">Создание политики защиты от фишинга в PowerShell — это двухшаговый процесс:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-359">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="8eb8f-360">Создание политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-360">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="8eb8f-361">Создайте правило защиты от фишинга, которое указывает политику защиты от фишинга, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-361">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="8eb8f-362">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-362">**Notes**:</span></span>

- <span data-ttu-id="8eb8f-363">Вы можете создать новое правило защиты от фишинга и назначить ему существующую, неассоциированную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-363">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="8eb8f-364">Правило защиты от фишинга не может быть связано с одной политикой защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-364">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>
- <span data-ttu-id="8eb8f-365">Вы можете настроить следующие параметры для новых политик защиты от фишинга в PowerShell, недоступных на портале Microsoft 365 Defender до создания политики:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-365">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="8eb8f-366">Создайте новую политику как отключенную _(включена_ `$false` в **кодлете New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-366">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="8eb8f-367">Задай приоритет политики во время создания _(приоритет)_ в _\<Number\>_ **комлете New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-367">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>
- <span data-ttu-id="8eb8f-368">Новая политика защиты от фишинга, которую вы создаете в PowerShell, не отображается на портале Microsoft 365 Defender, пока не назначите политику правилу защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-368">A new anti-phish policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="8eb8f-369">Шаг 1. Использование PowerShell для создания политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-369">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="8eb8f-370">Чтобы создать политику защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-370">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="8eb8f-371">В этом примере создается политика защиты от фишинга с именем Research Quarantine со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-371">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="8eb8f-372">Политика включена (мы не используем параметр _Включен,_ а значение по `$true` умолчанию).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-372">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="8eb8f-373">Описание: Политика отдела исследований.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-373">The description is: Research department policy.</span></span>
- <span data-ttu-id="8eb8f-374">Включает защиту доменов организации для всех принятых доменов и адресную защиту доменов для fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-374">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="8eb8f-375">Указывает, что защищать от имитации нужно пользователя Mai Fujito (mfujito@fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-375">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="8eb8f-376">Включает аналитику почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-376">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="8eb8f-377">Включает защиту разведданных почтовых ящиков и указывает действие карантина.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-377">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="8eb8f-378">Включает советы по безопасности.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-378">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="8eb8f-379">Подробные сведения о синтаксисе и параметрах см. в [обзоре New-AntiPhishPolicy.](/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="8eb8f-379">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="8eb8f-380">Шаг 2. Использование PowerShell для создания правила защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-380">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="8eb8f-381">Чтобы создать правило защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-381">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="8eb8f-382">В этом примере создается правило защиты от фишинга с именем Research Department со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-382">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="8eb8f-383">Это правило связано с политикой защиты от фишинга с именем Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-383">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="8eb8f-384">Правило применяется к членам группы "Research Department".</span><span class="sxs-lookup"><span data-stu-id="8eb8f-384">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="8eb8f-385">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-385">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="8eb8f-386">Подробные сведения о синтаксисе и параметрах см. [в обзоре New-AntiPhishRule.](/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="8eb8f-386">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="8eb8f-387">Использование PowerShell для просмотра политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-387">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="8eb8f-388">Чтобы просмотреть существующие политики защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-388">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="8eb8f-389">В этом примере возвращается сводный список всех политик защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-389">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="8eb8f-390">В этом примере возвращаются все значения свойств для политики защиты от фишинга с именем Executives.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-390">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="8eb8f-391">Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-AntiPhishPolicy.](/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="8eb8f-391">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="8eb8f-392">Использование PowerShell для просмотра правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-392">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="8eb8f-393">Чтобы просмотреть существующие правила защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-393">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="8eb8f-394">В этом примере возвращается сводный список всех правил по борьбе с фишингом вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-394">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="8eb8f-395">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-395">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="8eb8f-396">В этом примере возвращаются все значения свойств для правила защиты от фишинга с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-396">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="8eb8f-397">Подробные сведения о синтаксисе и параметрах см. в [ссылке Get-AntiPhishRule.](/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="8eb8f-397">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="8eb8f-398">Использование PowerShell для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-398">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="8eb8f-399">Кроме следующих элементов, при изменении политики защиты от фишинга в PowerShell доступны те же параметры, что и при создании политики, описанной в разделе [Шаг 1. Использование PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) для создания раздела политики защиты от фишинга в этой статье.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-399">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="8eb8f-400">Переключатель _MakeDefault,_ который превращает указанную политику в политику по  умолчанию (применяется для всех, всегда самый низкий приоритет, и вы не можете удалить ее) доступен только при изменении политики защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-400">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="8eb8f-401">Нельзя переименовать политику защиты от фишинга (в **кодлете Set-AntiPhishPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="8eb8f-401">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="8eb8f-402">При переименовании политики защиты от фишинга на портале Microsoft 365 Defender вы только переименовывать правило защиты от _фишинга._</span><span class="sxs-lookup"><span data-stu-id="8eb8f-402">When you rename an anti-phishing policy in the Microsoft 365 Defender portal, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="8eb8f-403">Чтобы изменить политику защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-403">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="8eb8f-404">Подробные сведения о синтаксисе и параметрах см. в [инструкции Set-AntiPhishPolicy.](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="8eb8f-404">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="8eb8f-405">Использование PowerShell для изменения правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-405">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="8eb8f-406">Единственным параметром, недоступным при изменении правила защиты от фишинга  в PowerShell, является параметр Включен, который позволяет создать правило отключено.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-406">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="8eb8f-407">Чтобы включить или отключить существующие правила защиты от фишинга, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-407">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="8eb8f-408">В противном случае дополнительные параметры не доступны при изменении правила защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-408">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="8eb8f-409">Эти же параметры доступны при создании правила, описанного в разделе Шаг [2. Использование PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) для создания раздела правил для защиты от фишинга в этой статье.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-409">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="8eb8f-410">Чтобы изменить правило защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-410">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="8eb8f-411">Подробные сведения о синтаксисе и параметрах см. в [инструкции Set-AntiPhishRule.](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="8eb8f-411">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="8eb8f-412">Использование PowerShell, чтобы включить или отключить правила защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-412">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="8eb8f-413">Включение или отключение правила защиты от фишинга в PowerShell включает или отключает всю политику защиты от фишинга (правило защиты от фишинга и назначенную политику защиты от фишинга).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-413">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="8eb8f-414">Вы не можете включить или отключить политику защиты от фишинга по умолчанию (она всегда применяется к всем получателям).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-414">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="8eb8f-415">Чтобы включить или отключить правило защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-415">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="8eb8f-416">В этом примере отключает правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-416">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="8eb8f-417">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-417">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="8eb8f-418">Подробные сведения о синтаксисе и параметрах см. в [сводке Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) и [Disable-AntiPhishRule.](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="8eb8f-418">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="8eb8f-419">Использование PowerShell для набора приоритета правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-419">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="8eb8f-p156">Максимальный приоритет, который можно задать для правила, — 0. Минимальное значение зависит от количества правил. Например, если у вас есть пять правил, вы можете использовать значения 0-4. Изменение приоритета существующего правила оказывает каскадное влияние на другие правила. Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-p156">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="8eb8f-425">Чтобы установить приоритет правила защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-425">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="8eb8f-p157">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="8eb8f-p157">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="8eb8f-428">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-428">**Notes**:</span></span>

- <span data-ttu-id="8eb8f-429">Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в **комлете New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-429">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="8eb8f-430">Политика защиты от фишинга по умолчанию не имеет соответствующего правила по борьбе с фишингом, и всегда имеет неоплаченное значение приоритета **Самое низкое.**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-430">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="8eb8f-431">Использование PowerShell для удаления политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-431">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="8eb8f-432">При удалении политики защиты от фишинга с помощью PowerShell соответствующее правило по борьбе с фишингом не удаляется.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-432">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="8eb8f-433">Чтобы удалить политику защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-433">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="8eb8f-434">В этом примере удаляется политика защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-434">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="8eb8f-435">Подробные сведения о синтаксисе и параметрах см. в [обзоре Remove-AntiPhishPolicy.](/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="8eb8f-435">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="8eb8f-436">Использование PowerShell для удаления правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="8eb8f-436">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="8eb8f-437">При удалении правила защиты от фишинга с помощью PowerShell соответствующая политика защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-437">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="8eb8f-438">Чтобы удалить правило защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-438">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="8eb8f-439">В этом примере удаляется правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-439">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="8eb8f-440">Подробные сведения о синтаксисе и параметрах см. в [инструкции Remove-AntiPhishRule.](/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="8eb8f-440">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="8eb8f-441">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="8eb8f-441">How do you know these procedures worked?</span></span>

<span data-ttu-id="8eb8f-442">Чтобы убедиться в успешной настройке политик защиты от фишинга в Defender для Office 365, необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-442">To verify that you've successfully configured anti-phishing policies in Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="8eb8f-443">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной** & электронной почты & политики угрозы правил раздел Политики защиты от \>  \>  \>  \> **фишинга**.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-443">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="8eb8f-444">Проверка списка политик, их значений **состояния** и **их значений приоритета.**</span><span class="sxs-lookup"><span data-stu-id="8eb8f-444">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="8eb8f-445">Чтобы просмотреть дополнительные сведения, выберите политику из списка, нажав на имя и просмотрев сведения в вылете, который появится.</span><span class="sxs-lookup"><span data-stu-id="8eb8f-445">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="8eb8f-446">В Exchange Online PowerShell замените имя политики или правила и запустите следующую команду и проверьте \<Name\> параметры:</span><span class="sxs-lookup"><span data-stu-id="8eb8f-446">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
