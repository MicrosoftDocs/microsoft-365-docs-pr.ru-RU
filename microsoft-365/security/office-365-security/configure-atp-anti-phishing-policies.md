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
description: Администраторы могут научиться создавать, изменять и удалять расширенные политики защиты от фишинга, доступные в организациях с Помощью Microsoft Defender для Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8b8a43127c4e445ab214a709bb27e5e29100d358
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165719"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="3c4ce-103">Настройка политик защиты от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="3c4ce-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3c4ce-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-104">**Applies to**</span></span>
- [<span data-ttu-id="3c4ce-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="3c4ce-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c4ce-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="3c4ce-107">Политики защиты от фишинга в [Microsoft Defender для Office 365](office-365-atp.md) помогут защитить организацию от фишинговых атак на основе вредоносных фишинговых атак на основе фишинга и других типов фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-107">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="3c4ce-108">Дополнительные сведения о различиях между политиками защиты от фишинга в Exchange Online Protection (EOP) и политиками [](anti-phishing-protection.md)защиты от фишинга в Microsoft Defender для Office 365 см. в этой теме.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="3c4ce-109">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="3c4ce-110">Для большей детализации можно также создать настраиваемые политики защиты от фишинга, которые применяются к определенным пользователям, группам или доменам в организации.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="3c4ce-111">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="3c4ce-112">Политики защиты от фишинга можно настроить в Центре безопасности & соответствия требованиям или в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="3c4ce-113">Дополнительные сведения о настройке более ограниченных политик защиты от фишинга, доступных в организациях Exchange Online Protection (то есть организациях без Microsoft Defender для Office 365), см. в подстройке "Настройка политик защиты от фишинга" в [EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="3c4ce-114">Основные элементы политики защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="3c4ce-115">**Политика защиты от фишинга**: определяет средства защиты от фишинга, которые необходимо включить или отключить, а также действия, которые необходимо применить.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="3c4ce-116">**Правило защиты от фишинга:** определяет приоритет и фильтры получателей (к кому применяется политика) для политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="3c4ce-117">Разница между этими двумя элементами не очевидна при управлении политиками защиты от фишинга в Центре безопасности & соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="3c4ce-118">При создании политики вы фактически создаете правило защиты от фишинга и связанную с ним политику одновременно, используя одно и то же имя для обоих этих правил.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="3c4ce-119">При изменении политики параметры, связанные с именем, приоритетом, включенным или отключенным фильтрами получателей, изменяют правило защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="3c4ce-120">Все остальные параметры изменяют связанную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="3c4ce-121">При удалении политики удаляются правило защиты от фишинга и связанная с ним политика защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="3c4ce-122">В Exchange Online PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="3c4ce-123">Дополнительные сведения см. в разделе "Использование Exchange Online PowerShell для настройки политик защиты от фишинга в [Microsoft Defender для Office 365"](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="3c4ce-124">В каждой организации Microsoft Defender для Office 365 есть встроенная политика защиты от фишинга с именем Office365 AntiPhish Default, которая имеет указанные здесь свойства.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="3c4ce-125">Политика применяется к всем получателям в организации, даже если с ней не связано ни одно правило защиты от фишинга (фильтры получателей).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="3c4ce-126">Для политики задано специальное значение приоритета **Самый низкий**, которое невозможно изменить (эта политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="3c4ce-127">Все созданные специальные политики всегда имеют более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="3c4ce-128">Эта политика является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="3c4ce-129">Чтобы повысить эффективность защиты от фишинга в Microsoft Defender для Office 365, можно создать настраиваемые политики защиты от фишинга с более строгими настройками, которые применяются к определенным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3c4ce-130">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="3c4ce-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3c4ce-131">Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3c4ce-132">Чтобы перейти непосредственно на страницу защиты от фишинга **ATP,** используйте <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="3c4ce-132">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="3c4ce-133">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="3c4ce-134">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-134">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="3c4ce-135">Чтобы добавлять, изменять и удалять политики защиты от фишинга, необходимо  быть членом группы ролей "Управление организацией" или "Администратор **безопасности".**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="3c4ce-136">Для доступа только для чтения к политикам защиты от фишинга необходимо  быть членом группы ролей **"Глобальный** читатель" или "Читатель <sup>\*</sup> безопасности".</span><span class="sxs-lookup"><span data-stu-id="3c4ce-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="3c4ce-137">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="3c4ce-138">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-138">**Notes**:</span></span>

  - <span data-ttu-id="3c4ce-139">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="3c4ce-140">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-140">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="3c4ce-141">Группа **ролей управления организацией** с доступом только для просмотра в Exchange [Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ к этой функции только для <sup>\*</sup> чтения.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-141">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="3c4ce-142"><sup>\*</sup> В Центре безопасности & соответствия требованиям доступ только для чтения позволяет пользователям просматривать параметры пользовательских политик защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="3c4ce-143">Пользователи, только для чтения, не могут видеть параметры в политике защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="3c4ce-144">Рекомендуемые параметры политик защиты от фишинга в Microsoft Defender для Office 365 см. в политике защиты от фишинга в параметрах [Защитника Office 365.](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="3c4ce-145">Позволяет применять новую или обновленную политику в течение 30 минут.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="3c4ce-146">Сведения о том, где политики защиты от фишинга применяются в конвейере фильтрации, см. в сведениях о порядке и приоритете [защиты электронной почты.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="3c4ce-147">Использование Центра безопасности & соответствия требованиям для создания политик защиты от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="3c4ce-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="3c4ce-148">При создании настраиваемой политики защиты от фишинга в Центре безопасности и соответствия требованиям & создается правило защиты от фишинга и связанная с ним политика одновременно с одинаковым именем для обоих этих правил.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="3c4ce-149">При создании политики защиты от фишинга можно указать только имя политики, описание и фильтр получателей, определяющий, к кому применяется политика.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="3c4ce-150">После создания политики можно изменить политику, чтобы изменить или просмотреть параметры защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="3c4ce-151">В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами ATP для защиты от \>  \> **фишинга.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="3c4ce-152">На странице **"Антифишинг"** нажмите кнопку **"Создать".**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="3c4ce-153">Откроется **мастер создания политики защиты от фишинга.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="3c4ce-154">На странице **"Имя политики"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="3c4ce-155">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="3c4ce-156">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="3c4ce-157">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="3c4ce-158">На странице **"Применено к"** определите внутренних получателей, к которые применяется политика.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="3c4ce-159">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="3c4ce-160">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="3c4ce-161">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="3c4ce-162">Нажмите **кнопку "Добавить условие".**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-162">Click **Add a condition**.</span></span> <span data-ttu-id="3c4ce-163">В отобраложенном выпадаемом окном выберите условие в области **"Применено", если:**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="3c4ce-164">**Получатель:** указывает один или несколько почтовых ящиков, почтовых пользователей или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="3c4ce-165">**Получатель является членом**: указывает одну или несколько групп в организации.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="3c4ce-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="3c4ce-167">После выбора условия появится соответствующее dropdown с любым **из этих полей.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="3c4ce-168">Щелкните поле и прокрутите список выбранных значений.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="3c4ce-169">Щелкните поле и начните вводить текст, чтобы отфильтровать список и выбрать значение.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="3c4ce-170">Чтобы добавить дополнительные значения, щелкните пустую область в поле.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="3c4ce-171">Чтобы удалить отдельные записи, **щелкните значок "Удалить** ![ удалить" ](../../media/scc-remove-icon.png) в значении.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="3c4ce-172">Чтобы удалить все условие, щелкните **значок "Удалить** ![ удалить" ](../../media/scc-remove-icon.png) в этом условии.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="3c4ce-173">Чтобы добавить дополнительное условие, нажмите кнопку **"Добавить условие"** и выберите оставшееся значение **в области "Применено", если**.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="3c4ce-174">Чтобы добавить исключения, нажмите **кнопку "Добавить условие"** и выберите исключение в области **"Кроме случаев, когда"**.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="3c4ce-175">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="3c4ce-176">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="3c4ce-177">На странице **"Просмотр параметров"** просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="3c4ce-178">Вы можете нажать **кнопку "Изменить"** для каждого параметра, чтобы изменить его.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="3c4ce-179">После завершения нажмите кнопку **"Создать эту политику".**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="3c4ce-180">Нажмите **кнопку** "ОК" в от появляются диалоговое окно подтверждения.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="3c4ce-181">После создания политики защиты от фишинга с этими общими настройками используйте инструкции, указанные в следующем разделе, для настройки параметров защиты в политике.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="3c4ce-182">Использование Центра безопасности & соответствия требованиям для изменения политик защиты от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="3c4ce-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="3c4ce-183">Для изменения политик защиты от фишинга используйте следующие процедуры: новую политику, созданную вами, или существующие политики, которые вы уже настроили.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="3c4ce-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="3c4ce-185">Выберите настраиваемую политику защиты от фишинга, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="3c4ce-186">Если он уже выбран, отоберем его и снова выберите.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="3c4ce-187">Появится **flyout \<name\>** изменения политики.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="3c4ce-188">Если **щелкнуть "Изменить"** в любом разделе, вы сможете получить доступ к настройкам в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="3c4ce-189">Следующие действия представлены в том порядке, в который отображаются разделы, но они не являются последовательной (разделы можно выбрать и изменить в любом порядке).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="3c4ce-190">После нажатия кнопки "Изменить" в разделе доступные параметры будут представлены в формате мастера, но вы  можете перейти к  страницам в любом порядке, и вы можете нажать кнопку "Сохранить" на любой странице (или   ![ ](../../media/scc-remove-icon.png) **\<name\>** значок "Отмена или закрыть", чтобы вернуться на страницу "Изменить политику" (для сохранения или закрытия страницы не требуется перейти на последнюю страницу мастера).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="3c4ce-191">**Параметр политики:** **нажмите кнопку** "Изменить", чтобы изменить те же параметры, которые были доступны при создании политики [в](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) предыдущем разделе:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="3c4ce-192">**Название**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-192">**Name**</span></span>
   - <span data-ttu-id="3c4ce-193">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-193">**Description**</span></span>
   - <span data-ttu-id="3c4ce-194">**Применяется к**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-194">**Applied to**</span></span>
   - <span data-ttu-id="3c4ce-195">**Просмотр параметров**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-195">**Review your settings**</span></span>

   <span data-ttu-id="3c4ce-196">Когда все будет готово, нажмите кнопку **"Сохранить** на любой странице".</span><span class="sxs-lookup"><span data-stu-id="3c4ce-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="3c4ce-197">**Под вопросом:** **нажмите кнопку** "Изменить", чтобы изменить защищенных отправителей и защищенные домены в политике.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="3c4ce-198">Эти параметры являются условием для политики, которая определяет поддельных отправителей, которые должны искать (по отдельности или по домену) в адресе отправителей входящего сообщения.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="3c4ce-199">Дополнительные сведения см. в параметрах защиты от фишинга в Политиках защиты от фишинга в [Microsoft Defender для Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="3c4ce-200">**Добавление пользователей для защиты:** значение по умолчанию **— "Вы выключено".**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="3c4ce-201">Чтобы включить его, перейдите к кнопке "Включить" и нажмите кнопку "Добавить пользователя". </span><span class="sxs-lookup"><span data-stu-id="3c4ce-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="3c4ce-202">В от **сети "Добавление пользовательского** интерфейса" настройте следующие значения:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="3c4ce-203">**Адрес электронной почты:**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-203">**Email address**:</span></span>

       - <span data-ttu-id="3c4ce-204">Щелкните поле и прокрутите список выбранных пользователей.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="3c4ce-205">Щелкните поле и начните вводить текст, чтобы отфильтровать список и выбрать пользователя.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="3c4ce-206">Чтобы удалить запись, щелкните **значок "Удалить** ![ ](../../media/scc-remove-icon.png) удаление" для пользователя.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="3c4ce-207">**Name**: это значение заполняется на основе выбранного адреса электронной почты, но вы можете изменить его.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="3c4ce-208">Когда все будет готово, нажмите кнопку **"Сохранить** на любой странице".</span><span class="sxs-lookup"><span data-stu-id="3c4ce-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="3c4ce-209">Чтобы изменить существующую запись, выберите защищенного пользователя в списке.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="3c4ce-210">В каждой политике защиты от фишинга можно указать не более 60 защищенных пользователей (адреса электронной почты отправитель).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="3c4ce-211">Нельзя указать одного и того же защищенного пользователя в нескольких политиках.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="3c4ce-212">Защита от обезличения пользователя не работает, если отправитель и получатель ранее общались по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="3c4ce-213">Если отправитель и получатель никогда не общались по электронной почте, сообщение будет определено как попытка обезличения.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="3c4ce-214">**Добавьте домены для защиты:** настройте один или оба следующих параметра:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="3c4ce-215">**Автоматически включите домены, которые я владею:** значение по умолчанию **— "Вы выключено".**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-215">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="3c4ce-216">Чтобы включить его, переключите его на **"Вкл.".**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-216">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="3c4ce-217">**Включите настраиваемые домены:** значение по умолчанию **— Off.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-217">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="3c4ce-218">Чтобы включить его, перейдите к кнопке "Вкл." и в поле "Добавить домены" введите имя домена (например, contoso.com), нажмите ввод и повторите его при необходимости. </span><span class="sxs-lookup"><span data-stu-id="3c4ce-218">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="3c4ce-219">Во всех политиках защиты от фишинга можно использовать не более 50 доменов.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-219">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="3c4ce-220">**Действия:** нажмите **кнопку "Изменить"**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-220">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="3c4ce-221">Если **сообщение** отправляется ненастоящем пользователем: настройте одно из следующих действий для сообщений, в которых поддельный отправитель является одним из защищенных пользователей, указанных в добавлении пользователей для **защиты:**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-221">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="3c4ce-222">**Не применяйте никаких действий**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="3c4ce-223">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="3c4ce-224">**Переместить сообщение в папку "Нежелательная почта"**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="3c4ce-225">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="3c4ce-226">**Доставка сообщения и добавление других адресов в строку "СК"**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="3c4ce-227">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-227">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="3c4ce-228">Если электронная почта отправляется подмененным доменом: настройте одно из следующих действий для сообщений, в которых поддельный отправитель находится в одном из защищенных доменов, указанных в добавлении доменов для **защиты:**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-228">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="3c4ce-229">**Не применяйте никаких действий**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-229">**Don't apply any action**</span></span>
       - <span data-ttu-id="3c4ce-230">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-230">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="3c4ce-231">**Переместить сообщение в папку "Нежелательная почта"**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-231">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="3c4ce-232">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-232">**Quarantine the message**</span></span>
       - <span data-ttu-id="3c4ce-233">**Доставка сообщения и добавление других адресов в строку "СК"**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-233">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="3c4ce-234">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-234">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="3c4ce-235">Нажмите **кнопку "Включить советы по** безопасности для обезличения" и настройте любой из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-235">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="3c4ce-236">**Показать подсказку для ненастоященных** пользователей: значение по умолчанию **— "Вы выключено".**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-236">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="3c4ce-237">Чтобы включить его, переключите его на **"Вкл.".**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-237">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="3c4ce-238">**Показать подсказку для подхавенных доменов:** значение по умолчанию **— Off.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-238">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="3c4ce-239">Чтобы включить его, переключите его на **"Вкл.".**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-239">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="3c4ce-240">**Показать подсказку для необычных символов:** значение по умолчанию **— "Вы выключено".**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-240">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="3c4ce-241">Чтобы включить его, переключите его на **"Вкл.".**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-241">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="3c4ce-242">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="3c4ce-243">**Аналитика почтовых ящиков:**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="3c4ce-244">**Включить аналитику почтовых ящиков?** По умолчанию значение **"В включить".**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-244">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="3c4ce-245">Чтобы отключить его, переключите его на **выключение.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-245">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="3c4ce-246">Включить защиту от поднастояния на основе аналитики **почтовых ящиков?**— Этот параметр доступен, только если включить аналитику почтовых **ящиков?** </span><span class="sxs-lookup"><span data-stu-id="3c4ce-246">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="3c4ce-247">В случае отправки электронной почты ненастоящем пользователем можно указать одно из следующих действий для сообщений, не входящих в аналитику почтовых ящиков (те же действия, которые доступны для защищенных пользователей и защищенных доменов):</span><span class="sxs-lookup"><span data-stu-id="3c4ce-247">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="3c4ce-248">**Не применяйте никаких действий**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-248">**Don't apply any action**</span></span>
       - <span data-ttu-id="3c4ce-249">**Перенаправление сообщения на другие адреса электронной почты**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-249">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="3c4ce-250">**Переместить сообщение в папку "Нежелательная почта"**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-250">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="3c4ce-251">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-251">**Quarantine the message**</span></span>
       - <span data-ttu-id="3c4ce-252">**Доставка сообщения и добавление других адресов в строку "СК"**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-252">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="3c4ce-253">**Удаление сообщения перед его доставкой**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-253">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="3c4ce-254">**Добавление надежных отправителей и доменов:** укажите исключения для политики:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-254">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="3c4ce-255">**Надежные отправитые:**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-255">**Trusted senders**:</span></span>

       - <span data-ttu-id="3c4ce-256">Щелкните поле и прокрутите список выбранных пользователей.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-256">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="3c4ce-257">Щелкните поле и начните вводить текст, чтобы отфильтровать список и выбрать пользователя.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-257">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="3c4ce-258">Чтобы удалить запись, щелкните **значок "Удалить** ![ ](../../media/scc-remove-icon.png) удаление" для пользователя.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-258">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="3c4ce-259">**Доверенные домены:** введите имя домена (например, contoso.com), нажмите ввод и повторите его при необходимости.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-259">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="3c4ce-260">**Просмотрите параметры:** вместо нажатия каждого отдельного шага параметры отображаются в сводке.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-260">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="3c4ce-261">Можно **щелкнуть "Изменить"** в каждом разделе, чтобы вернуться на соответствующую страницу.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-261">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="3c4ce-262">Вы можете отключить или отключить  следующие параметры **непосредственно** на этой странице:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-262">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="3c4ce-263">**Защищенные пользователи**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-263">**Protected users**</span></span>
       - <span data-ttu-id="3c4ce-264">**Защищенные домены** \> **Включить собственные домены**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-264">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="3c4ce-265">**Защищенные домены** \> **Защищенные домены** (настраиваемые домены)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-265">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="3c4ce-266">**Аналитика почтовых ящиков**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-266">**Mailbox intelligence**</span></span>

   <span data-ttu-id="3c4ce-267">Когда все будет готово, нажмите кнопку **"Сохранить** на любой странице".</span><span class="sxs-lookup"><span data-stu-id="3c4ce-267">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="3c4ce-268">**Подмена:**  нажмите кнопку "Изменить", чтобы включить или отключить аналитику спуфингов, включите или отключите идентификацию отправителей, неавтериаленную идентификацию отправителей в Outlook, и настройте действие для применения к сообщениям от заблокированных поддельных отправителей.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-268">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="3c4ce-269">Дополнительные сведения [см. в параметрах спуфинга в](set-up-anti-phishing-policies.md#spoof-settings)политиках защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-269">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="3c4ce-270">Обратите внимание, что эти же параметры также доступны в политиках защиты от фишинга в EOP.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-270">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="3c4ce-271">**Параметры фильтра спуфинга:** значение по умолчанию — **"В** активе", и мы рекомендуем оставить его на месте.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-271">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="3c4ce-272">Чтобы отключить его, переключите его на **выключение.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-272">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="3c4ce-273">Дополнительные сведения см. в сведениях [о настройке аналитики спуфинга в EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-273">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="3c4ce-274">Вам не нужно отключать защиту от спуфинга, если запись MX не означает Microsoft 365; Вместо этого включается расширенная фильтрация для соединителя.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-274">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="3c4ce-275">Инструкции см. в [расширенной фильтрации соединителях в Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-275">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="3c4ce-276">**Включить функцию неавтоматического** отправитель : значение по умолчанию **" В.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-276">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="3c4ce-277">Чтобы отключить его, переключите его на **выключение.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-277">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="3c4ce-278">**Действия:** укажите действие, которое необходимо принять с сообщениями, которые не сбой аналитики подмены:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-278">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="3c4ce-279">**Если сообщение отправляется человеком, которому** запрещено подменять ваш домен:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-279">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="3c4ce-280">**Перемещение сообщения в папки нежелательной почты получателей**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-280">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="3c4ce-281">**Карантин сообщения**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-281">**Quarantine the message**</span></span>

   - <span data-ttu-id="3c4ce-282">**Просмотрите параметры:** вместо нажатия каждого отдельного шага параметры отображаются в сводке.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-282">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="3c4ce-283">Можно **щелкнуть "Изменить"** в каждом разделе, чтобы вернуться на соответствующую страницу.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-283">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="3c4ce-284">Вы можете отключить или отключить  следующие параметры **непосредственно** на этой странице:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-284">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="3c4ce-285">**Включить защиту от спуфинга**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-285">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="3c4ce-286">**Включить функцию "Отправителю, не проавентированному"**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-286">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="3c4ce-287">Когда все будет готово, нажмите кнопку **"Сохранить** на любой странице".</span><span class="sxs-lookup"><span data-stu-id="3c4ce-287">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="3c4ce-288">**Дополнительные параметры:** нажмите **кнопку** "Изменить", чтобы настроить расширенные пороговые значения фишинга.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-288">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="3c4ce-289">Дополнительные сведения см. в дополнительных пороговых значениях фишинга в политиках защиты от фишинга в [Microsoft Defender для Office 365.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-289">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="3c4ce-290">**Дополнительные пороговые значения фишинга:** выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-290">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="3c4ce-291">**1 — стандарт** (это значение по умолчанию).)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-291">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="3c4ce-292">**2 — агрессивный**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-292">**2 - Aggressive**</span></span>
   - <span data-ttu-id="3c4ce-293">**3 — более агрессивный**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-293">**3 - More aggressive**</span></span>
   - <span data-ttu-id="3c4ce-294">**4 — самый агрессивный**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-294">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="3c4ce-295">**Просмотрите параметры:** нажмите **кнопку** "Изменить", чтобы вернуться на страницу **"Расширенные** пороговые значения фишинга".</span><span class="sxs-lookup"><span data-stu-id="3c4ce-295">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="3c4ce-296">По завершению нажмите кнопку **"Сохранить"** на любой странице.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-296">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="3c4ce-297">На странице **"Изменение \<Name\> политики"** просмотрите параметры и нажмите кнопку **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-297">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="3c4ce-298">Использование Центра безопасности & соответствия требованиям для изменения политики защиты от фишинга по умолчанию в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="3c4ce-298">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="3c4ce-299">Политика защиты от фишинга по умолчанию в Microsoft Defender для Office 365 называется Office365 AntiPhish Default и не появляется в списке политик.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-299">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="3c4ce-300">Чтобы изменить политику защиты от фишинга по умолчанию, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-300">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="3c4ce-301">В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами ATP для защиты от \>  \> **фишинга.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="3c4ce-302">На странице **"Антифишинг"** щелкните политику **по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-302">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="3c4ce-303">Появится **страница "Изменение политики Office 365 по** умолчанию".</span><span class="sxs-lookup"><span data-stu-id="3c4ce-303">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="3c4ce-304">Доступны следующие разделы, которые содержат идентичные параметры при изменении [настраиваемой политики:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-304">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="3c4ce-305">**Олицетворение**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-305">**Impersonation**</span></span>
   - <span data-ttu-id="3c4ce-306">**Подмена**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-306">**Spoof**</span></span>
   - <span data-ttu-id="3c4ce-307">**Дополнительные параметры**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-307">**Advanced settings**</span></span>

   <span data-ttu-id="3c4ce-308">При изменении политики по умолчанию недоступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-308">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="3c4ce-309">Вы можете  увидеть раздел и значения параметров политики, но нет ссылки на изменение, поэтому изменить параметры (имя политики, описание и к кому применяется политика (применяется ко всем получателям)) нельзя. </span><span class="sxs-lookup"><span data-stu-id="3c4ce-309">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="3c4ce-310">Политику по умолчанию удалить нельзя.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-310">You can't delete the default policy.</span></span>
   - <span data-ttu-id="3c4ce-311">Вы не можете изменить приоритет политики по умолчанию (она всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-311">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="3c4ce-312">На странице **"Изменение политики Office 365** по умолчанию" просмотрите параметры и нажмите кнопку **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-312">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="3c4ce-313">Включить или отключить настраиваемые политики защиты от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="3c4ce-313">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="3c4ce-314">В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами ATP для защиты от \>  \> **фишинга.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-314">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="3c4ce-315">Обратите внимание на значение в **столбце "Состояние":**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-315">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="3c4ce-316">Переключите его, **чтобы** отключить политику.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-316">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="3c4ce-317">Чтобы включить политику,  передвигает его на "Вкл.".</span><span class="sxs-lookup"><span data-stu-id="3c4ce-317">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="3c4ce-318">Вы не можете отключить политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-318">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="3c4ce-319">Настройка приоритета пользовательских политик защиты от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="3c4ce-319">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="3c4ce-320">По умолчанию политикам защиты от фишинга предоставляется приоритет, основанный на порядке их создания (приоритет новых политик ниже, чем у старых).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-320">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="3c4ce-321">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-321">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="3c4ce-322">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-322">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="3c4ce-323">Дополнительные сведения о приоритетах, а также оценке и применении нескольких политик см. в статье [Порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-323">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="3c4ce-324">Настраиваемые политики защиты от фишинга отображаются в порядке их обработки (первая политика имеет значение **приоритета** 0).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-324">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="3c4ce-325">Политика защиты от фишинга по умолчанию с именем Office365 AntiPhish Default имеет настраиваемое значение приоритета **"Самый** низкий", и вы не можете изменить его.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-325">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="3c4ce-326">**Примечание.** В Центре & соответствия требованиям приоритет политики защиты от фишинга можно изменить только после ее создания.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-326">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="3c4ce-327">В PowerShell можно переопредить приоритет по умолчанию при создании правила защиты от фишинга (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-327">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="3c4ce-328">Чтобы изменить приоритет политики, нажмите  кнопку "Увеличить приоритет" или "Уменьшить приоритет" в свойствах  политики (нельзя напрямую изменить номер приоритета в Центре безопасности и соответствия & соответствия требованиям). </span><span class="sxs-lookup"><span data-stu-id="3c4ce-328">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="3c4ce-329">Изменение приоритета политики имеет смысл, только если имеется несколько политик.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-329">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="3c4ce-330">В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами ATP для защиты от \>  \> **фишинга.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-330">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="3c4ce-331">Выберите политику, которую нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-331">Select the policy that you want to modify.</span></span> <span data-ttu-id="3c4ce-332">Если он уже выбран, отоберем его и снова выберите.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-332">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="3c4ce-333">Появится **flyout \<name\>** изменения политики.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-333">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="3c4ce-334">Настраиваемая политика защиты от фишинга со значением **приоритета** **0** имеет только доступную кнопку "Уменьшить **приоритет".**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-334">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="3c4ce-335">В настраиваемой политике защиты  от фишинга с наименьшим значением приоритета (например, **3)** доступна только кнопка "Увеличить **приоритет".**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-335">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="3c4ce-336">Если у вас есть три или более пользовательских политик защиты от фишинга, политики  между самыми  высокими и минимальными значениями приоритета имеют доступные кнопки "Увеличить приоритет" и "Уменьшить приоритет".</span><span class="sxs-lookup"><span data-stu-id="3c4ce-336">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="3c4ce-337">Нажмите **кнопку "Увеличить приоритет"** или **"Уменьшить приоритет",** чтобы изменить **значение приоритета.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-337">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="3c4ce-338">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-338">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="3c4ce-339">Использование Центра безопасности & соответствия требованиям для просмотра политик защиты от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="3c4ce-339">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="3c4ce-340">В Центре безопасности & соответствия требованиям перейдите к политике управления угрозами ATP для защиты от  \>  \> **фишинга.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-340">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="3c4ce-341">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-341">Do one of the following steps:</span></span>

   - <span data-ttu-id="3c4ce-342">Выберите настраиваемую политику защиты от фишинга, которую необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-342">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="3c4ce-343">Если он уже выбран, отоберем его и снова выберите.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-343">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="3c4ce-344">Щелкните **политику по умолчанию,** чтобы просмотреть политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-344">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="3c4ce-345">Появится **flyout \<name\>** изменения политики, где можно просмотреть параметры и значения.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-345">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="3c4ce-346">Использование Центра безопасности & соответствия требованиям для удаления политик защиты от фишинга в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="3c4ce-346">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="3c4ce-347">В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами ATP для защиты от \>  \> **фишинга.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-347">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="3c4ce-348">Выберите политику, которую нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-348">Select the policy that you want to remove.</span></span> <span data-ttu-id="3c4ce-349">Если он уже выбран, отоберем его и снова выберите.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-349">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="3c4ce-350">В **отредактируемом \<name\>** окте "Изменить политику" щелкните "Удалить **политику",** а затем нажмите кнопку **"Да"** в отредактируемом диалоговом окле предупреждения.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-350">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="3c4ce-351">Политику по умолчанию удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-351">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="3c4ce-352">Настройка политик защиты от фишинга в Microsoft Defender для Office 365 с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c4ce-352">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="3c4ce-353">Как было описано выше, политика защиты от нежелательной почты состоит из политики защиты от фишинга и правила защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-353">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="3c4ce-354">В Exchange Online PowerShell разница между политиками защиты от фишинга и правилами защиты от фишинга очевидна.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-354">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="3c4ce-355">Вы управляете политиками защиты от фишинга с помощью cmdlets **\* -AntiPhishPolicy** и управляете правилами защиты от фишинга с помощью **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-355">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="3c4ce-356">В PowerShell сначала создается политика защиты от фишинга, а затем создается правило защиты от фишинга, которое определяет политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-356">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="3c4ce-357">В PowerShell параметры политики защиты от фишинга и правила защиты от фишинга изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-357">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="3c4ce-358">При удалении политики защиты от фишинга из PowerShell соответствующее правило не удаляется автоматически и наоборот.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-358">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="3c4ce-359">Создание политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c4ce-359">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="3c4ce-360">Создание политики защиты от фишинга в PowerShell — это двухшаговая процедура:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-360">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="3c4ce-361">Создайте политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-361">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="3c4ce-362">Создайте правило защиты от фишинга, которое определяет политику защиты от фишинга, к которую оно применяется.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-362">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="3c4ce-363">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-363">**Notes**:</span></span>

- <span data-ttu-id="3c4ce-364">Вы можете создать новое правило защиты от фишинга и назначить ему существующую несвязаную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-364">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="3c4ce-365">Правило защиты от фишинга не может быть связано с более чем одной политикой защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-365">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="3c4ce-366">Вы можете настроить следующие параметры для новых политик защиты от фишинга в PowerShell, которые недоступны в Центре безопасности & соответствия требованиям, пока не создайте политику:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-366">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="3c4ce-367">Создайте новую политику как отключенную _(включена_ `$false` в **cmdlet New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-367">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="3c4ce-368">Установите приоритет политики во время создания _(priority)_ в _\<Number\>_ **cmdlet New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-368">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="3c4ce-369">Новая политика защиты от фишинга, которую вы создаете в PowerShell, не отображается в Центре безопасности & соответствия требованиям, пока вы не назначите политику правилу защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-369">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="3c4ce-370">Шаг 1. Создание политики защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c4ce-370">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="3c4ce-371">Чтобы создать политику защиты от фишинга, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-371">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="3c4ce-372">В этом примере создается политика защиты от фишинга Research Quarantine со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-372">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="3c4ce-373">Политика включена (мы не используем параметр _Enabled,_ а по умолчанию используется `$true` значение).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-373">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="3c4ce-374">Описание: "Политика исследовательского отдела".</span><span class="sxs-lookup"><span data-stu-id="3c4ce-374">The description is: Research department policy.</span></span>
- <span data-ttu-id="3c4ce-375">Включает защиту доменов организации для всех принятых доменов и защиту целевых доменов для fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-375">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="3c4ce-376">Указывает, что защищать от имитации нужно пользователя Mai Fujito (mfujito@fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-376">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="3c4ce-377">Включает аналитику почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-377">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="3c4ce-378">Включает защиту аналитики почтовых ящиков и определяет действие карантина.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-378">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="3c4ce-379">Включает советы по безопасности.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-379">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="3c4ce-380">Подробные сведения о синтаксисе и параметрах см. в описании [New-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-380">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="3c4ce-381">Шаг 2. Создание правила защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c4ce-381">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="3c4ce-382">Чтобы создать правило защиты от фишинга, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-382">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="3c4ce-383">В этом примере создается правило защиты от фишинга Research Department со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-383">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="3c4ce-384">Правило связано с политикой защиты от фишинга Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-384">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="3c4ce-385">Правило применяется к членам группы "Research Department".</span><span class="sxs-lookup"><span data-stu-id="3c4ce-385">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="3c4ce-386">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-386">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="3c4ce-387">Подробные сведения о синтаксисе и параметрах см. в описании [New-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-387">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="3c4ce-388">Просмотр политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c4ce-388">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="3c4ce-389">Чтобы просмотреть существующие политики защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-389">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="3c4ce-390">В этом примере возвращается сводный список всех политик защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-390">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="3c4ce-391">В этом примере возвращаются все значения свойств для политики защиты от фишинга Executives.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-391">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="3c4ce-392">Подробные сведения о синтаксисе и параметрах см. в описании [Get-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-392">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="3c4ce-393">Просмотр правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c4ce-393">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="3c4ce-394">Чтобы просмотреть существующие правила защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-394">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="3c4ce-395">В этом примере возвращается сводный список всех правил защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-395">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="3c4ce-396">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-396">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="3c4ce-397">В этом примере возвращаются все значения свойств правила защиты от фишинга с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-397">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="3c4ce-398">Подробные сведения о синтаксисе и параметрах см. в описании [get-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-398">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="3c4ce-399">Изменение политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c4ce-399">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="3c4ce-400">Кроме следующих элементов, при изменении политики защиты от фишинга в PowerShell доступны те же параметры, что и при создании политики, как описано в шаге 1. Создание раздела политики защиты от фишинга с помощью [PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-400">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="3c4ce-401">Переключатель _MakeDefault,_ который превращает указанную политику в политику по  умолчанию (применяется для всех, всегда имеет самый низкий приоритет и вы не можете удалить ее), доступен только при изменении политики защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-401">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="3c4ce-402">Политику защиты от фишинга нельзя переименовать (у cmdlet **Set-AntiPhishPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="3c4ce-402">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="3c4ce-403">При переименовании политики защиты от фишинга в Центре безопасности и соответствия требованиям & только переименовывать правило защиты от _фишинга._</span><span class="sxs-lookup"><span data-stu-id="3c4ce-403">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="3c4ce-404">Чтобы изменить политику защиты от фишинга, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-404">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="3c4ce-405">Подробные сведения о синтаксисе и параметрах см. в описании [Set-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-405">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="3c4ce-406">Изменение правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c4ce-406">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="3c4ce-407">Единственным параметром, недоступным при изменении правила защиты от фишинга в PowerShell, является параметр _Enabled,_ позволяющий создать отключенное правило.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-407">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="3c4ce-408">Чтобы включить или отключить существующие правила защиты от фишинга, см. следующий раздел.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-408">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="3c4ce-409">В противном случае при изменении правила защиты от фишинга в PowerShell дополнительные параметры недоступны.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-409">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="3c4ce-410">Те же параметры доступны при создании правила, как описано в разделе "Шаг 2. Создание правила защиты от фишинга с помощью [PowerShell"](#step-2-use-powershell-to-create-an-anti-phish-rule) ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-410">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="3c4ce-411">Чтобы изменить правило защиты от фишинга, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-411">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="3c4ce-412">Подробные сведения о синтаксисе и параметрах см. в описании [set-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-412">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="3c4ce-413">Использование PowerShell для включаемого или отключения правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="3c4ce-413">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="3c4ce-414">Включение или отключение правила защиты от фишинга в PowerShell включает или отключает всю политику защиты от фишинга (правило защиты от фишинга и назначенную политику защиты от фишинга).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-414">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="3c4ce-415">Вы не можете включить или отключить политику защиты от фишинга по умолчанию (она всегда применяется для всех получателей).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-415">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="3c4ce-416">Чтобы включить или отключить правило защиты от фишинга в PowerShell, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-416">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="3c4ce-417">В этом примере отключается правило защиты от фишинга Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-417">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3c4ce-418">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-418">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3c4ce-419">Подробные сведения о синтаксисе и параметрах см. в описании [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) и [Disable-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-419">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="3c4ce-420">Настройка приоритета правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c4ce-420">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="3c4ce-421">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-421">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="3c4ce-422">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-422">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="3c4ce-423">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-423">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="3c4ce-424">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-424">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="3c4ce-425">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-425">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="3c4ce-426">Чтобы установить приоритет правила защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-426">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="3c4ce-p148">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="3c4ce-p148">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="3c4ce-429">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-429">**Notes**:</span></span>

- <span data-ttu-id="3c4ce-430">Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в вместо этого в cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-430">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="3c4ce-431">Политика защиты от фишинга по умолчанию не имеет соответствующего правила защиты от фишинга и всегда имеет немодифимируемый приоритет **"Самый низкий"**.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-431">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="3c4ce-432">Удаление политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c4ce-432">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="3c4ce-433">При удалении политики защиты от фишинга с помощью PowerShell соответствующее правило защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-433">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="3c4ce-434">Чтобы удалить политику защиты от фишинга в PowerShell, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-434">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="3c4ce-435">В этом примере удаляется политика защиты от фишинга Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-435">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="3c4ce-436">Подробные сведения о синтаксисе и параметрах см. в описании [remove-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-436">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="3c4ce-437">Удаление правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c4ce-437">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="3c4ce-438">При удалении правила защиты от фишинга с помощью PowerShell соответствующая политика защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-438">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="3c4ce-439">Чтобы удалить правило защиты от фишинга в PowerShell, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-439">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="3c4ce-440">В этом примере удаляется правило защиты от фишинга Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-440">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3c4ce-441">Подробные сведения о синтаксисе и параметрах см. в описании [remove-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="3c4ce-441">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="3c4ce-442">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="3c4ce-442">How do you know these procedures worked?</span></span>

<span data-ttu-id="3c4ce-443">Чтобы убедиться, что вы успешно настроили политики защиты от фишинга в Microsoft Defender для Office 365, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-443">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="3c4ce-444">В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами ATP для защиты от \>  \> **фишинга.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-444">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="3c4ce-445">Проверьте список политик, их значения **состояния** и их **значения приоритета.**</span><span class="sxs-lookup"><span data-stu-id="3c4ce-445">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="3c4ce-446">Чтобы просмотреть дополнительные сведения, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-446">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="3c4ce-447">Выберите политику в списке и просмотреть сведения во flyout.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-447">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="3c4ce-448">Щелкните **политику по умолчанию** и просмотрете сведения во flyout.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-448">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="3c4ce-449">В Exchange Online PowerShell замените имя политики или правила, а затем запустите следующую команду и проверьте \<Name\> параметры:</span><span class="sxs-lookup"><span data-stu-id="3c4ce-449">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
