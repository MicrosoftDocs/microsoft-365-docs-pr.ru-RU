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
ms.openlocfilehash: bc3c15d2a652e9acd3407ecb91fc99b7ef295c7e
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537923"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="e6aac-103">Настройка политик защиты от фишинга в EOP</span><span class="sxs-lookup"><span data-stu-id="e6aac-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e6aac-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="e6aac-104">**Applies to**</span></span>
- [<span data-ttu-id="e6aac-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e6aac-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="e6aac-106">В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без Exchange Online почтовых ящиков по умолчанию существует политика защиты от фишинга, которая содержит ограниченное количество функций защиты от спуфинга, которые включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6aac-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="e6aac-107">Дополнительные сведения см. в [параметрах Spoof в политиках защиты от фишинга.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="e6aac-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="e6aac-108">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6aac-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="e6aac-109">Для большей детализации можно также создать настраиваемые политики защиты от фишинга, применимые к определенным пользователям, группам или доменам в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e6aac-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="e6aac-110">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="e6aac-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="e6aac-111">Организации с Exchange Online почтовыми ящиками могут настраивать политики защиты от фишинга в Центре & безопасности или в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6aac-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="e6aac-112">Автономные организации EOP могут использовать только Центр & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="e6aac-112">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="e6aac-113">Сведения о создании и изменении более продвинутых политик защиты от фишинга в Microsoft Defender для Office 365, доступных в Defender для Office 365, см. в руб. Настройка политик защиты от фишинга в [Microsoft Defender](configure-atp-anti-phishing-policies.md)для Office 365 .</span><span class="sxs-lookup"><span data-stu-id="e6aac-113">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="e6aac-114">Основные элементы политики защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="e6aac-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="e6aac-115">**Политика защиты от фишинга:** указывает средства защиты от фишинга, чтобы включить или отключить, а также действия по применении параметров.</span><span class="sxs-lookup"><span data-stu-id="e6aac-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="e6aac-116">**Правило защиты от фишинга:** указывает фильтры приоритета и получателей (к кому применяется политика) для политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="e6aac-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="e6aac-117">Разница между этими двумя элементами не очевидна при управлении политиками защиты от фишинга в Центре & безопасности:</span><span class="sxs-lookup"><span data-stu-id="e6aac-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="e6aac-118">При создании политики защиты от фишинга создается правило защиты от фишинга и связанная с ним политика защиты от фишинга, используя одно и то же имя для обоих.</span><span class="sxs-lookup"><span data-stu-id="e6aac-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="e6aac-119">При изменении политики защиты от фишинга параметры, связанные с именем, приоритетом, включенной или отключенной, а также фильтры получателей изменяют правило защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="e6aac-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="e6aac-120">Все остальные параметры изменяют связанную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="e6aac-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="e6aac-121">При удалении политики защиты от фишинга правило защиты от фишинга и связанная с ним политика защиты от фишинга удаляются.</span><span class="sxs-lookup"><span data-stu-id="e6aac-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="e6aac-122">В Exchange Online PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="e6aac-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="e6aac-123">Дополнительные сведения см. в [разделе Использование Exchange Online PowerShell для](#use-exchange-online-powershell-to-configure-anti-phishing-policies) настройки политики защиты от фишинга в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e6aac-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="e6aac-124">Каждая организация имеет встроенную политику защиты от фишинга с именем Office365 AntiPhish Default, которая имеет эти свойства:</span><span class="sxs-lookup"><span data-stu-id="e6aac-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="e6aac-125">Политика применяется к всем получателям в организации, несмотря на отсутствие правила защиты от фишинга (фильтры получателей), связанного с политикой.</span><span class="sxs-lookup"><span data-stu-id="e6aac-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="e6aac-126">Для политики задано специальное значение приоритета **Самый низкий**, которое невозможно изменить (эта политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="e6aac-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="e6aac-127">Все созданные специальные политики всегда имеют более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="e6aac-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="e6aac-128">Эта политика является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.</span><span class="sxs-lookup"><span data-stu-id="e6aac-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="e6aac-129">Чтобы повысить эффективность защиты от фишинга, можно создать настраиваемые политики защиты от фишинга с более строгими настройками, которые применяются к конкретным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="e6aac-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e6aac-130">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="e6aac-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e6aac-131">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="e6aac-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e6aac-132">Чтобы перейти непосредственно на страницу **anti-phishing,** используйте <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="e6aac-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="e6aac-133">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e6aac-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="e6aac-134">Вы не можете управлять политиками защиты от фишинга в автономных EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6aac-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="e6aac-135">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="e6aac-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e6aac-136">Чтобы добавить, изменить и удалить политики защиты от фишинга, необходимо  быть членом групп ролей администратора организации или **администратора** безопасности.</span><span class="sxs-lookup"><span data-stu-id="e6aac-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="e6aac-137">Для доступа только для чтения к политикам защиты от фишинга необходимо быть членом групп ролей **Global Reader** или **Security Reader.** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6aac-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="e6aac-138">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="e6aac-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="e6aac-139">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="e6aac-139">**Notes**:</span></span>

  - <span data-ttu-id="e6aac-140">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6aac-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e6aac-141">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e6aac-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="e6aac-142">Группа **ролей только** для организации просмотра в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой <sup>\*</sup> функции.</span><span class="sxs-lookup"><span data-stu-id="e6aac-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="e6aac-143"><sup>\*</sup> В Центре & безопасности доступ только для чтения позволяет пользователям просматривать параметры настраиваемой политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="e6aac-143"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="e6aac-144">Пользователи, только для чтения, не могут видеть параметры в политике защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6aac-144">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="e6aac-145">Чтобы создать и изменить политики защиты от фишинга в автономных EOP, необходимо сделать что-то, что требует _гидратации_ для клиента.</span><span class="sxs-lookup"><span data-stu-id="e6aac-145">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="e6aac-146">Например, в центре администрирования Exchange (EAC) можно перейти на вкладку **Permissions,** выбрать существующую группу ролей, щелкнуть значок **Edit** Edit и удалить роль (которую вы в конечном счете добавите ![ ](../../media/ITPro-EAC-EditIcon.png) обратно).</span><span class="sxs-lookup"><span data-stu-id="e6aac-146">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="e6aac-147">Если клиент никогда не был увлажнён, вы получаете **диалоговое окно** с Параметры с помощью панели прогресса, которая должна успешно завершиться.</span><span class="sxs-lookup"><span data-stu-id="e6aac-147">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="e6aac-148">Дополнительные сведения о гидратации см. в комлете [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) (который не доступен в автономных центрах EOP PowerShell или в Центре & безопасности).</span><span class="sxs-lookup"><span data-stu-id="e6aac-148">For more information about hydration, see the [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="e6aac-149">Рекомендуемые параметры для политик защиты от фишинга см. в нашем сайте [параметры](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings)политики защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6aac-149">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="e6aac-150">Разрешить до 30 минут для обновленной политики, которая будет применяться.</span><span class="sxs-lookup"><span data-stu-id="e6aac-150">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="e6aac-151">Сведения о том, где политики защиты от фишинга применяются в конвейере фильтрации, см. в рублях [Order и precedence of email protection.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="e6aac-151">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="e6aac-152">Используйте Центр & безопасности для создания политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-152">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="e6aac-153">Создание настраиваемой политики защиты от фишинга в Центре & безопасности создает правило защиты от фишинга и связанную с ним политику защиты от фишинга, одновременно используя одно и то же имя для обоих.</span><span class="sxs-lookup"><span data-stu-id="e6aac-153">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="e6aac-154">При создании политики защиты от фишинга можно указать только имя политики, описание и фильтр получателя, который определяет, к кому применяется политика.</span><span class="sxs-lookup"><span data-stu-id="e6aac-154">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="e6aac-155">После создания политики можно изменить политику, чтобы изменить или просмотреть параметры защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6aac-155">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="e6aac-156">В Центре & безопасности перейдите в **центр по** борьбе с фишингом политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e6aac-157">На странице **Anti-phishing** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e6aac-157">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="e6aac-158">Откроется мастер политики защиты от **фишинга.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-158">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="e6aac-159">На странице **Имя политики** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e6aac-159">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="e6aac-160">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="e6aac-160">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="e6aac-161">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="e6aac-161">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="e6aac-162">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e6aac-162">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="e6aac-163">На странице **Applied to** page, которая появится, определите внутренних получателей, к которые применяется политика.</span><span class="sxs-lookup"><span data-stu-id="e6aac-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="e6aac-164">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="e6aac-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="e6aac-165">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="e6aac-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="e6aac-166">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="e6aac-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="e6aac-167">Нажмите **кнопку Добавить условие**.</span><span class="sxs-lookup"><span data-stu-id="e6aac-167">Click **Add a condition**.</span></span> <span data-ttu-id="e6aac-168">В отсеве, которое появится, выберите условие в **applied, если**:</span><span class="sxs-lookup"><span data-stu-id="e6aac-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="e6aac-169">**Получатель:** указывает один или несколько почтовых ящиков, пользователей почты или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="e6aac-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="e6aac-170">**Получатель является членом**: указывает одну или несколько групп в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e6aac-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="e6aac-171">**Домен получателя**: Указывает получателей в одном или нескольких настроенных принятых доменов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e6aac-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="e6aac-172">После выбора условия в любом из этих поле появится соответствующее **отсев.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="e6aac-173">Щелкните в поле и прокрутите список значений для выбора.</span><span class="sxs-lookup"><span data-stu-id="e6aac-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="e6aac-174">Щелкните в поле и начните печатать, чтобы отфильтровать список и выбрать значение.</span><span class="sxs-lookup"><span data-stu-id="e6aac-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="e6aac-175">Чтобы добавить дополнительные значения, щелкните в пустой области в поле.</span><span class="sxs-lookup"><span data-stu-id="e6aac-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="e6aac-176">Чтобы удалить отдельные записи, **нажмите кнопку Удалить** ![ значок Удалить ](../../media/scc-remove-icon.png) значение.</span><span class="sxs-lookup"><span data-stu-id="e6aac-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="e6aac-177">Чтобы удалить все условие, нажмите **кнопку Удалить значок Удалить** ![ в ](../../media/scc-remove-icon.png) состоянии.</span><span class="sxs-lookup"><span data-stu-id="e6aac-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="e6aac-178">Чтобы добавить дополнительное условие, нажмите **кнопку Добавить условие** и выберите оставшееся значение **в applied if**.</span><span class="sxs-lookup"><span data-stu-id="e6aac-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="e6aac-179">Чтобы добавить исключения, нажмите **кнопку Добавить условие** и выберите исключение в соответствии **с исключением, если**.</span><span class="sxs-lookup"><span data-stu-id="e6aac-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="e6aac-180">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="e6aac-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="e6aac-181">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e6aac-181">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="e6aac-182">На странице **Обзор параметров,** которая отображается, просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="e6aac-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="e6aac-183">Чтобы изменить его, можно нажать **кнопку Изменить** каждый параметр.</span><span class="sxs-lookup"><span data-stu-id="e6aac-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="e6aac-184">По завершению нажмите кнопку **Создать эту политику.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-184">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="e6aac-185">Нажмите **кнопку ОК** в диалоговом окте подтверждения, который отображается.</span><span class="sxs-lookup"><span data-stu-id="e6aac-185">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="e6aac-186">После создания политики защиты от фишинга с помощью этих общих параметров политики используйте инструкции в следующем разделе для настройки параметров защиты в политике.</span><span class="sxs-lookup"><span data-stu-id="e6aac-186">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="e6aac-187">Используйте Центр & безопасности для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-187">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="e6aac-188">Чтобы изменить политики защиты от фишинга, используйте следующие процедуры: созданную новую политику или уже настроенные политики.</span><span class="sxs-lookup"><span data-stu-id="e6aac-188">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="e6aac-189">Если вы еще не существует, откройте центр & безопасности и  перейдите к политике управления угрозами по борьбе \>  \> **с фишингом.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-189">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e6aac-190">Выберите настраиваемую политику защиты от фишинга, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="e6aac-190">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="e6aac-191">Если он уже выбран, вытаницу его и выберите еще раз.</span><span class="sxs-lookup"><span data-stu-id="e6aac-191">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="e6aac-192">Появится **флааут Edit \<name\> your policy.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-192">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="e6aac-193">**Щелкнув кнопку Изменить** в любом разделе, вы сможете получить доступ к настройкам в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e6aac-193">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="e6aac-194">В порядке появления разделов представлены следующие действия, но они не являются последовательной (разделы можно выбрать и изменить в любом порядке).</span><span class="sxs-lookup"><span data-stu-id="e6aac-194">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="e6aac-195">После нажатия кнопки Изменить в разделе доступные параметры представлены в формате мастера, но вы можете перейти на страницы в  любом  порядке, и вы можете щелкнуть Сохранить на любой странице (или Отмена или закрыть закрыть значок, чтобы вернуться на страницу   Изменить ![ ](../../media/scc-remove-icon.png) **\<name\>** политику (вам не требуется посещать последнюю страницу мастера, чтобы сохранить или оставить).</span><span class="sxs-lookup"><span data-stu-id="e6aac-195">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="e6aac-196">**Параметр политики.** **Нажмите кнопку Изменить,** чтобы изменить те же параметры, которые были доступны при создании [политики](#use-the-security--compliance-center-to-create-anti-phishing-policies) в предыдущем разделе:</span><span class="sxs-lookup"><span data-stu-id="e6aac-196">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="e6aac-197">**Название**</span><span class="sxs-lookup"><span data-stu-id="e6aac-197">**Name**</span></span>
   - <span data-ttu-id="e6aac-198">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e6aac-198">**Description**</span></span>
   - <span data-ttu-id="e6aac-199">**Применяется к**</span><span class="sxs-lookup"><span data-stu-id="e6aac-199">**Applied to**</span></span>
   - <span data-ttu-id="e6aac-200">**Проверка параметров**</span><span class="sxs-lookup"><span data-stu-id="e6aac-200">**Review your settings**</span></span>

   <span data-ttu-id="e6aac-201">По завершению щелкните **Сохранить на** любой странице.</span><span class="sxs-lookup"><span data-stu-id="e6aac-201">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="e6aac-202">**Spoof**: Нажмите кнопку **Изменить,** чтобы включить или отключить спуф-аналитику, включить неавентированную идентификацию отправителей в Outlook или отключить, а также настроить действие для применения к сообщениям от заблокированных подмененных отправителей.</span><span class="sxs-lookup"><span data-stu-id="e6aac-202">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="e6aac-203">Дополнительные сведения об этих параметрах см. в сообщении [Spoof settings in anti-phishing policies.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="e6aac-203">For more information about these settings, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="e6aac-204">Обратите внимание, что эти же параметры также доступны в политиках защиты от фишинга в Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="e6aac-204">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="e6aac-205">**Параметры фильтра spoofing:** Используйте параметр **Enable spoof intelligence?** чтобы включить или отключить подмену сведений.</span><span class="sxs-lookup"><span data-stu-id="e6aac-205">**Spoofing filter settings**: Use the **Enable spoof intelligence?** setting to turn spoof intelligence on or off.</span></span> <span data-ttu-id="e6aac-206">Значение по умолчанию **находится в режиме On,** и мы рекомендуем оставить его.</span><span class="sxs-lookup"><span data-stu-id="e6aac-206">The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="e6aac-207">Чтобы отключить его, сдвиньте очки до **Off** ![ Toggle ](../../media/scc-toggle-off.png) Off.</span><span class="sxs-lookup"><span data-stu-id="e6aac-207">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

     > [!NOTE]
     > <span data-ttu-id="e6aac-208">Вам не нужно отключать защиту от подмены, если запись MX не означает Microsoft 365; Вместо этого вы включаете усиленную фильтрацию соединителя.</span><span class="sxs-lookup"><span data-stu-id="e6aac-208">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="e6aac-209">Инструкции см. в [расширенной фильтрации соединители в Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="e6aac-209">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="e6aac-210">**Неавентированные параметры** отправитель: Вы можете настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e6aac-210">**Unauthenticated sender settings**: You can configure the following settings:</span></span>
     - <span data-ttu-id="e6aac-211">Включить неавентичный знак вопроса отправитель **(?) символ?**: Эти параметры добавляют знак вопроса к фотографии отправитель в поле From в Outlook,  если сообщение не проходит проверки SPF или DKIM и сообщение не проходит DMARC или композитную проверку подлинности [.](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="e6aac-211">**Enable unauthenticated sender question mark (?) symbol?**: This settings adds question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span> <span data-ttu-id="e6aac-212">Значение по умолчанию — **Включено**.</span><span class="sxs-lookup"><span data-stu-id="e6aac-212">The default value is **On**.</span></span> <span data-ttu-id="e6aac-213">Чтобы отключить его, сдвиньте очки до **Off** ![ Toggle ](../../media/scc-toggle-off.png) Off.</span><span class="sxs-lookup"><span data-stu-id="e6aac-213">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>
     - <span data-ttu-id="e6aac-214">**Включить тег "via"?**: Этот параметр добавляет тег через тег (chris@contoso.com через fabrikam.com) отличается от домена в подписи DKIM или **адреса MAIL FROM.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-214">**Enable "via" tag?**: This setting adds a via tag (chris@contoso.com via fabrikam.com) is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="e6aac-215">Значение по умолчанию — **Включено**.</span><span class="sxs-lookup"><span data-stu-id="e6aac-215">The default value is **On**.</span></span> <span data-ttu-id="e6aac-216">Чтобы отключить его, сдвиньте очки до **Off** ![ Toggle ](../../media/scc-toggle-off.png) Off.</span><span class="sxs-lookup"><span data-stu-id="e6aac-216">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="e6aac-217">**Действия:** Укажите действие для принятия сообщений от заблокированных поддельных отправителей:</span><span class="sxs-lookup"><span data-stu-id="e6aac-217">**Actions**: Specify the action to take on messages from blocked spoofed senders:</span></span>

     <span data-ttu-id="e6aac-218">**Если электронная почта отправляется кем-то,** кому запрещено подменять домен:</span><span class="sxs-lookup"><span data-stu-id="e6aac-218">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="e6aac-219">**Перемещение сообщения в папки нежелательной почты получателей**</span><span class="sxs-lookup"><span data-stu-id="e6aac-219">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="e6aac-220">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="e6aac-220">**Quarantine the message**</span></span>

   - <span data-ttu-id="e6aac-221">**Просмотрите параметры.** Вместо нажатия на каждый отдельный шаг параметры отображаются в сводке.</span><span class="sxs-lookup"><span data-stu-id="e6aac-221">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="e6aac-222">Чтобы вернуться на соответствующую страницу, нажмите кнопку **Изменить** в каждом разделе.</span><span class="sxs-lookup"><span data-stu-id="e6aac-222">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="e6aac-223">Вы можете переключать следующие параметры **На** или **Выключение** непосредственно на этой странице:</span><span class="sxs-lookup"><span data-stu-id="e6aac-223">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="e6aac-224">**Параметры фильтра Spoof**</span><span class="sxs-lookup"><span data-stu-id="e6aac-224">**Spoof filter settings**</span></span>
       - <span data-ttu-id="e6aac-225">**Неавентированные параметры отправитель**</span><span class="sxs-lookup"><span data-stu-id="e6aac-225">**Unauthenticated sender settings**</span></span>
       - <span data-ttu-id="e6aac-226">**Actions**</span><span class="sxs-lookup"><span data-stu-id="e6aac-226">**Actions**</span></span>

   <span data-ttu-id="e6aac-227">По завершению щелкните **Сохранить на** любой странице.</span><span class="sxs-lookup"><span data-stu-id="e6aac-227">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="e6aac-228">Возвращаясь на **страницу Изменить политику, \<Name\>** просмотрите параметры и нажмите **кнопку Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e6aac-228">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="e6aac-229">Используйте Центр & безопасности для изменения политики защиты от фишинга по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e6aac-229">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="e6aac-230">Политика защиты от фишинга по умолчанию называется Office365 AntiPhish Default и не появляется в списке политик.</span><span class="sxs-lookup"><span data-stu-id="e6aac-230">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="e6aac-231">Чтобы изменить политику защиты от фишинга по умолчанию, необходимо сделать следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e6aac-231">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="e6aac-232">В Центре & безопасности перейдите в **центр по** борьбе с фишингом политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-232">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e6aac-233">На странице **Anti-phishing** нажмите кнопку **Политика по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="e6aac-233">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="e6aac-234">Появится **страница "Изменить политику Office365 по** умолчанию".</span><span class="sxs-lookup"><span data-stu-id="e6aac-234">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="e6aac-235">Доступен только **раздел Spoof,** который содержит идентичные параметры при изменении [настраиваемой политики.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="e6aac-235">Only the **Spoof** section is available, which contains identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   <span data-ttu-id="e6aac-236">При изменении политики по умолчанию недоступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e6aac-236">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="e6aac-237">Вы можете  увидеть раздел параметр политики и значения, но нет ссылки **Изменить,** поэтому вы не можете изменить параметры (имя политики, описание и к кому применяется политика (она применяется ко всем получателям)).</span><span class="sxs-lookup"><span data-stu-id="e6aac-237">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="e6aac-238">Вы не можете удалить политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6aac-238">You can't delete the default policy.</span></span>
   - <span data-ttu-id="e6aac-239">Нельзя изменить приоритет политики по умолчанию (она всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="e6aac-239">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="e6aac-240">На странице **Изменить политику Office365 По** умолчанию просмотрите параметры и нажмите **кнопку Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e6aac-240">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="e6aac-241">Включить или отключить настраиваемые политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-241">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="e6aac-242">В Центре & безопасности перейдите в **центр по** борьбе с фишингом политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-242">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e6aac-243">Обратите внимание на значение в **столбце Состояние:**</span><span class="sxs-lookup"><span data-stu-id="e6aac-243">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="e6aac-244">Чтобы отключить политику, сдвиньте переключить переключеть на **Off** ![ Toggle ](../../media/scc-toggle-off.png) Off.</span><span class="sxs-lookup"><span data-stu-id="e6aac-244">Slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png) to disable the policy.</span></span>

   - <span data-ttu-id="e6aac-245">Чтобы включить политику, сдвиньте перемежок в **On** ![ Toggle ](../../media/scc-toggle-on.png) On.</span><span class="sxs-lookup"><span data-stu-id="e6aac-245">Slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png) to enable the policy.</span></span>

<span data-ttu-id="e6aac-246">Вы не можете отключить политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6aac-246">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="e6aac-247">Установите приоритет настраиваемой политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-247">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="e6aac-248">По умолчанию политикам защиты от фишинга предоставляется приоритет, основанный на порядке, в который они были созданы (более новые политики имеют более низкий приоритет по сравнению с более старыми политиками).</span><span class="sxs-lookup"><span data-stu-id="e6aac-248">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="e6aac-249">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="e6aac-249">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="e6aac-250">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="e6aac-250">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="e6aac-251">Дополнительные сведения о приоритетах, а также оценке и применении нескольких политик см. в статье [Порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="e6aac-251">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="e6aac-252">Пользовательские политики защиты от фишинга отображаются в порядке их обработки (первая политика имеет значение **Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="e6aac-252">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="e6aac-253">Политика защиты от фишинга по умолчанию с именем Office365 AntiPhish Default имеет настраиваемое значение приоритета **Самое** низкое, и изменить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="e6aac-253">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="e6aac-254">**Примечание.** В Центре & безопасности можно изменить приоритет политики защиты от фишинга только после ее создания.</span><span class="sxs-lookup"><span data-stu-id="e6aac-254">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="e6aac-255">В PowerShell можно переопредить приоритет по умолчанию при создании правила защиты от фишинга (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="e6aac-255">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="e6aac-256">Чтобы изменить приоритет политики, нажмите  кнопку Увеличение  приоритета или Уменьшение приоритета в свойствах политики (вы не можете напрямую изменить номер **Priority** в Центре & соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="e6aac-256">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="e6aac-257">Изменение приоритета политики имеет смысл только при нескольких политиках.</span><span class="sxs-lookup"><span data-stu-id="e6aac-257">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="e6aac-258">В Центре & безопасности перейдите в **центр по** борьбе с фишингом политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-258">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e6aac-259">Выберите политику, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="e6aac-259">Select the policy that you want to modify.</span></span> <span data-ttu-id="e6aac-260">Если он уже выбран, вытаницу его и выберите еще раз.</span><span class="sxs-lookup"><span data-stu-id="e6aac-260">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="e6aac-261">Появится **флааут Edit \<name\> your policy.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-261">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="e6aac-262">Настраиваемая политика защиты от фишинга со значением **Приоритет** **0** имеет только доступную кнопку **Приоритет уменьшения.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-262">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="e6aac-263">Настраиваемая политика защиты от  фишинга с наименьшим значением приоритета (например, **3)** имеет только доступную кнопку **Увеличение приоритета.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-263">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="e6aac-264">Если у вас есть три или более настраиваемые политики защиты от фишинга, политики между самыми  высокими и самыми низкими значениями приоритетов имеют доступные кнопки **"Увеличение** приоритета" и "Уменьшение приоритетов".</span><span class="sxs-lookup"><span data-stu-id="e6aac-264">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="e6aac-265">Щелкните **Увеличить приоритет или** уменьшить **приоритет,** чтобы изменить **значение Priority.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-265">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="e6aac-266">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e6aac-266">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="e6aac-267">Используйте Центр & безопасности для просмотра политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-267">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="e6aac-268">В Центре & безопасности и перейдите в **центр** по борьбе с фишингом политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-268">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e6aac-269">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e6aac-269">Do one of the following steps:</span></span>

   - <span data-ttu-id="e6aac-270">Выберите настраиваемую политику защиты от фишинга, которую необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="e6aac-270">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="e6aac-271">Если он уже выбран, вытаницу его и выберите еще раз.</span><span class="sxs-lookup"><span data-stu-id="e6aac-271">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="e6aac-272">Щелкните **политику по умолчанию,** чтобы просмотреть политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6aac-272">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="e6aac-273">Появится **флаевка \<name\>** "Изменить политику", в которой можно просмотреть параметры и значения.</span><span class="sxs-lookup"><span data-stu-id="e6aac-273">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="e6aac-274">Используйте Центр & безопасности для удаления политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-274">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="e6aac-275">В Центре & безопасности перейдите в **центр по** борьбе с фишингом политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-275">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e6aac-276">Выберите политику, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="e6aac-276">Select the policy that you want to remove.</span></span> <span data-ttu-id="e6aac-277">Если он уже выбран, вытаницу его и выберите еще раз.</span><span class="sxs-lookup"><span data-stu-id="e6aac-277">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="e6aac-278">В **появится \<name\> флажок Изменить** политику, нажмите кнопку **Удалить** политику, а затем нажмите **кнопку Да** в диалоговом окте предупреждения, который появится.</span><span class="sxs-lookup"><span data-stu-id="e6aac-278">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="e6aac-279">Политику по умолчанию удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="e6aac-279">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="e6aac-280">Используйте Exchange Online PowerShell для настройки политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-280">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="e6aac-281">Как описано выше, политика защиты от фишинга состоит из политики защиты от фишинга и правила защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="e6aac-281">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="e6aac-282">В Exchange Online PowerShell разница между политиками защиты от фишинга и правилами защиты от фишинга очевидна.</span><span class="sxs-lookup"><span data-stu-id="e6aac-282">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="e6aac-283">Вы управляете политиками защиты от фишинга с помощью кодлетов **\* -AntiPhishPolicy** и управляете правилами защиты от фишинга с помощью cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-283">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="e6aac-284">В PowerShell сначала создается политика защиты от фишинга, а затем создается правило защиты от фишинга, которое определяет политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="e6aac-284">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="e6aac-285">В PowerShell параметры политики защиты от фишинга и правила защиты от фишинга изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="e6aac-285">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="e6aac-286">При удалении политики защиты от фишинга из PowerShell соответствующее правило не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="e6aac-286">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="e6aac-287">Следующие процедуры PowerShell недоступны в автономных организациях EOP с Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6aac-287">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="e6aac-288">Использование PowerShell для создания политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-288">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="e6aac-289">Создание политики защиты от фишинга в PowerShell — это двухшаговый процесс:</span><span class="sxs-lookup"><span data-stu-id="e6aac-289">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="e6aac-290">Создание политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="e6aac-290">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="e6aac-291">Создайте правило защиты от фишинга, которое указывает политику защиты от фишинга, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="e6aac-291">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="e6aac-292">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="e6aac-292">**Notes**:</span></span>

- <span data-ttu-id="e6aac-293">Вы можете создать новое правило защиты от фишинга и назначить ему существующую, неассоциированную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="e6aac-293">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="e6aac-294">Правило защиты от фишинга не может быть связано с одной политикой защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="e6aac-294">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="e6aac-295">Вы можете настроить следующие параметры для новых политик защиты от фишинга в PowerShell, недоступных в Центре обеспечения безопасности & до момента создания политики:</span><span class="sxs-lookup"><span data-stu-id="e6aac-295">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="e6aac-296">Создайте новую политику как отключенную _(включена_ `$false` в **кодлете New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="e6aac-296">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="e6aac-297">Задай приоритет политики во время создания _(приоритет)_ в _\<Number\>_ **комлете New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-297">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="e6aac-298">Новая политика защиты от фишинга, которую вы создаете в PowerShell, не отображается в Центре & безопасности, пока не назначите политику правилу защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="e6aac-298">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="e6aac-299">Шаг 1. Использование PowerShell для создания политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-299">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="e6aac-300">Чтобы создать политику защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6aac-300">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

<span data-ttu-id="e6aac-301">В этом примере создается политика защиты от фишинга с именем Research Quarantine со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="e6aac-301">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="e6aac-302">Описание: Политика отдела исследований.</span><span class="sxs-lookup"><span data-stu-id="e6aac-302">The description is: Research department policy.</span></span>
- <span data-ttu-id="e6aac-303">Изменяет действие по умолчанию для подмены на карантин.</span><span class="sxs-lookup"><span data-stu-id="e6aac-303">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="e6aac-304">Подробные сведения о синтаксисе и параметрах см. в [обзоре New-AntiPhishPolicy.](/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="e6aac-304">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="e6aac-305">Шаг 2. Использование PowerShell для создания правила защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-305">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="e6aac-306">Чтобы создать правило защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6aac-306">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="e6aac-307">В этом примере создается правило защиты от фишинга с именем Research Department со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="e6aac-307">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="e6aac-308">Это правило связано с политикой защиты от фишинга с именем Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="e6aac-308">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="e6aac-309">Правило применяется к членам группы "Research Department".</span><span class="sxs-lookup"><span data-stu-id="e6aac-309">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="e6aac-310">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6aac-310">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="e6aac-311">Подробные сведения о синтаксисе и параметрах см. [в обзоре New-AntiPhishRule.](/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="e6aac-311">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="e6aac-312">Использование PowerShell для просмотра политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-312">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="e6aac-313">Чтобы просмотреть существующие политики защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6aac-313">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="e6aac-314">В этом примере возвращается сводный список всех политик защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="e6aac-314">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="e6aac-315">В этом примере возвращаются все значения свойств для политики защиты от фишинга с именем Executives.</span><span class="sxs-lookup"><span data-stu-id="e6aac-315">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="e6aac-316">Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-AntiPhishPolicy.](/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="e6aac-316">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="e6aac-317">Использование PowerShell для просмотра правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-317">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="e6aac-318">Чтобы просмотреть существующие правила защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6aac-318">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="e6aac-319">В этом примере возвращается сводный список всех правил по борьбе с фишингом вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="e6aac-319">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="e6aac-320">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="e6aac-320">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="e6aac-321">В этом примере возвращаются все значения свойств для правила защиты от фишинга с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="e6aac-321">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="e6aac-322">Подробные сведения о синтаксисе и параметрах см. в [ссылке Get-AntiPhishRule.](/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="e6aac-322">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="e6aac-323">Использование PowerShell для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-323">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="e6aac-324">Кроме следующих элементов, при изменении политики защиты от фишинга в PowerShell доступны те же параметры, что и при создании политики, описанной в шаге [1: Использование PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) для создания политики защиты от фишинга ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e6aac-324">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="e6aac-325">Переключатель _MakeDefault,_ который превращает указанную политику в политику по  умолчанию (применяется для всех, всегда самый низкий приоритет, и вы не можете удалить ее) доступен только при изменении политики защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6aac-325">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="e6aac-326">Нельзя переименовать политику защиты от фишинга (в **кодлете Set-AntiPhishPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="e6aac-326">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="e6aac-327">При переименовании политики защиты от фишинга в Центре & безопасности переименуется только правило защиты от _фишинга._</span><span class="sxs-lookup"><span data-stu-id="e6aac-327">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="e6aac-328">Чтобы изменить политику защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6aac-328">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="e6aac-329">Подробные сведения о синтаксисе и параметрах см. в [инструкции Set-AntiPhishPolicy.](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="e6aac-329">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="e6aac-330">Использование PowerShell для изменения правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-330">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="e6aac-331">Единственным параметром, недоступным при изменении правила защиты от фишинга в PowerShell, является параметр _Включен,_ который позволяет создать правило отключения.</span><span class="sxs-lookup"><span data-stu-id="e6aac-331">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="e6aac-332">Чтобы включить или отключить существующие правила защиты от фишинга, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="e6aac-332">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="e6aac-333">В противном случае те же параметры доступны при создании правила, описанного в разделе [Шаг 2: Использование PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) для создания раздела правил по борьбе с фишингом ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e6aac-333">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="e6aac-334">Чтобы изменить правило защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6aac-334">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="e6aac-335">Подробные сведения о синтаксисе и параметрах см. в [инструкции Set-AntiPhishRule.](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="e6aac-335">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="e6aac-336">Использование PowerShell, чтобы включить или отключить правила защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-336">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="e6aac-337">Включение или отключение правила защиты от фишинга в PowerShell включает или отключает всю политику защиты от фишинга (правило защиты от фишинга и назначенную политику защиты от фишинга).</span><span class="sxs-lookup"><span data-stu-id="e6aac-337">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="e6aac-338">Вы не можете включить или отключить политику защиты от фишинга по умолчанию (она всегда применяется к всем получателям).</span><span class="sxs-lookup"><span data-stu-id="e6aac-338">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="e6aac-339">Чтобы включить или отключить правило защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6aac-339">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="e6aac-340">В этом примере отключает правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="e6aac-340">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="e6aac-341">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="e6aac-341">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="e6aac-342">Подробные сведения о синтаксисе и параметрах см. в [сводке Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) и [Disable-AntiPhishRule.](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="e6aac-342">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="e6aac-343">Использование PowerShell для набора приоритета правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-343">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="e6aac-344">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="e6aac-344">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="e6aac-345">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="e6aac-345">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="e6aac-346">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="e6aac-346">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="e6aac-347">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="e6aac-347">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="e6aac-348">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="e6aac-348">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="e6aac-349">Чтобы установить приоритет правила защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6aac-349">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="e6aac-p139">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="e6aac-p139">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="e6aac-352">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="e6aac-352">**Notes**:</span></span>

- <span data-ttu-id="e6aac-353">Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в **комлете New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-353">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="e6aac-354">Политика защиты от фишинга по умолчанию не имеет соответствующего правила по борьбе с фишингом, и всегда имеет неоплаченное значение приоритета **Самое низкое.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-354">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="e6aac-355">Использование PowerShell для удаления политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-355">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="e6aac-356">При удалении политики защиты от фишинга с помощью PowerShell соответствующее правило по борьбе с фишингом не удаляется.</span><span class="sxs-lookup"><span data-stu-id="e6aac-356">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="e6aac-357">Чтобы удалить политику защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6aac-357">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="e6aac-358">В этом примере удаляется политика защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="e6aac-358">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="e6aac-359">Подробные сведения о синтаксисе и параметрах см. в [обзоре Remove-AntiPhishPolicy.](/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="e6aac-359">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="e6aac-360">Использование PowerShell для удаления правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="e6aac-360">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="e6aac-361">При удалении правила защиты от фишинга с помощью PowerShell соответствующая политика защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="e6aac-361">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="e6aac-362">Чтобы удалить правило защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6aac-362">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="e6aac-363">В этом примере удаляется правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="e6aac-363">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="e6aac-364">Подробные сведения о синтаксисе и параметрах см. в [инструкции Remove-AntiPhishRule.](/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="e6aac-364">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e6aac-365">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="e6aac-365">How do you know these procedures worked?</span></span>

<span data-ttu-id="e6aac-366">Чтобы убедиться, что политики защиты от фишинга успешно настроены в Microsoft Defender для Office 365, сделайте все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e6aac-366">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="e6aac-367">В Центре & безопасности перейдите в **центр по** борьбе с фишингом политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-367">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="e6aac-368">Проверка списка политик, их значений **состояния** и **их значений приоритета.**</span><span class="sxs-lookup"><span data-stu-id="e6aac-368">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="e6aac-369">Чтобы просмотреть дополнительные сведения, необходимо сделать любой из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e6aac-369">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="e6aac-370">Выберите политику из списка и просмотреть сведения в вылете.</span><span class="sxs-lookup"><span data-stu-id="e6aac-370">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="e6aac-371">Щелкните **политику по умолчанию** и просмотреть сведения в вылете.</span><span class="sxs-lookup"><span data-stu-id="e6aac-371">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="e6aac-372">В Exchange Online PowerShell замените имя политики или правила, запустите следующую команду и проверьте \<Name\> параметры:</span><span class="sxs-lookup"><span data-stu-id="e6aac-372">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```