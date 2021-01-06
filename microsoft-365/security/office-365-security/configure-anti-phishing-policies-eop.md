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
ms.openlocfilehash: 03c1ce8e940491607fe04988d41c927f92479d96
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760336"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="bb5e2-103">Настройка политик защиты от фишинга в EOP</span><span class="sxs-lookup"><span data-stu-id="bb5e2-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="bb5e2-104">В организациях Microsoft 365 с почтовыми ящиками в Организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online существует политика защиты от фишинга по умолчанию, которая содержит ограниченное количество функций защиты от спуфинга, включенных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="bb5e2-105">Дополнительные сведения [см. в параметрах спуфинга в](set-up-anti-phishing-policies.md#spoof-settings)политиках защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="bb5e2-106">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="bb5e2-107">Для большей детализации можно также создать настраиваемые политики защиты от фишинга, которые применяются к определенным пользователям, группам или доменам в организации.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="bb5e2-108">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="bb5e2-109">Организации с почтовыми ящиками Exchange Online могут настраивать политики защиты от фишинга в Центре безопасности & соответствия требованиям или в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="bb5e2-110">Автономные организации EOP могут использовать только Центр безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="bb5e2-111">Сведения о создании и изменении более сложных политик защиты от фишинга в Microsoft Defender для Office 365, доступных в Защитнике Office 365, см. в подстройке "Настройка политик защиты от фишинга" в Microsoft Defender для [Office 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="bb5e2-111">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="bb5e2-112">Основные элементы политики защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-112">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="bb5e2-113">**Политика защиты от фишинга**: определяет средства защиты от фишинга, которые необходимо включить или отключить, а также действия, которые необходимо применить.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-113">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="bb5e2-114">**Правило защиты от фишинга:** определяет приоритет и фильтры получателей (к кому применяется политика) для политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-114">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="bb5e2-115">Разница между этими двумя элементами не очевидна при управлении политиками защиты от фишинга в Центре безопасности & соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-115">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="bb5e2-116">При создании политики защиты от фишинга фактически создается правило защиты от фишинга и связанная с ним политика одновременно с одинаковым именем для обоих этих правил.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-116">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="bb5e2-117">При изменении политики защиты от фишинга параметры, связанные с именем, приоритетом, включенным или отключенным фильтрами получателей, изменяют правило защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-117">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="bb5e2-118">Все остальные параметры изменяют связанную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-118">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="bb5e2-119">При удалении политики защиты от фишинга удаляются правило защиты от фишинга и связанная с ним политика защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-119">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="bb5e2-120">В Exchange Online PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-120">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="bb5e2-121">Дополнительные сведения см. в разделе "Настройка политик защиты от фишинга с помощью [Exchange Online PowerShell"](#use-exchange-online-powershell-to-configure-anti-phishing-policies) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-121">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="bb5e2-122">В каждой организации есть встроенная политика защиты от фишинга с именем Office365 AntiPhish Default, которая имеет указанные здесь свойства.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-122">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="bb5e2-123">Политика применяется к всем получателям в организации, даже если с ней не связано ни одно правило защиты от фишинга (фильтры получателей).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-123">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="bb5e2-124">Для политики задано специальное значение приоритета **Самый низкий**, которое невозможно изменить (эта политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-124">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="bb5e2-125">Все созданные специальные политики всегда имеют более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-125">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="bb5e2-126">Эта политика является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-126">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="bb5e2-127">Чтобы повысить эффективность защиты от фишинга, можно создать настраиваемые политики защиты от фишинга с более строгими настройками, применяемыми к определенным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-127">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bb5e2-128">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="bb5e2-128">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bb5e2-129">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-129">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="bb5e2-130">Чтобы перейти непосредственно на страницу защиты **от фишинга,** используйте <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="bb5e2-130">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="bb5e2-131">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="bb5e2-132">Вы не можете управлять политиками защиты от фишинга в автономных EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-132">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="bb5e2-133">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-133">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="bb5e2-134">Чтобы добавлять, изменять и удалять политики защиты от фишинга, необходимо  быть членом группы ролей "Управление организацией" или "Администратор **безопасности".**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-134">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="bb5e2-135">Для доступа только для чтения к политикам защиты от фишинга необходимо  быть членом группы ролей **"Глобальный** читатель" или "Читатель <sup>\*</sup> безопасности".</span><span class="sxs-lookup"><span data-stu-id="bb5e2-135">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="bb5e2-136">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-136">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="bb5e2-137">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-137">**Notes**:</span></span>

  - <span data-ttu-id="bb5e2-138">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="bb5e2-139">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-139">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="bb5e2-140">Группа **ролей управления организацией** с доступом только для просмотра в Exchange [Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ к этой функции только для <sup>\*</sup> чтения.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-140">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="bb5e2-141"><sup>\*</sup> В Центре & соответствия требованиям доступ только для чтения позволяет пользователям просматривать параметры пользовательских политик защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-141"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="bb5e2-142">Пользователи, только для чтения, не могут видеть параметры в политике защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-142">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="bb5e2-143">Чтобы создать и изменить политики защиты от фишинга в автономных EOP,  необходимо сделать что-то, для чего требуется реанимация клиента.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-143">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="bb5e2-144">Например, в Центре администрирования Exchange можно перейти  на вкладку "Разрешения", выбрать  существующую группу ролей, щелкнуть значок редактирования и удалить роль (которую вы в конечном счете ![ добавите). ](../../media/ITPro-EAC-EditIcon.png)</span><span class="sxs-lookup"><span data-stu-id="bb5e2-144">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="bb5e2-145">Если клиент никогда не был перерисован, вы получите диалоговое окно с именем **Update Organization Settings** (Обновить параметры организации) с помощью панели хода выполнения, которая должна быть успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-145">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="bb5e2-146">Дополнительные сведения о реадрайтах см. в сведениях о том, как получить сведения о нем, см. в средстве [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (который не доступен в автономных службах EOP PowerShell или в Центре безопасности & соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-146">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="bb5e2-147">Рекомендуемые параметры для политик защиты от фишинга см. в настройках политики защиты от фишинга по умолчанию [для EOP.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="bb5e2-147">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="bb5e2-148">Чтобы применить обновленную политику, можно использовать до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-148">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="bb5e2-149">Сведения о том, где политики защиты от фишинга применяются в конвейере фильтрации, см. в сведениях о порядке и приоритете [защиты электронной почты.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="bb5e2-149">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="bb5e2-150">Использование Центра безопасности & соответствия требованиям для создания политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="bb5e2-150">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="bb5e2-151">При создании настраиваемой политики защиты от фишинга в Центре безопасности & соответствия требованиям одновременно создаются правило защиты от фишинга и связанная с ним политика с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-151">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="bb5e2-152">При создании политики защиты от фишинга можно указать только имя политики, описание и фильтр получателей, определяющий, к кому применяется политика.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-152">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="bb5e2-153">После создания политики можно изменить политику, чтобы изменить или просмотреть параметры защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-153">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="bb5e2-154">В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами для защиты \>  \> **от фишинга.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-154">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="bb5e2-155">На странице **"Антифишинг"** нажмите кнопку **"Создать".**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-155">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="bb5e2-156">Откроется **мастер создания политики защиты от фишинга.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-156">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="bb5e2-157">На странице **"Имя политики"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-157">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="bb5e2-158">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-158">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="bb5e2-159">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-159">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="bb5e2-160">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-160">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="bb5e2-161">На странице **"Применено к"** определите внутренних получателей, к которые применяется политика.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-161">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="bb5e2-162">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-162">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="bb5e2-163">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-163">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="bb5e2-164">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-164">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="bb5e2-165">Нажмите **кнопку "Добавить условие".**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-165">Click **Add a condition**.</span></span> <span data-ttu-id="bb5e2-166">В отобрабяемом выпадаемом окном выберите условие в области **"Применено", если:**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-166">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="bb5e2-167">**Получатель:** указывает один или несколько почтовых ящиков, почтовых пользователей или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-167">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="bb5e2-168">**Получатель является членом**: указывает одну или несколько групп в организации.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-168">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="bb5e2-169">**Домен получателя**: Указывает получателей в одном или нескольких настроенных принятых доменов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-169">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="bb5e2-170">После выбора условия появится соответствующее dropdown с любым **из этих полей.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-170">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="bb5e2-171">Щелкните поле и прокрутите список выбранных значений.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-171">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="bb5e2-172">Щелкните поле и начните вводить текст, чтобы отфильтровать список и выбрать значение.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-172">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="bb5e2-173">Чтобы добавить дополнительные значения, щелкните пустую область в поле.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-173">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="bb5e2-174">Чтобы удалить отдельные записи, **щелкните значок** ![ "Удалить" в ](../../media/scc-remove-icon.png) значении.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-174">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="bb5e2-175">Чтобы удалить все условие, щелкните **значок "Удалить** ![ удалить" ](../../media/scc-remove-icon.png) в этом условии.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-175">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="bb5e2-176">Чтобы добавить дополнительное условие, нажмите кнопку **"Добавить условие"** и выберите оставшееся значение **в области "Применено", если**.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-176">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="bb5e2-177">Чтобы добавить исключения, нажмите **кнопку "Добавить условие"** и выберите исключение в области **"Кроме случаев, когда"**.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-177">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="bb5e2-178">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-178">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="bb5e2-179">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-179">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="bb5e2-180">На странице **"Просмотр параметров"** просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-180">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="bb5e2-181">Вы можете нажать **кнопку "Изменить"** для каждого параметра, чтобы изменить его.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-181">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="bb5e2-182">После завершения нажмите кнопку **"Создать эту политику".**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-182">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="bb5e2-183">Нажмите **кнопку** "ОК" в от появляются диалоговое окно подтверждения.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-183">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="bb5e2-184">После создания политики защиты от фишинга с этими общими настройками политики используйте инструкции, указанные в следующем разделе, для настройки параметров защиты в политике.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-184">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="bb5e2-185">Использование Центра безопасности & соответствия требованиям для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="bb5e2-185">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="bb5e2-186">Для изменения политик защиты от фишинга используйте следующие процедуры: новую политику, созданную вами, или существующие политики, которые вы уже настроили.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-186">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="bb5e2-187">Если вы еще не там, откройте Центр безопасности & соответствия  требованиям и перейдите к политике управления угрозами для защиты от \>  \> **фишинга.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-187">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="bb5e2-188">Выберите настраиваемую политику защиты от фишинга, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-188">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="bb5e2-189">Если он уже выбран, отоберем его и снова выберите.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-189">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="bb5e2-190">Появится **flyout \<name\>** изменения политики.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-190">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="bb5e2-191">Если **щелкнуть "Изменить"** в любом разделе, вы сможете получить доступ к настройкам в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-191">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="bb5e2-192">Следующие действия представлены в том порядке, в который отображаются разделы, но они не являются последовательной (разделы можно выбрать и изменить в любом порядке).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-192">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="bb5e2-193">После нажатия кнопки "Изменить" в разделе доступные параметры будут представлены в формате мастера, но вы  можете перейти к  страницам в любом порядке, и вы можете нажать кнопку "Сохранить" на любой странице (или   ![ ](../../media/scc-remove-icon.png) **\<name\>** значок "Отмена или закрыть", чтобы вернуться на страницу "Изменить политику" (для сохранения или закрытия страницы не требуется перейти на последнюю страницу мастера).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-193">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="bb5e2-194">**Параметр политики:** **нажмите кнопку** "Изменить", чтобы изменить те же параметры, которые были доступны при создании политики [в](#use-the-security--compliance-center-to-create-anti-phishing-policies) предыдущем разделе:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-194">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="bb5e2-195">**Название**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-195">**Name**</span></span>
   - <span data-ttu-id="bb5e2-196">**Описание**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-196">**Description**</span></span>
   - <span data-ttu-id="bb5e2-197">**Применяется к**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-197">**Applied to**</span></span>
   - <span data-ttu-id="bb5e2-198">**Просмотр параметров**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-198">**Review your settings**</span></span>

   <span data-ttu-id="bb5e2-199">По завершению нажмите кнопку **"Сохранить** на любой странице".</span><span class="sxs-lookup"><span data-stu-id="bb5e2-199">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="bb5e2-200">**Подмена:**  нажмите кнопку "Изменить", чтобы включить или отключить аналитику спуфингов, включите или отключите идентификацию отправителей, неавтериаленную идентификацию отправителей в Outlook, и настройте действие для применения к сообщениям от заблокированных поддельных отправителей.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-200">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="bb5e2-201">Дополнительные сведения [см. в параметрах спуфинга в](set-up-anti-phishing-policies.md#spoof-settings)политиках защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-201">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="bb5e2-202">Обратите внимание, что эти же параметры также доступны в политиках защиты от фишинга в Защитнике для Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-202">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="bb5e2-203">**Параметры фильтра спуфинга:** значение по умолчанию — **"В** активе", и мы рекомендуем оставить его на месте.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-203">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="bb5e2-204">Чтобы отключить его, переключите его на **выключение.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-204">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="bb5e2-205">Дополнительные сведения см. в сведениях [о настройке аналитики спуфинга в EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="bb5e2-205">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="bb5e2-206">Вам не нужно отключать защиту от спуфинга, если запись MX не означает Microsoft 365; Вместо этого включается расширенная фильтрация для соединителя.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-206">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="bb5e2-207">Инструкции см. в [расширенной фильтрации соединителях в Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="bb5e2-207">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="bb5e2-208">**Включить функцию неавтоматического** отправитель : значение по умолчанию **" В.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-208">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="bb5e2-209">Чтобы отключить его, переключите его на **выключение.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-209">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="bb5e2-210">**Действия:** укажите действие, которое необходимо принять с сообщениями, которые не сбой аналитики спуфинг:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-210">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="bb5e2-211">**Если сообщение отправляется человеком, которому** запрещено подменять ваш домен:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-211">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="bb5e2-212">**Перемещение сообщения в папки нежелательной почты получателей**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-212">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="bb5e2-213">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-213">**Quarantine the message**</span></span>

   - <span data-ttu-id="bb5e2-214">**Просмотрите параметры:** вместо того чтобы щелкать каждый отдельный шаг, параметры отображаются в сводке.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-214">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="bb5e2-215">Можно **щелкнуть "Изменить"** в каждом разделе, чтобы вернуться на соответствующую страницу.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-215">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="bb5e2-216">На этой странице можно отключить или  **отключить** следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-216">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="bb5e2-217">**Включить защиту от спуфинга**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-217">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="bb5e2-218">**Включить функцию "Отправителю, не проавентированному"**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-218">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="bb5e2-219">По завершению нажмите кнопку **"Сохранить** на любой странице".</span><span class="sxs-lookup"><span data-stu-id="bb5e2-219">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="bb5e2-220">На странице **"Изменение \<Name\> политики"** просмотрите параметры и нажмите кнопку **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-220">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="bb5e2-221">Использование Центра безопасности & соответствия требованиям для изменения политики защиты от фишинга по умолчанию</span><span class="sxs-lookup"><span data-stu-id="bb5e2-221">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="bb5e2-222">Политика защиты от фишинга по умолчанию называется Office365 AntiPhish Default и не появляется в списке политик.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-222">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="bb5e2-223">Чтобы изменить политику защиты от фишинга по умолчанию, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-223">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="bb5e2-224">В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами для защиты \>  \> **от фишинга.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="bb5e2-225">На странице **"Антифишинг"** щелкните политику **по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-225">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="bb5e2-226">Появится **страница "Изменение политики Office 365 по** умолчанию".</span><span class="sxs-lookup"><span data-stu-id="bb5e2-226">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="bb5e2-227">Доступны следующие разделы, которые содержат идентичные параметры при [изменении настраиваемой политики.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="bb5e2-227">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="bb5e2-228">**Олицетворение**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-228">**Impersonation**</span></span>
   - <span data-ttu-id="bb5e2-229">**Подмена**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-229">**Spoof**</span></span>
   - <span data-ttu-id="bb5e2-230">**Дополнительные параметры**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-230">**Advanced settings**</span></span>

   <span data-ttu-id="bb5e2-231">При изменении политики по умолчанию недоступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-231">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="bb5e2-232">Вы можете  увидеть раздел и значения параметров политики, но нет ссылки на изменение, поэтому изменить параметры (имя политики, описание и к кому применяется политика (применяется ко всем получателям)) нельзя. </span><span class="sxs-lookup"><span data-stu-id="bb5e2-232">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="bb5e2-233">Политику по умолчанию удалить нельзя.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-233">You can't delete the default policy.</span></span>
   - <span data-ttu-id="bb5e2-234">Вы не можете изменить приоритет политики по умолчанию (она всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-234">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="bb5e2-235">На странице **"Изменение политики Office 365** по умолчанию" просмотрите параметры и нажмите кнопку **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-235">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="bb5e2-236">Включить или отключить настраиваемые политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="bb5e2-236">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="bb5e2-237">В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами для защиты \>  \> **от фишинга.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-237">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="bb5e2-238">Обратите внимание на значение в **столбце "Состояние":**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-238">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="bb5e2-239">Переключите его, **чтобы** отключить политику.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-239">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="bb5e2-240">Чтобы включить политику,  передвигает его на "Вкл.".</span><span class="sxs-lookup"><span data-stu-id="bb5e2-240">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="bb5e2-241">Вы не можете отключить политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-241">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="bb5e2-242">Настройка приоритета пользовательских политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="bb5e2-242">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="bb5e2-243">По умолчанию политикам защиты от фишинга предоставляется приоритет, основанный на порядке их создания (приоритет новых политик ниже, чем у старых).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-243">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="bb5e2-244">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-244">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="bb5e2-245">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-245">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="bb5e2-246">Дополнительные сведения о приоритетах, а также оценке и применении нескольких политик см. в статье [Порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-246">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="bb5e2-247">Настраиваемые политики защиты от фишинга отображаются в порядке их обработки (первая политика имеет значение **приоритета** 0).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-247">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="bb5e2-248">Политика защиты от фишинга по умолчанию с именем Office365 AntiPhish Default имеет настраиваемое значение приоритета **"Самый** низкий", и вы не можете изменить его.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-248">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="bb5e2-249">**Примечание.** В Центре & соответствия требованиям приоритет политики защиты от фишинга можно изменить только после ее создания.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-249">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="bb5e2-250">В PowerShell можно переопредить приоритет по умолчанию при создании правила защиты от фишинга (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-250">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="bb5e2-251">Чтобы изменить приоритет политики, нажмите  кнопку "Увеличить приоритет" или "Уменьшить приоритет" в свойствах  политики (нельзя напрямую изменить номер приоритета в Центре безопасности и соответствия & соответствия требованиям). </span><span class="sxs-lookup"><span data-stu-id="bb5e2-251">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="bb5e2-252">Изменение приоритета политики имеет смысл, только если имеется несколько политик.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-252">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="bb5e2-253">В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами ATP для защиты от \>  \> **фишинга.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="bb5e2-254">Выберите политику, которую нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-254">Select the policy that you want to modify.</span></span> <span data-ttu-id="bb5e2-255">Если он уже выбран, отоберем его и снова выберите.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-255">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="bb5e2-256">Появится **flyout \<name\>** изменения политики.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-256">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="bb5e2-257">Настраиваемая политика защиты от фишинга со значением **приоритета** **0** имеет только доступную кнопку "Уменьшить **приоритет".**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-257">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="bb5e2-258">Настраиваемая политика защиты от  фишинга с наименьшим значением приоритета (например, **3)** имеет только доступную кнопку "Увеличить **приоритет".**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-258">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="bb5e2-259">Если у вас есть три или более пользовательских политик защиты от фишинга, политики  между самыми  высокими и минимальными значениями приоритета имеют доступные кнопки "Увеличить приоритет" и "Уменьшить приоритет".</span><span class="sxs-lookup"><span data-stu-id="bb5e2-259">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="bb5e2-260">Нажмите **кнопку "Увеличить приоритет"** или **"Уменьшить приоритет",** чтобы изменить **значение приоритета.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-260">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="bb5e2-261">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-261">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="bb5e2-262">Просмотр политик защиты & безопасности с помощью Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="bb5e2-262">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="bb5e2-263">В Центре безопасности & соответствия требованиям перейдите к политике управления угрозами для защиты  \>  \> **от фишинга.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-263">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="bb5e2-264">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-264">Do one of the following steps:</span></span>

   - <span data-ttu-id="bb5e2-265">Выберите настраиваемую политику защиты от фишинга, которую необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-265">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="bb5e2-266">Если он уже выбран, отоберем его и снова выберите.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-266">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="bb5e2-267">Щелкните **политику по умолчанию,** чтобы просмотреть политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-267">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="bb5e2-268">Появится **flyout \<name\>** изменения политики, где можно просмотреть параметры и значения.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-268">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="bb5e2-269">Удаление политик защиты & безопасности с помощью Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="bb5e2-269">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="bb5e2-270">В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами для защиты \>  \> **от фишинга.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-270">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="bb5e2-271">Выберите политику, которую нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-271">Select the policy that you want to remove.</span></span> <span data-ttu-id="bb5e2-272">Если он уже выбран, отоберем его и снова выберите.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-272">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="bb5e2-273">В **отметок \<name\> "Изменить** политику" щелкните "Удалить политику", а затем нажмите кнопку **"Да"** в диалоговом окле предупреждения.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-273">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="bb5e2-274">Политику по умолчанию удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-274">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="bb5e2-275">Настройка политик защиты от фишинга с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb5e2-275">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="bb5e2-276">Как было описано выше, политика защиты от фишинга состоит из политики защиты от фишинга и правила защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-276">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="bb5e2-277">В Exchange Online PowerShell разница между политиками защиты от фишинга и правилами защиты от фишинга очевидна.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-277">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="bb5e2-278">Вы управляете политиками защиты от фишинга с помощью cmdlets **\* -AntiPhishPolicy** и управляете правилами защиты от фишинга с помощью **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-278">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="bb5e2-279">В PowerShell сначала создается политика защиты от фишинга, а затем создается правило защиты от фишинга, которое определяет политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-279">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="bb5e2-280">В PowerShell параметры политики защиты от фишинга и правила защиты от фишинга изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-280">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="bb5e2-281">При удалении политики защиты от фишинга из PowerShell соответствующее правило не удаляется автоматически и наоборот.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-281">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="bb5e2-282">Следующие процедуры PowerShell недоступны в автономных организациях EOP с помощью Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-282">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="bb5e2-283">Создание политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb5e2-283">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="bb5e2-284">Создание политики защиты от фишинга в PowerShell — это двухшаговая процедура:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-284">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="bb5e2-285">Создайте политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-285">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="bb5e2-286">Создайте правило защиты от фишинга, которое определяет политику защиты от фишинга, к которую оно применяется.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-286">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="bb5e2-287">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-287">**Notes**:</span></span>

- <span data-ttu-id="bb5e2-288">Вы можете создать новое правило защиты от фишинга и назначить ему существующую несвязаную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-288">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="bb5e2-289">Правило защиты от фишинга не может быть связано с более чем одной политикой защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-289">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="bb5e2-290">Вы можете настроить следующие параметры для новых политик защиты от фишинга в PowerShell, которые недоступны в Центре безопасности & соответствия требованиям, пока не создайте политику:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-290">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="bb5e2-291">Создайте новую политику как отключенную _(включена_ `$false` в **cmdlet New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-291">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="bb5e2-292">Установите приоритет политики во время создания _(priority)_ в _\<Number\>_ **cmdlet New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-292">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="bb5e2-293">Новая политика защиты от фишинга, которую вы создаете в PowerShell, не отображается в Центре безопасности & соответствия требованиям, пока вы не назначите политику правилу защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-293">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="bb5e2-294">Шаг 1. Создание политики защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb5e2-294">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="bb5e2-295">Чтобы создать политику защиты от фишинга, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-295">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="bb5e2-296">В этом примере создается политика защиты от фишинга Research Quarantine со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-296">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="bb5e2-297">Описание: "Политика исследовательского отдела".</span><span class="sxs-lookup"><span data-stu-id="bb5e2-297">The description is: Research department policy.</span></span>
- <span data-ttu-id="bb5e2-298">Изменяет действие по умолчанию для спуфинга на Карантин.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-298">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="bb5e2-299">Подробные сведения о синтаксисе и параметрах см. в описании [New-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="bb5e2-299">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="bb5e2-300">Шаг 2. Создание правила защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb5e2-300">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="bb5e2-301">Чтобы создать правило защиты от фишинга, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-301">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="bb5e2-302">В этом примере создается правило защиты от фишинга Research Department со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-302">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="bb5e2-303">Правило связано с политикой защиты от фишинга Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-303">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="bb5e2-304">Правило применяется к членам группы "Research Department".</span><span class="sxs-lookup"><span data-stu-id="bb5e2-304">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="bb5e2-305">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-305">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="bb5e2-306">Подробные сведения о синтаксисе и параметрах см. в описании [New-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="bb5e2-306">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="bb5e2-307">Просмотр политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb5e2-307">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="bb5e2-308">Чтобы просмотреть существующие политики защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-308">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="bb5e2-309">В этом примере возвращается сводный список всех политик защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-309">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="bb5e2-310">В этом примере возвращаются все значения свойств для политики защиты от фишинга Executives.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-310">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="bb5e2-311">Подробные сведения о синтаксисе и параметрах см. в описании [Get-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="bb5e2-311">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="bb5e2-312">Просмотр правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb5e2-312">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="bb5e2-313">Чтобы просмотреть существующие правила защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-313">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="bb5e2-314">В этом примере возвращается сводный список всех правил защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-314">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="bb5e2-315">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-315">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="bb5e2-316">В этом примере возвращаются все значения свойств правила защиты от фишинга с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-316">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="bb5e2-317">Подробные сведения о синтаксисе и параметрах см. в описании [get-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="bb5e2-317">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="bb5e2-318">Изменение политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb5e2-318">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="bb5e2-319">Кроме следующих элементов, при изменении политики защиты от фишинга в PowerShell доступны те же параметры, что и при создании политики, описанной в шаге 1. Создание политики защиты от фишинга с помощью [PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-319">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="bb5e2-320">Переключатель _MakeDefault,_ который превращает указанную политику в политику по  умолчанию (применяется для всех, всегда имеет самый низкий приоритет и удалить ее нельзя) доступен только при изменении политики защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-320">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="bb5e2-321">Политику защиты от фишинга нельзя переименовать (у cmdlet **Set-AntiPhishPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="bb5e2-321">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="bb5e2-322">При переименовании политики защиты от фишинга в Центре безопасности и соответствия требованиям & только переименовывать правило защиты от _фишинга._</span><span class="sxs-lookup"><span data-stu-id="bb5e2-322">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="bb5e2-323">Чтобы изменить политику защиты от фишинга, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-323">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="bb5e2-324">Подробные сведения о синтаксисе и параметрах см. в описании [Set-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="bb5e2-324">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="bb5e2-325">Изменение правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb5e2-325">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="bb5e2-326">Единственным параметром, недоступным при изменении правила защиты от фишинга в PowerShell, является параметр _Enabled,_ позволяющий создать отключенное правило.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-326">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="bb5e2-327">Чтобы включить или отключить существующие правила защиты от фишинга, см. следующий раздел.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-327">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="bb5e2-328">В противном случае при создании правила доступны те же параметры, что и в разделе "Шаг 2. Создание правила защиты от фишинга с помощью [PowerShell",](#step-2-use-powershell-to-create-an-anti-phish-rule) описанного ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-328">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="bb5e2-329">Чтобы изменить правило защиты от фишинга, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-329">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="bb5e2-330">Подробные сведения о синтаксисе и параметрах см. в описании [set-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="bb5e2-330">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="bb5e2-331">Использование PowerShell для включаемого или отключения правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="bb5e2-331">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="bb5e2-332">Включение или отключение правила защиты от фишинга в PowerShell включает или отключает всю политику защиты от фишинга (правило защиты от фишинга и назначенную политику защиты от фишинга).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-332">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="bb5e2-333">Вы не можете включить или отключить политику защиты от фишинга по умолчанию (она всегда применяется для всех получателей).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-333">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="bb5e2-334">Чтобы включить или отключить правило защиты от фишинга в PowerShell, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-334">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="bb5e2-335">В этом примере отключается правило защиты от фишинга Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-335">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="bb5e2-336">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-336">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="bb5e2-337">Подробные сведения о синтаксисе и параметрах см. в описании [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) и [Disable-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="bb5e2-337">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="bb5e2-338">Настройка приоритета правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb5e2-338">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="bb5e2-339">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-339">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="bb5e2-340">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-340">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="bb5e2-341">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-341">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="bb5e2-342">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-342">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="bb5e2-343">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-343">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="bb5e2-344">Чтобы установить приоритет правила защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-344">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="bb5e2-p138">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="bb5e2-p138">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="bb5e2-347">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-347">**Notes**:</span></span>

- <span data-ttu-id="bb5e2-348">Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в вместо этого в cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-348">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="bb5e2-349">Политика защиты от фишинга по умолчанию не имеет соответствующего правила защиты от фишинга и всегда имеет немодифимируемый приоритет **"Самый низкий"**.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-349">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="bb5e2-350">Удаление политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb5e2-350">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="bb5e2-351">При удалении политики защиты от фишинга с помощью PowerShell соответствующее правило защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-351">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="bb5e2-352">Чтобы удалить политику защиты от фишинга в PowerShell, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-352">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="bb5e2-353">В этом примере удаляется политика защиты от фишинга Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-353">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="bb5e2-354">Подробные сведения о синтаксисе и параметрах см. в описании [remove-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="bb5e2-354">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="bb5e2-355">Удаление правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb5e2-355">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="bb5e2-356">При удалении правила защиты от фишинга с помощью PowerShell соответствующая политика защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-356">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="bb5e2-357">Чтобы удалить правило защиты от фишинга в PowerShell, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-357">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="bb5e2-358">В этом примере удаляется правило защиты от фишинга Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-358">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="bb5e2-359">Подробные сведения о синтаксисе и параметрах см. в описании [remove-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="bb5e2-359">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="bb5e2-360">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="bb5e2-360">How do you know these procedures worked?</span></span>

<span data-ttu-id="bb5e2-361">Чтобы убедиться, что вы успешно настроили политики защиты от фишинга в Microsoft Defender для Office 365, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-361">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="bb5e2-362">В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами для защиты \>  \> **от фишинга.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-362">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="bb5e2-363">Проверьте список политик, их значения **состояния** и их **значения приоритета.**</span><span class="sxs-lookup"><span data-stu-id="bb5e2-363">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="bb5e2-364">Чтобы просмотреть дополнительные сведения, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-364">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="bb5e2-365">Выберите политику в списке и просмотреть сведения во flyout.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-365">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="bb5e2-366">Щелкните **политику по умолчанию** и просмотрете сведения во flyout.</span><span class="sxs-lookup"><span data-stu-id="bb5e2-366">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="bb5e2-367">В Exchange Online PowerShell замените имя политики или правила, запустите следующую команду и проверьте \<Name\> параметры:</span><span class="sxs-lookup"><span data-stu-id="bb5e2-367">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
