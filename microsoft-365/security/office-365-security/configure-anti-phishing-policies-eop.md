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
description: Администраторы могут научиться создавать, изменять и удалять политики защиты от фишинга, доступные в организациях Exchange Online Protection (EOP) с почтовыми ящиками Exchange Online или без них.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 945c993c32d6258fc4d9a9edd51b9ed7e8f64c37
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906604"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="db6b3-103">Настройка политик защиты от фишинга в EOP</span><span class="sxs-lookup"><span data-stu-id="db6b3-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="db6b3-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="db6b3-104">**Applies to**</span></span>
- [<span data-ttu-id="db6b3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="db6b3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="db6b3-106">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online по умолчанию существует политика защиты от фишинга, которая содержит ограниченное число функций защиты от спуфинга, которые включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="db6b3-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="db6b3-107">Дополнительные сведения см. в [параметрах Spoof в политиках защиты от фишинга.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="db6b3-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="db6b3-108">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="db6b3-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="db6b3-109">Для большей детализации можно также создать настраиваемые политики защиты от фишинга, применимые к определенным пользователям, группам или доменам в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="db6b3-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="db6b3-110">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="db6b3-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="db6b3-111">Организации с почтовыми ящиками Exchange Online могут настраивать политики защиты от фишинга в Центре & безопасности или в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db6b3-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="db6b3-112">Автономные организации EOP могут использовать только Центр & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="db6b3-112">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="db6b3-113">Сведения о создании и изменении более совершенных политик защиты от фишинга в Microsoft Defender для Office 365, доступных в Defender for Office 365, см. в этой рубке Настройка политик защиты от фишинга в [Microsoft Defender для Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="db6b3-113">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="db6b3-114">Основные элементы политики защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="db6b3-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="db6b3-115">**Политика защиты от фишинга:** указывает средства защиты от фишинга, чтобы включить или отключить, а также действия по применении параметров.</span><span class="sxs-lookup"><span data-stu-id="db6b3-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="db6b3-116">**Правило защиты от фишинга:** указывает фильтры приоритета и получателей (к кому применяется политика) для политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="db6b3-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="db6b3-117">Разница между этими двумя элементами не очевидна при управлении политиками защиты от фишинга в Центре & безопасности:</span><span class="sxs-lookup"><span data-stu-id="db6b3-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="db6b3-118">При создании политики защиты от фишинга создается правило защиты от фишинга и связанная с ним политика защиты от фишинга, используя одно и то же имя для обоих.</span><span class="sxs-lookup"><span data-stu-id="db6b3-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="db6b3-119">При изменении политики защиты от фишинга параметры, связанные с именем, приоритетом, включенной или отключенной, а также фильтры получателей изменяют правило защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="db6b3-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="db6b3-120">Все остальные параметры изменяют связанную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="db6b3-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="db6b3-121">При удалении политики защиты от фишинга правило защиты от фишинга и связанная с ним политика защиты от фишинга удаляются.</span><span class="sxs-lookup"><span data-stu-id="db6b3-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="db6b3-122">В Exchange Online PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="db6b3-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="db6b3-123">Дополнительные сведения см. в разделе [Use Exchange Online PowerShell для](#use-exchange-online-powershell-to-configure-anti-phishing-policies) настройки политики защиты от фишинга в этой статье.</span><span class="sxs-lookup"><span data-stu-id="db6b3-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="db6b3-124">Каждая организация имеет встроенную политику защиты от фишинга с именем Office365 AntiPhish Default, которая имеет эти свойства:</span><span class="sxs-lookup"><span data-stu-id="db6b3-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="db6b3-125">Политика применяется к всем получателям в организации, несмотря на отсутствие правила защиты от фишинга (фильтры получателей), связанного с политикой.</span><span class="sxs-lookup"><span data-stu-id="db6b3-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="db6b3-126">Для политики задано специальное значение приоритета **Самый низкий**, которое невозможно изменить (эта политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="db6b3-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="db6b3-127">Все созданные специальные политики всегда имеют более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="db6b3-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="db6b3-128">Эта политика является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.</span><span class="sxs-lookup"><span data-stu-id="db6b3-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="db6b3-129">Чтобы повысить эффективность защиты от фишинга, можно создать настраиваемые политики защиты от фишинга с более строгими настройками, которые применяются к конкретным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="db6b3-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="db6b3-130">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="db6b3-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="db6b3-131">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="db6b3-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="db6b3-132">Чтобы перейти непосредственно на страницу **anti-phishing,** используйте <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="db6b3-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="db6b3-133">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="db6b3-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="db6b3-134">Вы не можете управлять политиками защиты от фишинга в автономных EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db6b3-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="db6b3-135">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="db6b3-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="db6b3-136">Чтобы добавить, изменить и удалить политики защиты от фишинга, необходимо  быть членом групп ролей администратора организации или **администратора** безопасности.</span><span class="sxs-lookup"><span data-stu-id="db6b3-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="db6b3-137">Для доступа только для чтения к политикам защиты от фишинга необходимо быть членом групп ролей **Global Reader** или **Security Reader.** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db6b3-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="db6b3-138">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="db6b3-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="db6b3-139">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="db6b3-139">**Notes**:</span></span>

  - <span data-ttu-id="db6b3-140">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db6b3-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="db6b3-141">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="db6b3-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="db6b3-142">Группа **ролей только для** организации просмотра в Exchange [Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции. <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db6b3-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="db6b3-143"><sup>\*</sup> В Центре & безопасности доступ только для чтения позволяет пользователям просматривать параметры настраиваемой политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="db6b3-143"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="db6b3-144">Пользователи, только для чтения, не могут видеть параметры в политике защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="db6b3-144">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="db6b3-145">Чтобы создать и изменить политики защиты от фишинга в автономных EOP, необходимо сделать что-то, что требует _гидратации_ для клиента.</span><span class="sxs-lookup"><span data-stu-id="db6b3-145">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="db6b3-146">Например, в центре администрирования Exchange (EAC) можно перейти на вкладку **Permissions,** выбрать существующую группу ролей, щелкнуть значок **Edit** Edit и удалить роль (которую вы в конечном счете ![ добавите). ](../../media/ITPro-EAC-EditIcon.png)</span><span class="sxs-lookup"><span data-stu-id="db6b3-146">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="db6b3-147">Если клиент никогда не был гидратирован, вы получите диалоговое окно с именем **Update Organization Settings** с планку прогресса, которая должна успешно завершиться.</span><span class="sxs-lookup"><span data-stu-id="db6b3-147">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="db6b3-148">Дополнительные сведения о гидратации см. в комлете [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) (который не доступен в автономных центрах EOP PowerShell или в Центре & безопасности).</span><span class="sxs-lookup"><span data-stu-id="db6b3-148">For more information about hydration, see the [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="db6b3-149">Рекомендуемые параметры для политик защиты от фишинга см. в нашем сайте [параметры](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)политики защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="db6b3-149">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="db6b3-150">Разрешить до 30 минут для обновленной политики, которая будет применяться.</span><span class="sxs-lookup"><span data-stu-id="db6b3-150">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="db6b3-151">Сведения о том, где политики защиты от фишинга применяются в конвейере фильтрации, см. в рублях [Order и precedence of email protection.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="db6b3-151">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="db6b3-152">Используйте Центр & безопасности для создания политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-152">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="db6b3-153">Создание настраиваемой политики защиты от фишинга в Центре & безопасности создает правило защиты от фишинга и связанную с ним политику защиты от фишинга, одновременно используя одно и то же имя для обоих.</span><span class="sxs-lookup"><span data-stu-id="db6b3-153">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="db6b3-154">При создании политики защиты от фишинга можно указать только имя политики, описание и фильтр получателя, который определяет, к кому применяется политика.</span><span class="sxs-lookup"><span data-stu-id="db6b3-154">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="db6b3-155">После создания политики можно изменить политику, чтобы изменить или просмотреть параметры защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="db6b3-155">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="db6b3-156">В Центре & безопасности перейдите в **центр по** борьбе с фишингом политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="db6b3-157">На странице **Anti-phishing** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="db6b3-157">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="db6b3-158">Откроется мастер политики защиты от **фишинга.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-158">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="db6b3-159">На странице **Имя политики** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="db6b3-159">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="db6b3-160">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="db6b3-160">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="db6b3-161">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="db6b3-161">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="db6b3-162">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="db6b3-162">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="db6b3-163">На странице **Applied to** page, которая появится, определите внутренних получателей, к которые применяется политика.</span><span class="sxs-lookup"><span data-stu-id="db6b3-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="db6b3-164">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="db6b3-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="db6b3-165">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="db6b3-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="db6b3-166">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="db6b3-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="db6b3-167">Нажмите **кнопку Добавить условие**.</span><span class="sxs-lookup"><span data-stu-id="db6b3-167">Click **Add a condition**.</span></span> <span data-ttu-id="db6b3-168">В отсеве, которое появится, выберите условие в **applied, если**:</span><span class="sxs-lookup"><span data-stu-id="db6b3-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="db6b3-169">**Получатель:** указывает один или несколько почтовых ящиков, пользователей почты или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="db6b3-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="db6b3-170">**Получатель является членом**: указывает одну или несколько групп в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="db6b3-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="db6b3-171">**Домен получателя**: Указывает получателей в одном или нескольких настроенных принятых доменов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="db6b3-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="db6b3-172">После выбора условия в любом из этих поле появится соответствующее **отсев.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="db6b3-173">Щелкните в поле и прокрутите список значений для выбора.</span><span class="sxs-lookup"><span data-stu-id="db6b3-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="db6b3-174">Щелкните в поле и начните печатать, чтобы отфильтровать список и выбрать значение.</span><span class="sxs-lookup"><span data-stu-id="db6b3-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="db6b3-175">Чтобы добавить дополнительные значения, щелкните в пустой области в поле.</span><span class="sxs-lookup"><span data-stu-id="db6b3-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="db6b3-176">Чтобы удалить отдельные записи, **нажмите кнопку Удалить** ![ значок Удалить ](../../media/scc-remove-icon.png) значение.</span><span class="sxs-lookup"><span data-stu-id="db6b3-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="db6b3-177">Чтобы удалить все условие, нажмите **кнопку Удалить значок Удалить** ![ в ](../../media/scc-remove-icon.png) состоянии.</span><span class="sxs-lookup"><span data-stu-id="db6b3-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="db6b3-178">Чтобы добавить дополнительное условие, нажмите **кнопку Добавить условие** и выберите оставшееся значение **в applied if**.</span><span class="sxs-lookup"><span data-stu-id="db6b3-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="db6b3-179">Чтобы добавить исключения, нажмите **кнопку Добавить условие** и выберите исключение в соответствии **с исключением, если**.</span><span class="sxs-lookup"><span data-stu-id="db6b3-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="db6b3-180">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="db6b3-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="db6b3-181">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="db6b3-181">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="db6b3-182">На странице **Обзор параметров,** которая отображается, просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="db6b3-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="db6b3-183">Чтобы изменить его, можно нажать **кнопку Изменить** каждый параметр.</span><span class="sxs-lookup"><span data-stu-id="db6b3-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="db6b3-184">По завершению нажмите кнопку **Создать эту политику.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-184">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="db6b3-185">Нажмите **кнопку ОК** в диалоговом окте подтверждения, который отображается.</span><span class="sxs-lookup"><span data-stu-id="db6b3-185">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="db6b3-186">После создания политики защиты от фишинга с помощью этих общих параметров политики используйте инструкции в следующем разделе для настройки параметров защиты в политике.</span><span class="sxs-lookup"><span data-stu-id="db6b3-186">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="db6b3-187">Используйте Центр & безопасности для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-187">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="db6b3-188">Чтобы изменить политики защиты от фишинга, используйте следующие процедуры: созданную новую политику или уже настроенные политики.</span><span class="sxs-lookup"><span data-stu-id="db6b3-188">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="db6b3-189">Если вы еще не существует, откройте центр & безопасности и  перейдите к политике управления угрозами по борьбе \>  \> **с фишингом.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-189">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="db6b3-190">Выберите настраиваемую политику защиты от фишинга, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="db6b3-190">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="db6b3-191">Если он уже выбран, вытаницу его и выберите еще раз.</span><span class="sxs-lookup"><span data-stu-id="db6b3-191">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="db6b3-192">Появится **флааут Edit \<name\> your policy.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-192">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="db6b3-193">**Щелкнув кнопку Изменить** в любом разделе, вы сможете получить доступ к настройкам в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="db6b3-193">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="db6b3-194">В порядке появления разделов представлены следующие действия, но они не являются последовательной (разделы можно выбрать и изменить в любом порядке).</span><span class="sxs-lookup"><span data-stu-id="db6b3-194">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="db6b3-195">После нажатия кнопки Изменить в разделе доступные параметры представлены в формате мастера, но вы можете перейти на страницы в  любом  порядке, и вы можете щелкнуть Сохранить на любой странице (или Отмена или закрыть закрыть значок, чтобы вернуться на страницу   Изменить ![ ](../../media/scc-remove-icon.png) **\<name\>** политику (вам не требуется посещать последнюю страницу мастера, чтобы сохранить или оставить).</span><span class="sxs-lookup"><span data-stu-id="db6b3-195">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="db6b3-196">**Параметр политики.** **Нажмите кнопку Изменить,** чтобы изменить те же параметры, которые были доступны при создании [политики](#use-the-security--compliance-center-to-create-anti-phishing-policies) в предыдущем разделе:</span><span class="sxs-lookup"><span data-stu-id="db6b3-196">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="db6b3-197">**Название**</span><span class="sxs-lookup"><span data-stu-id="db6b3-197">**Name**</span></span>
   - <span data-ttu-id="db6b3-198">**Описание**</span><span class="sxs-lookup"><span data-stu-id="db6b3-198">**Description**</span></span>
   - <span data-ttu-id="db6b3-199">**Применяется к**</span><span class="sxs-lookup"><span data-stu-id="db6b3-199">**Applied to**</span></span>
   - <span data-ttu-id="db6b3-200">**Просмотр параметров**</span><span class="sxs-lookup"><span data-stu-id="db6b3-200">**Review your settings**</span></span>

   <span data-ttu-id="db6b3-201">По завершению щелкните **Сохранить на** любой странице.</span><span class="sxs-lookup"><span data-stu-id="db6b3-201">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="db6b3-202">**Spoof**: Нажмите кнопку **Изменить,** чтобы включить или отключить подмену сведений, включить неавентированную идентификацию отправителей в Outlook или отключить, а также настроить действие для применения к сообщениям от заблокированных поддельных отправителей.</span><span class="sxs-lookup"><span data-stu-id="db6b3-202">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="db6b3-203">Дополнительные сведения см. в [параметрах Spoof в политиках защиты от фишинга.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="db6b3-203">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="db6b3-204">Обратите внимание, что эти же параметры также доступны в политиках по борьбе с фишингом в Defender for Office 365.</span><span class="sxs-lookup"><span data-stu-id="db6b3-204">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="db6b3-205">**Параметры фильтра спуфинга:** значение по умолчанию **в режиме On,** и мы рекомендуем оставить его.</span><span class="sxs-lookup"><span data-stu-id="db6b3-205">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="db6b3-206">Чтобы отключить его, сдвиньте переключить его на **off.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-206">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="db6b3-207">Дополнительные сведения см. в [перенастройке сведений о подмене в EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="db6b3-207">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="db6b3-208">Вам не нужно отключать защиту от спуфинга, если запись MX не указывая на Microsoft 365; Вместо этого вы включаете усиленную фильтрацию соединителя.</span><span class="sxs-lookup"><span data-stu-id="db6b3-208">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="db6b3-209">Инструкции см. в [расширенной фильтрации соединитений в Exchange Online.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="db6b3-209">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="db6b3-210">**Включить неавентированные функции отправитель:** значение по умолчанию **на**.</span><span class="sxs-lookup"><span data-stu-id="db6b3-210">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="db6b3-211">Чтобы отключить его, сдвиньте переключить его на **off.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-211">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="db6b3-212">**Действия:** укажите действие для принятия сообщений, которые не подавлили сведения о подмене:</span><span class="sxs-lookup"><span data-stu-id="db6b3-212">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="db6b3-213">**Если электронная почта отправляется кем-то,** кому запрещено подменять домен:</span><span class="sxs-lookup"><span data-stu-id="db6b3-213">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="db6b3-214">**Перемещение сообщения в папки нежелательной почты получателей**</span><span class="sxs-lookup"><span data-stu-id="db6b3-214">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="db6b3-215">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="db6b3-215">**Quarantine the message**</span></span>

   - <span data-ttu-id="db6b3-216">**Просмотрите параметры.** Вместо нажатия на каждый отдельный шаг параметры отображаются в сводке.</span><span class="sxs-lookup"><span data-stu-id="db6b3-216">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="db6b3-217">Чтобы вернуться на соответствующую страницу, нажмите кнопку **Изменить** в каждом разделе.</span><span class="sxs-lookup"><span data-stu-id="db6b3-217">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="db6b3-218">Вы можете переключать следующие параметры **На** или **Выключение** непосредственно на этой странице:</span><span class="sxs-lookup"><span data-stu-id="db6b3-218">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="db6b3-219">**Включить защиту от непопуфинга**</span><span class="sxs-lookup"><span data-stu-id="db6b3-219">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="db6b3-220">**Включить функцию unauthenticated Sender**</span><span class="sxs-lookup"><span data-stu-id="db6b3-220">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="db6b3-221">По завершению щелкните **Сохранить на** любой странице.</span><span class="sxs-lookup"><span data-stu-id="db6b3-221">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="db6b3-222">Возвращаясь на **страницу Изменить политику, \<Name\>** просмотрите параметры и нажмите **кнопку Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="db6b3-222">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="db6b3-223">Используйте Центр & безопасности для изменения политики защиты от фишинга по умолчанию</span><span class="sxs-lookup"><span data-stu-id="db6b3-223">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="db6b3-224">Политика защиты от фишинга по умолчанию называется Office365 AntiPhish Default и не появляется в списке политик.</span><span class="sxs-lookup"><span data-stu-id="db6b3-224">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="db6b3-225">Чтобы изменить политику защиты от фишинга по умолчанию, необходимо сделать следующие действия:</span><span class="sxs-lookup"><span data-stu-id="db6b3-225">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="db6b3-226">В Центре & безопасности перейдите в **центр по** борьбе с фишингом политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="db6b3-227">На странице **Anti-phishing** нажмите кнопку **Политика по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="db6b3-227">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="db6b3-228">Появится **страница "Изменить политику Office365 по** умолчанию".</span><span class="sxs-lookup"><span data-stu-id="db6b3-228">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="db6b3-229">Доступны следующие разделы, содержащие идентичные параметры при изменении [настраиваемой политики.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="db6b3-229">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="db6b3-230">**Олицетворение**</span><span class="sxs-lookup"><span data-stu-id="db6b3-230">**Impersonation**</span></span>
   - <span data-ttu-id="db6b3-231">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="db6b3-231">**Spoof**</span></span>
   - <span data-ttu-id="db6b3-232">**Дополнительные параметры**</span><span class="sxs-lookup"><span data-stu-id="db6b3-232">**Advanced settings**</span></span>

   <span data-ttu-id="db6b3-233">При изменении политики по умолчанию недоступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="db6b3-233">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="db6b3-234">Вы можете  увидеть раздел параметр политики и значения, но нет ссылки **Изменить,** поэтому вы не можете изменить параметры (имя политики, описание и к кому применяется политика (она применяется ко всем получателям)).</span><span class="sxs-lookup"><span data-stu-id="db6b3-234">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="db6b3-235">Вы не можете удалить политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="db6b3-235">You can't delete the default policy.</span></span>
   - <span data-ttu-id="db6b3-236">Нельзя изменить приоритет политики по умолчанию (она всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="db6b3-236">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="db6b3-237">На странице **Изменить политику Office365 По** умолчанию просмотрите параметры и нажмите **кнопку Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="db6b3-237">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="db6b3-238">Включить или отключить настраиваемые политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-238">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="db6b3-239">В Центре & безопасности перейдите в **центр по** борьбе с фишингом политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="db6b3-240">Обратите внимание на значение в **столбце Состояние:**</span><span class="sxs-lookup"><span data-stu-id="db6b3-240">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="db6b3-241">Чтобы отключить политику,  сдвиньте переключеть переключеть.</span><span class="sxs-lookup"><span data-stu-id="db6b3-241">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="db6b3-242">Чтобы включить политику, сдвиньте перемежок на **on.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-242">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="db6b3-243">Вы не можете отключить политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="db6b3-243">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="db6b3-244">Установите приоритет настраиваемой политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-244">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="db6b3-245">По умолчанию политикам защиты от фишинга предоставляется приоритет, основанный на порядке, в который они были созданы (более новые политики имеют более низкий приоритет по сравнению с более старыми политиками).</span><span class="sxs-lookup"><span data-stu-id="db6b3-245">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="db6b3-246">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="db6b3-246">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="db6b3-247">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="db6b3-247">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="db6b3-248">Дополнительные сведения о приоритетах, а также оценке и применении нескольких политик см. в статье [Порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="db6b3-248">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="db6b3-249">Пользовательские политики защиты от фишинга отображаются в порядке их обработки (первая политика имеет значение **Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="db6b3-249">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="db6b3-250">Политика защиты от фишинга по умолчанию с именем Office365 AntiPhish Default имеет настраиваемое значение приоритета **Самое** низкое, и изменить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="db6b3-250">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="db6b3-251">**Примечание.** В Центре & безопасности можно изменить приоритет политики защиты от фишинга только после ее создания.</span><span class="sxs-lookup"><span data-stu-id="db6b3-251">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="db6b3-252">В PowerShell можно переопредить приоритет по умолчанию при создании правила защиты от фишинга (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="db6b3-252">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="db6b3-253">Чтобы изменить приоритет политики, нажмите  кнопку Увеличение  приоритета или Уменьшение приоритета в свойствах политики (вы не можете напрямую изменить номер **Priority** в Центре & соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="db6b3-253">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="db6b3-254">Изменение приоритета политики имеет смысл только при нескольких политиках.</span><span class="sxs-lookup"><span data-stu-id="db6b3-254">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="db6b3-255">В Центре & безопасности перейдите в  центр политики управления угрозами \>  \> **ATP по борьбе с фишингом.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-255">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="db6b3-256">Выберите политику, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="db6b3-256">Select the policy that you want to modify.</span></span> <span data-ttu-id="db6b3-257">Если он уже выбран, вытаницу его и выберите еще раз.</span><span class="sxs-lookup"><span data-stu-id="db6b3-257">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="db6b3-258">Появится **флааут Edit \<name\> your policy.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-258">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="db6b3-259">Настраиваемая политика защиты от фишинга со значением **Приоритет** **0** имеет только доступную кнопку **Приоритет уменьшения.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-259">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="db6b3-260">Настраиваемая политика защиты от  фишинга с наименьшим значением приоритета (например, **3)** имеет только доступную кнопку **Увеличение приоритета.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-260">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="db6b3-261">Если у вас есть три или более настраиваемые политики защиты от фишинга, политики между самыми  высокими и самыми низкими значениями приоритетов имеют доступные кнопки **"Увеличение** приоритета" и "Уменьшение приоритетов".</span><span class="sxs-lookup"><span data-stu-id="db6b3-261">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="db6b3-262">Щелкните **Увеличить приоритет или** уменьшить **приоритет,** чтобы изменить **значение Priority.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-262">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="db6b3-263">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="db6b3-263">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="db6b3-264">Используйте Центр & безопасности для просмотра политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-264">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="db6b3-265">В Центре & безопасности и перейдите в **центр** по борьбе с фишингом политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-265">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="db6b3-266">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="db6b3-266">Do one of the following steps:</span></span>

   - <span data-ttu-id="db6b3-267">Выберите настраиваемую политику защиты от фишинга, которую необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="db6b3-267">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="db6b3-268">Если он уже выбран, вытаницу его и выберите еще раз.</span><span class="sxs-lookup"><span data-stu-id="db6b3-268">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="db6b3-269">Щелкните **политику по умолчанию,** чтобы просмотреть политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="db6b3-269">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="db6b3-270">Появится **флаевка \<name\>** "Изменить политику", в которой можно просмотреть параметры и значения.</span><span class="sxs-lookup"><span data-stu-id="db6b3-270">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="db6b3-271">Используйте Центр & безопасности для удаления политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-271">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="db6b3-272">В Центре & безопасности перейдите в **центр по** борьбе с фишингом политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-272">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="db6b3-273">Выберите политику, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="db6b3-273">Select the policy that you want to remove.</span></span> <span data-ttu-id="db6b3-274">Если он уже выбран, вытаницу его и выберите еще раз.</span><span class="sxs-lookup"><span data-stu-id="db6b3-274">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="db6b3-275">В **появится \<name\> флажок Изменить** политику, нажмите кнопку **Удалить** политику, а затем нажмите **кнопку Да** в диалоговом окте предупреждения, который появится.</span><span class="sxs-lookup"><span data-stu-id="db6b3-275">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="db6b3-276">Политику по умолчанию удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="db6b3-276">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="db6b3-277">Используйте Exchange Online PowerShell для настройки политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-277">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="db6b3-278">Как описано выше, политика защиты от фишинга состоит из политики защиты от фишинга и правила защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="db6b3-278">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="db6b3-279">В Exchange Online PowerShell разница между политиками защиты от фишинга и правилами защиты от фишинга очевидна.</span><span class="sxs-lookup"><span data-stu-id="db6b3-279">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="db6b3-280">Вы управляете политиками защиты от фишинга с помощью кодлетов **\* -AntiPhishPolicy** и управляете правилами защиты от фишинга с помощью cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-280">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="db6b3-281">В PowerShell сначала создается политика защиты от фишинга, а затем создается правило защиты от фишинга, которое определяет политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="db6b3-281">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="db6b3-282">В PowerShell параметры политики защиты от фишинга и правила защиты от фишинга изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="db6b3-282">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="db6b3-283">При удалении политики защиты от фишинга из PowerShell соответствующее правило не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="db6b3-283">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="db6b3-284">Следующие процедуры PowerShell недоступны в автономных организациях EOP с помощью Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db6b3-284">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="db6b3-285">Использование PowerShell для создания политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-285">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="db6b3-286">Создание политики защиты от фишинга в PowerShell — это двухшаговый процесс:</span><span class="sxs-lookup"><span data-stu-id="db6b3-286">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="db6b3-287">Создание политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="db6b3-287">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="db6b3-288">Создайте правило защиты от фишинга, которое указывает политику защиты от фишинга, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="db6b3-288">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="db6b3-289">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-289">**Notes**:</span></span>

- <span data-ttu-id="db6b3-290">Вы можете создать новое правило защиты от фишинга и назначить ему существующую, неассоциированную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="db6b3-290">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="db6b3-291">Правило защиты от фишинга не может быть связано с одной политикой защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="db6b3-291">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="db6b3-292">Вы можете настроить следующие параметры для новых политик защиты от фишинга в PowerShell, недоступных в Центре обеспечения безопасности & до момента создания политики:</span><span class="sxs-lookup"><span data-stu-id="db6b3-292">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="db6b3-293">Создайте новую политику как отключенную _(включена_ `$false` в **кодлете New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="db6b3-293">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="db6b3-294">Задай приоритет политики во время создания _(приоритет)_ в _\<Number\>_ **комлете New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-294">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="db6b3-295">Новая политика защиты от фишинга, которую вы создаете в PowerShell, не отображается в Центре & безопасности, пока не назначите политику правилу защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="db6b3-295">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="db6b3-296">Шаг 1. Использование PowerShell для создания политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-296">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="db6b3-297">Чтобы создать политику защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="db6b3-297">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="db6b3-298">В этом примере создается политика защиты от фишинга с именем Research Quarantine со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="db6b3-298">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="db6b3-299">Описание: Политика отдела исследований.</span><span class="sxs-lookup"><span data-stu-id="db6b3-299">The description is: Research department policy.</span></span>
- <span data-ttu-id="db6b3-300">Изменяет действие по умолчанию для подмены на карантин.</span><span class="sxs-lookup"><span data-stu-id="db6b3-300">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="db6b3-301">Подробные сведения о синтаксисе и параметрах см. в [обзоре New-AntiPhishPolicy.](/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="db6b3-301">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="db6b3-302">Шаг 2. Использование PowerShell для создания правила защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-302">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="db6b3-303">Чтобы создать правило защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="db6b3-303">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="db6b3-304">В этом примере создается правило защиты от фишинга с именем Research Department со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="db6b3-304">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="db6b3-305">Это правило связано с политикой защиты от фишинга с именем Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="db6b3-305">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="db6b3-306">Правило применяется к членам группы "Research Department".</span><span class="sxs-lookup"><span data-stu-id="db6b3-306">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="db6b3-307">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="db6b3-307">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="db6b3-308">Подробные сведения о синтаксисе и параметрах см. [в обзоре New-AntiPhishRule.](/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="db6b3-308">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="db6b3-309">Использование PowerShell для просмотра политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-309">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="db6b3-310">Чтобы просмотреть существующие политики защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="db6b3-310">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="db6b3-311">В этом примере возвращается сводный список всех политик защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="db6b3-311">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="db6b3-312">В этом примере возвращаются все значения свойств для политики защиты от фишинга с именем Executives.</span><span class="sxs-lookup"><span data-stu-id="db6b3-312">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="db6b3-313">Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-AntiPhishPolicy.](/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="db6b3-313">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="db6b3-314">Использование PowerShell для просмотра правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-314">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="db6b3-315">Чтобы просмотреть существующие правила защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="db6b3-315">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="db6b3-316">В этом примере возвращается сводный список всех правил по борьбе с фишингом вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="db6b3-316">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="db6b3-317">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="db6b3-317">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="db6b3-318">В этом примере возвращаются все значения свойств для правила защиты от фишинга с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="db6b3-318">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="db6b3-319">Подробные сведения о синтаксисе и параметрах см. в [ссылке Get-AntiPhishRule.](/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="db6b3-319">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="db6b3-320">Использование PowerShell для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-320">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="db6b3-321">Кроме следующих элементов, при изменении политики защиты от фишинга в PowerShell доступны те же параметры, что и при создании политики, описанной в шаге [1: Использование PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) для создания политики защиты от фишинга ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="db6b3-321">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="db6b3-322">Переключатель _MakeDefault,_ который превращает указанную политику в политику по  умолчанию (применяется для всех, всегда самый низкий приоритет, и вы не можете удалить ее) доступен только при изменении политики защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db6b3-322">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="db6b3-323">Нельзя переименовать политику защиты от фишинга (в **кодлете Set-AntiPhishPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="db6b3-323">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="db6b3-324">При переименовании политики защиты от фишинга в Центре & безопасности переименуется только правило защиты от _фишинга._</span><span class="sxs-lookup"><span data-stu-id="db6b3-324">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="db6b3-325">Чтобы изменить политику защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="db6b3-325">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="db6b3-326">Подробные сведения о синтаксисе и параметрах см. в [инструкции Set-AntiPhishPolicy.](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="db6b3-326">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="db6b3-327">Использование PowerShell для изменения правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-327">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="db6b3-328">Единственным параметром, недоступным при изменении правила защиты от фишинга в PowerShell, является параметр _Включен,_ который позволяет создать правило отключения.</span><span class="sxs-lookup"><span data-stu-id="db6b3-328">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="db6b3-329">Чтобы включить или отключить существующие правила защиты от фишинга, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="db6b3-329">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="db6b3-330">В противном случае те же параметры доступны при создании правила, описанного в разделе [Шаг 2: Использование PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) для создания раздела правил по борьбе с фишингом ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="db6b3-330">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="db6b3-331">Чтобы изменить правило защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="db6b3-331">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="db6b3-332">Подробные сведения о синтаксисе и параметрах см. в [инструкции Set-AntiPhishRule.](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="db6b3-332">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="db6b3-333">Использование PowerShell, чтобы включить или отключить правила защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-333">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="db6b3-334">Включение или отключение правила защиты от фишинга в PowerShell включает или отключает всю политику защиты от фишинга (правило защиты от фишинга и назначенную политику защиты от фишинга).</span><span class="sxs-lookup"><span data-stu-id="db6b3-334">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="db6b3-335">Вы не можете включить или отключить политику защиты от фишинга по умолчанию (она всегда применяется к всем получателям).</span><span class="sxs-lookup"><span data-stu-id="db6b3-335">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="db6b3-336">Чтобы включить или отключить правило защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="db6b3-336">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="db6b3-337">В этом примере отключает правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="db6b3-337">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="db6b3-338">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="db6b3-338">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="db6b3-339">Подробные сведения о синтаксисе и параметрах см. в [сводке Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) и [Disable-AntiPhishRule.](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="db6b3-339">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="db6b3-340">Использование PowerShell для набора приоритета правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-340">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="db6b3-341">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="db6b3-341">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="db6b3-342">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="db6b3-342">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="db6b3-343">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="db6b3-343">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="db6b3-344">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="db6b3-344">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="db6b3-345">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="db6b3-345">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="db6b3-346">Чтобы установить приоритет правила защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="db6b3-346">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="db6b3-p138">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="db6b3-p138">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="db6b3-349">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="db6b3-349">**Notes**:</span></span>

- <span data-ttu-id="db6b3-350">Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в **комлете New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-350">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="db6b3-351">Политика защиты от фишинга по умолчанию не имеет соответствующего правила по борьбе с фишингом, и всегда имеет неоплаченное значение приоритета **Самое низкое.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-351">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="db6b3-352">Использование PowerShell для удаления политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-352">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="db6b3-353">При удалении политики защиты от фишинга с помощью PowerShell соответствующее правило по борьбе с фишингом не удаляется.</span><span class="sxs-lookup"><span data-stu-id="db6b3-353">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="db6b3-354">Чтобы удалить политику защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="db6b3-354">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="db6b3-355">В этом примере удаляется политика защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="db6b3-355">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="db6b3-356">Подробные сведения о синтаксисе и параметрах см. в [обзоре Remove-AntiPhishPolicy.](/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="db6b3-356">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="db6b3-357">Использование PowerShell для удаления правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="db6b3-357">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="db6b3-358">При удалении правила защиты от фишинга с помощью PowerShell соответствующая политика защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="db6b3-358">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="db6b3-359">Чтобы удалить правило защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="db6b3-359">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="db6b3-360">В этом примере удаляется правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="db6b3-360">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="db6b3-361">Подробные сведения о синтаксисе и параметрах см. в [инструкции Remove-AntiPhishRule.](/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="db6b3-361">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="db6b3-362">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="db6b3-362">How do you know these procedures worked?</span></span>

<span data-ttu-id="db6b3-363">Чтобы убедиться, что политики защиты от фишинга успешно настроены в Microsoft Defender для Office 365, необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="db6b3-363">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="db6b3-364">В Центре & безопасности перейдите в **центр по** борьбе с фишингом политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-364">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="db6b3-365">Проверка списка политик, их значений **состояния** и **их значений приоритета.**</span><span class="sxs-lookup"><span data-stu-id="db6b3-365">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="db6b3-366">Чтобы просмотреть дополнительные сведения, необходимо сделать любой из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="db6b3-366">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="db6b3-367">Выберите политику из списка и просмотреть сведения в вылете.</span><span class="sxs-lookup"><span data-stu-id="db6b3-367">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="db6b3-368">Щелкните **политику по умолчанию** и просмотреть сведения в вылете.</span><span class="sxs-lookup"><span data-stu-id="db6b3-368">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="db6b3-369">В Exchange Online PowerShell замените имя политики или правила, запустите следующую команду и проверьте \<Name\> параметры:</span><span class="sxs-lookup"><span data-stu-id="db6b3-369">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```