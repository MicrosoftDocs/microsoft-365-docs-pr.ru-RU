---
title: Готовые политики безопасности
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
description: Администраторы могут узнать, как применять стандартные и строгие параметры политики для Exchange Online Protection (EOP) и Microsoft Defender для Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ca65f003b0c206b0f7e23f3498a4ef0d0bc03fa6
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788983"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="6279f-103">Предустановленные политики безопасности в EOP и Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="6279f-103">Preset security policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6279f-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="6279f-104">**Applies to**</span></span>
- [<span data-ttu-id="6279f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6279f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6279f-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="6279f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6279f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6279f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6279f-108">Предустановленные политики безопасности предоставляют централизованное расположение для одновременного применения всех рекомендуемых политик нежелательной почты, вредоносных программ и фишинга для пользователей.</span><span class="sxs-lookup"><span data-stu-id="6279f-108">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="6279f-109">Параметры политики не настраиваются.</span><span class="sxs-lookup"><span data-stu-id="6279f-109">The policy settings are not configurable.</span></span> <span data-ttu-id="6279f-110">Вместо этого они устанавливаются нами и основываются на наших наблюдениях и опытах в центрах обработки данных для баланса между сохранением вредного контента от пользователей и предотвращением ненужных сбоев.</span><span class="sxs-lookup"><span data-stu-id="6279f-110">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users and avoiding unnecessary disruptions.</span></span>

<span data-ttu-id="6279f-111">В остальной части этой статьи описаны заранее заданной политики безопасности и их настройка.</span><span class="sxs-lookup"><span data-stu-id="6279f-111">The rest of this article describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="6279f-112">Какие предустановленные политики безопасности сделаны из</span><span class="sxs-lookup"><span data-stu-id="6279f-112">What preset security policies are made of</span></span>

<span data-ttu-id="6279f-113">Предустановленные политики безопасности состоят из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="6279f-113">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="6279f-114">Профили</span><span class="sxs-lookup"><span data-stu-id="6279f-114">Profiles</span></span>
- <span data-ttu-id="6279f-115">Политики</span><span class="sxs-lookup"><span data-stu-id="6279f-115">Policies</span></span>
- <span data-ttu-id="6279f-116">Параметры политики</span><span class="sxs-lookup"><span data-stu-id="6279f-116">Policy settings</span></span>

<span data-ttu-id="6279f-117">Кроме того, порядок приоритета важен, если к одному и тому же лицу применяются несколько заранее.</span><span class="sxs-lookup"><span data-stu-id="6279f-117">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="6279f-118">Профили в предустановленных политиках безопасности</span><span class="sxs-lookup"><span data-stu-id="6279f-118">Profiles in preset security policies</span></span>

<span data-ttu-id="6279f-119">Профиль определяет уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="6279f-119">A profile determines the level of protection.</span></span> <span data-ttu-id="6279f-120">Доступны следующие профили:</span><span class="sxs-lookup"><span data-stu-id="6279f-120">The following profiles are available:</span></span>

- <span data-ttu-id="6279f-121">**Стандартная защита:** базовый профиль защиты, который подходит большинству пользователей.</span><span class="sxs-lookup"><span data-stu-id="6279f-121">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="6279f-122">**Строгая** защита: более агрессивный профиль защиты для выбранных пользователей (целевые объекты с высоким значением или приоритетные пользователи).</span><span class="sxs-lookup"><span data-stu-id="6279f-122">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="6279f-123">Вы используете правила с условиями и исключениями, которые определяют, к кому или к которым не применяются профили.</span><span class="sxs-lookup"><span data-stu-id="6279f-123">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="6279f-124">Доступные условия и исключения:</span><span class="sxs-lookup"><span data-stu-id="6279f-124">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="6279f-125">**Пользователи**: указывает один или несколько почтовых ящиков, пользователей почты или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="6279f-125">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="6279f-126">**Группы**: указывает группы рассылки, группы безопасности с поддержкой почты или группы Microsoft 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6279f-126">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
- <span data-ttu-id="6279f-127">**Домены**: все получатели в указанных [обслуживаемых доменах](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6279f-127">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

<span data-ttu-id="6279f-128">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="6279f-128">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="6279f-129">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="6279f-129">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="6279f-130">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="6279f-130">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="6279f-131">Политики в предустановленных политиках безопасности</span><span class="sxs-lookup"><span data-stu-id="6279f-131">Policies in preset security policies</span></span>

<span data-ttu-id="6279f-132">Предустановленные политики безопасности используют соответствующие политики из различных компонентов защиты в EOP и Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="6279f-132">Preset security policies use the corresponding policies from the various protection features in EOP and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="6279f-133">Эти политики _создаются_ после назначения пользователям политик безопасности **Standard protection** или **Strict protection** preset.</span><span class="sxs-lookup"><span data-stu-id="6279f-133">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="6279f-134">Вы не можете изменить эти политики.</span><span class="sxs-lookup"><span data-stu-id="6279f-134">You can't modify these policies.</span></span>

- <span data-ttu-id="6279f-135">**политики Exchange Online Protection (EOP):** Это включает Microsoft 365 с Exchange Online почтовыми ящиками и автономными организациями EOP без Exchange Online почтовых ящиков:</span><span class="sxs-lookup"><span data-stu-id="6279f-135">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="6279f-136">[Политики защиты от нежелательной почты](configure-your-spam-filter-policies.md) с именем **Standard Preset Security Policy** и Strict **Preset Security Policy**.</span><span class="sxs-lookup"><span data-stu-id="6279f-136">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="6279f-137">[Политики защиты от вредоносных программ](configure-anti-malware-policies.md) с именем **Standard Preset Security Policy** и Strict **Preset Security Policy**.</span><span class="sxs-lookup"><span data-stu-id="6279f-137">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="6279f-138">[Политики защиты от фишинга EOP](set-up-anti-phishing-policies.md#spoof-settings) с именем **Standard Preset Security Policy** и Strict **Preset Security Policy** (параметры spoof).</span><span class="sxs-lookup"><span data-stu-id="6279f-138">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="6279f-139">**Microsoft Defender для Office 365** политик: это организации с Microsoft 365 E5 или Defender для Office 365 надстройки:</span><span class="sxs-lookup"><span data-stu-id="6279f-139">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="6279f-140">Политики защиты от фишинга в Microsoft Defender для Office 365 с именем **Standard Preset Security Policy** и Strict **Preset Security Policy**, которые включают:</span><span class="sxs-lookup"><span data-stu-id="6279f-140">Anti-phishing policies in Microsoft Defender for Office 365 named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="6279f-141">Те же [параметры подмены,](set-up-anti-phishing-policies.md#spoof-settings) которые доступны в антифишинговых политиках EOP.</span><span class="sxs-lookup"><span data-stu-id="6279f-141">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="6279f-142">Параметры обезличения</span><span class="sxs-lookup"><span data-stu-id="6279f-142">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="6279f-143">Расширенные пороговые значения фишинга</span><span class="sxs-lookup"><span data-stu-id="6279f-143">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="6279f-144">[Сейф ссылки политик](set-up-safe-links-policies.md) с именем **Standard Preset Security Policy** и Strict **Preset Security Policy**.</span><span class="sxs-lookup"><span data-stu-id="6279f-144">[Safe Links policies](set-up-safe-links-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="6279f-145">[Сейф политики вложений](set-up-safe-attachments-policies.md) с именем **Standard Preset Security Policy** и Strict **Preset Security Policy**.</span><span class="sxs-lookup"><span data-stu-id="6279f-145">[Safe Attachments policies](set-up-safe-attachments-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="6279f-146">Обратите внимание, что для защиты от EOP можно применять различные пользователи, Office 365 Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="6279f-146">Note that you can apply EOP protections to different users than Microsoft Defender for Office 365 protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="6279f-147">Параметры политики в предустановленных политиках безопасности</span><span class="sxs-lookup"><span data-stu-id="6279f-147">Policy settings in preset security policies</span></span>

<span data-ttu-id="6279f-148">Вы не можете изменить параметры политики в профилях защиты.</span><span class="sxs-lookup"><span data-stu-id="6279f-148">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="6279f-149">Значения **стандартных** и строгих параметров политики описаны в рекомендуемых параметрах для EOP и [Microsoft Defender для Office 365 безопасности.](recommended-settings-for-eop-and-office365.md) </span><span class="sxs-lookup"><span data-stu-id="6279f-149">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="6279f-150">Порядок приоритета для предустановленных политик безопасности и других политик</span><span class="sxs-lookup"><span data-stu-id="6279f-150">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="6279f-151">Если к пользователю применяется несколько политик, то следующий порядок применяется с самого высокого приоритета к самому низкому приоритету:</span><span class="sxs-lookup"><span data-stu-id="6279f-151">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="6279f-152">**Политика строгой** защиты, предустановленная для безопасности</span><span class="sxs-lookup"><span data-stu-id="6279f-152">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="6279f-153">**Стандартная политика** безопасности, предустановленная для защиты</span><span class="sxs-lookup"><span data-stu-id="6279f-153">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="6279f-154">Настраиваемые политики безопасности</span><span class="sxs-lookup"><span data-stu-id="6279f-154">Custom security policies</span></span>
4. <span data-ttu-id="6279f-155">Политики безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6279f-155">Default security policies</span></span>

<span data-ttu-id="6279f-156">Другими словами, параметры  политики строгой защиты переопределяют параметры политики стандартной защиты, которая переопределяет параметры из настраиваемой политики, которая переопределяет параметры из политики по умолчанию. </span><span class="sxs-lookup"><span data-stu-id="6279f-156">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="6279f-157">Назначение предустановленных политик безопасности пользователям</span><span class="sxs-lookup"><span data-stu-id="6279f-157">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6279f-158">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="6279f-158">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6279f-159">Вы открываете центр Microsoft 365 безопасности по <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="6279f-159">You open the Microsoft 365 security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="6279f-160">Чтобы перейти непосредственно на страницу политики безопасности **preset,** используйте <https://security.microsoft.com/presetSecurityPolicies> .</span><span class="sxs-lookup"><span data-stu-id="6279f-160">To go directly to the **Preset security policies** page, use <https://security.microsoft.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="6279f-161">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="6279f-161">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="6279f-162">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="6279f-162">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="6279f-163">Чтобы настроить заранее заранее заранее настроенные политики безопасности, необходимо быть членом групп ролей **"Управление** организацией" или **"Администратор** безопасности".</span><span class="sxs-lookup"><span data-stu-id="6279f-163">To configure preset security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="6279f-164">Для доступа только для чтения к предустановленным политикам безопасности необходимо быть членом группы **ролей Global Reader.**</span><span class="sxs-lookup"><span data-stu-id="6279f-164">For read-only access to preset security policies, you need to be a member of the **Global Reader** role group.</span></span>

  <span data-ttu-id="6279f-165">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="6279f-165">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="6279f-166">**Примечание.** Добавление пользователей к соответствующей роли Azure Active Directory в центре администрирования Microsoft 365 предоставляет  пользователям необходимые разрешения и разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6279f-166">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="6279f-167">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="6279f-167">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

### <a name="use-the-security-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="6279f-168">Используйте центр безопасности, чтобы назначить пользователям заранее задатки политики безопасности.</span><span class="sxs-lookup"><span data-stu-id="6279f-168">Use the security center to assign preset security policies to users</span></span>

1. <span data-ttu-id="6279f-169">В центре безопасности перейдите к разделу Политики **совместной &** электронной почты & политики шаблонных политик правил предустановленной \>  \>  \>  \> **политики безопасности**.</span><span class="sxs-lookup"><span data-stu-id="6279f-169">In the security center, go to **Email & collaboration** \> **Policies & Rules** \> **Threat Policies** \> **Templated policies** section \> **Preset Security Policies**.</span></span>

2. <span data-ttu-id="6279f-170">В **соответствии со стандартной защитой** или **строгой защитой** нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="6279f-170">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="6279f-171">Начинается **мастер применения стандартной защиты** или мастер **строгой** защиты.</span><span class="sxs-lookup"><span data-stu-id="6279f-171">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="6279f-172">На странице **защиты EOP** определите внутренних получателей, к которых применяются защитные средства [EOP](#policies-in-preset-security-policies) (условия получателей):</span><span class="sxs-lookup"><span data-stu-id="6279f-172">On the **EOP protections apply to** page, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to (recipient conditions):</span></span>
   - <span data-ttu-id="6279f-173">**пользователи**;</span><span class="sxs-lookup"><span data-stu-id="6279f-173">**Users**</span></span>
   - <span data-ttu-id="6279f-174">**Группы**</span><span class="sxs-lookup"><span data-stu-id="6279f-174">**Groups**</span></span>
   - <span data-ttu-id="6279f-175">**Домены**</span><span class="sxs-lookup"><span data-stu-id="6279f-175">**Domains**</span></span>

   <span data-ttu-id="6279f-176">Щелкните соответствующее поле, начните вводить значение и выберите нужное значение в результатах.</span><span class="sxs-lookup"><span data-stu-id="6279f-176">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="6279f-177">Повторите эти действия необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="6279f-177">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="6279f-178">Чтобы удалить существующее значение, нажмите "Удалить".</span><span class="sxs-lookup"><span data-stu-id="6279f-178">To remove an existing value, click remove</span></span> ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="6279f-180">рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="6279f-180">next to the value.</span></span>

   <span data-ttu-id="6279f-181">Для пользователей и групп можно использовать большинство идентификаторов (имя, отображаемое имя, псевдоним, адрес электронной почты, имя учетной записи и т. д.), но в результатах будет выведено отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="6279f-181">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="6279f-182">Для получения списка всех пользователей введите звездочку (\*) без добавлений, чтобы увидеть все доступные значения.</span><span class="sxs-lookup"><span data-stu-id="6279f-182">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   - <span data-ttu-id="6279f-183">**Исключить этих пользователей, группы и домены**. Чтобы добавить исключения для внутренних получателей, к которым применяется политика (исключение получателей), выберите этот параметр и настройте исключения.</span><span class="sxs-lookup"><span data-stu-id="6279f-183">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="6279f-184">Настройки и поведение такие же, как в разделе условий.</span><span class="sxs-lookup"><span data-stu-id="6279f-184">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="6279f-185">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6279f-185">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6279f-186">В Microsoft Defender для Office 365 организаций на  страницу применяются Office 365 для определения внутренних получателей, к Office 365 которых применяется защита Microsoft [Defender](#policies-in-preset-security-policies) для Office 365 (условия получателей).</span><span class="sxs-lookup"><span data-stu-id="6279f-186">In Microsoft Defender for Office 365 organizations, you're taken to the **Defender for Office 365 protections apply to** page to identify the internal recipients that the [Microsoft Defender for Office 365 protections](#policies-in-preset-security-policies) apply to (recipient conditions).</span></span>

   <span data-ttu-id="6279f-187">Параметры и поведение точно так же, как защиты **EOP применяются к странице.**</span><span class="sxs-lookup"><span data-stu-id="6279f-187">The settings and behavior are exactly like the **EOP protections apply to** page.</span></span>

   <span data-ttu-id="6279f-188">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6279f-188">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6279f-189">На странице **Обзор и подтвердите изменения,** проверьте выбор, а затем нажмите **кнопку Подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="6279f-189">On the **Review and confirm your changes** page, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-security-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="6279f-190">Используйте центр безопасности для изменения назначений заранее</span><span class="sxs-lookup"><span data-stu-id="6279f-190">Use the security center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="6279f-191">Действия по изменению назначения политики безопасности **standard protection** или **Strict protection** такие же, как при первоначальном назначении заранее [назначенных политик безопасности пользователям.](#use-the-security-center-to-assign-preset-security-policies-to-users)</span><span class="sxs-lookup"><span data-stu-id="6279f-191">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="6279f-192">Чтобы отключить политики безопасности **standard protection** или **Strict protection,** сохраняя существующие условия и исключения, сдвиньте переключение на **отключенное** отключение. ![ ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="6279f-192">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="6279f-193">Чтобы включить политики, сдвиньте окантовку с **включенной** ![ возможностью ](../../media/scc-toggle-on.png) включения.</span><span class="sxs-lookup"><span data-stu-id="6279f-193">To enable the policies, slide the toggle to **Enabled** ![Toggle On](../../media/scc-toggle-on.png).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="6279f-194">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="6279f-194">How do you know these procedures worked?</span></span>

<span data-ttu-id="6279f-195">Чтобы убедиться, что пользователю успешно назначена политика безопасности **Standard protection** или **Strict** protection, используйте параметр защиты, где значение по умолчанию отличается от параметра **Standard protection,** которое отличается от параметра **Strict protection.**</span><span class="sxs-lookup"><span data-stu-id="6279f-195">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="6279f-196">Например, для электронной почты, обнаруженной в качестве нежелательной почты (не с высокой достоверности), убедитесь,  что сообщение доставляется в папку нежелательной почты для пользователей стандартной защиты и карантин для пользователей строгой защиты. </span><span class="sxs-lookup"><span data-stu-id="6279f-196">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="6279f-197">Или, для массовой почты, убедитесь, что значение BCL 6 или  выше доставляет сообщение в папку нежелательной почты для  пользователей стандартной защиты, а значение BCL 4 или более высокий карантин сообщения для пользователей строгой защиты. [](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="6279f-197">Or, for [bulk mail](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
