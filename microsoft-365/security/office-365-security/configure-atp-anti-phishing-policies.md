---
title: Настройка политик защиты от фишинга в ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как создавать, изменять и удалять расширенные политики защиты от фишинга, доступные в организациях с Office 365 Advanced Threat protection (Office 365 ATP).
ms.openlocfilehash: 458a4eac348598d1b752267ed7d79b97bc594580
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726768"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="85e92-103">Настройка политик защиты от фишинга в ATP</span><span class="sxs-lookup"><span data-stu-id="85e92-103">Configure ATP anti-phishing policies</span></span>

<span data-ttu-id="85e92-104">Антифишинговые политики ATP входят в состав [Office 365 Advanced Threat protection](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="85e92-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="85e92-105">Антифишинговые политики ATP могут помочь защитить организацию от вредоносных фишинговых атак на основе олицетворений и других типов фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="85e92-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="85e92-106">Дополнительные сведения о различиях между политиками защиты от фишинга в Exchange Online Protection (EOP) и ATP антифишинговой политикой можно узнать в статье [Защита от фишинга](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="85e92-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="85e92-107">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику защиты от фишинга ATP по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="85e92-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="85e92-108">Для большей детализации можно также создать настраиваемые политики защиты ATP от фишинга, которые применяются к определенным пользователям, группам или доменам в Организации.</span><span class="sxs-lookup"><span data-stu-id="85e92-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="85e92-109">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="85e92-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="85e92-110">Политики защиты от фишинга ATP можно настроить в центре безопасности & соответствия требованиям или в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85e92-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="85e92-111">Дополнительные сведения о настройке политик защиты от фишинга, доступных в организациях Exchange Online Protection (то есть в организациях Microsoft 365 без Office 365 ATP), приведены в разделе [Настройка политик защиты от фишинга в EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="85e92-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="85e92-112">Политики защиты от фишинга ATP в центре безопасности & соответствия требованиям VS PowerShell</span><span class="sxs-lookup"><span data-stu-id="85e92-112">ATP anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="85e92-113">Основные элементы политики защиты от фишинга ATP:</span><span class="sxs-lookup"><span data-stu-id="85e92-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="85e92-114">**Политика защиты от фишинга**: определяет защиту от фишинга, которую необходимо включить или отключить, а также действия, которые необходимо применить к параметрам.</span><span class="sxs-lookup"><span data-stu-id="85e92-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="85e92-115">**Правило защиты от фишинга**: определяет приоритет и фильтры получателей (к которым применяется политика) для политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="85e92-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="85e92-116">Различия между этими двумя элементами не очевидны при управлении политиками защиты от фишинга ATP в центре безопасности & соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="85e92-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="85e92-117">При создании политики защиты от фишинга ATP в центре безопасности & соответствия требованиям вы фактически создаете правило защиты от фишинга и сопоставленную политику защиты от фишинга с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="85e92-117">When you create an ATP anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="85e92-118">При изменении политики защиты от фишинга ATP в центре безопасности & соответствия требованиям параметры, связанные с фильтрами "имя", "приоритет", "включено" или "отключено" и "отправителяировать", изменяют правило защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="85e92-118">When you modify an ATP anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="85e92-119">Все остальные параметры изменяют соответствующую политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="85e92-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="85e92-120">При удалении политики защиты от фишинга ATP из центра безопасности & соответствия требованиям, удаляются правила защиты от фишинга и связанная с ним политика защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="85e92-120">When you remove an ATP anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="85e92-121">В Exchange Online PowerShell разница между политиками защиты от фишинга и правилами защиты от фишинга очевидна.</span><span class="sxs-lookup"><span data-stu-id="85e92-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="85e92-122">Вы управляете политиками защиты от фишинга с помощью командлетов \*\* \* -AntiPhishPolicy\*\* , а также управляете правилами защиты от фишинга с помощью командлетов \*\* \* -AntiPhishRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="85e92-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="85e92-123">В PowerShell сначала создается политика защиты от фишинга, затем создается правило защиты от фишинга, идентифицирующее политику, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="85e92-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="85e92-124">В PowerShell параметры политики защиты от фишинга и антифишинга изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="85e92-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

- <span data-ttu-id="85e92-125">При удалении политики защиты от фишинга из PowerShell соответствующее правило защиты от фишинга не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="85e92-125">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="85e92-126">Политика защиты от фишинга по умолчанию ATP</span><span class="sxs-lookup"><span data-stu-id="85e92-126">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="85e92-127">Каждая организация с пакетом ATP имеет встроенную антифишинговую политику ATP Office365 по умолчанию, которая имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="85e92-127">Every ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="85e92-128">Политика защиты от фишинга с именем Office365 по умолчанию применяется ко всем получателям в Организации, несмотря на то, что правило защиты от фишинга (фильтры получателей), связанное с политикой, отсутствует.</span><span class="sxs-lookup"><span data-stu-id="85e92-128">The anti-phish policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="85e92-129">Политика с именем Office365 по умолчанию имеет значение приоритета, которое **меньше** , чем недоступно для изменения (политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="85e92-129">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="85e92-130">Все создаваемые настраиваемые политики всегда имеют более высокий приоритет, чем политика с именем Office365 по умолчанию, отличная от фишинга.</span><span class="sxs-lookup"><span data-stu-id="85e92-130">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="85e92-131">Политика с именем Office365-фишинг по умолчанию является политикой **по умолчанию (свойство IsDefault** имеет значение `True` ), и вы не можете удалить политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="85e92-131">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="85e92-132">Чтобы повысить эффективность защиты от фишинга, вы можете создать настраиваемые политики защиты от фишинга ATP с более четкими параметрами, которые применяются к определенным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="85e92-132">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="85e92-133">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="85e92-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="85e92-134">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="85e92-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="85e92-135">Чтобы перейти непосредственно на страницу **защиты от фишинга ATP** , используйте <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="85e92-135">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="85e92-136">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="85e92-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="85e92-137">Прежде чем выполнять процедуры, описанные в этом разделе, необходимо назначить разрешения.</span><span class="sxs-lookup"><span data-stu-id="85e92-137">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="85e92-138">Для добавления, изменения и удаления политик защиты от фишинга ATP необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="85e92-138">To add, modify, and delete ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="85e92-139">**Управление организацией** или **администратор безопасности** в [центре безопасности & соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="85e92-139">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="85e92-140">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="85e92-140">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="85e92-141">Для доступа только для чтения к политикам защиты от фишинга ATP необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="85e92-141">For read-only access to ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="85e92-142">**Средство чтения безопасности** в [центре безопасности & соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="85e92-142">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="85e92-143">**Управление организацией только с просмотром** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="85e92-143">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="85e92-144">Рекомендуемые параметры политик защиты от фишинга ATP приведены в статье [Параметры политики защиты от фишинга в Office ATP](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="85e92-144">For our recommended settings for ATP anti-phishing policies, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="85e92-145">Разрешить применение новой или обновленной политики до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="85e92-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="85e92-146">Сведения о том, когда политики защиты от фишинга применяются в конвейере фильтрации, приведены в статье [порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="85e92-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="85e92-147">Использование центра безопасности & соответствия требованиям для создания политик защиты от фишинга ATP</span><span class="sxs-lookup"><span data-stu-id="85e92-147">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="85e92-148">Создание настраиваемой политики защиты от фишинга ATP в центре безопасности & соответствия требованиям создает правило защиты от фишинга и сопоставленную политику защиты от фишинга одновременно с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="85e92-148">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="85e92-149">При создании политики защиты от фишинга ATP можно указать только имя политики, описание и фильтр получателей, которые определяют, к кому применяется политика.</span><span class="sxs-lookup"><span data-stu-id="85e92-149">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="85e92-150">После создания политики вы можете изменить политику, чтобы изменить или просмотреть параметры защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="85e92-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="85e92-151">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** для \> **Policy** \> **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="85e92-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="85e92-152">На странице **Защита от фишинга** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="85e92-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="85e92-153">Откроется мастер **создания новой политики защиты от фишинга** .</span><span class="sxs-lookup"><span data-stu-id="85e92-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="85e92-154">На странице " **назвать политику** " настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="85e92-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="85e92-155">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="85e92-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="85e92-156">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="85e92-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="85e92-157">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="85e92-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="85e92-158">На появившейся странице " **применено к** " определите внутренних получателей, к которым применяется политика.</span><span class="sxs-lookup"><span data-stu-id="85e92-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="85e92-159">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="85e92-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="85e92-160">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="85e92-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="85e92-161">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="85e92-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="85e92-162">Нажмите кнопку **Добавить условие**.</span><span class="sxs-lookup"><span data-stu-id="85e92-162">Click **Add a condition**.</span></span> <span data-ttu-id="85e92-163">В появившемся раскрывающемся меню выберите условие **применено, если**:</span><span class="sxs-lookup"><span data-stu-id="85e92-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="85e92-164">**Получатель**: указывает один или несколько почтовых ящиков, почтовых пользователей или почтовых контактов в Организации.</span><span class="sxs-lookup"><span data-stu-id="85e92-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="85e92-165">**Получатель является участником**: указывает одну или несколько групп в Организации.</span><span class="sxs-lookup"><span data-stu-id="85e92-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="85e92-166">**Домен получателя**: указывает получателей в одном или нескольких настроенных обслуживаемых доменах в Организации.</span><span class="sxs-lookup"><span data-stu-id="85e92-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="85e92-167">После выбора условия появится соответствующее раскрывающийся список с **одним из этих** полей.</span><span class="sxs-lookup"><span data-stu-id="85e92-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="85e92-168">Щелкните поле и прокрутите список выбираемых значений.</span><span class="sxs-lookup"><span data-stu-id="85e92-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="85e92-169">Щелкните поле и начните ввод текста, чтобы отфильтровать список и выбрать значение.</span><span class="sxs-lookup"><span data-stu-id="85e92-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="85e92-170">Чтобы добавить дополнительные значения, щелкните пустую область в поле.</span><span class="sxs-lookup"><span data-stu-id="85e92-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="85e92-171">Чтобы удалить отдельные записи, нажмите кнопку **Удалить** ![ значок "удалить ](../../media/scc-remove-icon.png) " на значении.</span><span class="sxs-lookup"><span data-stu-id="85e92-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="85e92-172">Чтобы удалить условие целиком, нажмите кнопку **Удалить** ![ значок "удалить ](../../media/scc-remove-icon.png) " в условии.</span><span class="sxs-lookup"><span data-stu-id="85e92-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="85e92-173">Чтобы добавить дополнительное условие, щелкните **Добавить условие** и выберите оставшееся значение в разделе **применено, если**.</span><span class="sxs-lookup"><span data-stu-id="85e92-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="85e92-174">Чтобы добавить исключения, щелкните **Добавить условие** и выберите исключение в разделе **за исключением if**.</span><span class="sxs-lookup"><span data-stu-id="85e92-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="85e92-175">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="85e92-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="85e92-176">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="85e92-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="85e92-177">На открывшейся странице **Проверьте параметры** проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="85e92-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="85e92-178">Для изменения каждого параметра можно нажать кнопку **изменить** .</span><span class="sxs-lookup"><span data-stu-id="85e92-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="85e92-179">По завершении нажмите кнопку **создать эту политику**.</span><span class="sxs-lookup"><span data-stu-id="85e92-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="85e92-180">Нажмите кнопку **ОК** в появившемся диалоговом окне подтверждения.</span><span class="sxs-lookup"><span data-stu-id="85e92-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="85e92-181">После создания политики защиты от фишинга ATP с помощью этих общих параметров политики используйте инструкции, приведенные в следующем разделе, для настройки параметров защиты в политике.</span><span class="sxs-lookup"><span data-stu-id="85e92-181">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="85e92-182">Использование центра безопасности & соответствия требованиям для изменения политик защиты от фишинга ATP</span><span class="sxs-lookup"><span data-stu-id="85e92-182">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="85e92-183">Используйте следующие процедуры для изменения политик защиты от фишинга ATP: созданной политики или существующих политик, которые вы уже настроили.</span><span class="sxs-lookup"><span data-stu-id="85e92-183">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="85e92-184">Если вы еще не сделали это, откройте центр безопасности & соответствия требованиям и перейдите к разделу политика **управления угрозами** для \> **Policy** \> **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="85e92-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="85e92-185">Выберите настраиваемую антифишинговую политику ATP, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="85e92-185">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="85e92-186">Если он уже выбран, отмените его выбор и снова выберите его.</span><span class="sxs-lookup"><span data-stu-id="85e92-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="85e92-187">Откроется всплывающее окно \*\*изменение политики \<name\> \*\* .</span><span class="sxs-lookup"><span data-stu-id="85e92-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="85e92-188">Если щелкнуть **изменить** в любом разделе, вы получите доступ к параметрам в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="85e92-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="85e92-189">Следующие действия представлены в порядке их появления, но не являются последовательными (можно выбирать и изменять разделы в любом порядке).</span><span class="sxs-lookup"><span data-stu-id="85e92-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="85e92-190">После нажатия кнопки **изменить** в разделе Доступные параметры отображаются в формате мастера, но вы можете перейти к страницам в любом порядке, а затем нажать кнопку **сохранить** на любой странице (или **отменить** или **Закрыть** ![ значок Закрыть ](../../media/scc-remove-icon.png) , чтобы вернуться на страницу \*\*изменение политики \<name\> \*\* (не обязательно посещать последнюю страницу мастера, чтобы сохранить или оставить).</span><span class="sxs-lookup"><span data-stu-id="85e92-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="85e92-191">**Параметр политики**: нажмите кнопку **изменить** , чтобы изменить параметры, которые были доступны при [создании политики](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) , описанной в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="85e92-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="85e92-192">**Name**</span><span class="sxs-lookup"><span data-stu-id="85e92-192">**Name**</span></span>
   - <span data-ttu-id="85e92-193">**Описание**</span><span class="sxs-lookup"><span data-stu-id="85e92-193">**Description**</span></span>
   - <span data-ttu-id="85e92-194">**Применяется к**</span><span class="sxs-lookup"><span data-stu-id="85e92-194">**Applied to**</span></span>
   - <span data-ttu-id="85e92-195">**Проверка параметров**</span><span class="sxs-lookup"><span data-stu-id="85e92-195">**Review your settings**</span></span>

   <span data-ttu-id="85e92-196">По завершении нажмите кнопку **сохранить** на любой странице.</span><span class="sxs-lookup"><span data-stu-id="85e92-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="85e92-197">**Олицетворение**: нажмите **изменить** , чтобы изменить защищенных отправителей и защищенных доменов в политике.</span><span class="sxs-lookup"><span data-stu-id="85e92-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="85e92-198">Эти параметры являются условием для политики, определяющим поддельные отправители для поиска (по отдельности или по домену) в адресе отправителя входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="85e92-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="85e92-199">Дополнительные сведения см. [в разделе параметры олицетворения в политиках защиты от фишинга ATP](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="85e92-199">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="85e92-200">**Добавление пользователей для защиты**: значение по умолчанию: **отключено**.</span><span class="sxs-lookup"><span data-stu-id="85e92-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="85e92-201">Чтобы включить его, на слайде установите переключатель в значение **вкл**., а затем нажмите появившуюся кнопку **Добавить пользователя** .</span><span class="sxs-lookup"><span data-stu-id="85e92-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="85e92-202">В появившемся всплывающем окне **Добавление пользователя** настройте следующие значения:</span><span class="sxs-lookup"><span data-stu-id="85e92-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="85e92-203">**Адрес электронной почты**:</span><span class="sxs-lookup"><span data-stu-id="85e92-203">**Email address**:</span></span>

        - <span data-ttu-id="85e92-204">Щелкните поле и прокрутите список пользователей, чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="85e92-204">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="85e92-205">Щелкните поле и начните ввод текста, чтобы отфильтровать список и выбрать пользователя.</span><span class="sxs-lookup"><span data-stu-id="85e92-205">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="85e92-206">Чтобы удалить запись, щелкните **Удалить** ![ значок удаления ](../../media/scc-remove-icon.png) на пользователе.</span><span class="sxs-lookup"><span data-stu-id="85e92-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="85e92-207">**Name**: это значение заполняется на основе выбранного адреса электронной почты, но его можно изменить.</span><span class="sxs-lookup"><span data-stu-id="85e92-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="85e92-208">По завершении нажмите кнопку **сохранить** на любой странице.</span><span class="sxs-lookup"><span data-stu-id="85e92-208">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="85e92-209">Чтобы изменить существующую запись, выберите защищенного пользователя в списке.</span><span class="sxs-lookup"><span data-stu-id="85e92-209">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="85e92-210">**Добавление доменов для защиты**: Настройте один или оба из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="85e92-210">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="85e92-211">**Автоматически включать домены, которые я принимаю**: значение по умолчанию — " **отключено**".</span><span class="sxs-lookup"><span data-stu-id="85e92-211">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="85e92-212">Чтобы включить его, установите переключатель в значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="85e92-212">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="85e92-213">**Включить пользовательские домены**: значение по умолчанию: **отключено**.</span><span class="sxs-lookup"><span data-stu-id="85e92-213">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="85e92-214">Чтобы включить его, на слайде установите переключатель в значение **вкл**., в поле **Добавить домены** введите имя домена (например, contoso.com), нажмите клавишу ВВОД и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="85e92-214">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="85e92-215">**Действия**: щелкните **Правка**</span><span class="sxs-lookup"><span data-stu-id="85e92-215">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="85e92-216">**Если олицетворенный пользователь отправляет сообщение электронной почты**: настройте одно из следующих действий для сообщений, для которых поддельный отправитель является одним из защищенных пользователей, указанных в разделе **Добавление пользователей для защиты**:</span><span class="sxs-lookup"><span data-stu-id="85e92-216">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="85e92-217">**Не применяйте никаких действий**</span><span class="sxs-lookup"><span data-stu-id="85e92-217">**Don't apply any action**</span></span>
       - <span data-ttu-id="85e92-218">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="85e92-218">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="85e92-219">**Переместить сообщение в папку "Нежелательная почта"**</span><span class="sxs-lookup"><span data-stu-id="85e92-219">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="85e92-220">**Помещать сообщение в карантин**</span><span class="sxs-lookup"><span data-stu-id="85e92-220">**Quarantine the message**</span></span>
       - <span data-ttu-id="85e92-221">**Доставка сообщения и добавление других адресов в строку "СК"**</span><span class="sxs-lookup"><span data-stu-id="85e92-221">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="85e92-222">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="85e92-222">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="85e92-223">**Если олицетворенный домен отправляет сообщение электронной почты**: настройте одно из следующих действий для сообщений, для которых поддельный отправитель находится в одном из защищенных доменов, указанных в разделе **Добавление доменов для защиты**:</span><span class="sxs-lookup"><span data-stu-id="85e92-223">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="85e92-224">**Не применяйте никаких действий**</span><span class="sxs-lookup"><span data-stu-id="85e92-224">**Don't apply any action**</span></span>
     - <span data-ttu-id="85e92-225">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="85e92-225">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="85e92-226">**Переместить сообщение в папку "Нежелательная почта"**</span><span class="sxs-lookup"><span data-stu-id="85e92-226">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="85e92-227">**Помещать сообщение в карантин**</span><span class="sxs-lookup"><span data-stu-id="85e92-227">**Quarantine the message**</span></span>
     - <span data-ttu-id="85e92-228">**Доставка сообщения и добавление других адресов в строку "СК"**</span><span class="sxs-lookup"><span data-stu-id="85e92-228">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="85e92-229">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="85e92-229">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="85e92-230">Щелкните **включить советы по безопасности олицетворения** и настройте любой из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="85e92-230">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="85e92-231">**Показывать подсказку для олицетворенных пользователей**: значение по умолчанию: **отключено**.</span><span class="sxs-lookup"><span data-stu-id="85e92-231">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="85e92-232">Чтобы включить его, установите переключатель в значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="85e92-232">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="85e92-233">**Показывать подсказку для олицетворенных доменов**: значение по умолчанию: **отключено**.</span><span class="sxs-lookup"><span data-stu-id="85e92-233">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="85e92-234">Чтобы включить его, установите переключатель в значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="85e92-234">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="85e92-235">**Показывать подсказку для нестандартных символов**: значение по умолчанию: **отключено**.</span><span class="sxs-lookup"><span data-stu-id="85e92-235">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="85e92-236">Чтобы включить его, установите переключатель в значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="85e92-236">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="85e92-237">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="85e92-237">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="85e92-238">**Аналитика почтовых ящиков**:</span><span class="sxs-lookup"><span data-stu-id="85e92-238">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="85e92-239">**Включить логику операций с почтовыми ящиками?**: значение по умолчанию: **включено**.</span><span class="sxs-lookup"><span data-stu-id="85e92-239">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="85e92-240">Чтобы отключить его, установите переключатель в значение **выкл**.</span><span class="sxs-lookup"><span data-stu-id="85e92-240">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="85e92-241">**Включить защиту от олицетворения на основе логики почтовых ящиков?**: этот параметр доступен, только **On**если **включена логика операций с почтовыми ящиками?** включен.</span><span class="sxs-lookup"><span data-stu-id="85e92-241">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="85e92-242">В **том случае, если сообщение отправляется олицетворенным пользователем**, можно указать одно из следующих действий, чтобы принять участие в сообщениях, которые не прошли логику операций с почтовыми ящиками (то же, что доступны для защищенных пользователей и защищенных доменов):</span><span class="sxs-lookup"><span data-stu-id="85e92-242">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="85e92-243">**Не применяйте никаких действий**</span><span class="sxs-lookup"><span data-stu-id="85e92-243">**Don't apply any action**</span></span>
       - <span data-ttu-id="85e92-244">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="85e92-244">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="85e92-245">**Переместить сообщение в папку "Нежелательная почта"**</span><span class="sxs-lookup"><span data-stu-id="85e92-245">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="85e92-246">**Помещать сообщение в карантин**</span><span class="sxs-lookup"><span data-stu-id="85e92-246">**Quarantine the message**</span></span>
       - <span data-ttu-id="85e92-247">**Доставка сообщения и добавление других адресов в строку "СК"**</span><span class="sxs-lookup"><span data-stu-id="85e92-247">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="85e92-248">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="85e92-248">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="85e92-249">**Добавление надежных отправителей и доменов**: Укажите исключения для политики:</span><span class="sxs-lookup"><span data-stu-id="85e92-249">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="85e92-250">**Надежные отправители**:</span><span class="sxs-lookup"><span data-stu-id="85e92-250">**Trusted senders**:</span></span>

       - <span data-ttu-id="85e92-251">Щелкните поле и прокрутите список пользователей, чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="85e92-251">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="85e92-252">Щелкните поле и начните ввод текста, чтобы отфильтровать список и выбрать пользователя.</span><span class="sxs-lookup"><span data-stu-id="85e92-252">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="85e92-253">Чтобы удалить запись, щелкните **Удалить** ![ значок удаления ](../../media/scc-remove-icon.png) на пользователе.</span><span class="sxs-lookup"><span data-stu-id="85e92-253">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="85e92-254">**Доверенные домены**: введите имя домена (например, contoso.com), нажмите клавишу ВВОД и повторите операцию при необходимости.</span><span class="sxs-lookup"><span data-stu-id="85e92-254">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="85e92-255">**Проверьте параметры**: вместо того, чтобы щелкать каждый отдельный шаг, параметры отображаются в сводке.</span><span class="sxs-lookup"><span data-stu-id="85e92-255">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="85e92-256">Вы можете щелкнуть **изменить** в каждом разделе, чтобы вернуться на соответствующую страницу.</span><span class="sxs-lookup"><span data-stu-id="85e92-256">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="85e92-257">Вы можете включать и **отключать** следующие параметры **непосредственно на этой** странице:</span><span class="sxs-lookup"><span data-stu-id="85e92-257">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="85e92-258">**Защищенные пользователи**</span><span class="sxs-lookup"><span data-stu-id="85e92-258">**Protected users**</span></span>
       - <span data-ttu-id="85e92-259">**Защищенные домены** \> **Включить домены, которыми я хочу**</span><span class="sxs-lookup"><span data-stu-id="85e92-259">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="85e92-260">**Защищенные домены** \> **Защищенные домены** (личные домены)</span><span class="sxs-lookup"><span data-stu-id="85e92-260">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="85e92-261">**Аналитика почтовых ящиков**</span><span class="sxs-lookup"><span data-stu-id="85e92-261">**Mailbox intelligence**</span></span>

   <span data-ttu-id="85e92-262">По завершении нажмите кнопку **сохранить** на любой странице.</span><span class="sxs-lookup"><span data-stu-id="85e92-262">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="85e92-263">**Подделка**: нажмите кнопку **изменить** , чтобы включить или отключить логику операций подделки, Отключить идентификацию отправителей, не прошедших проверку подлинности, в Outlook, а также настроить действие, применяемое к сообщениям от заблокированных поддельных отправителей.</span><span class="sxs-lookup"><span data-stu-id="85e92-263">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="85e92-264">Дополнительные сведения см в разделе [Параметры подделки в политиках защиты от фишинга](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="85e92-264">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="85e92-265">Обратите внимание, что эти же параметры также доступны в политиках защиты от фишинга в EOP.</span><span class="sxs-lookup"><span data-stu-id="85e92-265">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="85e92-266">**Параметры фильтра подделки**: значение по умолчанию — **включено**, и мы рекомендуем оставить его.</span><span class="sxs-lookup"><span data-stu-id="85e92-266">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="85e92-267">Чтобы отключить его, установите переключатель в значение **выкл**.</span><span class="sxs-lookup"><span data-stu-id="85e92-267">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="85e92-268">Дополнительные сведения: [Настройка логики анализа подделки в EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="85e92-268">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="85e92-269">Отключение защиты от спуфинга не требуется, если запись MX не указывает на Microsoft 365; Вместо этого вы включите расширенную фильтрацию для соединителей.</span><span class="sxs-lookup"><span data-stu-id="85e92-269">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="85e92-270">Инструкции см в разделе [Расширенная фильтрация соединителей в Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="85e92-270">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="85e92-271">**Включить функцию отправителя, не прошедший проверку подлинности**: значение по умолчанию: **включено**.</span><span class="sxs-lookup"><span data-stu-id="85e92-271">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="85e92-272">Чтобы отключить его, установите переключатель в значение **выкл**.</span><span class="sxs-lookup"><span data-stu-id="85e92-272">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="85e92-273">**Действия**: укажите действие, которое следует предпринять для сообщений, не прошедших анализ подделки:</span><span class="sxs-lookup"><span data-stu-id="85e92-273">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="85e92-274">**Если сообщение электронной почты отправлено пользователем, который не может подменить ваш домен**:</span><span class="sxs-lookup"><span data-stu-id="85e92-274">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="85e92-275">**Перемещение сообщения в папки "Нежелательная почта" получателей**</span><span class="sxs-lookup"><span data-stu-id="85e92-275">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="85e92-276">**Помещать сообщение в карантин**</span><span class="sxs-lookup"><span data-stu-id="85e92-276">**Quarantine the message**</span></span>

   - <span data-ttu-id="85e92-277">**Проверьте параметры**: вместо того, чтобы щелкать каждый отдельный шаг, параметры отображаются в сводке.</span><span class="sxs-lookup"><span data-stu-id="85e92-277">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="85e92-278">Вы можете щелкнуть **изменить** в каждом разделе, чтобы вернуться на соответствующую страницу.</span><span class="sxs-lookup"><span data-stu-id="85e92-278">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="85e92-279">Вы можете включать и **отключать** следующие параметры **непосредственно на этой** странице:</span><span class="sxs-lookup"><span data-stu-id="85e92-279">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="85e92-280">**Включение защиты от спуфинга**</span><span class="sxs-lookup"><span data-stu-id="85e92-280">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="85e92-281">**Включение функции отправителя без проверки подлинности**</span><span class="sxs-lookup"><span data-stu-id="85e92-281">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="85e92-282">По завершении нажмите кнопку **сохранить** на любой странице.</span><span class="sxs-lookup"><span data-stu-id="85e92-282">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="85e92-283">**Дополнительные параметры**: нажмите кнопку **изменить** , чтобы настроить расширенные пороговые значения фишинга.</span><span class="sxs-lookup"><span data-stu-id="85e92-283">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="85e92-284">Дополнительные сведения см в разделе [Расширенные пороговые значения фишинга в политиках защиты от фишинга ATP](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="85e92-284">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="85e92-285">**Расширенные пороговые значения фишинга**: выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="85e92-285">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="85e92-286">**1 — Стандартный** (это значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="85e92-286">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="85e92-287">**2 агрессивно**</span><span class="sxs-lookup"><span data-stu-id="85e92-287">**2 - Aggressive**</span></span>
   - <span data-ttu-id="85e92-288">**3 — более агрессивный**</span><span class="sxs-lookup"><span data-stu-id="85e92-288">**3 - More aggressive**</span></span>
   - <span data-ttu-id="85e92-289">**4 — наиболее агрессивный**</span><span class="sxs-lookup"><span data-stu-id="85e92-289">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="85e92-290">**Проверьте параметры**: нажмите кнопку **изменить** , чтобы вернуться на страницу **Расширенные пороговые значения фишинга** .</span><span class="sxs-lookup"><span data-stu-id="85e92-290">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="85e92-291">Когда все будет готово, нажмите кнопку **сохранить** на любой странице.</span><span class="sxs-lookup"><span data-stu-id="85e92-291">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="85e92-292">Вернитесь на страницу \*\*изменение политики \<Name\> \*\* , проверьте параметры и нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="85e92-292">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="85e92-293">Использование центра безопасности & соответствия требованиям для изменения политики защиты от фишинга ATP по умолчанию</span><span class="sxs-lookup"><span data-stu-id="85e92-293">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="85e92-294">Антифишинговая политика по умолчанию ATP называется Office365 Anti-фишингом по умолчанию и не отображается в списке политик.</span><span class="sxs-lookup"><span data-stu-id="85e92-294">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="85e92-295">Чтобы изменить политику защиты от фишинга ATP по умолчанию, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="85e92-295">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="85e92-296">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** для \> **Policy** \> **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="85e92-296">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="85e92-297">На странице **Защита от фишинга** щелкните **Политика по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="85e92-297">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="85e92-298">Откроется страница **изменение политики Office365 антифишинга по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="85e92-298">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="85e92-299">Доступны следующие разделы, которые содержат идентичные параметры при [изменении настраиваемой политики](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span><span class="sxs-lookup"><span data-stu-id="85e92-299">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="85e92-300">**Олицетворение**</span><span class="sxs-lookup"><span data-stu-id="85e92-300">**Impersonation**</span></span>
   - <span data-ttu-id="85e92-301">**Спуфинг**</span><span class="sxs-lookup"><span data-stu-id="85e92-301">**Spoof**</span></span>
   - <span data-ttu-id="85e92-302">**Дополнительные параметры**</span><span class="sxs-lookup"><span data-stu-id="85e92-302">**Advanced settings**</span></span>

   <span data-ttu-id="85e92-303">При изменении политики по умолчанию недоступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="85e92-303">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="85e92-304">Вы можете увидеть раздел и значения **параметра политики** , но нет ссылки для **редактирования** , поэтому вы не можете изменить параметры (имя политики, описание и пользователей, к которым применяется политика (она применяется ко всем получателям)).</span><span class="sxs-lookup"><span data-stu-id="85e92-304">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="85e92-305">Вы не можете удалить политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="85e92-305">You can't delete the default policy.</span></span>
   - <span data-ttu-id="85e92-306">Невозможно изменить приоритет политики по умолчанию (всегда применяется последний).</span><span class="sxs-lookup"><span data-stu-id="85e92-306">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="85e92-307">На странице **изменение политики Office365 Антифишинг по умолчанию** проверьте параметры и нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="85e92-307">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="85e92-308">Включение и отключение настраиваемых политик защиты от фишинга ATP</span><span class="sxs-lookup"><span data-stu-id="85e92-308">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="85e92-309">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** для \> **Policy** \> **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="85e92-309">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="85e92-310">Обратите внимание на значение в столбце **состояние** :</span><span class="sxs-lookup"><span data-stu-id="85e92-310">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="85e92-311">Чтобы отключить политику, на слайде переключитесь в режим **выключен** .</span><span class="sxs-lookup"><span data-stu-id="85e92-311">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="85e92-312">Чтобы включить политику, на слайде установите переключатель в значение **вкл** .</span><span class="sxs-lookup"><span data-stu-id="85e92-312">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="85e92-313">Отключить политику защиты от фишинга по умолчанию невозможно.</span><span class="sxs-lookup"><span data-stu-id="85e92-313">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="85e92-314">Установка приоритета настраиваемых политик защиты от фишинга ATP</span><span class="sxs-lookup"><span data-stu-id="85e92-314">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="85e92-315">По умолчанию политикам защиты от фишинга ATP назначается приоритет, основанный на порядке, в котором они были созданы (более новые политики имеют более низкий приоритет, чем старые политики).</span><span class="sxs-lookup"><span data-stu-id="85e92-315">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="85e92-316">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="85e92-316">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="85e92-317">Приоритеты двух политик не могут совпадать.</span><span class="sxs-lookup"><span data-stu-id="85e92-317">No two policies can have the same priority.</span></span>

<span data-ttu-id="85e92-318">Настраиваемые политики защиты от фишинга ATP отображаются в порядке их обработки (первая политика имеет значение **приоритета** 0).</span><span class="sxs-lookup"><span data-stu-id="85e92-318">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="85e92-319">По умолчанию политика защиты от фишинга с именем Office365 по умолчанию имеет **самый низкий**приоритет, и вы не можете изменить его.</span><span class="sxs-lookup"><span data-stu-id="85e92-319">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="85e92-320">**Note**: в центре безопасности & соответствия требованиям можно изменить приоритет антифишинговой политики ATP после ее создания.</span><span class="sxs-lookup"><span data-stu-id="85e92-320">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="85e92-321">В PowerShell можно переопределить приоритет по умолчанию при создании правила защиты от фишинга (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="85e92-321">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="85e92-322">Чтобы изменить приоритет политики, щелкните **увеличить** или **уменьшить** приоритет в свойствах политики (нельзя напрямую изменить номер **приоритета** в центре безопасности & соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="85e92-322">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="85e92-323">Изменение приоритета политики имеет смысл только в том случае, если у вас есть несколько политик.</span><span class="sxs-lookup"><span data-stu-id="85e92-323">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="85e92-324">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** для \> **Policy** \> **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="85e92-324">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="85e92-325">Выберите политику, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="85e92-325">Select the policy that you want to modify.</span></span> <span data-ttu-id="85e92-326">Если он уже выбран, отмените его выбор и снова выберите его.</span><span class="sxs-lookup"><span data-stu-id="85e92-326">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="85e92-327">Откроется всплывающее окно \*\*изменение политики \<name\> \*\* .</span><span class="sxs-lookup"><span data-stu-id="85e92-327">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="85e92-328">Для настраиваемой политики антифишинга ATP со значением **приоритета** **0** доступна только кнопка " **уменьшить приоритет** ".</span><span class="sxs-lookup"><span data-stu-id="85e92-328">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="85e92-329">Для настраиваемой политики антифишинга ATP с наименьшим значением **приоритета** (например, **3**) доступна только кнопка **повышения приоритета** .</span><span class="sxs-lookup"><span data-stu-id="85e92-329">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="85e92-330">При наличии трех или более настраиваемых политик защиты от фишинга для политик между максимальным и минимальным значениями приоритета доступны кнопки **увеличить приоритет** и **уменьшить приоритет** .</span><span class="sxs-lookup"><span data-stu-id="85e92-330">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="85e92-331">Щелкните **увеличить** или **уменьшить** приоритет, чтобы изменить значение **приоритета** .</span><span class="sxs-lookup"><span data-stu-id="85e92-331">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="85e92-332">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="85e92-332">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="85e92-333">Использование центра безопасности & соответствия требованиям для просмотра политик защиты от фишинга ATP</span><span class="sxs-lookup"><span data-stu-id="85e92-333">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="85e92-334">В центре безопасности & соответствия требованиям и перейдите к разделу политика **управления угрозами** для \> **Policy** \> **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="85e92-334">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="85e92-335">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="85e92-335">Do one of the following steps:</span></span>

   - <span data-ttu-id="85e92-336">Выберите настраиваемую антифишинговую политику ATP, которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="85e92-336">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="85e92-337">Если он уже выбран, отмените его выбор и снова выберите его.</span><span class="sxs-lookup"><span data-stu-id="85e92-337">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="85e92-338">Щелкните **политику по умолчанию** , чтобы просмотреть политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="85e92-338">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="85e92-339">Откроется всплывающее окно \*\*изменение политики \<name\> \*\* , в котором можно просмотреть параметры и значения.</span><span class="sxs-lookup"><span data-stu-id="85e92-339">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="85e92-340">Использование центра безопасности & соответствия требованиям для удаления политик защиты от фишинга ATP</span><span class="sxs-lookup"><span data-stu-id="85e92-340">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="85e92-341">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** для \> **Policy** \> **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="85e92-341">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="85e92-342">Выберите политику, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="85e92-342">Select the policy that you want to remove.</span></span> <span data-ttu-id="85e92-343">Если он уже выбран, отмените его выбор и снова выберите его.</span><span class="sxs-lookup"><span data-stu-id="85e92-343">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="85e92-344">В появившемся всплывающем окне \*\*изменение политики \<name\> \*\* выберите команду **удалить политику**, а затем нажмите кнопку **Да** в появившемся диалоговом окне предупреждения.</span><span class="sxs-lookup"><span data-stu-id="85e92-344">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="85e92-345">Политику по умолчанию удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="85e92-345">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="85e92-346">Настройка политик защиты от фишинга ATP с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="85e92-346">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="85e92-347">Создание политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="85e92-347">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="85e92-348">Создание политики защиты от фишинга в PowerShell состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="85e92-348">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="85e92-349">Создайте политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="85e92-349">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="85e92-350">Создайте правило защиты от фишинга, которое определяет политику защиты от фишинга, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="85e92-350">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="85e92-351">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="85e92-351">**Notes**:</span></span>

- <span data-ttu-id="85e92-352">Вы можете создать новое правило защиты от фишинга и назначить для него существующую, несвязанную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="85e92-352">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="85e92-353">Правило защиты от фишинга не может быть связано с несколькими политиками защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="85e92-353">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="85e92-354">Вы можете настроить следующие параметры для новых политик защиты от фишинга в PowerShell, которые недоступны в центре безопасности & соответствия требованиям, пока не будет создана политика:</span><span class="sxs-lookup"><span data-stu-id="85e92-354">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="85e92-355">Создайте новую политику как отключенную (_включена_ `$false` в командлете **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="85e92-355">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="85e92-356">Задайте приоритет политики при создании (_приоритет_ _\<Number\>_ ) для командлета **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="85e92-356">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="85e92-357">Новая политика защиты от фишинга, созданная в PowerShell, не отображается в центре безопасности & соответствия требованиям, пока вы не назначите политику для правила защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="85e92-357">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="85e92-358">Шаг 1: использование PowerShell для создания политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="85e92-358">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="85e92-359">Чтобы создать политику защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="85e92-359">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="85e92-360">В этом примере создается политика защиты от фишинга с именем Research карантин со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="85e92-360">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="85e92-361">Политика включена (параметр _Enabled_ не используется, а значение по умолчанию — `$true` ).</span><span class="sxs-lookup"><span data-stu-id="85e92-361">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="85e92-362">Описание: "политика отделов исследований".</span><span class="sxs-lookup"><span data-stu-id="85e92-362">The description is: Research department policy.</span></span>
- <span data-ttu-id="85e92-363">Включает защиту доменов организации для всех обслуживаемых доменов, а также целевые домены для защиты fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="85e92-363">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="85e92-364">Указывает, что защищать от имитации нужно пользователя Mai Fujito (mfujito@fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="85e92-364">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="85e92-365">Включает аналитику почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="85e92-365">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="85e92-366">Включает защиту каталога почтовых ящиков и задает действие карантина.</span><span class="sxs-lookup"><span data-stu-id="85e92-366">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="85e92-367">Включает советы по безопасности.</span><span class="sxs-lookup"><span data-stu-id="85e92-367">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="85e92-368">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="85e92-368">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="85e92-369">Шаг 2: использование PowerShell для создания правила защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="85e92-369">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="85e92-370">Чтобы создать правило защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="85e92-370">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="85e92-371">В этом примере создается правило защиты от фишинга с именем "Отдел исследований" со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="85e92-371">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="85e92-372">Правило связано с политикой защиты от фишинга с именем "карантин исследований".</span><span class="sxs-lookup"><span data-stu-id="85e92-372">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="85e92-373">Правило применяется к членам группы "Research Department".</span><span class="sxs-lookup"><span data-stu-id="85e92-373">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="85e92-374">Так как мы не используем параметр _Priority_ , используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="85e92-374">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="85e92-375">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="85e92-375">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="85e92-376">Просмотр политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="85e92-376">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="85e92-377">Чтобы просмотреть существующие политики защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="85e92-377">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="85e92-378">В этом примере возвращается сводный список всех политик защиты от фишинга вместе с заданными свойствами.</span><span class="sxs-lookup"><span data-stu-id="85e92-378">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="85e92-379">В этом примере возвращаются все значения свойств для политики защиты от фишинга под названием "руководители".</span><span class="sxs-lookup"><span data-stu-id="85e92-379">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="85e92-380">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="85e92-380">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="85e92-381">Просмотр правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="85e92-381">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="85e92-382">Чтобы просмотреть существующие правила защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="85e92-382">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="85e92-383">В этом примере возвращается сводный список всех правил защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="85e92-383">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="85e92-384">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="85e92-384">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="85e92-385">В этом примере возвращаются все значения свойств для правила защиты от фишинга Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="85e92-385">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="85e92-386">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="85e92-386">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="85e92-387">Использование PowerShell для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="85e92-387">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="85e92-388">Кроме следующих элементов, одни и те же параметры доступны при изменении политики защиты от фишинга в PowerShell, как при создании политики, как описано в [шаге 1: с помощью PowerShell создайте раздел политики защиты от фишинга](#step-1-use-powershell-to-create-an-anti-phish-policy) , приведенный ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="85e92-388">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="85e92-389">Переключатель _македефаулт_ , который включает указанную политику в политику по умолчанию (применяется ко всем, всегда **самый низкий** приоритет и не может удалить его), доступна только при изменении политики защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85e92-389">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="85e92-390">Вы не можете переименовать политику защиты от фишинга (командлет **Set-AntiPhishPolicy** не имеет параметра _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="85e92-390">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="85e92-391">При переименовании политики защиты от фишинга в центре безопасности & соответствия требованиям Вы переименовываете только _правило_защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="85e92-391">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="85e92-392">Чтобы изменить политику защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="85e92-392">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="85e92-393">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="85e92-393">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="85e92-394">Использование PowerShell для изменения правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="85e92-394">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="85e92-395">Единственный параметр, недоступный при изменении правила защиты от фишинга в PowerShell — это параметр _Enabled_ , позволяющий создать отключенное правило.</span><span class="sxs-lookup"><span data-stu-id="85e92-395">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="85e92-396">Чтобы включить или отключить существующие правила защиты от фишинга, ознакомьтесь со статьей в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="85e92-396">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="85e92-397">В противном случае дополнительные параметры не будут доступны при изменении правила защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85e92-397">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="85e92-398">Те же параметры доступны при создании правила, как описано в [шаге 2: используйте PowerShell для создания раздела правила защиты от фишинга](#step-2-use-powershell-to-create-an-anti-phish-rule) , приведенного ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="85e92-398">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="85e92-399">Чтобы изменить правило защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="85e92-399">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="85e92-400">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="85e92-400">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="85e92-401">Включение и отключение правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="85e92-401">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="85e92-402">Включение или отключение правила защиты от фишинга в PowerShell включает или отключает всю политику защиты от фишинга (правило защиты от фишинга и назначенную политику защиты от фишинга).</span><span class="sxs-lookup"><span data-stu-id="85e92-402">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="85e92-403">Вы не можете включать или отключать политику защиты от фишинга по умолчанию (всегда применяется ко всем получателям).</span><span class="sxs-lookup"><span data-stu-id="85e92-403">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="85e92-404">Чтобы включить или отключить правило защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="85e92-404">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="85e92-405">В этом примере отключается правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="85e92-405">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="85e92-406">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="85e92-406">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="85e92-407">Подробные сведения о синтаксисе и параметрах можно найти в статье [Enable – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="85e92-407">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="85e92-408">Настройка приоритета правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="85e92-408">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="85e92-409">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="85e92-409">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="85e92-410">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="85e92-410">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="85e92-411">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="85e92-411">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="85e92-412">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="85e92-412">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="85e92-413">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="85e92-413">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="85e92-414">Чтобы задать приоритет правила защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="85e92-414">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="85e92-p143">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="85e92-p143">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="85e92-417">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="85e92-417">**Notes**:</span></span>

- <span data-ttu-id="85e92-418">Чтобы задать приоритет нового правила при его создании, используйте параметр _Priority_ в командлете **New – AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="85e92-418">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="85e92-419">По умолчанию политика защиты от фишинга не имеет соответствующего правила защиты от фишинга и имеет **самое низкое**значение приоритета.</span><span class="sxs-lookup"><span data-stu-id="85e92-419">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="85e92-420">Удаление политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="85e92-420">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="85e92-421">При использовании PowerShell для удаления политики защиты от фишинга соответствующее правило защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="85e92-421">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="85e92-422">Чтобы удалить политику защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="85e92-422">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="85e92-423">В этом примере удаляется политика защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="85e92-423">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="85e92-424">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="85e92-424">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="85e92-425">Удаление правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="85e92-425">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="85e92-426">При использовании PowerShell для удаления правила защиты от фишинга соответствующая политика защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="85e92-426">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="85e92-427">Чтобы удалить правило защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="85e92-427">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="85e92-428">В этом примере удаляется правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="85e92-428">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="85e92-429">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="85e92-429">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="85e92-430">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="85e92-430">How do you know these procedures worked?</span></span>

<span data-ttu-id="85e92-431">Чтобы убедиться в успешной настройке политик защиты от фишинга ATP, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="85e92-431">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="85e92-432">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** для \> **Policy** \> **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="85e92-432">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="85e92-433">Проверьте список политик, их значения **состояния** и значения **приоритета** .</span><span class="sxs-lookup"><span data-stu-id="85e92-433">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="85e92-434">Чтобы просмотреть дополнительные сведения, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="85e92-434">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="85e92-435">Выберите политику из списка и просмотрите сведения в всплывающем меню.</span><span class="sxs-lookup"><span data-stu-id="85e92-435">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="85e92-436">Щелкните **Политика по умолчанию** и просмотрите сведения в всплывающем меню.</span><span class="sxs-lookup"><span data-stu-id="85e92-436">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="85e92-437">В Exchange Online PowerShell замените на \<Name\> имя политики или правила и выполните следующую команду и проверьте параметры:</span><span class="sxs-lookup"><span data-stu-id="85e92-437">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
