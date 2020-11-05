---
title: Настройка политик защиты от фишинга в защитнике Майкрософт для Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как создавать, изменять и удалять расширенные политики защиты от фишинга, доступные в организациях с помощью защитника Майкрософт для Office 365.
ms.openlocfilehash: ecc68a8dc050a5f08c6982b023861e0ea8976775
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920660"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0a9ad-103">Настройка политик защиты от фишинга в защитнике Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="0a9ad-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0a9ad-104">Политики защиты от фишинга в [защитнике Microsoft для Office 365](office-365-atp.md) помогут защитить организацию от атак с фишингом на основе олицетворений и других типов фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-104">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="0a9ad-105">Для получения дополнительных сведений о различиях между политиками защиты от фишинга в Exchange Online Protection (EOP) и политиках защиты от фишинга в защитнике Microsoft для Office 365, обратитесь к разделу [Защита от фишинга](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-105">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="0a9ad-106">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="0a9ad-107">Для большей детализации можно также создать настраиваемые политики защиты от фишинга, которые применяются к определенным пользователям, группам или доменам в Организации.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="0a9ad-108">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="0a9ad-109">Политики защиты от фишинга можно настроить в центре безопасности & соответствия требованиям или в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-109">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="0a9ad-110">Дополнительные сведения о настройке политик защиты от фишинга, доступных в организациях Exchange Online Protection (то есть в организациях без защитника Майкрософт для Office 365), можно узнать [в статье Настройка политик защиты от фишинга в EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-110">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="0a9ad-111">Основные элементы политики защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-111">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="0a9ad-112">**Политика защиты от фишинга** : определяет защиту от фишинга, которую необходимо включить или отключить, а также действия, которые необходимо применить к параметрам.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-112">**The anti-phish policy** : Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="0a9ad-113">**Правило защиты от фишинга** : определяет приоритет и фильтры получателей (к которым применяется политика) для политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-113">**The anti-phish rule** : Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="0a9ad-114">Различия между этими двумя элементами не очевидны при управлении политиками защиты от фишинга в центре безопасности & соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-114">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="0a9ad-115">При создании политики вы фактически создаете правило защиты от фишинга и сопоставленную политику защиты от фишинга, используя одно и то же имя.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-115">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="0a9ad-116">При изменении политики параметры, связанные с фильтрами имен, приоритетов, включенных или отключенных и получателей, изменяют правило защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-116">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="0a9ad-117">Все остальные параметры изменяют соответствующую политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-117">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="0a9ad-118">При удалении политики удаляется правило защиты от фишинга и связанная с ним политика защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-118">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="0a9ad-119">В Exchange Online PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-119">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="0a9ad-120">Для получения дополнительных сведений обратитесь к разделу [использование Exchange Online PowerShell для настройки политик защиты от фишинга в разделе Microsoft Defender для Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-120">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this topic.</span></span>

<span data-ttu-id="0a9ad-121">Каждая организация Microsoft Defender для Office 365 имеет встроенную политику защиты от фишинга Office365 по умолчанию, которая имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-121">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="0a9ad-122">Политика применяется ко всем получателям в Организации, несмотря на то, что не существует правила защиты от фишинга (фильтры получателей), связанные с этой политикой.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-122">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="0a9ad-123">Для политики задано специальное значение приоритета **Самый низкий** , которое невозможно изменить (эта политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-123">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="0a9ad-124">Все созданные специальные политики всегда имеют более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-124">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="0a9ad-125">Эта политика является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-125">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="0a9ad-126">Чтобы повысить эффективность защиты от фишинга в защитнике Майкрософт для Office 365, можно создать настраиваемые политики защиты от фишинга с помощью более четких параметров, применяемых к определенным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-126">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0a9ad-127">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="0a9ad-127">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0a9ad-128">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-128">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0a9ad-129">Чтобы перейти непосредственно на страницу **защиты от фишинга ATP** , используйте <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="0a9ad-129">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="0a9ad-130">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="0a9ad-131">Прежде чем выполнять процедуры, описанные в этой статье, необходимо назначить разрешения.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="0a9ad-132">Для добавления, изменения и удаления политик защиты от фишинга необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-132">To add, modify, and delete anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="0a9ad-133">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-133">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="0a9ad-134">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-134">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="0a9ad-135">Для доступа только для чтения к политикам защиты от фишинга необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-135">For read-only access to anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="0a9ad-136">**Средство считывания сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-136">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="0a9ad-137">**Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-137">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="0a9ad-138">Для наших рекомендуемых параметров для политик защиты от фишинга в защитнике Microsoft для Office 365, обратитесь к разделу [Политика защиты от фишинга в разделе "Параметры защитника для office 365"](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-138">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="0a9ad-139">Разрешить применение новой или обновленной политики до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-139">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="0a9ad-140">Сведения о том, когда политики защиты от фишинга применяются в конвейере фильтрации, приведены в статье [порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-140">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0a9ad-141">Использование центра безопасности & соответствия требованиям для создания политик защиты от фишинга в защитнике Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="0a9ad-141">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0a9ad-142">Создание настраиваемой политики защиты от фишинга в центре безопасности & соответствия требованиям создает правило защиты от фишинга и сопоставленную политику защиты от фишинга одновременно с одним и тем же именем.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-142">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="0a9ad-143">При создании политики защиты от фишинга можно указать только имя политики, описание и фильтр получателей, которые определяют, к кому применяется политика.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-143">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="0a9ad-144">После создания политики вы можете изменить политику, чтобы изменить или просмотреть параметры защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-144">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="0a9ad-145">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** для \> **Policy** \> **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0a9ad-146">На странице **Защита от фишинга** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-146">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="0a9ad-147">Откроется мастер **создания новой политики защиты от фишинга** .</span><span class="sxs-lookup"><span data-stu-id="0a9ad-147">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="0a9ad-148">На странице " **назвать политику** " настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-148">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="0a9ad-149">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-149">**Name** : Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="0a9ad-150">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-150">**Description** : Enter an optional description for the policy.</span></span>

   <span data-ttu-id="0a9ad-151">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0a9ad-152">На появившейся странице " **применено к** " определите внутренних получателей, к которым применяется политика.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-152">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="0a9ad-153">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-153">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="0a9ad-154">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-154">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span> <span data-ttu-id="0a9ad-155">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-155">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

   <span data-ttu-id="0a9ad-156">Нажмите кнопку **Добавить условие**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-156">Click **Add a condition**.</span></span> <span data-ttu-id="0a9ad-157">В появившемся раскрывающемся меню выберите условие **применено, если** :</span><span class="sxs-lookup"><span data-stu-id="0a9ad-157">In the dropdown that appears, select a condition under **Applied if** :</span></span>

   - <span data-ttu-id="0a9ad-158">**Получатель** : указывает один или несколько почтовых ящиков, почтовых пользователей или почтовых контактов в Организации.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-158">**The recipient is** : Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="0a9ad-159">**Получатель является участником** : указывает одну или несколько групп в Организации.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-159">**The recipient is a member of** : Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="0a9ad-160">**Домен получателя** : указывает получателей в одном или нескольких настроенных обслуживаемых доменах в Организации.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-160">**The recipient domain is** : Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="0a9ad-161">После выбора условия появится соответствующее раскрывающийся список с **одним из этих** полей.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-161">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="0a9ad-162">Щелкните поле и прокрутите список выбираемых значений.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-162">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="0a9ad-163">Щелкните поле и начните ввод текста, чтобы отфильтровать список и выбрать значение.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-163">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="0a9ad-164">Чтобы добавить дополнительные значения, щелкните пустую область в поле.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-164">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="0a9ad-165">Чтобы удалить отдельные записи, нажмите кнопку **Удалить** ![ значок "удалить ](../../media/scc-remove-icon.png) " на значении.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-165">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="0a9ad-166">Чтобы удалить условие целиком, нажмите кнопку **Удалить** ![ значок "удалить ](../../media/scc-remove-icon.png) " в условии.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-166">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="0a9ad-167">Чтобы добавить дополнительное условие, щелкните **Добавить условие** и выберите оставшееся значение в разделе **применено, если**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-167">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="0a9ad-168">Чтобы добавить исключения, щелкните **Добавить условие** и выберите исключение в разделе **за исключением if**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-168">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="0a9ad-169">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="0a9ad-170">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0a9ad-171">На открывшейся странице **Проверьте параметры** проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-171">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="0a9ad-172">Для изменения каждого параметра можно нажать кнопку **изменить** .</span><span class="sxs-lookup"><span data-stu-id="0a9ad-172">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="0a9ad-173">По завершении нажмите кнопку **создать эту политику**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-173">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="0a9ad-174">Нажмите кнопку **ОК** в появившемся диалоговом окне подтверждения.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-174">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="0a9ad-175">После создания политики защиты от фишинга с помощью этих общих параметров выполните инструкции, приведенные в следующем разделе, чтобы настроить параметры защиты в политике.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-175">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0a9ad-176">Использование центра безопасности & соответствия требованиям для изменения политик защиты от фишинга в защитнике Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="0a9ad-176">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0a9ad-177">Используйте следующие процедуры для изменения политик защиты от фишинга: созданной вами новой политики или существующей ранее настроенной политики.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-177">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="0a9ad-178">Если вы еще не сделали это, откройте центр безопасности & соответствия требованиям и перейдите к разделу политика **управления угрозами** для \> **Policy** \> **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-178">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0a9ad-179">Выберите настраиваемую политику защиты от фишинга, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-179">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="0a9ad-180">Если он уже выбран, отмените его выбор и снова выберите его.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-180">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0a9ad-181">Откроется всплывающее окно **изменение политики \<name\>** .</span><span class="sxs-lookup"><span data-stu-id="0a9ad-181">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="0a9ad-182">Если щелкнуть **изменить** в любом разделе, вы получите доступ к параметрам в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-182">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="0a9ad-183">Следующие действия представлены в порядке их появления, но не являются последовательными (можно выбирать и изменять разделы в любом порядке).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-183">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="0a9ad-184">После нажатия кнопки **изменить** в разделе Доступные параметры отображаются в формате мастера, но вы можете перейти к страницам в любом порядке, а затем нажать кнопку **сохранить** на любой странице (или **отменить** или **Закрыть** ![ значок Закрыть ](../../media/scc-remove-icon.png) , чтобы вернуться на страницу **изменение политики \<name\>** (не обязательно посещать последнюю страницу мастера, чтобы сохранить или оставить).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-184">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="0a9ad-185">**Параметр политики** : нажмите кнопку **изменить** , чтобы изменить параметры, которые были доступны при [создании политики](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) , описанной в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-185">**Policy setting** : Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="0a9ad-186">**Название**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-186">**Name**</span></span>
   - <span data-ttu-id="0a9ad-187">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-187">**Description**</span></span>
   - <span data-ttu-id="0a9ad-188">**Применяется к**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-188">**Applied to**</span></span>
   - <span data-ttu-id="0a9ad-189">**Проверка параметров**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-189">**Review your settings**</span></span>

   <span data-ttu-id="0a9ad-190">По завершении нажмите кнопку **сохранить** на любой странице.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-190">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="0a9ad-191">**Олицетворение** : нажмите **изменить** , чтобы изменить защищенных отправителей и защищенных доменов в политике.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-191">**Impersonation** : Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="0a9ad-192">Эти параметры являются условием для политики, определяющим поддельные отправители для поиска (по отдельности или по домену) в адресе отправителя входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-192">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="0a9ad-193">Для получения дополнительных сведений см. [параметры олицетворения в политиках защиты от фишинга в защитнике Майкрософт для Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-193">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="0a9ad-194">**Добавление пользователей для защиты** : значение по умолчанию: **отключено**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-194">**Add users to protect** : The default value is **Off**.</span></span> <span data-ttu-id="0a9ad-195">Чтобы включить его, на слайде установите переключатель в значение **вкл**., а затем нажмите появившуюся кнопку **Добавить пользователя** .</span><span class="sxs-lookup"><span data-stu-id="0a9ad-195">To turn it on, slide the toggle to **On** , and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="0a9ad-196">В появившемся всплывающем окне **Добавление пользователя** настройте следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-196">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="0a9ad-197">**Адрес электронной почты** :</span><span class="sxs-lookup"><span data-stu-id="0a9ad-197">**Email address** :</span></span>

       - <span data-ttu-id="0a9ad-198">Щелкните поле и прокрутите список пользователей, чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-198">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="0a9ad-199">Щелкните поле и начните ввод текста, чтобы отфильтровать список и выбрать пользователя.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-199">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="0a9ad-200">Чтобы удалить запись, щелкните **Удалить** ![ значок удаления ](../../media/scc-remove-icon.png) на пользователе.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-200">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="0a9ad-201">**Name** : это значение заполняется на основе выбранного адреса электронной почты, но его можно изменить.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-201">**Name** : This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="0a9ad-202">По завершении нажмите кнопку **сохранить** на любой странице.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-202">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="0a9ad-203">Чтобы изменить существующую запись, выберите защищенного пользователя в списке.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-203">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     > <span data-ttu-id="0a9ad-204">В политиках защиты от фишинга может быть не более 60 пользователей.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-204">You can have a maximum of 60 users in all anti-phishing policies.</span></span> <span data-ttu-id="0a9ad-205">Другими словами, вы можете иметь 60 защищенных пользователей в одной политике, 12 защищенных пользователями в 5 политиках и т. д.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-205">In other words, you can have 60 protected users in one policy, 12 protected users in 5 policies, etc.</span></span>

   - <span data-ttu-id="0a9ad-206">**Добавление доменов для защиты** : Настройте один или оба из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-206">**Add domains to protect** : Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="0a9ad-207">**Автоматически включать домены, которые я принимаю** : значение по умолчанию — " **отключено** ".</span><span class="sxs-lookup"><span data-stu-id="0a9ad-207">**Automatically include the domains I own** : The default value is **Off**.</span></span> <span data-ttu-id="0a9ad-208">Чтобы включить его, установите переключатель в значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-208">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0a9ad-209">**Включить пользовательские домены** : значение по умолчанию: **отключено**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-209">**Include custom domains** : The default value is **Off**.</span></span> <span data-ttu-id="0a9ad-210">Чтобы включить его, на слайде установите переключатель в значение **вкл**., в поле **Добавить домены** введите имя домена (например, contoso.com), нажмите клавишу ВВОД и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-210">To turn it on, slide the toggle to **On** , and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="0a9ad-211">В политиках защиты от фишинга может быть не более 50 доменов.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-211">You can have a maximum of 50 domains in all anti-phishing policies.</span></span> <span data-ttu-id="0a9ad-212">Другими словами, вы можете иметь защищенных пользователей 50 в одной политике, 10 защищенных пользователей в 5 политиках и т. д.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-212">In other words, you can have 50 protected users in one policy, 10 protected users in 5 policies, etc.</span></span>

   - <span data-ttu-id="0a9ad-213">**Действия** : щелкните **Правка**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-213">**Actions** : Click **Edit**</span></span>

     - <span data-ttu-id="0a9ad-214">**Если олицетворенный пользователь отправляет сообщение электронной почты** : настройте одно из следующих действий для сообщений, для которых поддельный отправитель является одним из защищенных пользователей, указанных в разделе **Добавление пользователей для защиты** :</span><span class="sxs-lookup"><span data-stu-id="0a9ad-214">**If email is sent by an impersonated user** : Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect** :</span></span>

       - <span data-ttu-id="0a9ad-215">**Не применяйте никаких действий**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-215">**Don't apply any action**</span></span>
       - <span data-ttu-id="0a9ad-216">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-216">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="0a9ad-217">**Переместить сообщение в папку "Нежелательная почта"**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-217">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="0a9ad-218">**Помещать сообщение в карантин**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-218">**Quarantine the message**</span></span>
       - <span data-ttu-id="0a9ad-219">**Доставка сообщения и добавление других адресов в строку "СК"**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-219">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="0a9ad-220">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-220">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="0a9ad-221">**Если олицетворенный домен отправляет сообщение электронной почты** : настройте одно из следующих действий для сообщений, для которых поддельный отправитель находится в одном из защищенных доменов, указанных в разделе **Добавление доменов для защиты** :</span><span class="sxs-lookup"><span data-stu-id="0a9ad-221">**If email is sent by an impersonated domain** : Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect** :</span></span>

       - <span data-ttu-id="0a9ad-222">**Не применяйте никаких действий**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="0a9ad-223">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="0a9ad-224">**Переместить сообщение в папку "Нежелательная почта"**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="0a9ad-225">**Помещать сообщение в карантин**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="0a9ad-226">**Доставка сообщения и добавление других адресов в строку "СК"**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="0a9ad-227">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-227">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="0a9ad-228">Щелкните **включить советы по безопасности олицетворения** и настройте любой из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-228">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="0a9ad-229">**Показывать подсказку для олицетворенных пользователей** : значение по умолчанию: **отключено**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-229">**Show tip for impersonated users** : The default value is **Off**.</span></span> <span data-ttu-id="0a9ad-230">Чтобы включить его, установите переключатель в значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-230">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0a9ad-231">**Показывать подсказку для олицетворенных доменов** : значение по умолчанию: **отключено**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-231">**Show tip for impersonated domains** : The default value is **Off**.</span></span> <span data-ttu-id="0a9ad-232">Чтобы включить его, установите переключатель в значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-232">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0a9ad-233">**Показывать подсказку для нестандартных символов** : значение по умолчанию: **отключено**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-233">**Show tip for unusual characters** : The default value is **Off**.</span></span> <span data-ttu-id="0a9ad-234">Чтобы включить его, установите переключатель в значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-234">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="0a9ad-235">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-235">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="0a9ad-236">**Аналитика почтовых ящиков** :</span><span class="sxs-lookup"><span data-stu-id="0a9ad-236">**Mailbox intelligence** :</span></span>

     - <span data-ttu-id="0a9ad-237">**Включить логику операций с почтовыми ящиками?** : значение по умолчанию: **включено**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-237">**Enable mailbox intelligence?** : The default value is **On**.</span></span> <span data-ttu-id="0a9ad-238">Чтобы отключить его, установите переключатель в значение **выкл**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-238">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="0a9ad-239">**Включить защиту от олицетворения на основе логики почтовых ящиков?** : этот параметр доступен, только **On** если **включена логика операций с почтовыми ящиками?** включен.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-239">**Enable mailbox intelligence based impersonation protection?** : This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="0a9ad-240">В **том случае, если сообщение отправляется олицетворенным пользователем** , можно указать одно из следующих действий, чтобы принять участие в сообщениях, которые не прошли логику операций с почтовыми ящиками (то же, что доступны для защищенных пользователей и защищенных доменов):</span><span class="sxs-lookup"><span data-stu-id="0a9ad-240">In **If email is sent by an impersonated user** , you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="0a9ad-241">**Не применяйте никаких действий**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-241">**Don't apply any action**</span></span>
       - <span data-ttu-id="0a9ad-242">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-242">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="0a9ad-243">**Переместить сообщение в папку "Нежелательная почта"**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-243">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="0a9ad-244">**Помещать сообщение в карантин**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-244">**Quarantine the message**</span></span>
       - <span data-ttu-id="0a9ad-245">**Доставка сообщения и добавление других адресов в строку "СК"**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-245">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="0a9ad-246">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-246">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="0a9ad-247">**Добавление надежных отправителей и доменов** : Укажите исключения для политики:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-247">**Add trusted senders and domains** : Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="0a9ad-248">**Надежные отправители** :</span><span class="sxs-lookup"><span data-stu-id="0a9ad-248">**Trusted senders** :</span></span>

       - <span data-ttu-id="0a9ad-249">Щелкните поле и прокрутите список пользователей, чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-249">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="0a9ad-250">Щелкните поле и начните ввод текста, чтобы отфильтровать список и выбрать пользователя.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-250">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="0a9ad-251">Чтобы удалить запись, щелкните **Удалить** ![ значок удаления ](../../media/scc-remove-icon.png) на пользователе.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-251">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="0a9ad-252">**Доверенные домены** : введите имя домена (например, contoso.com), нажмите клавишу ВВОД и повторите операцию при необходимости.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-252">**Trusted domains** : Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="0a9ad-253">**Проверьте параметры** : вместо того, чтобы щелкать каждый отдельный шаг, параметры отображаются в сводке.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-253">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="0a9ad-254">Вы можете щелкнуть **изменить** в каждом разделе, чтобы вернуться на соответствующую страницу.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-254">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="0a9ad-255">Вы можете включать и **отключать** следующие параметры **непосредственно на этой** странице:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-255">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="0a9ad-256">**Защищенные пользователи**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-256">**Protected users**</span></span>
       - <span data-ttu-id="0a9ad-257">**Защищенные домены** \> **Включить домены, которыми я хочу**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-257">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="0a9ad-258">**Защищенные домены** \> **Защищенные домены** (личные домены)</span><span class="sxs-lookup"><span data-stu-id="0a9ad-258">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="0a9ad-259">**Аналитика почтовых ящиков**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-259">**Mailbox intelligence**</span></span>

   <span data-ttu-id="0a9ad-260">По завершении нажмите кнопку **сохранить** на любой странице.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-260">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="0a9ad-261">**Подделка** : нажмите кнопку **изменить** , чтобы включить или отключить логику операций подделки, Отключить идентификацию отправителей, не прошедших проверку подлинности, в Outlook, а также настроить действие, применяемое к сообщениям от заблокированных поддельных отправителей.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-261">**Spoof** : Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="0a9ad-262">Дополнительные сведения см в разделе [Параметры подделки в политиках защиты от фишинга](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-262">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="0a9ad-263">Обратите внимание, что эти же параметры также доступны в политиках защиты от фишинга в EOP.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-263">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="0a9ad-264">**Параметры фильтра подделки** : значение по умолчанию — **включено** , и мы рекомендуем оставить его.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-264">**Spoofing filter settings** : The default value is **On** , and we recommend that you leave it on.</span></span> <span data-ttu-id="0a9ad-265">Чтобы отключить его, установите переключатель в значение **выкл**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-265">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="0a9ad-266">Дополнительные сведения: [Настройка логики анализа подделки в EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-266">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="0a9ad-267">Отключение защиты от спуфинга не требуется, если запись MX не указывает на Microsoft 365; Вместо этого вы включите расширенную фильтрацию для соединителей.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-267">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="0a9ad-268">Инструкции см в разделе [Расширенная фильтрация соединителей в Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-268">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="0a9ad-269">**Включить функцию отправителя, не прошедший проверку подлинности** : значение по умолчанию: **включено**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-269">**Enable Unauthenticated Sender feature** : The default value is **On**.</span></span> <span data-ttu-id="0a9ad-270">Чтобы отключить его, установите переключатель в значение **выкл**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-270">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="0a9ad-271">**Действия** : укажите действие, которое следует предпринять для сообщений, не прошедших анализ подделки:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-271">**Actions** : Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="0a9ad-272">**Если сообщение электронной почты отправлено пользователем, который не может подменить ваш домен** :</span><span class="sxs-lookup"><span data-stu-id="0a9ad-272">**If email is sent by someone who's not allowed to spoof your domain** :</span></span>

     - <span data-ttu-id="0a9ad-273">**Перемещение сообщения в папки "Нежелательная почта" получателей**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-273">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="0a9ad-274">**Помещать сообщение в карантин**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-274">**Quarantine the message**</span></span>

   - <span data-ttu-id="0a9ad-275">**Проверьте параметры** : вместо того, чтобы щелкать каждый отдельный шаг, параметры отображаются в сводке.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-275">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="0a9ad-276">Вы можете щелкнуть **изменить** в каждом разделе, чтобы вернуться на соответствующую страницу.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-276">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="0a9ad-277">Вы можете включать и **отключать** следующие параметры **непосредственно на этой** странице:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-277">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="0a9ad-278">**Включение защиты от спуфинга**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-278">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="0a9ad-279">**Включение функции отправителя без проверки подлинности**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-279">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="0a9ad-280">По завершении нажмите кнопку **сохранить** на любой странице.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-280">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="0a9ad-281">**Дополнительные параметры** : нажмите кнопку **изменить** , чтобы настроить расширенные пороговые значения фишинга.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-281">**Advanced settings** : Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="0a9ad-282">Для получения дополнительных сведений см. Дополнительные [пороговые значения фишинга в политиках защиты от фишинга в защитнике Microsoft для Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-282">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="0a9ad-283">**Расширенные пороговые значения фишинга** : выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-283">**Advanced phishing thresholds** : Select one of the following values:</span></span>

   - <span data-ttu-id="0a9ad-284">**1 — Стандартный** (это значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-284">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="0a9ad-285">**2 агрессивно**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-285">**2 - Aggressive**</span></span>
   - <span data-ttu-id="0a9ad-286">**3 — более агрессивный**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-286">**3 - More aggressive**</span></span>
   - <span data-ttu-id="0a9ad-287">**4 — наиболее агрессивный**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-287">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="0a9ad-288">**Проверьте параметры** : нажмите кнопку **изменить** , чтобы вернуться на страницу **Расширенные пороговые значения фишинга** .</span><span class="sxs-lookup"><span data-stu-id="0a9ad-288">**Review your settings** : Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="0a9ad-289">Когда все будет готово, нажмите кнопку **сохранить** на любой странице.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-289">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="0a9ad-290">Вернитесь на страницу **изменение политики \<Name\>** , проверьте параметры и нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-290">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0a9ad-291">Использование центра безопасности & соответствия требованиям для изменения политики защиты от фишинга по умолчанию в защитнике Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="0a9ad-291">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0a9ad-292">Политика защиты от фишинга по умолчанию в защитнике Microsoft для Office 365 называется Office365-фишингом по умолчанию и не отображается в списке политик.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-292">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="0a9ad-293">Чтобы изменить политику защиты от фишинга по умолчанию, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-293">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="0a9ad-294">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** для \> **Policy** \> **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-294">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0a9ad-295">На странице **Защита от фишинга** щелкните **Политика по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-295">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="0a9ad-296">Откроется страница **изменение политики Office365 антифишинга по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="0a9ad-296">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="0a9ad-297">Доступны следующие разделы, которые содержат идентичные параметры при [изменении настраиваемой политики](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span><span class="sxs-lookup"><span data-stu-id="0a9ad-297">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="0a9ad-298">**Олицетворение**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-298">**Impersonation**</span></span>
   - <span data-ttu-id="0a9ad-299">**Спуфинг**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-299">**Spoof**</span></span>
   - <span data-ttu-id="0a9ad-300">**Дополнительные параметры**</span><span class="sxs-lookup"><span data-stu-id="0a9ad-300">**Advanced settings**</span></span>

   <span data-ttu-id="0a9ad-301">При изменении политики по умолчанию недоступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-301">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="0a9ad-302">Вы можете увидеть раздел и значения **параметра политики** , но нет ссылки для **редактирования** , поэтому вы не можете изменить параметры (имя политики, описание и пользователей, к которым применяется политика (она применяется ко всем получателям)).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-302">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="0a9ad-303">Вы не можете удалить политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-303">You can't delete the default policy.</span></span>
   - <span data-ttu-id="0a9ad-304">Невозможно изменить приоритет политики по умолчанию (всегда применяется последний).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-304">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="0a9ad-305">На странице **изменение политики Office365 Антифишинг по умолчанию** проверьте параметры и нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-305">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0a9ad-306">Включение и отключение настраиваемых политик защиты от фишинга в защитнике Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="0a9ad-306">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="0a9ad-307">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** для \> **Policy** \> **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-307">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0a9ad-308">Обратите внимание на значение в столбце **состояние** :</span><span class="sxs-lookup"><span data-stu-id="0a9ad-308">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="0a9ad-309">Чтобы отключить политику, на слайде переключитесь в режим **выключен** .</span><span class="sxs-lookup"><span data-stu-id="0a9ad-309">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="0a9ad-310">Чтобы включить политику, на слайде установите переключатель в значение **вкл** .</span><span class="sxs-lookup"><span data-stu-id="0a9ad-310">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="0a9ad-311">Отключить политику защиты от фишинга по умолчанию невозможно.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-311">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0a9ad-312">Установка приоритета настраиваемых политик защиты от фишинга в защитнике Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="0a9ad-312">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0a9ad-313">По умолчанию политикам защиты от фишинга назначается приоритет, основанный на порядке их создания (более новые политики имеют более низкий приоритет, чем старые политики).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-313">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="0a9ad-314">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-314">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="0a9ad-315">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-315">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="0a9ad-316">Дополнительные сведения о приоритетах, а также оценке и применении нескольких политик см. в статье [Порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-316">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="0a9ad-317">Настраиваемые политики защиты от фишинга отображаются в порядке их обработки (первая политика имеет значение **приоритета** 0).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-317">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="0a9ad-318">По умолчанию политика защиты от фишинга с именем Office365 по умолчанию имеет **самый низкий** приоритет, и вы не можете изменить его.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-318">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest** , and you can't change it.</span></span>

 <span data-ttu-id="0a9ad-319">**Note** : в центре безопасности & соответствия требованиям можно изменить приоритет политики защиты от фишинга после ее создания.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-319">**Note** : In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="0a9ad-320">В PowerShell можно переопределить приоритет по умолчанию при создании правила защиты от фишинга (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-320">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="0a9ad-321">Чтобы изменить приоритет политики, щелкните **увеличить** или **уменьшить** приоритет в свойствах политики (нельзя напрямую изменить номер **приоритета** в центре безопасности & соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-321">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="0a9ad-322">Изменение приоритета политики имеет смысл только в том случае, если у вас есть несколько политик.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-322">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="0a9ad-323">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** для \> **Policy** \> **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-323">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0a9ad-324">Выберите политику, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-324">Select the policy that you want to modify.</span></span> <span data-ttu-id="0a9ad-325">Если он уже выбран, отмените его выбор и снова выберите его.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-325">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0a9ad-326">Откроется всплывающее окно **изменение политики \<name\>** .</span><span class="sxs-lookup"><span data-stu-id="0a9ad-326">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="0a9ad-327">Для настраиваемой политики защиты от фишинга со значением **приоритета** **0** будет доступна только кнопка " **уменьшить приоритет** ".</span><span class="sxs-lookup"><span data-stu-id="0a9ad-327">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="0a9ad-328">Для настраиваемой политики защиты от фишинга с наименьшим значением **приоритета** (например, **3** ) доступна только кнопка **повышения приоритета** .</span><span class="sxs-lookup"><span data-stu-id="0a9ad-328">The custom anti-phishing policy with the lowest **Priority** value (for example, **3** ) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="0a9ad-329">При наличии трех или более настраиваемых политик защиты от фишинга для политик между максимальным и минимальным значениями приоритета доступны кнопки **увеличить приоритет** и **уменьшить приоритет** .</span><span class="sxs-lookup"><span data-stu-id="0a9ad-329">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="0a9ad-330">Щелкните **увеличить** или **уменьшить** приоритет, чтобы изменить значение **приоритета** .</span><span class="sxs-lookup"><span data-stu-id="0a9ad-330">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="0a9ad-331">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-331">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0a9ad-332">Использование центра безопасности & соответствия требованиям для просмотра политик защиты от фишинга в защитнике Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="0a9ad-332">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="0a9ad-333">В центре безопасности & соответствия требованиям и перейдите к разделу политика **управления угрозами** для \> **Policy** \> **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-333">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0a9ad-334">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-334">Do one of the following steps:</span></span>

   - <span data-ttu-id="0a9ad-335">Выберите настраиваемую политику защиты от фишинга, которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-335">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="0a9ad-336">Если он уже выбран, отмените его выбор и снова выберите его.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-336">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="0a9ad-337">Щелкните **политику по умолчанию** , чтобы просмотреть политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-337">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="0a9ad-338">Откроется всплывающее окно **изменение политики \<name\>** , в котором можно просмотреть параметры и значения.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-338">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0a9ad-339">Использование центра безопасности & соответствия требованиям для удаления политик защиты от фишинга в защитнике Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="0a9ad-339">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="0a9ad-340">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** для \> **Policy** \> **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-340">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0a9ad-341">Выберите политику, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-341">Select the policy that you want to remove.</span></span> <span data-ttu-id="0a9ad-342">Если он уже выбран, отмените его выбор и снова выберите его.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-342">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0a9ad-343">В появившемся всплывающем окне **изменение политики \<name\>** выберите команду **удалить политику** , а затем нажмите кнопку **Да** в появившемся диалоговом окне предупреждения.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-343">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy** , and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="0a9ad-344">Политику по умолчанию удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-344">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0a9ad-345">Настройка политик защиты от фишинга в защитнике Microsoft для Office 365 с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a9ad-345">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0a9ad-346">Как было сказано ранее, политика защиты от нежелательной почты состоит из политики защиты от фишинга и правила защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-346">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="0a9ad-347">В Exchange Online PowerShell разница между политиками защиты от фишинга и правилами защиты от фишинга очевидна.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-347">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="0a9ad-348">Вы управляете политиками защиты от фишинга с помощью командлетов **\* -AntiPhishPolicy** , а также управляете правилами защиты от фишинга с помощью командлетов **\* -AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="0a9ad-348">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="0a9ad-349">В PowerShell сначала создается политика защиты от фишинга, затем создается правило защиты от фишинга, идентифицирующее политику, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-349">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="0a9ad-350">В PowerShell параметры политики защиты от фишинга и антифишинга изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-350">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="0a9ad-351">При удалении политики защиты от фишинга из PowerShell соответствующее правило защиты от фишинга не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-351">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="0a9ad-352">Создание политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a9ad-352">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="0a9ad-353">Создание политики защиты от фишинга в PowerShell состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-353">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="0a9ad-354">Создайте политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-354">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="0a9ad-355">Создайте правило защиты от фишинга, которое определяет политику защиты от фишинга, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-355">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="0a9ad-356">**Примечания** :</span><span class="sxs-lookup"><span data-stu-id="0a9ad-356">**Notes** :</span></span>

- <span data-ttu-id="0a9ad-357">Вы можете создать новое правило защиты от фишинга и назначить для него существующую, несвязанную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-357">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="0a9ad-358">Правило защиты от фишинга не может быть связано с несколькими политиками защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-358">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="0a9ad-359">Вы можете настроить следующие параметры для новых политик защиты от фишинга в PowerShell, которые недоступны в центре безопасности & соответствия требованиям, пока не будет создана политика:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-359">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="0a9ad-360">Создайте новую политику как отключенную ( _включена_ `$false` в командлете **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-360">Create the new policy as disabled ( _Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="0a9ad-361">Задайте приоритет политики при создании ( _приоритет_ _\<Number\>_ ) для командлета **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="0a9ad-361">Set the priority of the policy during creation ( _Priority_ _\<Number\>_ ) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="0a9ad-362">Новая политика защиты от фишинга, созданная в PowerShell, не отображается в центре безопасности & соответствия требованиям, пока вы не назначите политику для правила защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-362">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="0a9ad-363">Шаг 1: использование PowerShell для создания политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="0a9ad-363">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="0a9ad-364">Чтобы создать политику защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-364">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="0a9ad-365">В этом примере создается политика защиты от фишинга с именем Research карантин со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-365">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="0a9ad-366">Политика включена (параметр _Enabled_ не используется, а значение по умолчанию — `$true` ).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-366">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="0a9ad-367">Описание: "политика отделов исследований".</span><span class="sxs-lookup"><span data-stu-id="0a9ad-367">The description is: Research department policy.</span></span>
- <span data-ttu-id="0a9ad-368">Включает защиту доменов организации для всех обслуживаемых доменов, а также целевые домены для защиты fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-368">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="0a9ad-369">Указывает, что защищать от имитации нужно пользователя Mai Fujito (mfujito@fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-369">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="0a9ad-370">Включает аналитику почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-370">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="0a9ad-371">Включает защиту каталога почтовых ящиков и задает действие карантина.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-371">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="0a9ad-372">Включает советы по безопасности.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-372">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="0a9ad-373">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-373">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="0a9ad-374">Шаг 2: использование PowerShell для создания правила защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="0a9ad-374">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="0a9ad-375">Чтобы создать правило защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-375">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="0a9ad-376">В этом примере создается правило защиты от фишинга с именем "Отдел исследований" со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-376">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="0a9ad-377">Правило связано с политикой защиты от фишинга с именем "карантин исследований".</span><span class="sxs-lookup"><span data-stu-id="0a9ad-377">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="0a9ad-378">Правило применяется к членам группы "Research Department".</span><span class="sxs-lookup"><span data-stu-id="0a9ad-378">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="0a9ad-379">Так как мы не используем параметр _Priority_ , используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-379">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="0a9ad-380">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-380">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="0a9ad-381">Просмотр политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a9ad-381">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="0a9ad-382">Чтобы просмотреть существующие политики защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-382">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0a9ad-383">В этом примере возвращается сводный список всех политик защиты от фишинга вместе с заданными свойствами.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-383">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="0a9ad-384">В этом примере возвращаются все значения свойств для политики защиты от фишинга под названием "руководители".</span><span class="sxs-lookup"><span data-stu-id="0a9ad-384">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="0a9ad-385">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-385">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="0a9ad-386">Просмотр правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a9ad-386">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="0a9ad-387">Чтобы просмотреть существующие правила защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-387">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0a9ad-388">В этом примере возвращается сводный список всех правил защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-388">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="0a9ad-389">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-389">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="0a9ad-390">В этом примере возвращаются все значения свойств для правила защиты от фишинга Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-390">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="0a9ad-391">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-391">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="0a9ad-392">Использование PowerShell для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="0a9ad-392">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="0a9ad-393">Кроме следующих элементов, одни и те же параметры доступны при изменении политики защиты от фишинга в PowerShell, как при создании политики, как описано в [шаге 1: с помощью PowerShell создайте раздел политики защиты от фишинга](#step-1-use-powershell-to-create-an-anti-phish-policy) , приведенный ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-393">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="0a9ad-394">Переключатель _македефаулт_ , который включает указанную политику в политику по умолчанию (применяется ко всем, всегда **самый низкий** приоритет и не может удалить его), доступна только при изменении политики защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-394">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="0a9ad-395">Вы не можете переименовать политику защиты от фишинга (командлет **Set-AntiPhishPolicy** не имеет параметра _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-395">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="0a9ad-396">При переименовании политики защиты от фишинга в центре безопасности & соответствия требованиям Вы переименовываете только _правило_ защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-396">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="0a9ad-397">Чтобы изменить политику защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-397">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="0a9ad-398">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-398">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="0a9ad-399">Использование PowerShell для изменения правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="0a9ad-399">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="0a9ad-400">Единственный параметр, недоступный при изменении правила защиты от фишинга в PowerShell — это параметр _Enabled_ , позволяющий создать отключенное правило.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-400">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="0a9ad-401">Чтобы включить или отключить существующие правила защиты от фишинга, ознакомьтесь со статьей в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-401">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="0a9ad-402">В противном случае дополнительные параметры не будут доступны при изменении правила защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-402">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="0a9ad-403">Те же параметры доступны при создании правила, как описано в [шаге 2: используйте PowerShell для создания раздела правила защиты от фишинга](#step-2-use-powershell-to-create-an-anti-phish-rule) , приведенного ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-403">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="0a9ad-404">Чтобы изменить правило защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-404">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="0a9ad-405">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-405">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="0a9ad-406">Включение и отключение правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a9ad-406">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="0a9ad-407">Включение или отключение правила защиты от фишинга в PowerShell включает или отключает всю политику защиты от фишинга (правило защиты от фишинга и назначенную политику защиты от фишинга).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-407">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="0a9ad-408">Вы не можете включать или отключать политику защиты от фишинга по умолчанию (всегда применяется ко всем получателям).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-408">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="0a9ad-409">Чтобы включить или отключить правило защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-409">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="0a9ad-410">В этом примере отключается правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-410">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0a9ad-411">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-411">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0a9ad-412">Подробные сведения о синтаксисе и параметрах можно найти в статье [Enable – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-412">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="0a9ad-413">Настройка приоритета правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a9ad-413">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="0a9ad-414">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-414">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="0a9ad-415">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-415">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="0a9ad-416">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-416">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="0a9ad-417">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-417">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="0a9ad-418">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-418">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="0a9ad-419">Чтобы задать приоритет правила защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-419">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="0a9ad-p146">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-p146">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="0a9ad-422">**Примечания** :</span><span class="sxs-lookup"><span data-stu-id="0a9ad-422">**Notes** :</span></span>

- <span data-ttu-id="0a9ad-423">Чтобы задать приоритет нового правила при его создании, используйте параметр _Priority_ в командлете **New – AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="0a9ad-423">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="0a9ad-424">По умолчанию политика защиты от фишинга не имеет соответствующего правила защиты от фишинга и имеет **самое низкое** значение приоритета.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-424">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="0a9ad-425">Удаление политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a9ad-425">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="0a9ad-426">При использовании PowerShell для удаления политики защиты от фишинга соответствующее правило защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-426">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="0a9ad-427">Чтобы удалить политику защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-427">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="0a9ad-428">В этом примере удаляется политика защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-428">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="0a9ad-429">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-429">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="0a9ad-430">Удаление правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a9ad-430">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="0a9ad-431">При использовании PowerShell для удаления правила защиты от фишинга соответствующая политика защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-431">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="0a9ad-432">Чтобы удалить правило защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-432">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="0a9ad-433">В этом примере удаляется правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-433">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0a9ad-434">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="0a9ad-434">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0a9ad-435">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="0a9ad-435">How do you know these procedures worked?</span></span>

<span data-ttu-id="0a9ad-436">Чтобы убедиться, что политики защиты от фишинга успешно настроены в защитнике Microsoft для Office 365, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-436">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="0a9ad-437">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** для \> **Policy** \> **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-437">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="0a9ad-438">Проверьте список политик, их значения **состояния** и значения **приоритета** .</span><span class="sxs-lookup"><span data-stu-id="0a9ad-438">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="0a9ad-439">Чтобы просмотреть дополнительные сведения, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-439">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="0a9ad-440">Выберите политику из списка и просмотрите сведения в всплывающем меню.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-440">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="0a9ad-441">Щелкните **Политика по умолчанию** и просмотрите сведения в всплывающем меню.</span><span class="sxs-lookup"><span data-stu-id="0a9ad-441">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="0a9ad-442">В Exchange Online PowerShell замените на \<Name\> имя политики или правила и выполните следующую команду и проверьте параметры:</span><span class="sxs-lookup"><span data-stu-id="0a9ad-442">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
