---
title: Настройка политик защиты от фишинга в ATP
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
description: Администраторы могут научиться создавать, изменять и удалять сложные политики защиты от фишинга, доступные в организациях с помощью Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: f7770945e6b99a3d2f3fa2b12daa13b2cc3c2612
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825741"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="98ea1-103">Настройка политик защиты от фишинга в ATP</span><span class="sxs-lookup"><span data-stu-id="98ea1-103">Configure ATP anti-phishing policies</span></span>

<span data-ttu-id="98ea1-104">Политики защиты от фишинга в ATP входят [в состав Office 365 Advanced Threat Protection.](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="98ea1-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="98ea1-105">Политики защиты от фишинга в ATP помогают защитить организацию от злоумышленников с фишингом и других типов фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="98ea1-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="98ea1-106">Дополнительные сведения о различиях между политиками защиты от фишинга в политиках Exchange Online Protection (EOP) и ATP см. в статье ["Защита от фишинга".](anti-phishing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="98ea1-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="98ea1-107">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику защиты от фишинга ATP по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="98ea1-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="98ea1-108">Для большей детализации можно также создать настраиваемые политики защиты от фишинга ATP, которые применяются к определенным пользователям, группам или доменам в организации.</span><span class="sxs-lookup"><span data-stu-id="98ea1-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="98ea1-109">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="98ea1-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="98ea1-110">Политику защиты от фишинга ATP можно настроить в Центре безопасности & безопасности и в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98ea1-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="98ea1-111">Сведения о настройке более ограниченного количества политик защиты от фишинга, доступных в организациях Exchange Online Protection (т.е. в организациях Microsoft 365 без Office 365 ATP), см. в [статье "Настройка политик защиты от фишинга" в EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="98ea1-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="98ea1-112">Политики защиты от фишинга ATP в Центре безопасности & и PowerShell</span><span class="sxs-lookup"><span data-stu-id="98ea1-112">ATP anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="98ea1-113">Ниже перечислены основные элементы политики защиты от фишинга ATP.</span><span class="sxs-lookup"><span data-stu-id="98ea1-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="98ea1-114">**Политика защиты от фишинга:** указывает средства защиты от фишинга, которые нужно включить или отключить, а также действия для применения параметров.</span><span class="sxs-lookup"><span data-stu-id="98ea1-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="98ea1-115">**Правило защиты от фишинга:** указание приоритета и фильтров получателей (к кому применяется политика) для политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="98ea1-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="98ea1-116">Разница между этими двумя элементами не так очевидна, если вы управляете политиками защиты от фишинга ATP в Центре & безопасности:</span><span class="sxs-lookup"><span data-stu-id="98ea1-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="98ea1-117">При создании политики вы фактически создаете правило защиты от фишинга и связанную с ним политику защиты от фишинга, используя одно и то же имя для обоих.</span><span class="sxs-lookup"><span data-stu-id="98ea1-117">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="98ea1-118">При изменении политики параметры, связанные с именем, приоритетом, включенным или отключенным, и фильтрами получателей, меняют правило защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="98ea1-118">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="98ea1-119">Все остальные параметры внедряют связанную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="98ea1-119">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="98ea1-120">При удалении политики удаляются правило защиты от фишинга и связанная политика защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="98ea1-120">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="98ea1-121">В Exchange Online PowerShell вы можете управлять политикой и правилом по отдельности.</span><span class="sxs-lookup"><span data-stu-id="98ea1-121">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="98ea1-122">Дополнительные сведения см. в разделе "Настройка политик защиты от фишинга [ATP"](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) далее в этой статье, в разделе "Использование Exchange Online PowerShell".</span><span class="sxs-lookup"><span data-stu-id="98ea1-122">For more information, see the [Use Exchange Online PowerShell to configure ATP anti-phishing policies](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) section later in this topic.</span></span>

<span data-ttu-id="98ea1-123">У каждой организации Office 365 ATP есть встроенная политика защиты от фишинга ATP под названием Office 365 AntiPhish Default, которая имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="98ea1-123">Every Office 365 ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="98ea1-124">Политика применяется ко всем получателям в организации, даже если с ней не связано ниодного правила защиты от фишинга (фильтрации получателей).</span><span class="sxs-lookup"><span data-stu-id="98ea1-124">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="98ea1-125">Для политики задано специальное значение приоритета **Самый низкий**, которое невозможно изменить (эта политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="98ea1-125">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="98ea1-126">Все созданные специальные политики всегда имеют более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="98ea1-126">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="98ea1-127">Эта политика является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.</span><span class="sxs-lookup"><span data-stu-id="98ea1-127">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="98ea1-128">Чтобы повысить эффективность защиты от фишинга, можно создать настраиваемые политики защиты от фишинга ATP с более строгими параметрами, которые применяются к определенным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="98ea1-128">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="98ea1-129">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="98ea1-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="98ea1-130">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="98ea1-130">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="98ea1-131">Чтобы перейти непосредственно на страницу **защиты от фишинга ATP,** используйте <https://protection.office.com/antiphishing> этот параметр.</span><span class="sxs-lookup"><span data-stu-id="98ea1-131">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="98ea1-132">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="98ea1-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="98ea1-133">Чтобы вы могли выполнить процедуры, упомянутые в этой теме, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="98ea1-133">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="98ea1-134">Чтобы добавить, изменить и удалить политики защиты от фишинга ATP, вы должны быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="98ea1-134">To add, modify, and delete ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="98ea1-135">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="98ea1-135">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="98ea1-136">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="98ea1-136">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="98ea1-137">Чтобы получить доступ только для чтения к политикам защиты от фишинга ATP, вы должны быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="98ea1-137">For read-only access to ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="98ea1-138">**Средство считывания сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="98ea1-138">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="98ea1-139">**Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="98ea1-139">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="98ea1-140">Рекомендуемые параметры для политик защиты от фишинга в ATP см. в статье [о параметрах политики защиты от фишинга в AtP в Office.](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="98ea1-140">For our recommended settings for ATP anti-phishing policies, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="98ea1-141">До применения новой или обновленной политики может потребоваться до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="98ea1-141">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="98ea1-142">Дополнительные сведения о том, куда применять политики защиты от фишинга в конвейере фильтрации, см. в разделе ["Порядок и приоритет защиты электронной почты".](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="98ea1-142">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="98ea1-143">Создание политик защиты & защиты от фишинга ATP с помощью Центра безопасности</span><span class="sxs-lookup"><span data-stu-id="98ea1-143">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="98ea1-144">При создании настраиваемой политики защиты от фишинга ATP в Центре безопасности & создается правило защиты от фишинга и связанная с ним политика защиты от фишинга одновременно с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="98ea1-144">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="98ea1-145">При создании политики защиты от фишинга ATP можно указать только имя, описание и фильтр получателей, который определяет, к кому применяется политика.</span><span class="sxs-lookup"><span data-stu-id="98ea1-145">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="98ea1-146">После создания политики вы можете изменить ее, чтобы изменить или просмотреть параметры защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="98ea1-146">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="98ea1-147">В Центре безопасности & соответствия требованиям перейдите в **антифишинговые** данные политики \> **Policy** \> **ATP.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="98ea1-148">На странице **"Защита от фишинга"** нажмите кнопку **"Создать".**</span><span class="sxs-lookup"><span data-stu-id="98ea1-148">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="98ea1-149">**Откроется мастер создания политики защиты от фишинга.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-149">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="98ea1-150">На странице **"Назовите политику"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="98ea1-150">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="98ea1-151">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="98ea1-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="98ea1-152">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="98ea1-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="98ea1-153">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="98ea1-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="98ea1-154">На **появившейся** странице применяемой к ней определите внутренних получателей, к которым применяется политика.</span><span class="sxs-lookup"><span data-stu-id="98ea1-154">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="98ea1-155">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="98ea1-155">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="98ea1-156">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="98ea1-156">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="98ea1-157">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="98ea1-157">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="98ea1-158">Нажмите **кнопку Добавить условие.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-158">Click **Add a condition**.</span></span> <span data-ttu-id="98ea1-159">В появившемся раскрывающемся списке выберите условие с **примененной меткой, если:**</span><span class="sxs-lookup"><span data-stu-id="98ea1-159">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="98ea1-160">**Получатель:** указывает один или несколько почтовых ящиков, почтовых пользователей или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="98ea1-160">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="98ea1-161">**Получатель состоит в группе:** указывает одну или несколько групп в организации.</span><span class="sxs-lookup"><span data-stu-id="98ea1-161">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="98ea1-162">**Домен получателя:** указывает получателей в одном или нескольких настроенных обслуживаемых доменах в организации.</span><span class="sxs-lookup"><span data-stu-id="98ea1-162">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="98ea1-163">После выбора условия появится соответствующее раскрывающееся меню с **любым из этих** полей.</span><span class="sxs-lookup"><span data-stu-id="98ea1-163">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="98ea1-164">Щелкните поле и прокрутите список значений для выбора.</span><span class="sxs-lookup"><span data-stu-id="98ea1-164">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="98ea1-165">Щелкните поле и начните вводить строку, чтобы отфильтровать список и выбрать нужное значение.</span><span class="sxs-lookup"><span data-stu-id="98ea1-165">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="98ea1-166">Чтобы добавить дополнительные значения, щелкните пустую областю в поле.</span><span class="sxs-lookup"><span data-stu-id="98ea1-166">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="98ea1-167">Чтобы удалить отдельные записи, выберите **"Удалить** ![ ](../../media/scc-remove-icon.png) значок в значении".</span><span class="sxs-lookup"><span data-stu-id="98ea1-167">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="98ea1-168">Чтобы удалить все условие, **нажмите** кнопку ![ "Удалить" ](../../media/scc-remove-icon.png) в условии.</span><span class="sxs-lookup"><span data-stu-id="98ea1-168">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="98ea1-169">Чтобы добавить дополнительное условие, нажмите **кнопку "Добавить условие" и** выберите оставшееся значение в **применяться, если.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-169">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="98ea1-170">Чтобы добавить исключения, нажмите **кнопку "Добавить условие" и** выберите исключение, **кроме случаев, если.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-170">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="98ea1-171">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="98ea1-171">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="98ea1-172">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="98ea1-172">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="98ea1-173">Просмотрите **параметры** на появившейся странице "Просмотр параметров".</span><span class="sxs-lookup"><span data-stu-id="98ea1-173">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="98ea1-174">Чтобы изменить **каждый** параметр, нажмите кнопку "Изменить" для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="98ea1-174">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="98ea1-175">По завершении нажмите кнопку **"Создать эту политику".**</span><span class="sxs-lookup"><span data-stu-id="98ea1-175">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="98ea1-176">Нажмите **кнопку ОК** в появившемся диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="98ea1-176">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="98ea1-177">После создания политики защиты от фишинга ATP с использованием этих общих параметров политики, настройте параметры защиты в политике, следуя инструкциям в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="98ea1-177">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="98ea1-178">Изменение политик защиты от фишинга в Центре безопасности & безопасности</span><span class="sxs-lookup"><span data-stu-id="98ea1-178">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="98ea1-179">Используйте следующие процедуры для изменения политик защиты от фишинга ATP: новой созданной политики или уже настроенных политик.</span><span class="sxs-lookup"><span data-stu-id="98ea1-179">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="98ea1-180">Если вы еще нете, откройте Центр безопасности & соответствия требованиям и перейдите в **антифишинг** \> **Policy** \> **политики управления угрозами ATP.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-180">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="98ea1-181">Выберите настраиваемую политику защиты от фишинга ATP, которую следует изменить.</span><span class="sxs-lookup"><span data-stu-id="98ea1-181">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="98ea1-182">Убедите, если он уже выбран, снова выберите его и снова.</span><span class="sxs-lookup"><span data-stu-id="98ea1-182">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="98ea1-183">Появится \*\* \<name\> всплывающее\*\* окно "Изменение политики".</span><span class="sxs-lookup"><span data-stu-id="98ea1-183">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="98ea1-184">Если **щелкнуть "Изменить"** в любом разделе, вы сможете получить доступ к параметрам в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="98ea1-184">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="98ea1-185">Следующие шаги представлены в том порядке, в котором появляются разделы, но не являются последовательным (разделы можно выбирать и изменять в любом порядке).</span><span class="sxs-lookup"><span data-stu-id="98ea1-185">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="98ea1-186">После нажатия **кнопки «Изменить»** в разделе доступные параметры отображаются в формате мастера, но вы можете перейти **Close** на страницы в любом порядке, и можно щелкнуть **«Сохранить»** на любой странице в любом порядке. Чтобы вернуться на страницу "Изменить" возвращающийся на странице **Cancel** ![ ](../../media/scc-remove-icon.png) \*\*"Изменить" \<name\> \*\* (для сохранения или выхода этого параметра не требуется открытие последней страницы мастера).</span><span class="sxs-lookup"><span data-stu-id="98ea1-186">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="98ea1-187">**Параметр политики:** нажмите **кнопку** "Изменить", чтобы изменить параметры, доступные при [создании политики в](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) предыдущем разделе:</span><span class="sxs-lookup"><span data-stu-id="98ea1-187">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="98ea1-188">**Название**</span><span class="sxs-lookup"><span data-stu-id="98ea1-188">**Name**</span></span>
   - <span data-ttu-id="98ea1-189">**Описание**</span><span class="sxs-lookup"><span data-stu-id="98ea1-189">**Description**</span></span>
   - <span data-ttu-id="98ea1-190">**Применяется к**</span><span class="sxs-lookup"><span data-stu-id="98ea1-190">**Applied to**</span></span>
   - <span data-ttu-id="98ea1-191">**Проверьте параметры**</span><span class="sxs-lookup"><span data-stu-id="98ea1-191">**Review your settings**</span></span>

   <span data-ttu-id="98ea1-192">По завершении нажмите кнопку **"Сохранить** на любой странице".</span><span class="sxs-lookup"><span data-stu-id="98ea1-192">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="98ea1-193">**Олицетворение:** **щелкните** "Правка", чтобы изменить защищенных отправителей и защищенные домены в политике.</span><span class="sxs-lookup"><span data-stu-id="98ea1-193">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="98ea1-194">Это условие для политики, определяющая поддельных отправителей, которые нужно искать (индивидуально или по домену) в адресе отправителя входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="98ea1-194">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="98ea1-195">Дополнительные сведения см. в статье ["Параметры олицетворения" в политиках защиты от фишинга в ATP.](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="98ea1-195">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="98ea1-196">**Добавьте пользователей для защиты:** по умолчанию используется значение **"Выкл.".**</span><span class="sxs-lookup"><span data-stu-id="98ea1-196">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="98ea1-197">Чтобы включить его, установите переключатель в **положение**"Вкл", а затем нажмите появившуюся кнопку "Добавить пользователя". **Add user**</span><span class="sxs-lookup"><span data-stu-id="98ea1-197">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="98ea1-198">В **появившемся** окне "Добавление пользователя" настройте следующие значения:</span><span class="sxs-lookup"><span data-stu-id="98ea1-198">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="98ea1-199">**Адрес электронной почты**:</span><span class="sxs-lookup"><span data-stu-id="98ea1-199">**Email address**:</span></span>

        - <span data-ttu-id="98ea1-200">Щелкните поле и прокрутите список пользователей, чтобы выбрать.</span><span class="sxs-lookup"><span data-stu-id="98ea1-200">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="98ea1-201">Щелкните поле и начните вводить имя, чтобы отфильтровать список и выбрать пользователя.</span><span class="sxs-lookup"><span data-stu-id="98ea1-201">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="98ea1-202">Чтобы удалить запись, нажмите **кнопку** ![ "Удалить" ](../../media/scc-remove-icon.png) пользователя.</span><span class="sxs-lookup"><span data-stu-id="98ea1-202">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="98ea1-203">**Name (Имя)**— это значение заполняется на основе выбранного адреса электронной почты, но вы можете изменить его.</span><span class="sxs-lookup"><span data-stu-id="98ea1-203">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="98ea1-204">По завершении нажмите кнопку **"Сохранить** на любой странице".</span><span class="sxs-lookup"><span data-stu-id="98ea1-204">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="98ea1-205">Чтобы изменить существующую запись, выберите защищенного пользователя в списке.</span><span class="sxs-lookup"><span data-stu-id="98ea1-205">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="98ea1-206">**Добавьте защищаемые**домены: настройте один или оба следующих параметра:</span><span class="sxs-lookup"><span data-stu-id="98ea1-206">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="98ea1-207">**Автоматически включайте принадлежащие домены:** значение по умолчанию **—Off (Отключено).**</span><span class="sxs-lookup"><span data-stu-id="98ea1-207">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="98ea1-208">Чтобы включить его, переведите переключатель в **положение Вкл.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-208">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="98ea1-209">**Включить настраиваемые домены:** по умолчанию используется значение **"Выкл.".**</span><span class="sxs-lookup"><span data-stu-id="98ea1-209">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="98ea1-210">Чтобы включить его, включите переключатель в положение **"Вкл."** и в поле **"Добавить** домены" введите доменное имя (например, contoso.com), нажмите клавишу ВВОД и повторите повторите по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="98ea1-210">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="98ea1-211">**Actions**: Click **Edit**</span><span class="sxs-lookup"><span data-stu-id="98ea1-211">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="98ea1-212">**Если олицетворенный**пользователь отправляет электронное письмо: настройте одно из следующих действий для сообщений, в которых поддельный отправитель является одним из защищенных пользователей, указанных в **поле Add Users to protect:**</span><span class="sxs-lookup"><span data-stu-id="98ea1-212">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="98ea1-213">**Не применять какие-либо действия**</span><span class="sxs-lookup"><span data-stu-id="98ea1-213">**Don't apply any action**</span></span>
       - <span data-ttu-id="98ea1-214">**Перенаправление сообщений на другие электронные адреса**</span><span class="sxs-lookup"><span data-stu-id="98ea1-214">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="98ea1-215">**Переместить сообщение в папку "Нежелательная почта"**</span><span class="sxs-lookup"><span data-stu-id="98ea1-215">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="98ea1-216">**Поместить сообщение в карантин**</span><span class="sxs-lookup"><span data-stu-id="98ea1-216">**Quarantine the message**</span></span>
       - <span data-ttu-id="98ea1-217">**Доставка сообщения и добавление других адресов в строку "СК"**</span><span class="sxs-lookup"><span data-stu-id="98ea1-217">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="98ea1-218">**Удалить сообщение перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="98ea1-218">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="98ea1-219">**Если олицетворенным**доменом отправляется сообщение электронной почты, настройте одно из следующих действий для сообщений, в которых поддельный отправитель находится в одном из защищенных доменов, указанных в **поле "Добавление домена для защиты":**</span><span class="sxs-lookup"><span data-stu-id="98ea1-219">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="98ea1-220">**Не применять какие-либо действия**</span><span class="sxs-lookup"><span data-stu-id="98ea1-220">**Don't apply any action**</span></span>
     - <span data-ttu-id="98ea1-221">**Перенаправление сообщений на другие электронные адреса**</span><span class="sxs-lookup"><span data-stu-id="98ea1-221">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="98ea1-222">**Переместить сообщение в папку "Нежелательная почта"**</span><span class="sxs-lookup"><span data-stu-id="98ea1-222">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="98ea1-223">**Поместить сообщение в карантин**</span><span class="sxs-lookup"><span data-stu-id="98ea1-223">**Quarantine the message**</span></span>
     - <span data-ttu-id="98ea1-224">**Доставка сообщения и добавление других адресов в строку "СК"**</span><span class="sxs-lookup"><span data-stu-id="98ea1-224">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="98ea1-225">**Удалить сообщение перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="98ea1-225">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="98ea1-226">Щелкните **советы по безопасности и настройте** один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="98ea1-226">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="98ea1-227">**Отображение подсказок для олицетворенных**пользователей: по умолчанию используется **значение "Выкл.".**</span><span class="sxs-lookup"><span data-stu-id="98ea1-227">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="98ea1-228">Чтобы включить его, переведите переключатель в **положение Вкл.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-228">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="98ea1-229">**Отображение подсказок для олицетворенных доменов:** по умолчанию используется **значение "Выкл.".**</span><span class="sxs-lookup"><span data-stu-id="98ea1-229">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="98ea1-230">Чтобы включить его, переведите переключатель в **положение Вкл.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-230">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="98ea1-231">**Отображение подсказок для нестандартных символов:** по умолчанию используется значение **"Выкл.".**</span><span class="sxs-lookup"><span data-stu-id="98ea1-231">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="98ea1-232">Чтобы включить его, переведите переключатель в **положение Вкл.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-232">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="98ea1-233">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="98ea1-233">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="98ea1-234">**Аналитика почтовых ящиков:**</span><span class="sxs-lookup"><span data-stu-id="98ea1-234">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="98ea1-235">**Включить аналитику почтовых ящиков?** По умолчанию используется значение **"Включено".**</span><span class="sxs-lookup"><span data-stu-id="98ea1-235">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="98ea1-236">Чтобы отключить его, переведите переключатель в **положение "Выкл."**</span><span class="sxs-lookup"><span data-stu-id="98ea1-236">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="98ea1-237">**Включить защиту олицетворения с учетом почтовых ящиков?** Этот параметр доступен, только если **включена аналитика почтовых ящиков?** **Включен.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-237">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="98ea1-238">Если **олицетворенный**пользователь отправляет электронное сообщение, вы можете указать одно из следующих действий, применяемых к сообщениям, которые не прошли их аналитику почтовых ящиков (те же действия, которые доступны для защищенных пользователей и защищенных доменов):</span><span class="sxs-lookup"><span data-stu-id="98ea1-238">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="98ea1-239">**Не применять какие-либо действия**</span><span class="sxs-lookup"><span data-stu-id="98ea1-239">**Don't apply any action**</span></span>
       - <span data-ttu-id="98ea1-240">**Перенаправление сообщений на другие электронные адреса**</span><span class="sxs-lookup"><span data-stu-id="98ea1-240">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="98ea1-241">**Переместить сообщение в папку "Нежелательная почта"**</span><span class="sxs-lookup"><span data-stu-id="98ea1-241">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="98ea1-242">**Поместить сообщение в карантин**</span><span class="sxs-lookup"><span data-stu-id="98ea1-242">**Quarantine the message**</span></span>
       - <span data-ttu-id="98ea1-243">**Доставка сообщения и добавление других адресов в строку "СК"**</span><span class="sxs-lookup"><span data-stu-id="98ea1-243">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="98ea1-244">**Удалить сообщение перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="98ea1-244">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="98ea1-245">**Добавьте надежных отправителей и доменов:** укажите исключения для политики:</span><span class="sxs-lookup"><span data-stu-id="98ea1-245">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="98ea1-246">**Надежные отправители:**</span><span class="sxs-lookup"><span data-stu-id="98ea1-246">**Trusted senders**:</span></span>

       - <span data-ttu-id="98ea1-247">Щелкните поле и прокрутите список пользователей, чтобы выбрать.</span><span class="sxs-lookup"><span data-stu-id="98ea1-247">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="98ea1-248">Щелкните поле и начните вводить имя, чтобы отфильтровать список и выбрать пользователя.</span><span class="sxs-lookup"><span data-stu-id="98ea1-248">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="98ea1-249">Чтобы удалить запись, нажмите **кнопку** ![ "Удалить" ](../../media/scc-remove-icon.png) пользователя.</span><span class="sxs-lookup"><span data-stu-id="98ea1-249">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="98ea1-250">**Доверенные домены:** введите доменное имя (например, contoso.com), нажмите клавишу ВВОД и повторите по вторию.</span><span class="sxs-lookup"><span data-stu-id="98ea1-250">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="98ea1-251">**Проверьте параметры,** а не щелкайте каждый из них на отдельном шаге.</span><span class="sxs-lookup"><span data-stu-id="98ea1-251">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="98ea1-252">Чтобы **вернуться на** релевантную страницу, можно щелкнуть "Правка" в каждом разделе.</span><span class="sxs-lookup"><span data-stu-id="98ea1-252">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="98ea1-253">На этой странице можно **включить** или **выключить** следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="98ea1-253">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="98ea1-254">**Защищенные пользователи**</span><span class="sxs-lookup"><span data-stu-id="98ea1-254">**Protected users**</span></span>
       - <span data-ttu-id="98ea1-255">**Защищенные домены** \> **Включать собственные домены**</span><span class="sxs-lookup"><span data-stu-id="98ea1-255">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="98ea1-256">**Защищенные домены** \> **Защищенные домены** (пользовательские домены)</span><span class="sxs-lookup"><span data-stu-id="98ea1-256">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="98ea1-257">**Аналитика почтовых ящиков**</span><span class="sxs-lookup"><span data-stu-id="98ea1-257">**Mailbox intelligence**</span></span>

   <span data-ttu-id="98ea1-258">По завершении нажмите кнопку **"Сохранить** на любой странице".</span><span class="sxs-lookup"><span data-stu-id="98ea1-258">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="98ea1-259">**Spoof:** Click **Edit** to turn or off spoof intelligence включения или отключения аналитики отправителей без проверки подлинности в Outlook, а также настройте действие для применения к сообщениям от заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="98ea1-259">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="98ea1-260">Дополнительные сведения см. в статье ["Параметры подделки" в политиках защиты от фишинга.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="98ea1-260">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="98ea1-261">Обратите внимание, что эти же параметры доступны и в политиках защиты от фишинга в EOP.</span><span class="sxs-lookup"><span data-stu-id="98ea1-261">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="98ea1-262">**Настройки фильтра спуфинга**— по умолчанию установлено значение **"Включено",** и мы рекомендуем оставить его невключенной.</span><span class="sxs-lookup"><span data-stu-id="98ea1-262">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="98ea1-263">Чтобы отключить его, переведите переключатель в **положение "Выкл."**</span><span class="sxs-lookup"><span data-stu-id="98ea1-263">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="98ea1-264">Дополнительные сведения см. в статье ["Настройка аналитики спуфинга" в EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="98ea1-264">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="98ea1-265">Вам не нужно отключать защиту от подделок, если запись MX не указывает на Microsoft 365; вместо этого включается расширенная фильтрация соединителей.</span><span class="sxs-lookup"><span data-stu-id="98ea1-265">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="98ea1-266">Инструкции см. в [статье "Улучшенная фильтрация для соединителей в Exchange Online".](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="98ea1-266">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="98ea1-267">**Включить функцию отправителя, не прошедшего проверку**подлинности: по умолчанию используется **значение "Включено".**</span><span class="sxs-lookup"><span data-stu-id="98ea1-267">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="98ea1-268">Чтобы отключить его, переведите переключатель в **положение "Выкл."**</span><span class="sxs-lookup"><span data-stu-id="98ea1-268">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="98ea1-269">**Действия:** укажите действие для сообщений, не прошедших аналитику спуфинга:</span><span class="sxs-lookup"><span data-stu-id="98ea1-269">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="98ea1-270">**Если сообщение электронной почты был отправлено лицом, запрещающему подделку вашего домена:**</span><span class="sxs-lookup"><span data-stu-id="98ea1-270">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="98ea1-271">**Перемещение сообщения в папки нежелательной почты получателя**</span><span class="sxs-lookup"><span data-stu-id="98ea1-271">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="98ea1-272">**Поместить сообщение в карантин**</span><span class="sxs-lookup"><span data-stu-id="98ea1-272">**Quarantine the message**</span></span>

   - <span data-ttu-id="98ea1-273">**Проверьте параметры,** а не щелкайте каждый из них на отдельном шаге.</span><span class="sxs-lookup"><span data-stu-id="98ea1-273">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="98ea1-274">Чтобы **вернуться на** релевантную страницу, можно щелкнуть "Правка" в каждом разделе.</span><span class="sxs-lookup"><span data-stu-id="98ea1-274">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="98ea1-275">На этой странице можно **включить** или **выключить** следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="98ea1-275">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="98ea1-276">**Включение защиты от спуфинга**</span><span class="sxs-lookup"><span data-stu-id="98ea1-276">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="98ea1-277">**Включить функцию "Включить отправитель, не прошедший проверку подлинности"**</span><span class="sxs-lookup"><span data-stu-id="98ea1-277">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="98ea1-278">По завершении нажмите кнопку **"Сохранить** на любой странице".</span><span class="sxs-lookup"><span data-stu-id="98ea1-278">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="98ea1-279">**Дополнительные параметры:** нажмите кнопку **"Изменить"** для настройки расширенных пороговых значений фишинга.</span><span class="sxs-lookup"><span data-stu-id="98ea1-279">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="98ea1-280">Дополнительные сведения см. в статье ["Дополнительные пороговые значения фишинга" в политиках защиты от фишинга в ATP.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="98ea1-280">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="98ea1-281">**Расширенные пороговые значения фишинга:** выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="98ea1-281">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="98ea1-282">**1 — стандартный** (значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="98ea1-282">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="98ea1-283">**2 — агрессивная**</span><span class="sxs-lookup"><span data-stu-id="98ea1-283">**2 - Aggressive**</span></span>
   - <span data-ttu-id="98ea1-284">**3 — более агрессивная**</span><span class="sxs-lookup"><span data-stu-id="98ea1-284">**3 - More aggressive**</span></span>
   - <span data-ttu-id="98ea1-285">**4 — наиболее агрессивная**</span><span class="sxs-lookup"><span data-stu-id="98ea1-285">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="98ea1-286">**Проверьте параметры:** нажмите **"Правка",** чтобы вернуться на **страницу "Пороговые значения фишинга".**</span><span class="sxs-lookup"><span data-stu-id="98ea1-286">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="98ea1-287">По завершении нажмите кнопку **"Сохранить** на любой странице".</span><span class="sxs-lookup"><span data-stu-id="98ea1-287">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="98ea1-288">Вернитесь на **страницу "Изменение \<Name\> политики"** и нажмите кнопку "Закрыть". **Close**</span><span class="sxs-lookup"><span data-stu-id="98ea1-288">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="98ea1-289">Использование центра & безопасности для изменения стандартной политики защиты от фишинга ATP</span><span class="sxs-lookup"><span data-stu-id="98ea1-289">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="98ea1-290">Политика защиты от фишинга ATP по умолчанию называется "По умолчанию office 365 AntiPhish Default", которая не отображается в списке политик.</span><span class="sxs-lookup"><span data-stu-id="98ea1-290">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="98ea1-291">Чтобы изменить политику защиты от фишинга ATP по умолчанию, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="98ea1-291">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="98ea1-292">В Центре безопасности & соответствия требованиям перейдите в **антифишинговые** данные политики \> **Policy** \> **ATP.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-292">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="98ea1-293">На странице **"Защита от фишинга"** выберите пункт "Политика **по умолчанию".**</span><span class="sxs-lookup"><span data-stu-id="98ea1-293">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="98ea1-294">**Появляется страница изменения политики по умолчанию для антифишинговых писем Office 365.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-294">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="98ea1-295">Доступны следующие разделы, содержащие идентичные параметры времени [изменения настраиваемой политики:](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="98ea1-295">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="98ea1-296">**Олицетворение**</span><span class="sxs-lookup"><span data-stu-id="98ea1-296">**Impersonation**</span></span>
   - <span data-ttu-id="98ea1-297">**Подделка**</span><span class="sxs-lookup"><span data-stu-id="98ea1-297">**Spoof**</span></span>
   - <span data-ttu-id="98ea1-298">**Дополнительные параметры**</span><span class="sxs-lookup"><span data-stu-id="98ea1-298">**Advanced settings**</span></span>

   <span data-ttu-id="98ea1-299">При изменении политики по умолчанию недоступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="98ea1-299">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="98ea1-300">Раздел и значения **параметра политики** не отображается, но ссылка на **редактирование** отсутствует, поэтому изменить параметры (имя политики, описание и кого применяется политика (она применяется ко всем получателям)).</span><span class="sxs-lookup"><span data-stu-id="98ea1-300">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="98ea1-301">Политику по умолчанию удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="98ea1-301">You can't delete the default policy.</span></span>
   - <span data-ttu-id="98ea1-302">Вы не можете изменить приоритет политики по умолчанию (она всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="98ea1-302">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="98ea1-303">На странице **"Изменение политики по умолчанию для антифишинговых данных Office 365"** проверьте параметры и нажмите кнопку **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="98ea1-303">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="98ea1-304">Включение и отключение пользовательских политик защиты от фишинга в ATP</span><span class="sxs-lookup"><span data-stu-id="98ea1-304">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="98ea1-305">В Центре безопасности & соответствия требованиям перейдите в **антифишинговые** данные политики \> **Policy** \> **ATP.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-305">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="98ea1-306">Обратите внимание на значение в **столбце "Состояние":**</span><span class="sxs-lookup"><span data-stu-id="98ea1-306">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="98ea1-307">Переведите **переключатель в положение** "Выкл.", чтобы отключить политику.</span><span class="sxs-lookup"><span data-stu-id="98ea1-307">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="98ea1-308">Переведите **переключатель в положение** Вкл, чтобы включить политику.</span><span class="sxs-lookup"><span data-stu-id="98ea1-308">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="98ea1-309">Политику защиты от фишинга по умолчанию отключить невозможно.</span><span class="sxs-lookup"><span data-stu-id="98ea1-309">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="98ea1-310">Установка приоритета настраиваемых политик защиты от фишинга ATP</span><span class="sxs-lookup"><span data-stu-id="98ea1-310">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="98ea1-311">По умолчанию политикам защиты от фишинга в ATP задается приоритет, основанный на том, в каком порядке они были созданы (приоритет новых политик ниже, чем у старых).</span><span class="sxs-lookup"><span data-stu-id="98ea1-311">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="98ea1-312">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="98ea1-312">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="98ea1-313">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="98ea1-313">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="98ea1-314">Дополнительные сведения о приоритетах, а также оценке и применении нескольких политик см. в статье [Порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="98ea1-314">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="98ea1-315">Настраиваемые политики защиты от фишинга ATP отображаются в том же порядке, в котором они обрабатываются (для первой политики установлен **приоритет** 0).</span><span class="sxs-lookup"><span data-stu-id="98ea1-315">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="98ea1-316">Для стандартной политики защиты от фишинга под названием "Office365 AntiPhish Default" (Антифишинговое значение по умолчанию) установлено **специальное значение приоритета**"Минимальный", ее невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="98ea1-316">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="98ea1-317">**Примечание.** В Центре безопасности & изменить приоритет политики защиты от фишинга ATP можно только после ее создания.</span><span class="sxs-lookup"><span data-stu-id="98ea1-317">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="98ea1-318">В PowerShell можно переопределить заданный по умолчанию приоритет при создании правила защиты от фишинга (это может повлиять на приоритеты существующих правил).</span><span class="sxs-lookup"><span data-stu-id="98ea1-318">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="98ea1-319">Чтобы изменить приоритет политики, в **свойствах** политики можно напрямую изменить приоритет или уменьшить приоритет (в Центре безопасности & требованиям невозможно напрямую изменить значение приоритета). **Decrease priority** **Priority**</span><span class="sxs-lookup"><span data-stu-id="98ea1-319">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="98ea1-320">Изменение приоритета политики имеет смысл только при наличии нескольких политик.</span><span class="sxs-lookup"><span data-stu-id="98ea1-320">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="98ea1-321">В Центре безопасности & соответствия требованиям перейдите в **антифишинговые** данные политики \> **Policy** \> **ATP.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-321">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="98ea1-322">Выберите политику, которую нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="98ea1-322">Select the policy that you want to modify.</span></span> <span data-ttu-id="98ea1-323">Убедите, если он уже выбран, снова выберите его и снова.</span><span class="sxs-lookup"><span data-stu-id="98ea1-323">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="98ea1-324">Появится \*\* \<name\> всплывающее\*\* окно "Изменение политики".</span><span class="sxs-lookup"><span data-stu-id="98ea1-324">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="98ea1-325">Настраиваемая политика защиты от фишинга ATP со **значением приоритета** **0 имеет** только доступную кнопку **"Ухудшать".**</span><span class="sxs-lookup"><span data-stu-id="98ea1-325">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="98ea1-326">Настраиваемая политика защиты от фишинга ATP с наименьшим значением **приоритета** (например, **3)** имеет только кнопку **"Повысить приоритет".**</span><span class="sxs-lookup"><span data-stu-id="98ea1-326">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="98ea1-327">Если у вас три и более настраиваемых политик защиты от фишинга, для политик **Increase priority** между наивысшими и наименьшими значениями приоритетов будут доступны кнопки "Увеличить" и **"Уменьшение** приоритета".</span><span class="sxs-lookup"><span data-stu-id="98ea1-327">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="98ea1-328">Чтобы **изменить значение приоритета,** установите "Увеличить **приоритет"** или "Уменьшить". **Priority**</span><span class="sxs-lookup"><span data-stu-id="98ea1-328">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="98ea1-329">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="98ea1-329">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="98ea1-330">Использование Центра безопасности & соответствия требованиям для просмотра политик защиты от фишинга ATP</span><span class="sxs-lookup"><span data-stu-id="98ea1-330">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="98ea1-331">В Центре безопасности & соответствия требованиям перейдите к **антифишинговым** \> **Policy** \> **требованиям atP политикой управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-331">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="98ea1-332">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="98ea1-332">Do one of the following steps:</span></span>

   - <span data-ttu-id="98ea1-333">Выберите настраиваемую политику защиты от фишинга ATP, которую хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="98ea1-333">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="98ea1-334">Убедите, если он уже выбран, снова выберите его и снова.</span><span class="sxs-lookup"><span data-stu-id="98ea1-334">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="98ea1-335">Чтобы **просмотреть политику** защиты от фишинга по умолчанию, нажмите "Политика по умолчанию".</span><span class="sxs-lookup"><span data-stu-id="98ea1-335">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="98ea1-336">Появится \*\* \<name\> всплывающая\*\* подсказка "Изменение" политики, в котором можно просмотреть параметры и значения.</span><span class="sxs-lookup"><span data-stu-id="98ea1-336">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="98ea1-337">Удаление политик защиты & защиты от фишинга ATP с помощью Центра безопасности</span><span class="sxs-lookup"><span data-stu-id="98ea1-337">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="98ea1-338">В Центре безопасности & соответствия требованиям перейдите в **антифишинговые** данные политики \> **Policy** \> **ATP.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-338">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="98ea1-339">Выберите политику, которую нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="98ea1-339">Select the policy that you want to remove.</span></span> <span data-ttu-id="98ea1-340">Убедите, если он уже выбран, снова выберите его и снова.</span><span class="sxs-lookup"><span data-stu-id="98ea1-340">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="98ea1-341">В \*\*появившемся \<name\> \*\* окне "Изменить политику" нажмите кнопку **"Удалить**политику", а **затем** в появившемся диалоговом окне предупреждения нажмите кнопку "Да".</span><span class="sxs-lookup"><span data-stu-id="98ea1-341">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="98ea1-342">Политику по умолчанию удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="98ea1-342">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="98ea1-343">Настройка политик защиты от фишинга в ATP с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="98ea1-343">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

<span data-ttu-id="98ea1-344">Как было сказано выше, политика защиты от фишинга ATP состоит из политики защиты от фишинга и правила защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="98ea1-344">As previously described, an ATP anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="98ea1-345">Разница между политиками защиты от фишинга и правилами защиты от фишинга очевидна.</span><span class="sxs-lookup"><span data-stu-id="98ea1-345">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="98ea1-346">Для управления политиками защиты от фишинга используются \*\* \* командлеты -AntiPhishPolicy,\*\* а правила защиты от фишинга управляются с \*\* \* помощью командлетов -AntiPhishRule.\*\*</span><span class="sxs-lookup"><span data-stu-id="98ea1-346">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="98ea1-347">Сначала в PowerShell создается политика защиты от фишинга, а затем — правило защиты от фишинга, указывающее политику, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="98ea1-347">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="98ea1-348">В PowerShell параметры политики защиты от фишинга и правила защиты от фишинга наменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="98ea1-348">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="98ea1-349">При удалении политики защиты от фишинга из PowerShell соответствующее правило защиты от фишинга не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="98ea1-349">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="98ea1-350">Создание политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="98ea1-350">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="98ea1-351">Создание политики защиты от фишинга в PowerShell выполняется в два этапа.</span><span class="sxs-lookup"><span data-stu-id="98ea1-351">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="98ea1-352">Создайте политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="98ea1-352">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="98ea1-353">Создайте правило защиты от фишинга, указывающее политику защиты от фишинга, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="98ea1-353">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="98ea1-354">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="98ea1-354">**Notes**:</span></span>

- <span data-ttu-id="98ea1-355">Вы можете создать новое правило защиты от фишинга и назначить ей существующую, несвязанную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="98ea1-355">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="98ea1-356">Правило защиты от фишинга невозможно связать с несколькими политиками защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="98ea1-356">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="98ea1-357">Вы можете настроить в новых политиках защиты от фишинга в PowerShell следующие параметры, которые будут недоступны в Центре безопасности & соответствия требованиям до создания политики:</span><span class="sxs-lookup"><span data-stu-id="98ea1-357">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="98ea1-358">Создайте новую политику как отключенную _(активна_ `$false` в **командлете New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="98ea1-358">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="98ea1-359">Задать приоритет политики во время создания _(Priority)_ _\<Number\>_ в **командлете New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-359">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="98ea1-360">В Центре безопасности & политика защиты от фишинга не отображается в Центре безопасности &, пока вы не назначите ее правилу защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="98ea1-360">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="98ea1-361">Шаг 1. Создание политики защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="98ea1-361">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="98ea1-362">Чтобы создать политику защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="98ea1-362">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="98ea1-363">В этом примере создается политика защиты от фишинга Research Quarantine со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="98ea1-363">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="98ea1-364">Политика включена (мы не используем параметр _Enabled,_ а значение по умолчанию `$true` равно).</span><span class="sxs-lookup"><span data-stu-id="98ea1-364">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="98ea1-365">Описание: "Политика отдела исследований".</span><span class="sxs-lookup"><span data-stu-id="98ea1-365">The description is: Research department policy.</span></span>
- <span data-ttu-id="98ea1-366">Обеспечивает защиту всех обслуживаемых доменов организации и защиту целевых доменов для fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="98ea1-366">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="98ea1-367">Указывает, что защищать от имитации нужно пользователя Mai Fujito (mfujito@fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="98ea1-367">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="98ea1-368">Включает аналитику почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="98ea1-368">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="98ea1-369">Включает защиту данных аналитики почтовых ящиков и указывает действие на карантине.</span><span class="sxs-lookup"><span data-stu-id="98ea1-369">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="98ea1-370">Включает советы по безопасности.</span><span class="sxs-lookup"><span data-stu-id="98ea1-370">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="98ea1-371">Дополнительные сведения о синтаксисе и параметрах [см. в статье New-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="98ea1-371">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="98ea1-372">Шаг 2. Создание правила защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="98ea1-372">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="98ea1-373">Чтобы создать правило защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="98ea1-373">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="98ea1-374">В этом примере создается антифишинговое правило Research Department со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="98ea1-374">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="98ea1-375">Правило связано с политикой защиты от фишинга с именем Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="98ea1-375">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="98ea1-376">Правило применяется к членам группы "Research Department".</span><span class="sxs-lookup"><span data-stu-id="98ea1-376">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="98ea1-377">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="98ea1-377">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="98ea1-378">Дополнительные сведения о синтаксисе и параметрах [см. в разделе New-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="98ea1-378">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="98ea1-379">Просмотр политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="98ea1-379">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="98ea1-380">Для просмотра существующих политик защиты от фишинга используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="98ea1-380">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="98ea1-381">В этом примере возвращается сводный список всех политик защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="98ea1-381">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="98ea1-382">В этом примере возвращаются значения всех свойств политики защиты от фишинга с именем Executives.</span><span class="sxs-lookup"><span data-stu-id="98ea1-382">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="98ea1-383">Дополнительные сведения о синтаксисе и параметрах см. в [статье Get-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="98ea1-383">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="98ea1-384">Просмотр правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="98ea1-384">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="98ea1-385">Чтобы просмотреть существующие правила защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="98ea1-385">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="98ea1-386">В этом примере возвращается сводный список всех правил защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="98ea1-386">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="98ea1-387">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="98ea1-387">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="98ea1-388">В этом примере возвращаются значения всех свойств правила защиты от фишинга с именем Contoso Executives .</span><span class="sxs-lookup"><span data-stu-id="98ea1-388">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="98ea1-389">Дополнительные сведения о синтаксисе и параметрах см. в [статье Get-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="98ea1-389">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="98ea1-390">Изменение политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="98ea1-390">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="98ea1-391">За другими указанными ниже элементами при изменении политики защиты от фишинга в PowerShell доступны такие же параметры, как и при создании политики, описанной в [разделе "Шаг 1." Создайте раздел](#step-1-use-powershell-to-create-an-anti-phish-policy) политики защиты от фишинга с помощью PowerShell выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="98ea1-391">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="98ea1-392">_Переключатель MakeDefault,_ который превращает указанную политику в политику по умолчанию (применяется ко всем, всегда низкий приоритет является обязательным и его нельзя удалить), доступен только при изменении политики защиты от фишинга в PowerShell. **Lowest**</span><span class="sxs-lookup"><span data-stu-id="98ea1-392">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="98ea1-393">Невозможно переименовать антифишинговую политику **(командлет Set-AntiPhishPolicy** не _имеет параметра_ Name).</span><span class="sxs-lookup"><span data-stu-id="98ea1-393">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="98ea1-394">При переименовании политики защиты от фишинга в Центре безопасности & соответствия _rule_требованиям вы переименовываете только правило защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="98ea1-394">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="98ea1-395">Чтобы изменить политику защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="98ea1-395">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="98ea1-396">Дополнительные сведения о синтаксисе и параметрах [см. в статье О Set-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="98ea1-396">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="98ea1-397">Изменение правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="98ea1-397">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="98ea1-398">При изменении правила защиты от фишинга в PowerShell недоступен только параметр _Enabled,_ позволяющий создать отключенное правило.</span><span class="sxs-lookup"><span data-stu-id="98ea1-398">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="98ea1-399">Сведения о включении или отключении существующих правил защиты от фишинга см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="98ea1-399">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="98ea1-400">В противном случае при изменении правила защиты от фишинга в PowerShell не используются никакие дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="98ea1-400">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="98ea1-401">Такие же параметры доступны при создании правила, как описано в разделе "Шаг 2. Создание правила защиты [от фишинга"](#step-2-use-powershell-to-create-an-anti-phish-rule) выше в этой статье с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98ea1-401">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="98ea1-402">Чтобы изменить правило защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="98ea1-402">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="98ea1-403">Дополнительные сведения о синтаксисе и параметрах [см. в статье О Set-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="98ea1-403">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="98ea1-404">Включение и отключение правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="98ea1-404">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="98ea1-405">Включение или отключение правила защиты от фишинга в PowerShell включает или отключает всю политику защиты от фишинга (правило защиты от фишинга и назначенную политику защиты от фишинга).</span><span class="sxs-lookup"><span data-stu-id="98ea1-405">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="98ea1-406">Вы не можете включить или отключить политику защиты от фишинга по умолчанию (она всегда применяется ко всем получателям).</span><span class="sxs-lookup"><span data-stu-id="98ea1-406">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="98ea1-407">Для включения и отключения правила защиты от фишинга в PowerShell используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="98ea1-407">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="98ea1-408">В этом примере отключается антифишинговое правило Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="98ea1-408">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="98ea1-409">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="98ea1-409">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="98ea1-410">Дополнительные сведения о синтаксисе и параметрах см. в [описании командлетов Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) [и Disable-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="98ea1-410">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="98ea1-411">Установка приоритета правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="98ea1-411">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="98ea1-412">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="98ea1-412">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="98ea1-413">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="98ea1-413">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="98ea1-414">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="98ea1-414">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="98ea1-415">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="98ea1-415">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="98ea1-416">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="98ea1-416">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="98ea1-417">Чтобы задать приоритет правила защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="98ea1-417">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="98ea1-p144">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="98ea1-p144">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="98ea1-420">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="98ea1-420">**Notes**:</span></span>

- <span data-ttu-id="98ea1-421">Чтобы задать приоритет нового правила при его создании, используйте параметр _Priority_ командлета **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-421">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="98ea1-422">Политика защиты от фишинга по умолчанию не имеет соответствующего правила защиты от фишинга, и не имеет неопределенное значение **приоритета (наименьший).**</span><span class="sxs-lookup"><span data-stu-id="98ea1-422">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="98ea1-423">Удаление политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="98ea1-423">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="98ea1-424">При удалении политики защиты от фишинга с помощью PowerShell соответствующее правило защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="98ea1-424">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="98ea1-425">Чтобы удалить политику защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="98ea1-425">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="98ea1-426">В этом примере удаляется политика защиты от фишинга Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="98ea1-426">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="98ea1-427">Дополнительные сведения о синтаксисе и параметрах [см. в статье Remove-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="98ea1-427">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="98ea1-428">Удаление правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="98ea1-428">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="98ea1-429">При удалении правила защиты от фишинга с помощью PowerShell соответствующая политика защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="98ea1-429">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="98ea1-430">Чтобы удалить правило защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="98ea1-430">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="98ea1-431">В этом примере удаляется антифишинговое правило Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="98ea1-431">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="98ea1-432">Дополнительные сведения о синтаксисе и параметрах [см. в статье Remove-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="98ea1-432">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="98ea1-433">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="98ea1-433">How do you know these procedures worked?</span></span>

<span data-ttu-id="98ea1-434">Чтобы убедиться, что политики защиты от фишинга ATP успешно настроены, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="98ea1-434">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="98ea1-435">В Центре безопасности & соответствия требованиям перейдите в **антифишинговые** данные политики \> **Policy** \> **ATP.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-435">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="98ea1-436">Проверьте список политик, **их значения состояния** и их значения **приоритета.**</span><span class="sxs-lookup"><span data-stu-id="98ea1-436">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="98ea1-437">Для просмотра дополнительных сведений выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="98ea1-437">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="98ea1-438">Выберите политику в списке и посмотрите сведения во всплывающем элементе.</span><span class="sxs-lookup"><span data-stu-id="98ea1-438">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="98ea1-439">Выберите **пункт "Политика по умолчанию"** и просмотрите сведения во всплывающем элементе.</span><span class="sxs-lookup"><span data-stu-id="98ea1-439">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="98ea1-440">В Exchange Online PowerShell \<Name\> замените имя политики или правила и выполните следующую команду и проверьте параметры:</span><span class="sxs-lookup"><span data-stu-id="98ea1-440">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
