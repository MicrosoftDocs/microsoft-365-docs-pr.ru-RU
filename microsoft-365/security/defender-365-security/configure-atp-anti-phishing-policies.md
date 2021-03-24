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
ms.openlocfilehash: 1c8d61aee9afb332a8426890560ad221a9c87c7d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073422"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b1613-103">Настройка политик защиты от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="b1613-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b1613-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="b1613-104">**Applies to**</span></span>
- [<span data-ttu-id="b1613-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="b1613-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b1613-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1613-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b1613-107">Политики защиты от фишинга в [Microsoft Defender для Office 365](defender-for-office-365.md) могут защитить организацию от вредоносных фишинговых атак на основе обезличения и других типов фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="b1613-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="b1613-108">Дополнительные сведения о различиях между политиками защиты от фишинга в Exchange Online Protection (EOP) и политиками защиты от фишинга в Microsoft Defender для Office 365 см. в сообщении о защите от [фишинга.](anti-phishing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="b1613-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="b1613-109">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b1613-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="b1613-110">Для большей детализации можно также создать настраиваемые политики защиты от фишинга, применимые к определенным пользователям, группам или доменам в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b1613-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="b1613-111">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="b1613-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="b1613-112">Политики защиты от фишинга можно настроить в Центре & безопасности или в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1613-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="b1613-113">Сведения о настройке более ограниченных политик защиты от фишинга, доступных в организациях Exchange Online Protection (то есть организациях без Microsoft Defender для Office 365), см. в рублях [Configure anti-phishing policies in EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="b1613-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="b1613-114">Основные элементы политики защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="b1613-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="b1613-115">**Политика защиты от фишинга:** указывает средства защиты от фишинга, чтобы включить или отключить, а также действия по применении параметров.</span><span class="sxs-lookup"><span data-stu-id="b1613-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="b1613-116">**Правило защиты от фишинга:** указывает фильтры приоритета и получателей (к кому применяется политика) для политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="b1613-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="b1613-117">Разница между этими двумя элементами не очевидна при управлении политиками защиты от фишинга в Центре & безопасности:</span><span class="sxs-lookup"><span data-stu-id="b1613-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="b1613-118">При создании политики создается правило защиты от фишинга и связанная с ним политика защиты от фишинга, используя одно и то же имя для обоих.</span><span class="sxs-lookup"><span data-stu-id="b1613-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="b1613-119">При изменении политики параметры, связанные с именем, приоритетом, включенной или отключенной, а также фильтры получателей изменяют правило защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="b1613-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="b1613-120">Все остальные параметры изменяют связанную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="b1613-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="b1613-121">При удалении политики удаляется правило защиты от фишинга и связанная с ним политика защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="b1613-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="b1613-122">В Exchange Online PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="b1613-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="b1613-123">Дополнительные сведения см. в разделе Use Exchange Online PowerShell для настройки политик защиты от фишинга в [разделе Microsoft Defender for Office 365,](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) опубликованном в этой статье.</span><span class="sxs-lookup"><span data-stu-id="b1613-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="b1613-124">Каждая организация Microsoft Defender для Office 365 имеет встроенную политику защиты от фишинга с именем Office365 AntiPhish Default, которая имеет эти свойства:</span><span class="sxs-lookup"><span data-stu-id="b1613-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="b1613-125">Политика применяется к всем получателям в организации, несмотря на отсутствие правила защиты от фишинга (фильтры получателей), связанного с политикой.</span><span class="sxs-lookup"><span data-stu-id="b1613-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="b1613-126">Для политики задано специальное значение приоритета **Самый низкий**, которое невозможно изменить (эта политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="b1613-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="b1613-127">Все созданные специальные политики всегда имеют более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="b1613-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="b1613-128">Эта политика является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.</span><span class="sxs-lookup"><span data-stu-id="b1613-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="b1613-129">Чтобы повысить эффективность защиты от фишинга в Microsoft Defender для Office 365, можно создать настраиваемые политики защиты от фишинга с более строгими настройками, которые применяются к конкретным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="b1613-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b1613-130">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="b1613-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b1613-131">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b1613-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b1613-132">Чтобы перейти непосредственно на страницу **atP по борьбе с** фишингом, используйте <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="b1613-132">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="b1613-133">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b1613-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="b1613-134">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="b1613-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="b1613-135">Чтобы добавить, изменить и удалить политики защиты от фишинга, необходимо  быть членом групп ролей администратора организации или **администратора** безопасности.</span><span class="sxs-lookup"><span data-stu-id="b1613-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="b1613-136">Для доступа только для чтения к политикам защиты от фишинга необходимо быть членом групп ролей **Global Reader** или **Security Reader.** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b1613-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="b1613-137">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="b1613-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="b1613-138">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="b1613-138">**Notes**:</span></span>

  - <span data-ttu-id="b1613-139">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b1613-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b1613-140">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b1613-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="b1613-141">Группа **ролей только для** организации просмотра в Exchange [Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции. <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b1613-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="b1613-142"><sup>\*</sup> В Центре & безопасности доступ только для чтения позволяет пользователям просматривать параметры настраиваемой политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="b1613-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="b1613-143">Пользователи, только для чтения, не могут видеть параметры в политике защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b1613-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="b1613-144">Рекомендуемые параметры для политик защиты от фишинга в Microsoft Defender для Office 365 см. в этой политике в [параметрах Defender for Office 365.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="b1613-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="b1613-145">Разрешить до 30 минут для новой или обновленной политики, которая будет применяться.</span><span class="sxs-lookup"><span data-stu-id="b1613-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="b1613-146">Сведения о том, где политики защиты от фишинга применяются в конвейере фильтрации, см. в рублях [Order и precedence of email protection.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="b1613-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b1613-147">Используйте Центр & безопасности для создания политик защиты от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="b1613-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="b1613-148">Создание настраиваемой политики защиты от фишинга в Центре & безопасности создает правило защиты от фишинга и связанную с ним политику защиты от фишинга, одновременно используя одно и то же имя для обоих.</span><span class="sxs-lookup"><span data-stu-id="b1613-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="b1613-149">При создании политики защиты от фишинга можно указать только имя политики, описание и фильтр получателя, который определяет, к кому применяется политика.</span><span class="sxs-lookup"><span data-stu-id="b1613-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="b1613-150">После создания политики можно изменить политику, чтобы изменить или просмотреть параметры защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b1613-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="b1613-151">В Центре & безопасности перейдите в  центр политики управления угрозами \>  \> **ATP по борьбе с фишингом.**</span><span class="sxs-lookup"><span data-stu-id="b1613-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="b1613-152">На странице **Anti-phishing** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="b1613-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="b1613-153">Откроется мастер политики защиты от **фишинга.**</span><span class="sxs-lookup"><span data-stu-id="b1613-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="b1613-154">На странице **Имя политики** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b1613-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="b1613-155">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="b1613-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="b1613-156">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="b1613-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="b1613-157">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b1613-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b1613-158">На странице **Applied to** page, которая появится, определите внутренних получателей, к которые применяется политика.</span><span class="sxs-lookup"><span data-stu-id="b1613-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="b1613-159">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="b1613-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="b1613-160">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="b1613-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="b1613-161">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="b1613-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="b1613-162">Нажмите **кнопку Добавить условие**.</span><span class="sxs-lookup"><span data-stu-id="b1613-162">Click **Add a condition**.</span></span> <span data-ttu-id="b1613-163">В отсеве, которое появится, выберите условие в **applied, если**:</span><span class="sxs-lookup"><span data-stu-id="b1613-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="b1613-164">**Получатель:** указывает один или несколько почтовых ящиков, пользователей почты или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="b1613-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="b1613-165">**Получатель является членом**: указывает одну или несколько групп в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b1613-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="b1613-166">**Домен получателя**: указывает получателей в одном или более настроенных принятых доменах в организации.</span><span class="sxs-lookup"><span data-stu-id="b1613-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="b1613-167">После выбора условия в любом из этих поле появится соответствующее **отсев.**</span><span class="sxs-lookup"><span data-stu-id="b1613-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="b1613-168">Щелкните в поле и прокрутите список значений для выбора.</span><span class="sxs-lookup"><span data-stu-id="b1613-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="b1613-169">Щелкните в поле и начните печатать, чтобы отфильтровать список и выбрать значение.</span><span class="sxs-lookup"><span data-stu-id="b1613-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="b1613-170">Чтобы добавить дополнительные значения, щелкните в пустой области в поле.</span><span class="sxs-lookup"><span data-stu-id="b1613-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="b1613-171">Чтобы удалить отдельные записи, **нажмите кнопку Удалить** ![ значок Удалить ](../../media/scc-remove-icon.png) значение.</span><span class="sxs-lookup"><span data-stu-id="b1613-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="b1613-172">Чтобы удалить все условие, нажмите **кнопку Удалить значок Удалить** ![ в ](../../media/scc-remove-icon.png) состоянии.</span><span class="sxs-lookup"><span data-stu-id="b1613-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="b1613-173">Чтобы добавить дополнительное условие, нажмите **кнопку Добавить условие** и выберите оставшееся значение **в applied if**.</span><span class="sxs-lookup"><span data-stu-id="b1613-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="b1613-174">Чтобы добавить исключения, нажмите **кнопку Добавить условие** и выберите исключение в соответствии **с исключением, если**.</span><span class="sxs-lookup"><span data-stu-id="b1613-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="b1613-175">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="b1613-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="b1613-176">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b1613-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b1613-177">На странице **Обзор параметров,** которая отображается, просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="b1613-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="b1613-178">Чтобы изменить его, можно нажать **кнопку Изменить** каждый параметр.</span><span class="sxs-lookup"><span data-stu-id="b1613-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="b1613-179">По завершению нажмите кнопку **Создать эту политику.**</span><span class="sxs-lookup"><span data-stu-id="b1613-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="b1613-180">Нажмите **кнопку ОК** в диалоговом окте подтверждения, который отображается.</span><span class="sxs-lookup"><span data-stu-id="b1613-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="b1613-181">После создания политики защиты от фишинга с помощью этих общих параметров используйте инструкции в следующем разделе для настройки параметров защиты в политике.</span><span class="sxs-lookup"><span data-stu-id="b1613-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b1613-182">Используйте Центр & безопасности для изменения политик защиты от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="b1613-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="b1613-183">Чтобы изменить политики защиты от фишинга, используйте следующие процедуры: созданную новую политику или уже настроенные политики.</span><span class="sxs-lookup"><span data-stu-id="b1613-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="b1613-184">Если вы еще не там, откройте центр & безопасности и  перейдите к политике управления угрозами ATP по борьбе \>  \> **с фишингом.**</span><span class="sxs-lookup"><span data-stu-id="b1613-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="b1613-185">Выберите настраиваемую политику защиты от фишинга, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="b1613-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="b1613-186">Если он уже выбран, вытаницу его и выберите еще раз.</span><span class="sxs-lookup"><span data-stu-id="b1613-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="b1613-187">Появится **флааут Edit \<name\> your policy.**</span><span class="sxs-lookup"><span data-stu-id="b1613-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="b1613-188">**Щелкнув кнопку Изменить** в любом разделе, вы сможете получить доступ к настройкам в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b1613-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="b1613-189">В порядке появления разделов представлены следующие действия, но они не являются последовательной (разделы можно выбрать и изменить в любом порядке).</span><span class="sxs-lookup"><span data-stu-id="b1613-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="b1613-190">После нажатия кнопки Изменить в разделе доступные параметры представлены в формате мастера, но вы можете перейти на страницы в  любом  порядке, и вы можете щелкнуть Сохранить на любой странице (или Отмена или закрыть закрыть значок, чтобы вернуться на страницу   Изменить ![ ](../../media/scc-remove-icon.png) **\<name\>** политику (вам не требуется посещать последнюю страницу мастера, чтобы сохранить или оставить).</span><span class="sxs-lookup"><span data-stu-id="b1613-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="b1613-191">**Параметр политики.** **Нажмите кнопку Изменить,** чтобы изменить те же параметры, которые были доступны при создании [политики](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) в предыдущем разделе:</span><span class="sxs-lookup"><span data-stu-id="b1613-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="b1613-192">**Название**</span><span class="sxs-lookup"><span data-stu-id="b1613-192">**Name**</span></span>
   - <span data-ttu-id="b1613-193">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b1613-193">**Description**</span></span>
   - <span data-ttu-id="b1613-194">**Применяется к**</span><span class="sxs-lookup"><span data-stu-id="b1613-194">**Applied to**</span></span>
   - <span data-ttu-id="b1613-195">**Просмотр параметров**</span><span class="sxs-lookup"><span data-stu-id="b1613-195">**Review your settings**</span></span>

   <span data-ttu-id="b1613-196">По завершению щелкните **Сохранить на** любой странице.</span><span class="sxs-lookup"><span data-stu-id="b1613-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="b1613-197">**Вымысление.** **Нажмите кнопку Изменить,** чтобы изменить защищенные отправители и защищенные домены в политике.</span><span class="sxs-lookup"><span data-stu-id="b1613-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="b1613-198">Эти параметры являются условием для политики, которая определяет поддельных отправителей, которые должны искать (по отдельности или по домену) в Адресе входящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="b1613-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="b1613-199">Дополнительные сведения см. в сведениях о параметрах Impersonation в политиках защиты от фишинга в [Microsoft Defender для Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="b1613-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="b1613-200">**Добавление пользователей для защиты:** значение по умолчанию **отключено.**</span><span class="sxs-lookup"><span data-stu-id="b1613-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="b1613-201">Чтобы включить его, сдвиньте переключить кнопку **On** и нажмите кнопку **Добавить** пользователя, которая появится.</span><span class="sxs-lookup"><span data-stu-id="b1613-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="b1613-202">В **вылете Добавить** пользователя, который отображается, настройте следующие значения:</span><span class="sxs-lookup"><span data-stu-id="b1613-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="b1613-203">**Адрес электронной почты:**</span><span class="sxs-lookup"><span data-stu-id="b1613-203">**Email address**:</span></span>

       - <span data-ttu-id="b1613-204">Щелкните в поле и прокрутите список выбранных пользователей.</span><span class="sxs-lookup"><span data-stu-id="b1613-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="b1613-205">Щелкните в поле и начните печатать, чтобы отфильтровать список и выбрать пользователя.</span><span class="sxs-lookup"><span data-stu-id="b1613-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="b1613-206">Чтобы удалить запись, нажмите **кнопку Удалить** ![ значок Удалить ](../../media/scc-remove-icon.png) пользователя.</span><span class="sxs-lookup"><span data-stu-id="b1613-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="b1613-207">**Имя.** Это значение заполняется на основе выбранного вами адреса электронной почты, но его можно изменить.</span><span class="sxs-lookup"><span data-stu-id="b1613-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="b1613-208">По завершению щелкните **Сохранить на** любой странице.</span><span class="sxs-lookup"><span data-stu-id="b1613-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="b1613-209">Чтобы изменить существующую запись, выберите защищенного пользователя в списке.</span><span class="sxs-lookup"><span data-stu-id="b1613-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="b1613-210">В каждой политике защиты от фишинга можно указать не более 60 защищенных пользователей (адреса электронной почты отправитель).</span><span class="sxs-lookup"><span data-stu-id="b1613-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="b1613-211">В нескольких политиках нельзя указать одного и того же защищенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="b1613-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="b1613-212">Защита от обезличения пользователя не работает, если отправитель и получатель ранее связывались по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="b1613-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="b1613-213">Если отправитель и получатель никогда не связывались по электронной почте, сообщение будет определено как попытка обезличения.</span><span class="sxs-lookup"><span data-stu-id="b1613-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="b1613-214">**Добавление доменов для защиты:** Настройка одного или обоих следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="b1613-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="b1613-215">**Автоматически включите домены, которые я владею:** значение по умолчанию **отключено.**</span><span class="sxs-lookup"><span data-stu-id="b1613-215">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="b1613-216">Чтобы включить его, сдвиньте переключить его на **On**.</span><span class="sxs-lookup"><span data-stu-id="b1613-216">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="b1613-217">**Включите настраиваемые домены:** значение по умолчанию **отключено.**</span><span class="sxs-lookup"><span data-stu-id="b1613-217">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="b1613-218">Чтобы включить его, сдвиньте переключение на **кнопку On** и в поле **Добавить** домены, введите доменное имя (например, contoso.com), нажмите кнопку ENTER и повторите по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="b1613-218">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="b1613-219">Во всех политиках защиты от фишинга можно использовать не более 50 доменов.</span><span class="sxs-lookup"><span data-stu-id="b1613-219">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="b1613-220">**Действия:** Нажмите **кнопку Изменить**</span><span class="sxs-lookup"><span data-stu-id="b1613-220">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="b1613-221">**Если электронная** почта отправляется обезличенным пользователем: настройте одно из следующих действий для сообщений, в которых подмененный отправитель является одним из защищенных пользователей, указанных в Добавлении пользователей для **защиты:**</span><span class="sxs-lookup"><span data-stu-id="b1613-221">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="b1613-222">**Не применяйте никаких действий**</span><span class="sxs-lookup"><span data-stu-id="b1613-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="b1613-223">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="b1613-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="b1613-224">**Переместить сообщение в папку "Нежелательная почта"**</span><span class="sxs-lookup"><span data-stu-id="b1613-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="b1613-225">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="b1613-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="b1613-226">**Доставка сообщения и добавление других адресов в строку Bcc**</span><span class="sxs-lookup"><span data-stu-id="b1613-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="b1613-227">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="b1613-227">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="b1613-228">**Если** электронная почта отправляется с помощью обезличенных доменов: настройте одно из следующих действий для сообщений, в которых подмененный отправитель находится в одном из защищенных доменов, указанных в доменах **Add** для защиты:</span><span class="sxs-lookup"><span data-stu-id="b1613-228">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="b1613-229">**Не применяйте никаких действий**</span><span class="sxs-lookup"><span data-stu-id="b1613-229">**Don't apply any action**</span></span>
       - <span data-ttu-id="b1613-230">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="b1613-230">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="b1613-231">**Переместить сообщение в папку "Нежелательная почта"**</span><span class="sxs-lookup"><span data-stu-id="b1613-231">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="b1613-232">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="b1613-232">**Quarantine the message**</span></span>
       - <span data-ttu-id="b1613-233">**Доставка сообщения и добавление других адресов в строку Bcc**</span><span class="sxs-lookup"><span data-stu-id="b1613-233">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="b1613-234">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="b1613-234">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="b1613-235">Щелкните **включайте подсказки по** безопасности обезличения и настройте любой из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="b1613-235">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="b1613-236">**Показать подсказку для обезличенных пользователей:** значение по умолчанию **отключено**.</span><span class="sxs-lookup"><span data-stu-id="b1613-236">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="b1613-237">Чтобы включить его, сдвиньте переключить его на **On**.</span><span class="sxs-lookup"><span data-stu-id="b1613-237">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="b1613-238">**Показать подсказку для обезличенных доменов:** значение по умолчанию **отключено.**</span><span class="sxs-lookup"><span data-stu-id="b1613-238">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="b1613-239">Чтобы включить его, сдвиньте переключить его на **On**.</span><span class="sxs-lookup"><span data-stu-id="b1613-239">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="b1613-240">**Показать подсказку для необычных символов:** значение по умолчанию **отключено**.</span><span class="sxs-lookup"><span data-stu-id="b1613-240">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="b1613-241">Чтобы включить его, сдвиньте переключить его на **On**.</span><span class="sxs-lookup"><span data-stu-id="b1613-241">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="b1613-242">Когда закончите, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b1613-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="b1613-243">**Разведка почтовых ящиков:**</span><span class="sxs-lookup"><span data-stu-id="b1613-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="b1613-244">**Включить разведданные почтовых ящиков?**: Значение по умолчанию **на**.</span><span class="sxs-lookup"><span data-stu-id="b1613-244">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="b1613-245">Чтобы отключить его, сдвиньте переключить его на **off.**</span><span class="sxs-lookup"><span data-stu-id="b1613-245">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="b1613-246">**Включить защиту от** обезличения на основе разведки почтовых ящиков? : Этот параметр доступен только в том случае, если включить разведку **почтовых ящиков?** </span><span class="sxs-lookup"><span data-stu-id="b1613-246">**Enable mailbox intelligence based impersonation protection?**: This setting is available only if **Enable mailbox intelligence?** is **On**.</span></span> <span data-ttu-id="b1613-247">Включи этот параметр, чтобы указать действие, которое необходимо принять для обнаружения сообщений для обнаружения обезличения из результатов разведки почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="b1613-247">Turn on this setting to specify the action to take on messages for impersonation detections from mailbox intelligence results.</span></span>

       <span data-ttu-id="b1613-248">В **случае отправки** электронной почты безымяенным пользователем можно указать одно из следующих действий (те же действия, которые доступны для защищенных пользователей и защищенных доменов):</span><span class="sxs-lookup"><span data-stu-id="b1613-248">In **If email is sent by an impersonated user**, you can specify one of the following actions (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="b1613-249">**Не применяйте** никаких действий: Обратите внимание, что это значение имеет тот же результат, что и включение учетных данных почтовых **ящиков?** Но отключение включить защиту от обезличения на основе разведки почтовых **ящиков?**.</span><span class="sxs-lookup"><span data-stu-id="b1613-249">**Don't apply any action**: Note that this value has the same result as turning on **Enable mailbox intelligence?** but turning off **Enable mailbox intelligence based impersonation protection?**.</span></span>
       - <span data-ttu-id="b1613-250">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="b1613-250">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="b1613-251">**Переместить сообщение в папку "Нежелательная почта"**</span><span class="sxs-lookup"><span data-stu-id="b1613-251">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="b1613-252">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="b1613-252">**Quarantine the message**</span></span>
       - <span data-ttu-id="b1613-253">**Доставка сообщения и добавление других адресов в строку Bcc**</span><span class="sxs-lookup"><span data-stu-id="b1613-253">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="b1613-254">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="b1613-254">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="b1613-255">**Добавление надежных отправителей и доменов:** укажите исключения для политики:</span><span class="sxs-lookup"><span data-stu-id="b1613-255">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="b1613-256">**Доверенные отправители:**</span><span class="sxs-lookup"><span data-stu-id="b1613-256">**Trusted senders**:</span></span>

       - <span data-ttu-id="b1613-257">Щелкните в поле и прокрутите список выбранных пользователей.</span><span class="sxs-lookup"><span data-stu-id="b1613-257">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="b1613-258">Щелкните в поле и начните печатать, чтобы отфильтровать список и выбрать пользователя.</span><span class="sxs-lookup"><span data-stu-id="b1613-258">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="b1613-259">Чтобы удалить запись, нажмите **кнопку Удалить** ![ значок Удалить ](../../media/scc-remove-icon.png) пользователя.</span><span class="sxs-lookup"><span data-stu-id="b1613-259">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="b1613-260">**Доверенные домены:** введите доменное имя (например, contoso.com), нажмите кнопку ENTER и повторите при необходимости.</span><span class="sxs-lookup"><span data-stu-id="b1613-260">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="b1613-261">**Просмотрите параметры.** Вместо нажатия на каждый отдельный шаг параметры отображаются в сводке.</span><span class="sxs-lookup"><span data-stu-id="b1613-261">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="b1613-262">Чтобы вернуться на соответствующую страницу, нажмите кнопку **Изменить** в каждом разделе.</span><span class="sxs-lookup"><span data-stu-id="b1613-262">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="b1613-263">Вы можете переключать следующие параметры **На** или **Выключение** непосредственно на этой странице:</span><span class="sxs-lookup"><span data-stu-id="b1613-263">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="b1613-264">**Защищенные пользователи**</span><span class="sxs-lookup"><span data-stu-id="b1613-264">**Protected users**</span></span>
       - <span data-ttu-id="b1613-265">**Защищенные домены** \> **Включаю домены, которые у меня есть**</span><span class="sxs-lookup"><span data-stu-id="b1613-265">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="b1613-266">**Защищенные домены** \> **Защищенные домены** (настраиваемые домены)</span><span class="sxs-lookup"><span data-stu-id="b1613-266">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="b1613-267">**Аналитика почтовых ящиков**</span><span class="sxs-lookup"><span data-stu-id="b1613-267">**Mailbox intelligence**</span></span>

   <span data-ttu-id="b1613-268">По завершению щелкните **Сохранить на** любой странице.</span><span class="sxs-lookup"><span data-stu-id="b1613-268">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="b1613-269">**Spoof**: Нажмите кнопку **Изменить,** чтобы включить или отключить подмену сведений, включить неавентированную идентификацию отправителей в Outlook или отключить, а также настроить действие для применения к сообщениям от заблокированных поддельных отправителей.</span><span class="sxs-lookup"><span data-stu-id="b1613-269">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="b1613-270">Дополнительные сведения см. в [параметрах Spoof в политиках защиты от фишинга.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="b1613-270">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="b1613-271">Обратите внимание, что эти же параметры также доступны в политиках защиты от фишинга в EOP.</span><span class="sxs-lookup"><span data-stu-id="b1613-271">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="b1613-272">**Параметры фильтра спуфинга:** значение по умолчанию **в режиме On,** и мы рекомендуем оставить его.</span><span class="sxs-lookup"><span data-stu-id="b1613-272">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="b1613-273">Чтобы отключить его, сдвиньте переключить его на **off.**</span><span class="sxs-lookup"><span data-stu-id="b1613-273">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="b1613-274">Дополнительные сведения см. в [перенастройке сведений о подмене в EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="b1613-274">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="b1613-275">Вам не нужно отключать защиту от спуфинга, если запись MX не указывая на Microsoft 365; Вместо этого вы включаете усиленную фильтрацию соединителя.</span><span class="sxs-lookup"><span data-stu-id="b1613-275">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="b1613-276">Инструкции см. в [расширенной фильтрации соединитений в Exchange Online.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="b1613-276">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="b1613-277">**Включить неавентированные функции отправитель:** значение по умолчанию **на**.</span><span class="sxs-lookup"><span data-stu-id="b1613-277">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="b1613-278">Чтобы отключить его, сдвиньте переключить его на **off.**</span><span class="sxs-lookup"><span data-stu-id="b1613-278">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="b1613-279">**Действия:** укажите действие для принятия сообщений, которые не подавлили сведения о подмене:</span><span class="sxs-lookup"><span data-stu-id="b1613-279">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="b1613-280">**Если электронная почта отправляется кем-то,** кому запрещено подменять домен:</span><span class="sxs-lookup"><span data-stu-id="b1613-280">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="b1613-281">**Перемещение сообщения в папки нежелательной почты получателей**</span><span class="sxs-lookup"><span data-stu-id="b1613-281">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="b1613-282">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="b1613-282">**Quarantine the message**</span></span>

   - <span data-ttu-id="b1613-283">**Просмотрите параметры.** Вместо нажатия на каждый отдельный шаг параметры отображаются в сводке.</span><span class="sxs-lookup"><span data-stu-id="b1613-283">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="b1613-284">Чтобы вернуться на соответствующую страницу, нажмите кнопку **Изменить** в каждом разделе.</span><span class="sxs-lookup"><span data-stu-id="b1613-284">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="b1613-285">Вы можете переключать следующие параметры **На** или **Выключение** непосредственно на этой странице:</span><span class="sxs-lookup"><span data-stu-id="b1613-285">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="b1613-286">**Включить защиту от непопуфинга**</span><span class="sxs-lookup"><span data-stu-id="b1613-286">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="b1613-287">**Включить функцию unauthenticated Sender**</span><span class="sxs-lookup"><span data-stu-id="b1613-287">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="b1613-288">По завершению щелкните **Сохранить на** любой странице.</span><span class="sxs-lookup"><span data-stu-id="b1613-288">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="b1613-289">**Расширенные параметры.** **Нажмите кнопку Изменить,** чтобы настроить расширенные пороговые значения фишинга.</span><span class="sxs-lookup"><span data-stu-id="b1613-289">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="b1613-290">Дополнительные сведения см. в расширенных пороговых значениях фишинга в политиках защиты от фишинга в [Microsoft Defender для Office 365.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="b1613-290">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="b1613-291">**Расширенные пороги фишинга:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="b1613-291">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="b1613-292">**1 . Стандартный** (это значение по умолчанию.)</span><span class="sxs-lookup"><span data-stu-id="b1613-292">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="b1613-293">**2 . Агрессивная**</span><span class="sxs-lookup"><span data-stu-id="b1613-293">**2 - Aggressive**</span></span>
   - <span data-ttu-id="b1613-294">**3 . Более агрессивная**</span><span class="sxs-lookup"><span data-stu-id="b1613-294">**3 - More aggressive**</span></span>
   - <span data-ttu-id="b1613-295">**4 . Наиболее агрессивный**</span><span class="sxs-lookup"><span data-stu-id="b1613-295">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="b1613-296">**Просмотрите параметры.** **Щелкните Изменить,** чтобы вернуться на страницу **Расширенные** пороги фишинга.</span><span class="sxs-lookup"><span data-stu-id="b1613-296">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="b1613-297">По завершению щелкните **Сохранить на** любой странице.</span><span class="sxs-lookup"><span data-stu-id="b1613-297">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="b1613-298">Возвращаясь на **страницу Изменить политику, \<Name\>** просмотрите параметры и нажмите **кнопку Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="b1613-298">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b1613-299">Используйте Центр & безопасности для изменения политики защиты от фишинга по умолчанию в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="b1613-299">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="b1613-300">Политика защиты от фишинга по умолчанию в Microsoft Defender для Office 365 называется Office365 AntiPhish Default и не появляется в списке политик.</span><span class="sxs-lookup"><span data-stu-id="b1613-300">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="b1613-301">Чтобы изменить политику защиты от фишинга по умолчанию, необходимо сделать следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b1613-301">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="b1613-302">В Центре & безопасности перейдите в  центр политики управления угрозами \>  \> **ATP по борьбе с фишингом.**</span><span class="sxs-lookup"><span data-stu-id="b1613-302">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="b1613-303">На странице **Anti-phishing** нажмите кнопку **Политика по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="b1613-303">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="b1613-304">Появится **страница "Изменить политику Office365 по** умолчанию".</span><span class="sxs-lookup"><span data-stu-id="b1613-304">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="b1613-305">Доступны следующие разделы, содержащие идентичные параметры при изменении [настраиваемой политики:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="b1613-305">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="b1613-306">**Олицетворение**</span><span class="sxs-lookup"><span data-stu-id="b1613-306">**Impersonation**</span></span>
   - <span data-ttu-id="b1613-307">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="b1613-307">**Spoof**</span></span>
   - <span data-ttu-id="b1613-308">**Дополнительные параметры**</span><span class="sxs-lookup"><span data-stu-id="b1613-308">**Advanced settings**</span></span>

   <span data-ttu-id="b1613-309">При изменении политики по умолчанию недоступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b1613-309">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="b1613-310">Вы можете  увидеть раздел параметр политики и значения, но нет ссылки **Изменить,** поэтому вы не можете изменить параметры (имя политики, описание и к кому применяется политика (она применяется ко всем получателям)).</span><span class="sxs-lookup"><span data-stu-id="b1613-310">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="b1613-311">Вы не можете удалить политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b1613-311">You can't delete the default policy.</span></span>
   - <span data-ttu-id="b1613-312">Нельзя изменить приоритет политики по умолчанию (она всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="b1613-312">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="b1613-313">На странице **Изменить политику Office365 По** умолчанию просмотрите параметры и нажмите **кнопку Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="b1613-313">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b1613-314">Включить или отключить настраиваемые политики защиты от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="b1613-314">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="b1613-315">В Центре & безопасности перейдите в  центр политики управления угрозами \>  \> **ATP по борьбе с фишингом.**</span><span class="sxs-lookup"><span data-stu-id="b1613-315">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="b1613-316">Обратите внимание на значение в **столбце Состояние:**</span><span class="sxs-lookup"><span data-stu-id="b1613-316">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="b1613-317">Чтобы отключить политику,  сдвиньте переключеть переключеть.</span><span class="sxs-lookup"><span data-stu-id="b1613-317">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="b1613-318">Чтобы включить политику, сдвиньте перемежок на **on.**</span><span class="sxs-lookup"><span data-stu-id="b1613-318">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="b1613-319">Вы не можете отключить политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b1613-319">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b1613-320">Установите приоритет пользовательских политик защиты от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="b1613-320">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="b1613-321">По умолчанию политикам защиты от фишинга предоставляется приоритет, основанный на порядке, в который они были созданы (более новые политики имеют более низкий приоритет по сравнению с более старыми политиками).</span><span class="sxs-lookup"><span data-stu-id="b1613-321">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="b1613-322">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="b1613-322">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="b1613-323">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="b1613-323">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="b1613-324">Дополнительные сведения о приоритетах, а также оценке и применении нескольких политик см. в статье [Порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="b1613-324">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="b1613-325">Пользовательские политики защиты от фишинга отображаются в порядке их обработки (первая политика имеет значение **Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="b1613-325">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="b1613-326">Политика защиты от фишинга по умолчанию с именем Office365 AntiPhish Default имеет настраиваемое значение приоритета **Самое** низкое, и изменить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="b1613-326">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="b1613-327">**Примечание.** В Центре & безопасности можно изменить приоритет политики защиты от фишинга только после ее создания.</span><span class="sxs-lookup"><span data-stu-id="b1613-327">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="b1613-328">В PowerShell можно переопредить приоритет по умолчанию при создании правила защиты от фишинга (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="b1613-328">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="b1613-329">Чтобы изменить приоритет политики, нажмите  кнопку Увеличение  приоритета или Уменьшение приоритета в свойствах политики (вы не можете напрямую изменить номер **Priority** в Центре & соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="b1613-329">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="b1613-330">Изменение приоритета политики имеет смысл только при нескольких политиках.</span><span class="sxs-lookup"><span data-stu-id="b1613-330">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="b1613-331">В Центре & безопасности перейдите в  центр политики управления угрозами \>  \> **ATP по борьбе с фишингом.**</span><span class="sxs-lookup"><span data-stu-id="b1613-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="b1613-332">Выберите политику, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="b1613-332">Select the policy that you want to modify.</span></span> <span data-ttu-id="b1613-333">Если он уже выбран, вытаницу его и выберите еще раз.</span><span class="sxs-lookup"><span data-stu-id="b1613-333">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="b1613-334">Появится **флааут Edit \<name\> your policy.**</span><span class="sxs-lookup"><span data-stu-id="b1613-334">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="b1613-335">Настраиваемая политика защиты от фишинга со значением **Приоритет** **0** имеет только доступную кнопку **Приоритет уменьшения.**</span><span class="sxs-lookup"><span data-stu-id="b1613-335">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="b1613-336">Настраиваемая политика защиты от  фишинга с наименьшим значением приоритета (например, **3)** имеет только доступную кнопку **Увеличение приоритета.**</span><span class="sxs-lookup"><span data-stu-id="b1613-336">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="b1613-337">Если у вас есть три или более настраиваемые политики защиты от фишинга, политики между самыми  высокими и самыми низкими значениями приоритетов имеют доступные кнопки **"Увеличение** приоритета" и "Уменьшение приоритетов".</span><span class="sxs-lookup"><span data-stu-id="b1613-337">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="b1613-338">Щелкните **Увеличить приоритет или** уменьшить **приоритет,** чтобы изменить **значение Priority.**</span><span class="sxs-lookup"><span data-stu-id="b1613-338">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="b1613-339">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="b1613-339">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b1613-340">Используйте Центр & безопасности для просмотра политик защиты от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="b1613-340">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="b1613-341">В Центре & безопасности и перейдите  к политике управления угрозами \>  \> **ATP по борьбе с фишингом.**</span><span class="sxs-lookup"><span data-stu-id="b1613-341">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="b1613-342">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="b1613-342">Do one of the following steps:</span></span>

   - <span data-ttu-id="b1613-343">Выберите настраиваемую политику защиты от фишинга, которую необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="b1613-343">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="b1613-344">Если он уже выбран, вытаницу его и выберите еще раз.</span><span class="sxs-lookup"><span data-stu-id="b1613-344">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="b1613-345">Щелкните **политику по умолчанию,** чтобы просмотреть политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b1613-345">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="b1613-346">Появится **флаевка \<name\>** "Изменить политику", в которой можно просмотреть параметры и значения.</span><span class="sxs-lookup"><span data-stu-id="b1613-346">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b1613-347">Используйте Центр & безопасности для удаления политик защиты от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="b1613-347">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="b1613-348">В Центре & безопасности перейдите в  центр политики управления угрозами \>  \> **ATP по борьбе с фишингом.**</span><span class="sxs-lookup"><span data-stu-id="b1613-348">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="b1613-349">Выберите политику, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="b1613-349">Select the policy that you want to remove.</span></span> <span data-ttu-id="b1613-350">Если он уже выбран, вытаницу его и выберите еще раз.</span><span class="sxs-lookup"><span data-stu-id="b1613-350">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="b1613-351">В **появится \<name\> флажок Изменить** политику, нажмите кнопку **Удалить** политику, а затем нажмите **кнопку Да** в диалоговом окте предупреждения, который появится.</span><span class="sxs-lookup"><span data-stu-id="b1613-351">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="b1613-352">Политику по умолчанию удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="b1613-352">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b1613-353">Используйте Exchange Online PowerShell для настройки политик защиты от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="b1613-353">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="b1613-354">Как описано выше, политика защиты от нежелательной почты состоит из политики защиты от фишинга и правила защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="b1613-354">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="b1613-355">В Exchange Online PowerShell разница между политиками защиты от фишинга и правилами защиты от фишинга очевидна.</span><span class="sxs-lookup"><span data-stu-id="b1613-355">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="b1613-356">Вы управляете политиками защиты от фишинга с помощью кодлетов **\* -AntiPhishPolicy** и управляете правилами защиты от фишинга с помощью cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="b1613-356">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="b1613-357">В PowerShell сначала создается политика защиты от фишинга, а затем создается правило защиты от фишинга, которое определяет политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="b1613-357">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="b1613-358">В PowerShell параметры политики защиты от фишинга и правила защиты от фишинга изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="b1613-358">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="b1613-359">При удалении политики защиты от фишинга из PowerShell соответствующее правило не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="b1613-359">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="b1613-360">Использование PowerShell для создания политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="b1613-360">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="b1613-361">Создание политики защиты от фишинга в PowerShell — это двухшаговый процесс:</span><span class="sxs-lookup"><span data-stu-id="b1613-361">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="b1613-362">Создание политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="b1613-362">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="b1613-363">Создайте правило защиты от фишинга, которое указывает политику защиты от фишинга, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="b1613-363">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="b1613-364">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="b1613-364">**Notes**:</span></span>

- <span data-ttu-id="b1613-365">Вы можете создать новое правило защиты от фишинга и назначить ему существующую, неассоциированную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="b1613-365">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="b1613-366">Правило защиты от фишинга не может быть связано с одной политикой защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="b1613-366">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="b1613-367">Вы можете настроить следующие параметры для новых политик защиты от фишинга в PowerShell, недоступных в Центре обеспечения безопасности & до момента создания политики:</span><span class="sxs-lookup"><span data-stu-id="b1613-367">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="b1613-368">Создайте новую политику как отключенную _(включена_ `$false` в **кодлете New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="b1613-368">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="b1613-369">Задай приоритет политики во время создания _(приоритет)_ в _\<Number\>_ **комлете New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="b1613-369">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="b1613-370">Новая политика защиты от фишинга, которую вы создаете в PowerShell, не отображается в Центре & безопасности, пока не назначите политику правилу защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="b1613-370">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="b1613-371">Шаг 1. Использование PowerShell для создания политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="b1613-371">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="b1613-372">Чтобы создать политику защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b1613-372">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="b1613-373">В этом примере создается политика защиты от фишинга с именем Research Quarantine со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="b1613-373">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="b1613-374">Политика включена (мы не используем параметр _Включен,_ а значение по `$true` умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b1613-374">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="b1613-375">Описание: Политика отдела исследований.</span><span class="sxs-lookup"><span data-stu-id="b1613-375">The description is: Research department policy.</span></span>
- <span data-ttu-id="b1613-376">Включает защиту доменов организации для всех принятых доменов и адресную защиту доменов для fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="b1613-376">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="b1613-377">Указывает, что защищать от имитации нужно пользователя Mai Fujito (mfujito@fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="b1613-377">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="b1613-378">Включает аналитику почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="b1613-378">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="b1613-379">Включает защиту разведданных почтовых ящиков и указывает действие карантина.</span><span class="sxs-lookup"><span data-stu-id="b1613-379">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="b1613-380">Включает советы по безопасности.</span><span class="sxs-lookup"><span data-stu-id="b1613-380">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="b1613-381">Подробные сведения о синтаксисе и параметрах см. в [обзоре New-AntiPhishPolicy.](/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="b1613-381">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="b1613-382">Шаг 2. Использование PowerShell для создания правила защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="b1613-382">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="b1613-383">Чтобы создать правило защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b1613-383">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="b1613-384">В этом примере создается правило защиты от фишинга с именем Research Department со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="b1613-384">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="b1613-385">Это правило связано с политикой защиты от фишинга с именем Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="b1613-385">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="b1613-386">Правило применяется к членам группы "Research Department".</span><span class="sxs-lookup"><span data-stu-id="b1613-386">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="b1613-387">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b1613-387">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="b1613-388">Подробные сведения о синтаксисе и параметрах см. [в обзоре New-AntiPhishRule.](/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="b1613-388">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="b1613-389">Использование PowerShell для просмотра политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="b1613-389">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="b1613-390">Чтобы просмотреть существующие политики защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b1613-390">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="b1613-391">В этом примере возвращается сводный список всех политик защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="b1613-391">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="b1613-392">В этом примере возвращаются все значения свойств для политики защиты от фишинга с именем Executives.</span><span class="sxs-lookup"><span data-stu-id="b1613-392">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="b1613-393">Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-AntiPhishPolicy.](/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="b1613-393">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="b1613-394">Использование PowerShell для просмотра правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="b1613-394">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="b1613-395">Чтобы просмотреть существующие правила защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b1613-395">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="b1613-396">В этом примере возвращается сводный список всех правил по борьбе с фишингом вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="b1613-396">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="b1613-397">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="b1613-397">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="b1613-398">В этом примере возвращаются все значения свойств для правила защиты от фишинга с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="b1613-398">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="b1613-399">Подробные сведения о синтаксисе и параметрах см. в [ссылке Get-AntiPhishRule.](/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="b1613-399">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="b1613-400">Использование PowerShell для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="b1613-400">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="b1613-401">Кроме следующих элементов, при изменении политики защиты от фишинга в PowerShell доступны те же параметры, что и при создании политики, описанной в разделе [Шаг 1. Использование PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) для создания раздела политики защиты от фишинга в этой статье.</span><span class="sxs-lookup"><span data-stu-id="b1613-401">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="b1613-402">Переключатель _MakeDefault,_ который превращает указанную политику в политику по  умолчанию (применяется для всех, всегда самый низкий приоритет, и вы не можете удалить ее) доступен только при изменении политики защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1613-402">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="b1613-403">Нельзя переименовать политику защиты от фишинга (в **кодлете Set-AntiPhishPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="b1613-403">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="b1613-404">При переименовании политики защиты от фишинга в Центре & безопасности переименуется только правило защиты от _фишинга._</span><span class="sxs-lookup"><span data-stu-id="b1613-404">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="b1613-405">Чтобы изменить политику защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b1613-405">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="b1613-406">Подробные сведения о синтаксисе и параметрах см. в [инструкции Set-AntiPhishPolicy.](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="b1613-406">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="b1613-407">Использование PowerShell для изменения правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="b1613-407">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="b1613-408">Единственным параметром, недоступным при изменении правила защиты от фишинга  в PowerShell, является параметр Включен, который позволяет создать правило отключено.</span><span class="sxs-lookup"><span data-stu-id="b1613-408">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="b1613-409">Чтобы включить или отключить существующие правила защиты от фишинга, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="b1613-409">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="b1613-410">В противном случае дополнительные параметры не доступны при изменении правила защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1613-410">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="b1613-411">Эти же параметры доступны при создании правила, описанного в разделе Шаг [2. Использование PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) для создания раздела правил для защиты от фишинга в этой статье.</span><span class="sxs-lookup"><span data-stu-id="b1613-411">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="b1613-412">Чтобы изменить правило защиты от фишинга, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b1613-412">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="b1613-413">Подробные сведения о синтаксисе и параметрах см. в [инструкции Set-AntiPhishRule.](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="b1613-413">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="b1613-414">Использование PowerShell, чтобы включить или отключить правила защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="b1613-414">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="b1613-415">Включение или отключение правила защиты от фишинга в PowerShell включает или отключает всю политику защиты от фишинга (правило защиты от фишинга и назначенную политику защиты от фишинга).</span><span class="sxs-lookup"><span data-stu-id="b1613-415">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="b1613-416">Вы не можете включить или отключить политику защиты от фишинга по умолчанию (она всегда применяется к всем получателям).</span><span class="sxs-lookup"><span data-stu-id="b1613-416">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="b1613-417">Чтобы включить или отключить правило защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b1613-417">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="b1613-418">В этом примере отключает правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="b1613-418">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="b1613-419">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="b1613-419">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="b1613-420">Подробные сведения о синтаксисе и параметрах см. в [сводке Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) и [Disable-AntiPhishRule.](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="b1613-420">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="b1613-421">Использование PowerShell для набора приоритета правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="b1613-421">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="b1613-422">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="b1613-422">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="b1613-423">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="b1613-423">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="b1613-424">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="b1613-424">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="b1613-425">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="b1613-425">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="b1613-426">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="b1613-426">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="b1613-427">Чтобы установить приоритет правила защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b1613-427">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="b1613-p149">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="b1613-p149">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="b1613-430">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="b1613-430">**Notes**:</span></span>

- <span data-ttu-id="b1613-431">Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в **комлете New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="b1613-431">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="b1613-432">Политика защиты от фишинга по умолчанию не имеет соответствующего правила по борьбе с фишингом, и всегда имеет неоплаченное значение приоритета **Самое низкое.**</span><span class="sxs-lookup"><span data-stu-id="b1613-432">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="b1613-433">Использование PowerShell для удаления политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="b1613-433">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="b1613-434">При удалении политики защиты от фишинга с помощью PowerShell соответствующее правило по борьбе с фишингом не удаляется.</span><span class="sxs-lookup"><span data-stu-id="b1613-434">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="b1613-435">Чтобы удалить политику защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b1613-435">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="b1613-436">В этом примере удаляется политика защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="b1613-436">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="b1613-437">Подробные сведения о синтаксисе и параметрах см. в [обзоре Remove-AntiPhishPolicy.](/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="b1613-437">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="b1613-438">Использование PowerShell для удаления правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="b1613-438">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="b1613-439">При удалении правила защиты от фишинга с помощью PowerShell соответствующая политика защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="b1613-439">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="b1613-440">Чтобы удалить правило защиты от фишинга в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b1613-440">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="b1613-441">В этом примере удаляется правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="b1613-441">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="b1613-442">Подробные сведения о синтаксисе и параметрах см. в [инструкции Remove-AntiPhishRule.](/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="b1613-442">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b1613-443">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="b1613-443">How do you know these procedures worked?</span></span>

<span data-ttu-id="b1613-444">Чтобы убедиться, что политики защиты от фишинга успешно настроены в Microsoft Defender для Office 365, необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b1613-444">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="b1613-445">В Центре & безопасности перейдите в  центр политики управления угрозами \>  \> **ATP по борьбе с фишингом.**</span><span class="sxs-lookup"><span data-stu-id="b1613-445">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="b1613-446">Проверка списка политик, их значений **состояния** и **их значений приоритета.**</span><span class="sxs-lookup"><span data-stu-id="b1613-446">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="b1613-447">Чтобы просмотреть дополнительные сведения, необходимо сделать любой из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="b1613-447">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="b1613-448">Выберите политику из списка и просмотреть сведения в вылете.</span><span class="sxs-lookup"><span data-stu-id="b1613-448">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="b1613-449">Щелкните **политику по умолчанию** и просмотреть сведения в вылете.</span><span class="sxs-lookup"><span data-stu-id="b1613-449">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="b1613-450">В Exchange Online PowerShell замените имя политики или правила и запустите следующую команду и проверьте \<Name\> параметры:</span><span class="sxs-lookup"><span data-stu-id="b1613-450">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```