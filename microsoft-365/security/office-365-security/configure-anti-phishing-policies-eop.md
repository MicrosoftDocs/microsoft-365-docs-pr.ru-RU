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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Администраторы могут научиться создавать, изменять и удалять политики защиты от фишинга, доступные в организациях Exchange Online Protection (EOP) с почтовыми ящиками Exchange Online или без них.
ms.openlocfilehash: af6577d32d43300867d29a365baaa4e1e7e1b5e3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825753"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="efa2a-103">Настройка политик защиты от фишинга в EOP</span><span class="sxs-lookup"><span data-stu-id="efa2a-103">Configure anti-phishing policies in EOP</span></span>

<span data-ttu-id="efa2a-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online существует политика защиты от фишинга, которая содержит ограниченное количество функций защиты от спуфинга, которые по умолчанию включены.</span><span class="sxs-lookup"><span data-stu-id="efa2a-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="efa2a-105">Дополнительные сведения см. в статье ["Параметры подделки" в политиках защиты от фишинга.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="efa2a-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="efa2a-106">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="efa2a-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="efa2a-107">Для большей детализации можно также создать настраиваемые политики защиты от фишинга, применяемые к определенным пользователям, группам или доменам в организации.</span><span class="sxs-lookup"><span data-stu-id="efa2a-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="efa2a-108">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="efa2a-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="efa2a-109">Организации с почтовыми ящиками Exchange Online могут настраивать политики защиты от фишинга в Центре безопасности & безопасности или Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="efa2a-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="efa2a-110">Автономные организации EOP могут использовать только Центр безопасности & безопасности.</span><span class="sxs-lookup"><span data-stu-id="efa2a-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="efa2a-111">Сведения о создании и изменении расширенных политик защиты от фишинга ATP, доступных в Office 365 Advanced Threat Protection (Office 365 ATP), см. в статье ["Настройка политик защиты от фишинга" ATP.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="efa2a-111">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection (Office 365 ATP), see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="efa2a-112">Ниже перечислены основные элементы политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="efa2a-112">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="efa2a-113">**Политика защиты от фишинга:** указывает средства защиты от фишинга, которые нужно включить или отключить, а также действия для применения параметров.</span><span class="sxs-lookup"><span data-stu-id="efa2a-113">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="efa2a-114">**Правило защиты от фишинга:** указание приоритета и фильтров получателей (к кому применяется политика) для политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="efa2a-114">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="efa2a-115">Разница между этими двумя элементами не так очевидна, если вы управляете политиками защиты от фишинга в Центре & соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="efa2a-115">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="efa2a-116">При создании политики защиты от фишинга в действительности вы одновременно создаете правило защиты от фишинга и связанную политику защиты от фишинга, используя одно и то же имя для обоих.</span><span class="sxs-lookup"><span data-stu-id="efa2a-116">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="efa2a-117">При изменении политики защиты от фишинга параметры, связанные с именем, приоритетом, включенным или отключенным и фильтрами получателей, меняют правило защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="efa2a-117">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="efa2a-118">Все остальные параметры внедряют связанную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="efa2a-118">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="efa2a-119">При удалении политики защиты от фишинга удаляются правило защиты от фишинга и связанная политика защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="efa2a-119">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="efa2a-120">В Exchange Online PowerShell вы можете управлять политикой и правилом по отдельности.</span><span class="sxs-lookup"><span data-stu-id="efa2a-120">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="efa2a-121">Дополнительные сведения см. в разделе ["Настройка политик защиты от фишинга"](#use-exchange-online-powershell-to-configure-anti-phishing-policies) далее в этой статье, в разделе "Использование Exchange Online PowerShell".</span><span class="sxs-lookup"><span data-stu-id="efa2a-121">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this topic.</span></span>

<span data-ttu-id="efa2a-122">В каждой организации есть встроенная политика защиты от фишинга под названием "По умолчанию для Office 365 antiPhish" с указанными ниже свойствами.</span><span class="sxs-lookup"><span data-stu-id="efa2a-122">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="efa2a-123">Политика применяется ко всем получателям в организации, даже если с ней не связано ниодного правила защиты от фишинга (фильтрации получателей).</span><span class="sxs-lookup"><span data-stu-id="efa2a-123">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="efa2a-124">Для политики задано специальное значение приоритета **Самый низкий**, которое невозможно изменить (эта политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="efa2a-124">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="efa2a-125">Все созданные специальные политики всегда имеют более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="efa2a-125">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="efa2a-126">Эта политика является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.</span><span class="sxs-lookup"><span data-stu-id="efa2a-126">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="efa2a-127">Чтобы повысить эффективность защиты от фишинга, можно создать настраиваемые политики защиты от фишинга с более строгими параметрами, которые применяются к определенным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="efa2a-127">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="efa2a-128">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="efa2a-128">What do you need to know before you begin?</span></span>

- <span data-ttu-id="efa2a-129">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="efa2a-129">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="efa2a-130">Чтобы перейти непосредственно на страницу **"Защита от фишинга"** используйте <https://protection.office.com/antiphishing> этот код.</span><span class="sxs-lookup"><span data-stu-id="efa2a-130">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="efa2a-131">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="efa2a-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="efa2a-132">Управлять политиками защиты от фишинга в автономном режиме EOP PowerShell невозможно.</span><span class="sxs-lookup"><span data-stu-id="efa2a-132">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="efa2a-133">Чтобы вы могли выполнить процедуры, упомянутые в этой теме, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="efa2a-133">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="efa2a-134">Чтобы добавлять, изменять и удалять политики защиты от фишинга, необходимо быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="efa2a-134">To add, modify, and delete anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="efa2a-135">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="efa2a-135">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="efa2a-136">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="efa2a-136">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="efa2a-137">Чтобы получить доступ только для чтения к политикам защиты от фишинга, вы должны быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="efa2a-137">For read-only access to anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="efa2a-138">**Средство считывания сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="efa2a-138">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="efa2a-139">**Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="efa2a-139">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="efa2a-140">Чтобы иметь возможность создавать и изменять политики защиты от нежелательной почты в автономной службе EOP, необходимо выполнить действие, требующие _дедронирования_ для клиента.</span><span class="sxs-lookup"><span data-stu-id="efa2a-140">To be able to create and modify anti-spam policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="efa2a-141">Например, в Центре администрирования Exchange можно перейти на вкладку **«Разрешения»,** выбрать существующую группу ролей, нажать кнопку **«Изменить** изменить» и удалить роль (которую вы в итоге ![ ](../../media/ITPro-EAC-EditIcon.png) будете добавить заново).</span><span class="sxs-lookup"><span data-stu-id="efa2a-141">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="efa2a-142">Если ваш клиент никогда не погашался, появится диалоговое окно с именем **"Параметры организации "Обновление** параметров организации" и индикатором выполнения, который должен быть успешно завершен.</span><span class="sxs-lookup"><span data-stu-id="efa2a-142">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="efa2a-143">Дополнительные сведения о такой реагировании см. в [описании командлета Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (который недоступен в автономном режиме EOP PowerShell или центре безопасности & соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="efa2a-143">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="efa2a-144">Рекомендуемые параметры политик защиты от фишинга см. в [статье о параметрах политики защиты от фишинга EOP по умолчанию.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="efa2a-144">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="efa2a-145">Долго в течение 30 минут до кнедрения обновленной политики.</span><span class="sxs-lookup"><span data-stu-id="efa2a-145">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="efa2a-146">Дополнительные сведения о том, куда применять политики защиты от фишинга в конвейере фильтрации, см. в разделе ["Порядок и приоритет защиты электронной почты".](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="efa2a-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="efa2a-147">Создание политик защиты & защиты от фишинга с помощью Центра безопасности данных</span><span class="sxs-lookup"><span data-stu-id="efa2a-147">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="efa2a-148">При создании настраиваемой политики защиты от фишинга в Центре соответствия требованиям & создается правило защиты от фишинга и связанная с ним политика защиты от фишинга, используя одно и то же имя для обоих.</span><span class="sxs-lookup"><span data-stu-id="efa2a-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="efa2a-149">При создании политики защиты от фишинга можно указать только имя, описание и фильтр получателей, для которого действует политика.</span><span class="sxs-lookup"><span data-stu-id="efa2a-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="efa2a-150">После создания политики вы можете изменить ее, чтобы изменить или просмотреть параметры защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="efa2a-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="efa2a-151">В Центре безопасности & выберите **защиту** от \> фишинга **Policy** \> **политики управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="efa2a-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="efa2a-152">На странице **"Защита от фишинга"** нажмите кнопку **"Создать".**</span><span class="sxs-lookup"><span data-stu-id="efa2a-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="efa2a-153">**Откроется мастер создания политики защиты от фишинга.**</span><span class="sxs-lookup"><span data-stu-id="efa2a-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="efa2a-154">На странице **"Назовите политику"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="efa2a-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="efa2a-155">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="efa2a-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="efa2a-156">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="efa2a-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="efa2a-157">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="efa2a-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="efa2a-158">На **появившейся** странице применяемой к ней определите внутренних получателей, к которым применяется политика.</span><span class="sxs-lookup"><span data-stu-id="efa2a-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="efa2a-159">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="efa2a-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="efa2a-160">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="efa2a-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="efa2a-161">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="efa2a-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="efa2a-162">Нажмите **кнопку Добавить условие.**</span><span class="sxs-lookup"><span data-stu-id="efa2a-162">Click **Add a condition**.</span></span> <span data-ttu-id="efa2a-163">В появившемся раскрывающемся списке выберите условие с **примененной меткой, если:**</span><span class="sxs-lookup"><span data-stu-id="efa2a-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="efa2a-164">**Получатель:** указывает один или несколько почтовых ящиков, почтовых пользователей или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="efa2a-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="efa2a-165">**Получатель состоит в группе:** указывает одну или несколько групп в организации.</span><span class="sxs-lookup"><span data-stu-id="efa2a-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="efa2a-166">**Домен получателя**: Указывает получателей в одном или нескольких настроенных принятых доменов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="efa2a-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="efa2a-167">После выбора условия появится соответствующее раскрывающееся меню с **любым из этих** полей.</span><span class="sxs-lookup"><span data-stu-id="efa2a-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="efa2a-168">Щелкните поле и прокрутите список значений для выбора.</span><span class="sxs-lookup"><span data-stu-id="efa2a-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="efa2a-169">Щелкните поле и начните вводить строку, чтобы отфильтровать список и выбрать нужное значение.</span><span class="sxs-lookup"><span data-stu-id="efa2a-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="efa2a-170">Чтобы добавить дополнительные значения, щелкните пустую областю в поле.</span><span class="sxs-lookup"><span data-stu-id="efa2a-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="efa2a-171">Чтобы удалить отдельные записи, выберите **"Удалить** ![ ](../../media/scc-remove-icon.png) значок в значении".</span><span class="sxs-lookup"><span data-stu-id="efa2a-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="efa2a-172">Чтобы удалить все условие, **нажмите** кнопку ![ "Удалить" ](../../media/scc-remove-icon.png) в условии.</span><span class="sxs-lookup"><span data-stu-id="efa2a-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="efa2a-173">Чтобы добавить дополнительное условие, нажмите **кнопку "Добавить условие" и** выберите оставшееся значение в **применяться, если.**</span><span class="sxs-lookup"><span data-stu-id="efa2a-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="efa2a-174">Чтобы добавить исключения, нажмите **кнопку "Добавить условие" и** выберите исключение, **кроме случаев, если.**</span><span class="sxs-lookup"><span data-stu-id="efa2a-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="efa2a-175">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="efa2a-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="efa2a-176">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="efa2a-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="efa2a-177">Просмотрите **параметры** на появившейся странице "Просмотр параметров".</span><span class="sxs-lookup"><span data-stu-id="efa2a-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="efa2a-178">Чтобы изменить **каждый** параметр, нажмите кнопку "Изменить" для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="efa2a-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="efa2a-179">По завершении нажмите кнопку **"Создать эту политику".**</span><span class="sxs-lookup"><span data-stu-id="efa2a-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="efa2a-180">Нажмите **кнопку ОК** в появившемся диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="efa2a-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="efa2a-181">После создания политики защиты от фишинга с использованием этих общих параметров политики настройте параметры защиты в политике, следуя инструкциям в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="efa2a-181">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="efa2a-182">Изменение политик защиты от & безопасности с помощью Центра безопасности для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="efa2a-182">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="efa2a-183">Используйте следующие процедуры для изменения политик защиты от фишинга: новой созданной политики или уже настроенных политик.</span><span class="sxs-lookup"><span data-stu-id="efa2a-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="efa2a-184">Если вы его еще нет, откройте Центр безопасности **Threat management** & и перейдите в антифишинг \> **Policy** \> **политики управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="efa2a-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="efa2a-185">Выберите настраиваемую политику защиты от фишинга, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="efa2a-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="efa2a-186">Убедите, если он уже выбран, снова выберите его и снова.</span><span class="sxs-lookup"><span data-stu-id="efa2a-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="efa2a-187">Появится \*\* \<name\> всплывающее\*\* окно "Изменение политики".</span><span class="sxs-lookup"><span data-stu-id="efa2a-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="efa2a-188">Если **щелкнуть "Изменить"** в любом разделе, вы сможете получить доступ к параметрам в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="efa2a-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="efa2a-189">Следующие шаги представлены в том порядке, в котором появляются разделы, но не являются последовательным (разделы можно выбирать и изменять в любом порядке).</span><span class="sxs-lookup"><span data-stu-id="efa2a-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="efa2a-190">После нажатия **кнопки «Изменить»** в разделе доступные параметры отображаются в формате мастера, но вы можете перейти **Close** на страницы в любом порядке, и можно щелкнуть **«Сохранить»** на любой странице в любом порядке. Чтобы вернуться на страницу "Изменить" возвращающийся на странице **Cancel** ![ ](../../media/scc-remove-icon.png) \*\*"Изменить" \<name\> \*\* (для сохранения или выхода этого параметра не требуется открытие последней страницы мастера).</span><span class="sxs-lookup"><span data-stu-id="efa2a-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="efa2a-191">**Параметр политики:** нажмите **кнопку** "Изменить", чтобы изменить параметры, доступные при [создании политики в](#use-the-security--compliance-center-to-create-anti-phishing-policies) предыдущем разделе:</span><span class="sxs-lookup"><span data-stu-id="efa2a-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="efa2a-192">**Название**</span><span class="sxs-lookup"><span data-stu-id="efa2a-192">**Name**</span></span>
   - <span data-ttu-id="efa2a-193">**Описание**</span><span class="sxs-lookup"><span data-stu-id="efa2a-193">**Description**</span></span>
   - <span data-ttu-id="efa2a-194">**Применяется к**</span><span class="sxs-lookup"><span data-stu-id="efa2a-194">**Applied to**</span></span>
   - <span data-ttu-id="efa2a-195">**Проверьте параметры**</span><span class="sxs-lookup"><span data-stu-id="efa2a-195">**Review your settings**</span></span>

   <span data-ttu-id="efa2a-196">По завершении нажмите кнопку **"Сохранить** на любой странице".</span><span class="sxs-lookup"><span data-stu-id="efa2a-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="efa2a-197">**Spoof:** Click **Edit** to turn or off spoof intelligence включения или отключения аналитики отправителей без проверки подлинности в Outlook, а также настройте действие для применения к сообщениям от заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="efa2a-197">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="efa2a-198">Дополнительные сведения см. в статье ["Параметры подделки" в политиках защиты от фишинга.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="efa2a-198">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="efa2a-199">Обратите внимание, что эти же параметры доступны также в политиках защиты от фишинга ATP.</span><span class="sxs-lookup"><span data-stu-id="efa2a-199">Note that these same settings are also available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="efa2a-200">**Настройки фильтра спуфинга**— по умолчанию установлено значение **"Включено",** и мы рекомендуем оставить его невключенной.</span><span class="sxs-lookup"><span data-stu-id="efa2a-200">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="efa2a-201">Чтобы отключить его, переведите переключатель в **положение "Выкл."**</span><span class="sxs-lookup"><span data-stu-id="efa2a-201">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="efa2a-202">Дополнительные сведения см. в статье ["Настройка аналитики спуфинга" в EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="efa2a-202">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="efa2a-203">Вам не нужно отключать защиту от подделок, если запись MX не указывает на Microsoft 365; вместо этого включается расширенная фильтрация соединителей.</span><span class="sxs-lookup"><span data-stu-id="efa2a-203">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="efa2a-204">Инструкции см. в [статье "Улучшенная фильтрация для соединителей в Exchange Online".](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="efa2a-204">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="efa2a-205">**Включить функцию отправителя, не прошедшего проверку**подлинности: по умолчанию используется **значение "Включено".**</span><span class="sxs-lookup"><span data-stu-id="efa2a-205">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="efa2a-206">Чтобы отключить его, переведите переключатель в **положение "Выкл."**</span><span class="sxs-lookup"><span data-stu-id="efa2a-206">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="efa2a-207">**Действия:** укажите действие для сообщений, не прошедших аналитику спуфинга:</span><span class="sxs-lookup"><span data-stu-id="efa2a-207">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="efa2a-208">**Если сообщение электронной почты был отправлено лицом, запрещающему подделку вашего домена:**</span><span class="sxs-lookup"><span data-stu-id="efa2a-208">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="efa2a-209">**Перемещение сообщения в папки нежелательной почты получателя**</span><span class="sxs-lookup"><span data-stu-id="efa2a-209">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="efa2a-210">**Поместить сообщение в карантин**</span><span class="sxs-lookup"><span data-stu-id="efa2a-210">**Quarantine the message**</span></span>

   - <span data-ttu-id="efa2a-211">**Проверьте параметры,** а не щелкайте каждый из них на отдельном шаге.</span><span class="sxs-lookup"><span data-stu-id="efa2a-211">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="efa2a-212">Чтобы **вернуться на** релевантную страницу, можно щелкнуть "Правка" в каждом разделе.</span><span class="sxs-lookup"><span data-stu-id="efa2a-212">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="efa2a-213">На этой странице можно **включить** или **выключить** следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="efa2a-213">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="efa2a-214">**Включение защиты от спуфинга**</span><span class="sxs-lookup"><span data-stu-id="efa2a-214">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="efa2a-215">**Включить функцию "Включить отправитель, не прошедший проверку подлинности"**</span><span class="sxs-lookup"><span data-stu-id="efa2a-215">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="efa2a-216">По завершении нажмите кнопку **"Сохранить** на любой странице".</span><span class="sxs-lookup"><span data-stu-id="efa2a-216">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="efa2a-217">Вернитесь на **страницу "Изменение \<Name\> политики"** и нажмите кнопку "Закрыть". **Close**</span><span class="sxs-lookup"><span data-stu-id="efa2a-217">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="efa2a-218">Изменение стандартной политики защиты от фишинга с помощью Центра безопасности & требованиям</span><span class="sxs-lookup"><span data-stu-id="efa2a-218">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="efa2a-219">Политика защиты от фишинга по умолчанию называется "По умолчанию Office 365 AntiPhish Default" и не отображается в списке политик.</span><span class="sxs-lookup"><span data-stu-id="efa2a-219">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="efa2a-220">Чтобы изменить политику защиты от фишинга по умолчанию, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="efa2a-220">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="efa2a-221">В Центре безопасности & выберите **защиту** от \> фишинга **Policy** \> **политики управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="efa2a-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="efa2a-222">На странице **"Защита от фишинга"** выберите пункт "Политика **по умолчанию".**</span><span class="sxs-lookup"><span data-stu-id="efa2a-222">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="efa2a-223">**Появляется страница изменения политики по умолчанию для антифишинговых писем Office 365.**</span><span class="sxs-lookup"><span data-stu-id="efa2a-223">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="efa2a-224">Доступны следующие разделы, содержащие идентичные параметры для [изменений настраиваемой политики.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="efa2a-224">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="efa2a-225">**Олицетворение**</span><span class="sxs-lookup"><span data-stu-id="efa2a-225">**Impersonation**</span></span>
   - <span data-ttu-id="efa2a-226">**Подделка**</span><span class="sxs-lookup"><span data-stu-id="efa2a-226">**Spoof**</span></span>
   - <span data-ttu-id="efa2a-227">**Дополнительные параметры**</span><span class="sxs-lookup"><span data-stu-id="efa2a-227">**Advanced settings**</span></span>

   <span data-ttu-id="efa2a-228">При изменении политики по умолчанию недоступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="efa2a-228">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="efa2a-229">Раздел и значения **параметра политики** не отображается, но ссылка на **редактирование** отсутствует, поэтому изменить параметры (имя политики, описание и кого применяется политика (она применяется ко всем получателям)).</span><span class="sxs-lookup"><span data-stu-id="efa2a-229">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="efa2a-230">Политику по умолчанию удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="efa2a-230">You can't delete the default policy.</span></span>
   - <span data-ttu-id="efa2a-231">Вы не можете изменить приоритет политики по умолчанию (она всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="efa2a-231">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="efa2a-232">На странице **"Изменение политики по умолчанию для антифишинговых данных Office 365"** проверьте параметры и нажмите кнопку **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="efa2a-232">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="efa2a-233">Включение и отключение пользовательских политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="efa2a-233">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="efa2a-234">В Центре безопасности & выберите **защиту** от \> фишинга **Policy** \> **политики управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="efa2a-234">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="efa2a-235">Обратите внимание на значение в **столбце "Состояние":**</span><span class="sxs-lookup"><span data-stu-id="efa2a-235">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="efa2a-236">Переведите **переключатель в положение** "Выкл.", чтобы отключить политику.</span><span class="sxs-lookup"><span data-stu-id="efa2a-236">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="efa2a-237">Переведите **переключатель в положение** Вкл, чтобы включить политику.</span><span class="sxs-lookup"><span data-stu-id="efa2a-237">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="efa2a-238">Политику защиты от фишинга по умолчанию отключить невозможно.</span><span class="sxs-lookup"><span data-stu-id="efa2a-238">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="efa2a-239">Установка приоритета настраиваемых политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="efa2a-239">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="efa2a-240">По умолчанию политикам защиты от фишинга присваивается приоритет, основанный на том, в каком порядке они были созданы (приоритет новых политик ниже, чем у старых).</span><span class="sxs-lookup"><span data-stu-id="efa2a-240">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="efa2a-241">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="efa2a-241">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="efa2a-242">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="efa2a-242">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="efa2a-243">Дополнительные сведения о приоритетах, а также оценке и применении нескольких политик см. в статье [Порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="efa2a-243">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="efa2a-244">Настраиваемые политики защиты от фишинга отображаются в порядке их обработки (для первой политики установлен **приоритет** 0).</span><span class="sxs-lookup"><span data-stu-id="efa2a-244">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="efa2a-245">Для стандартной политики защиты от фишинга под названием "Office365 AntiPhish Default" (Антифишинговое значение по умолчанию) установлено **специальное значение приоритета**"Минимальный", ее невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="efa2a-245">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="efa2a-246">**Примечание.** В Центре безопасности & политику можно изменить только после ее создания.</span><span class="sxs-lookup"><span data-stu-id="efa2a-246">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="efa2a-247">В PowerShell можно переопределить заданный по умолчанию приоритет при создании правила защиты от фишинга (это может повлиять на приоритеты существующих правил).</span><span class="sxs-lookup"><span data-stu-id="efa2a-247">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="efa2a-248">Чтобы изменить приоритет политики, в **свойствах** политики можно напрямую изменить приоритет или уменьшить приоритет (в Центре безопасности & требованиям невозможно напрямую изменить значение приоритета). **Decrease priority** **Priority**</span><span class="sxs-lookup"><span data-stu-id="efa2a-248">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="efa2a-249">Изменение приоритета политики имеет смысл только при наличии нескольких политик.</span><span class="sxs-lookup"><span data-stu-id="efa2a-249">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="efa2a-250">В Центре безопасности & соответствия требованиям перейдите в **антифишинговые** данные политики \> **Policy** \> **ATP.**</span><span class="sxs-lookup"><span data-stu-id="efa2a-250">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="efa2a-251">Выберите политику, которую нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="efa2a-251">Select the policy that you want to modify.</span></span> <span data-ttu-id="efa2a-252">Убедите, если он уже выбран, снова выберите его и снова.</span><span class="sxs-lookup"><span data-stu-id="efa2a-252">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="efa2a-253">Появится \*\* \<name\> всплывающее\*\* окно "Изменение политики".</span><span class="sxs-lookup"><span data-stu-id="efa2a-253">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="efa2a-254">Настраиваемая политика защиты от фишинга со **значением приоритета** **0** имеет только кнопку **"Ухудшать** приоритет".</span><span class="sxs-lookup"><span data-stu-id="efa2a-254">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="efa2a-255">Настраиваемая политика защиты от фишинга с наименьшим **значением приоритета** (например, **3)** имеет только кнопку **"Повысить приоритет".**</span><span class="sxs-lookup"><span data-stu-id="efa2a-255">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="efa2a-256">Если у вас три и более настраиваемых политик защиты от фишинга, для политик **Increase priority** между наивысшими и наименьшими значениями приоритетов будут доступны кнопки "Увеличить" и **"Уменьшение** приоритета".</span><span class="sxs-lookup"><span data-stu-id="efa2a-256">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="efa2a-257">Чтобы **изменить значение приоритета,** установите "Увеличить **приоритет"** или "Уменьшить". **Priority**</span><span class="sxs-lookup"><span data-stu-id="efa2a-257">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="efa2a-258">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="efa2a-258">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="efa2a-259">Просмотр политик защиты & безопасности для просмотра политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="efa2a-259">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="efa2a-260">В Центре безопасности & соответствия требованиям перейдите в раздел **"Защита** \> **от** \> **фишинга политики управления угрозами".**</span><span class="sxs-lookup"><span data-stu-id="efa2a-260">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="efa2a-261">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="efa2a-261">Do one of the following steps:</span></span>

   - <span data-ttu-id="efa2a-262">Выберите настраиваемую политику защиты от фишинга, которую хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="efa2a-262">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="efa2a-263">Убедите, если он уже выбран, снова выберите его и снова.</span><span class="sxs-lookup"><span data-stu-id="efa2a-263">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="efa2a-264">Чтобы **просмотреть политику** защиты от фишинга по умолчанию, нажмите "Политика по умолчанию".</span><span class="sxs-lookup"><span data-stu-id="efa2a-264">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="efa2a-265">Появится \*\* \<name\> всплывающая\*\* подсказка "Изменение" политики, в котором можно просмотреть параметры и значения.</span><span class="sxs-lookup"><span data-stu-id="efa2a-265">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="efa2a-266">Удаление политик защиты & безопасности с помощью Центра безопасности</span><span class="sxs-lookup"><span data-stu-id="efa2a-266">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="efa2a-267">В Центре безопасности & выберите **защиту** от \> фишинга **Policy** \> **политики управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="efa2a-267">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="efa2a-268">Выберите политику, которую нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="efa2a-268">Select the policy that you want to remove.</span></span> <span data-ttu-id="efa2a-269">Убедите, если он уже выбран, снова выберите его и снова.</span><span class="sxs-lookup"><span data-stu-id="efa2a-269">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="efa2a-270">В \*\*появившемся \<name\> \*\* окне "Изменить политику" нажмите кнопку **"Удалить**политику", а **затем** в появившемся диалоговом окне предупреждения нажмите кнопку "Да".</span><span class="sxs-lookup"><span data-stu-id="efa2a-270">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="efa2a-271">Политику по умолчанию удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="efa2a-271">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="efa2a-272">Настройка политик защиты от фишинга с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="efa2a-272">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="efa2a-273">Как было сказано выше, политика защиты от фишинга состоит из политики защиты от фишинга и правила защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="efa2a-273">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="efa2a-274">Разница между политиками защиты от фишинга и правилами защиты от фишинга очевидна.</span><span class="sxs-lookup"><span data-stu-id="efa2a-274">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="efa2a-275">Для управления политиками защиты от фишинга используются \*\* \* командлеты -AntiPhishPolicy,\*\* а правила защиты от фишинга управляются с \*\* \* помощью командлетов -AntiPhishRule.\*\*</span><span class="sxs-lookup"><span data-stu-id="efa2a-275">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="efa2a-276">Сначала в PowerShell создается политика защиты от фишинга, а затем — правило защиты от фишинга, указывающее политику, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="efa2a-276">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="efa2a-277">В PowerShell параметры политики защиты от фишинга и правила защиты от фишинга наменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="efa2a-277">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="efa2a-278">При удалении политики защиты от фишинга из PowerShell соответствующее правило защиты от фишинга не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="efa2a-278">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="efa2a-279">Приведенные ниже процедуры PowerShell недоступны в автономных организациях EOP с помощью Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="efa2a-279">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="efa2a-280">Создание политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="efa2a-280">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="efa2a-281">Создание политики защиты от фишинга в PowerShell выполняется в два этапа.</span><span class="sxs-lookup"><span data-stu-id="efa2a-281">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="efa2a-282">Создайте политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="efa2a-282">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="efa2a-283">Создайте правило защиты от фишинга, указывающее политику защиты от фишинга, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="efa2a-283">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="efa2a-284">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="efa2a-284">**Notes**:</span></span>

- <span data-ttu-id="efa2a-285">Вы можете создать новое правило защиты от фишинга и назначить ей существующую, несвязанную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="efa2a-285">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="efa2a-286">Правило защиты от фишинга невозможно связать с несколькими политиками защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="efa2a-286">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="efa2a-287">Вы можете настроить в новых политиках защиты от фишинга в PowerShell следующие параметры, которые будут недоступны в Центре безопасности & соответствия требованиям до создания политики:</span><span class="sxs-lookup"><span data-stu-id="efa2a-287">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="efa2a-288">Создайте новую политику как отключенную _(активна_ `$false` в **командлете New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="efa2a-288">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="efa2a-289">Задать приоритет политики во время создания _(Priority)_ _\<Number\>_ в **командлете New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="efa2a-289">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="efa2a-290">В Центре безопасности & политика защиты от фишинга не отображается в Центре безопасности &, пока вы не назначите ее правилу защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="efa2a-290">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="efa2a-291">Шаг 1. Создание политики защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="efa2a-291">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="efa2a-292">Чтобы создать политику защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="efa2a-292">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="efa2a-293">В этом примере создается политика защиты от фишинга Research Quarantine со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="efa2a-293">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="efa2a-294">Политика включена (мы не используем параметр _Enabled,_ а значение по умолчанию `$true` равно).</span><span class="sxs-lookup"><span data-stu-id="efa2a-294">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="efa2a-295">Описание: "Политика отдела исследований".</span><span class="sxs-lookup"><span data-stu-id="efa2a-295">The description is: Research department policy.</span></span>
- <span data-ttu-id="efa2a-296">Изменяет действие по умолчанию для спуфинга на "Поместитель в карантин".</span><span class="sxs-lookup"><span data-stu-id="efa2a-296">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="efa2a-297">Дополнительные сведения о синтаксисе и параметрах [см. в статье New-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="efa2a-297">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="efa2a-298">Шаг 2. Создание правила защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="efa2a-298">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="efa2a-299">Чтобы создать правило защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="efa2a-299">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="efa2a-300">В этом примере создается антифишинговое правило Research Department со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="efa2a-300">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="efa2a-301">Правило связано с политикой защиты от фишинга с именем Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="efa2a-301">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="efa2a-302">Правило применяется к членам группы "Research Department".</span><span class="sxs-lookup"><span data-stu-id="efa2a-302">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="efa2a-303">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="efa2a-303">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="efa2a-304">Дополнительные сведения о синтаксисе и параметрах [см. в разделе New-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="efa2a-304">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="efa2a-305">Просмотр политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="efa2a-305">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="efa2a-306">Для просмотра существующих политик защиты от фишинга используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="efa2a-306">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="efa2a-307">В этом примере возвращается сводный список всех политик защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="efa2a-307">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="efa2a-308">В этом примере возвращаются значения всех свойств политики защиты от фишинга с именем Executives.</span><span class="sxs-lookup"><span data-stu-id="efa2a-308">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="efa2a-309">Дополнительные сведения о синтаксисе и параметрах см. в [статье Get-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="efa2a-309">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="efa2a-310">Просмотр правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="efa2a-310">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="efa2a-311">Чтобы просмотреть существующие правила защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="efa2a-311">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="efa2a-312">В этом примере возвращается сводный список всех правил защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="efa2a-312">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="efa2a-313">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="efa2a-313">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="efa2a-314">В этом примере возвращаются значения всех свойств правила защиты от фишинга с именем Contoso Executives .</span><span class="sxs-lookup"><span data-stu-id="efa2a-314">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="efa2a-315">Дополнительные сведения о синтаксисе и параметрах см. в [статье Get-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="efa2a-315">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="efa2a-316">Изменение политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="efa2a-316">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="efa2a-317">За другими указанными ниже элементами при изменении политики защиты от фишинга в PowerShell доступны такие же параметры, как и при создании политики, описанной в [разделе "Шаг 1." Создайте раздел](#step-1-use-powershell-to-create-an-anti-phish-policy) политики защиты от фишинга с помощью PowerShell выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="efa2a-317">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="efa2a-318">_Переключатель MakeDefault,_ который превращает указанную политику в политику по умолчанию (применяется ко всем, всегда низкий приоритет является обязательным и его нельзя удалить), доступен только при изменении политики защиты от фишинга в PowerShell. **Lowest**</span><span class="sxs-lookup"><span data-stu-id="efa2a-318">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="efa2a-319">Невозможно переименовать антифишинговую политику **(командлет Set-AntiPhishPolicy** не _имеет параметра_ Name).</span><span class="sxs-lookup"><span data-stu-id="efa2a-319">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="efa2a-320">При переименовании политики защиты от фишинга в Центре безопасности & соответствия _rule_требованиям вы переименовываете только правило защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="efa2a-320">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="efa2a-321">Чтобы изменить политику защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="efa2a-321">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="efa2a-322">Дополнительные сведения о синтаксисе и параметрах [см. в статье О Set-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="efa2a-322">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="efa2a-323">Изменение правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="efa2a-323">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="efa2a-324">При изменении правила защиты от фишинга в PowerShell недоступен только параметр _Enabled,_ позволяющий создать отключенное правило.</span><span class="sxs-lookup"><span data-stu-id="efa2a-324">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="efa2a-325">Сведения о включении или отключении существующих правил защиты от фишинга см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="efa2a-325">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="efa2a-326">В противном случае при изменении правила защиты от фишинга в PowerShell не используются никакие дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="efa2a-326">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="efa2a-327">Такие же параметры доступны при создании правила, как описано в разделе "Шаг 2. Создание правила защиты [от фишинга"](#step-2-use-powershell-to-create-an-anti-phish-rule) выше в этой статье с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="efa2a-327">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="efa2a-328">Чтобы изменить правило защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="efa2a-328">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="efa2a-329">Дополнительные сведения о синтаксисе и параметрах [см. в статье О Set-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="efa2a-329">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="efa2a-330">Включение и отключение правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="efa2a-330">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="efa2a-331">Включение или отключение правила защиты от фишинга в PowerShell включает или отключает всю политику защиты от фишинга (правило защиты от фишинга и назначенную политику защиты от фишинга).</span><span class="sxs-lookup"><span data-stu-id="efa2a-331">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="efa2a-332">Вы не можете включить или отключить политику защиты от фишинга по умолчанию (она всегда применяется ко всем получателям).</span><span class="sxs-lookup"><span data-stu-id="efa2a-332">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="efa2a-333">Для включения и отключения правила защиты от фишинга в PowerShell используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="efa2a-333">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="efa2a-334">В этом примере отключается антифишинговое правило Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="efa2a-334">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="efa2a-335">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="efa2a-335">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="efa2a-336">Дополнительные сведения о синтаксисе и параметрах см. в [описании командлетов Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) [и Disable-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="efa2a-336">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="efa2a-337">Установка приоритета правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="efa2a-337">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="efa2a-338">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="efa2a-338">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="efa2a-339">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="efa2a-339">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="efa2a-340">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="efa2a-340">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="efa2a-341">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="efa2a-341">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="efa2a-342">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="efa2a-342">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="efa2a-343">Чтобы задать приоритет правила защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="efa2a-343">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="efa2a-p137">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="efa2a-p137">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="efa2a-346">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="efa2a-346">**Notes**:</span></span>

- <span data-ttu-id="efa2a-347">Чтобы задать приоритет нового правила при его создании, используйте параметр _Priority_ командлета **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="efa2a-347">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="efa2a-348">Политика защиты от фишинга по умолчанию не имеет соответствующего правила защиты от фишинга, и не имеет неопределенное значение **приоритета (наименьший).**</span><span class="sxs-lookup"><span data-stu-id="efa2a-348">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="efa2a-349">Удаление политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="efa2a-349">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="efa2a-350">При удалении политики защиты от фишинга с помощью PowerShell соответствующее правило защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="efa2a-350">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="efa2a-351">Чтобы удалить политику защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="efa2a-351">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="efa2a-352">В этом примере удаляется политика защиты от фишинга Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="efa2a-352">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="efa2a-353">Дополнительные сведения о синтаксисе и параметрах [см. в статье Remove-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="efa2a-353">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="efa2a-354">Удаление правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="efa2a-354">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="efa2a-355">При удалении правила защиты от фишинга с помощью PowerShell соответствующая политика защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="efa2a-355">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="efa2a-356">Чтобы удалить правило защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="efa2a-356">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="efa2a-357">В этом примере удаляется антифишинговое правило Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="efa2a-357">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="efa2a-358">Дополнительные сведения о синтаксисе и параметрах [см. в статье Remove-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="efa2a-358">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="efa2a-359">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="efa2a-359">How do you know these procedures worked?</span></span>

<span data-ttu-id="efa2a-360">Чтобы убедиться, что политики защиты от фишинга ATP успешно настроены, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="efa2a-360">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="efa2a-361">В Центре безопасности & выберите **защиту** от \> фишинга **Policy** \> **политики управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="efa2a-361">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="efa2a-362">Проверьте список политик, **их значения состояния** и их значения **приоритета.**</span><span class="sxs-lookup"><span data-stu-id="efa2a-362">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="efa2a-363">Для просмотра дополнительных сведений выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="efa2a-363">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="efa2a-364">Выберите политику в списке и посмотрите сведения во всплывающем элементе.</span><span class="sxs-lookup"><span data-stu-id="efa2a-364">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="efa2a-365">Выберите **пункт "Политика по умолчанию"** и просмотрите сведения во всплывающем элементе.</span><span class="sxs-lookup"><span data-stu-id="efa2a-365">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="efa2a-366">В Exchange Online PowerShell \<Name\> замените имя политики или правила и выполните следующую команду и проверьте параметры:</span><span class="sxs-lookup"><span data-stu-id="efa2a-366">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
