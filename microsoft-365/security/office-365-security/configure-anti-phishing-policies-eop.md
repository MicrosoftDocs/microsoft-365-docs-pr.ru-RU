---
title: Настройка политик защиты от фишинга в EOP
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
description: Администраторы могут узнать, как создавать, изменять и удалять политики защиты от фишинга, доступные в организациях Exchange Online Protection (EOP) с почтовыми ящиками Exchange Online или без них.
ms.openlocfilehash: 770990cdd7927ebb8afa088f2d5be09c75824d59
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949275"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="45f0c-103">Настройка политик защиты от фишинга в EOP</span><span class="sxs-lookup"><span data-stu-id="45f0c-103">Configure anti-phishing policies in EOP</span></span>

<span data-ttu-id="45f0c-104">Организации Office 365 с почтовыми ящиками Exchange Online и отдельными организациями Exchange Online Protection (EOP) без почтовых ящиков Exchange Online имеют политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="45f0c-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes have a default anti-phishing policy.</span></span> <span data-ttu-id="45f0c-105">Эта политика содержит ограниченное число функций защиты от спуфинга, которые включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="45f0c-105">This policy contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="45f0c-106">Дополнительные сведения см в разделе [Параметры подделки в политиках защиты от фишинга](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="45f0c-106">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="45f0c-107">Администраторы могут просматривать, изменять и настраивать (но не удалять) политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="45f0c-107">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="45f0c-108">Для большей детализации можно также создать настраиваемые политики защиты от фишинга, которые применяются к определенным пользователям, группам или доменам в Организации.</span><span class="sxs-lookup"><span data-stu-id="45f0c-108">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="45f0c-109">Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="45f0c-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="45f0c-110">В организациях с почтовыми ящиками Exchange Online можно настраивать политики защиты от фишинга в центре безопасности & соответствия требованиям или в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="45f0c-110">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="45f0c-111">Изолированные Организации EOP могут использовать только центр безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="45f0c-111">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="45f0c-112">Сведения о создании и изменении дополнительных политик защиты от фишинга ATP, доступных в Office 365 Advanced Threat Protection, приведены в разделе [Настройка политик защиты от фишинга ATP в office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="45f0c-112">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="anti-phishing-policies-in-the-security--compliance-center-vs-exchange-online-powershell"></a><span data-ttu-id="45f0c-113">Политики защиты от фишинга в центре безопасности & соответствия требованиям VS Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="45f0c-113">Anti-phishing policies in the Security & Compliance Center vs Exchange Online PowerShell</span></span>

<span data-ttu-id="45f0c-114">Основные элементы политики защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="45f0c-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="45f0c-115">**Политика защиты от фишинга**: определяет защиту от фишинга, которую необходимо включить или отключить, а также действия, которые необходимо применить к параметрам.</span><span class="sxs-lookup"><span data-stu-id="45f0c-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="45f0c-116">**Правило защиты от фишинга**: определяет приоритет и фильтры получателей (к которым применяется политика) для политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="45f0c-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="45f0c-117">Различия между этими двумя элементами не очевидны при управлении политиками защиты от фишинга в центре безопасности & соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="45f0c-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="45f0c-118">Когда вы создаете политику защиты от фишинга в центре безопасности & соответствия требованиям, вы фактически создаете правило защиты от фишинга и связанную политику антифишинга одновременно с одним и тем же именем.</span><span class="sxs-lookup"><span data-stu-id="45f0c-118">When you create an anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="45f0c-119">При изменении политики защиты от фишинга в центре безопасности & соответствия требованиям параметры, связанные с фильтрами "имя", "приоритет", "включено" или "отключено" и "фильтры получателей", изменяют правило защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="45f0c-119">When you modify an anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="45f0c-120">Все остальные параметры изменяют соответствующую политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="45f0c-120">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="45f0c-121">При удалении антифишинговой политики из центра безопасности & соответствия требованиям, удаляются правило защиты от фишинга и связанная с ним политика защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="45f0c-121">When you remove an anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="45f0c-122">В Exchange Online PowerShell разница между политиками защиты от фишинга и правилами защиты от фишинга очевидна.</span><span class="sxs-lookup"><span data-stu-id="45f0c-122">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="45f0c-123">Вы управляете политиками защиты от фишинга с помощью командлетов \*\* \*-AntiPhishPolicy\*\* , а также управляете правилами защиты от фишинга с помощью командлетов \*\* \*-AntiPhishRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="45f0c-123">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="45f0c-124">В PowerShell сначала создается политика защиты от фишинга, затем создается правило защиты от фишинга, идентифицирующее политику, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="45f0c-124">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="45f0c-125">В PowerShell параметры политики защиты от фишинга и антифишинга изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="45f0c-125">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="45f0c-126">Политика защиты от фишинга по умолчанию ATP</span><span class="sxs-lookup"><span data-stu-id="45f0c-126">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="45f0c-127">Каждая организация имеет встроенную политику защиты от фишинга Office365 по умолчанию, которая имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="45f0c-127">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="45f0c-128">Политика с именем Office365 Anti фишинг применяется ко всем получателям в Организации, несмотря на то, что не существует правила защиты от фишинга (фильтры получателей), связанные с этой политикой.</span><span class="sxs-lookup"><span data-stu-id="45f0c-128">The policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="45f0c-129">Политика с именем Office365 по умолчанию имеет значение приоритета, которое **меньше** , чем недоступно для изменения (политика всегда применяется последней).</span><span class="sxs-lookup"><span data-stu-id="45f0c-129">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="45f0c-130">Все создаваемые настраиваемые политики всегда имеют более высокий приоритет, чем политика с именем Office365 по умолчанию, отличная от фишинга.</span><span class="sxs-lookup"><span data-stu-id="45f0c-130">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="45f0c-131">Политика с именем Office365-фишинг по умолчанию является политикой **по умолчанию (свойство IsDefault** имеет значение `True`), и вы не можете удалить политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="45f0c-131">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="45f0c-132">Чтобы повысить эффективность защиты от фишинга, можно создать настраиваемые политики защиты от фишинга с помощью более четких параметров, применяемых к определенным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="45f0c-132">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="45f0c-133">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="45f0c-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="45f0c-134">Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="45f0c-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="45f0c-135">Чтобы перейти непосредственно на страницу **защиты от фишинга** , используйте <https://protection.office.com/antiphishing>.</span><span class="sxs-lookup"><span data-stu-id="45f0c-135">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="45f0c-136">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="45f0c-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="45f0c-137">Вы не можете управлять политиками защиты от фишинга в изолированной EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="45f0c-137">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="45f0c-138">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="45f0c-138">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="45f0c-139">Для добавления, изменения и удаления политик защиты от фишинга необходимо быть членом группы ролей " **Управление организацией** " или " **администратор безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="45f0c-139">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="45f0c-140">Для доступа только для чтения к политикам защиты от фишинга необходимо быть участником группы ролей " **читатель безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="45f0c-140">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="45f0c-141">Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="45f0c-141">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="45f0c-142">Чтобы иметь возможность создавать и изменять политики защиты от нежелательной почты в автономных EOP, необходимо выполнить некоторые действия, требующие _гидратации_ для вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="45f0c-142">To be able to create and modify anti-spam policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="45f0c-143">Например, в центре администрирования Exchange можно перейти на вкладку **разрешения** , выбрать существующую группу ролей, щелкнуть **изменить** ![значок](../../media/ITPro-EAC-EditIcon.png)редактирования и удалить роль (которая, в конечном итоге, будет добавлена обратно).</span><span class="sxs-lookup"><span data-stu-id="45f0c-143">For example, in the EAC, you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="45f0c-144">Если ваш клиент никогда не заходился в процессе восстановления, вы получите диалоговое окно с именем **Обновление параметров Организации** с индикатором выполнения, который должен завершиться успешно.</span><span class="sxs-lookup"><span data-stu-id="45f0c-144">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="45f0c-145">Дополнительные сведения о гидратации можно найти в разделе [Enable-организатионкустомизатион](https://docs.microsoft.com/powershell/module/exchange/organization/enable-organizationcustomization) (недоступен в изолированном EOP PowerShell или в центре безопасности & соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="45f0c-145">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/organization/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="45f0c-146">Рекомендуемые параметры политик защиты от фишинга приведены в статье [EOP Default Anti-фишингового политики](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="45f0c-146">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="45f0c-147">Разрешить применение обновленной политики до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="45f0c-147">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="45f0c-148">Сведения о том, когда политики защиты от фишинга применяются в конвейере фильтрации, приведены в статье [порядок и приоритет защиты электронной почты в Office 365](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="45f0c-148">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection in Office 365](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="45f0c-149">Использование центра безопасности & соответствия требованиям для создания политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="45f0c-149">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="45f0c-150">Создание настраиваемой политики защиты от фишинга в центре безопасности & соответствия требованиям создает правило защиты от фишинга и сопоставленную политику защиты от фишинга одновременно с одним и тем же именем.</span><span class="sxs-lookup"><span data-stu-id="45f0c-150">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="45f0c-151">При создании политики защиты от фишинга можно указать только имя политики, описание и фильтр получателей, которые определяют, к кому применяется политика.</span><span class="sxs-lookup"><span data-stu-id="45f0c-151">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="45f0c-152">После создания политики вы можете изменить политику, чтобы изменить или просмотреть параметры защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="45f0c-152">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="45f0c-153">В центре безопасности & соответствия требованиям перейдите к разделу \> **Политика** \> **управления угрозами** : **Защита от фишинга**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="45f0c-154">На странице **Защита от фишинга** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-154">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="45f0c-155">Откроется мастер **создания новой политики защиты от фишинга** .</span><span class="sxs-lookup"><span data-stu-id="45f0c-155">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="45f0c-156">На странице " **назвать политику** " настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="45f0c-156">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="45f0c-157">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="45f0c-157">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="45f0c-158">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="45f0c-158">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="45f0c-159">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-159">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="45f0c-160">На появившейся странице " **применено к** " определите внутренних получателей, к которым применяется политика.</span><span class="sxs-lookup"><span data-stu-id="45f0c-160">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="45f0c-161">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="45f0c-161">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="45f0c-162">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<получатель1\>_ or _\<получатель2\>_).</span><span class="sxs-lookup"><span data-stu-id="45f0c-162">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="45f0c-163">Между разными условиями и исключениями используется оператор AND (например, _\<получатель1\>_ and _\<участник группы 1\>_).</span><span class="sxs-lookup"><span data-stu-id="45f0c-163">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="45f0c-164">Нажмите кнопку **Добавить условие**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-164">Click **Add a condition**.</span></span> <span data-ttu-id="45f0c-165">В появившемся раскрывающемся меню выберите условие **применено, если**:</span><span class="sxs-lookup"><span data-stu-id="45f0c-165">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="45f0c-166">**Получатель**: указывает один или несколько почтовых ящиков, почтовых пользователей или почтовых контактов в Организации.</span><span class="sxs-lookup"><span data-stu-id="45f0c-166">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="45f0c-167">**Получатель является участником**: указывает одну или несколько групп в Организации.</span><span class="sxs-lookup"><span data-stu-id="45f0c-167">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="45f0c-168">**Домен получателя**. Указывает получателей из одного или нескольких настроенных обслуживаемых доменов в Office 365.</span><span class="sxs-lookup"><span data-stu-id="45f0c-168">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in Office 365.</span></span>

   <span data-ttu-id="45f0c-169">После выбора условия появится соответствующее раскрывающийся список с **одним из этих** полей.</span><span class="sxs-lookup"><span data-stu-id="45f0c-169">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="45f0c-170">Щелкните поле и прокрутите список выбираемых значений.</span><span class="sxs-lookup"><span data-stu-id="45f0c-170">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="45f0c-171">Щелкните поле и начните ввод текста, чтобы отфильтровать список и выбрать значение.</span><span class="sxs-lookup"><span data-stu-id="45f0c-171">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="45f0c-172">Чтобы добавить дополнительные значения, щелкните пустую область в поле.</span><span class="sxs-lookup"><span data-stu-id="45f0c-172">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="45f0c-173">Чтобы удалить отдельные записи, нажмите кнопку **Удалить** ![значок](../../media/scc-remove-icon.png) "Удалить" на значении.</span><span class="sxs-lookup"><span data-stu-id="45f0c-173">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="45f0c-174">Чтобы удалить условие целиком, нажмите кнопку **Удалить** ![значок](../../media/scc-remove-icon.png) "Удалить" в условии.</span><span class="sxs-lookup"><span data-stu-id="45f0c-174">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="45f0c-175">Чтобы добавить дополнительное условие, щелкните **Добавить условие** и выберите оставшееся значение в разделе **применено, если**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-175">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="45f0c-176">Чтобы добавить исключения, щелкните **Добавить условие** и выберите исключение в разделе **за исключением if**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-176">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="45f0c-177">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="45f0c-177">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="45f0c-178">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-178">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="45f0c-179">На открывшейся странице **Проверьте параметры** проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="45f0c-179">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="45f0c-180">Для изменения каждого параметра можно нажать кнопку **изменить** .</span><span class="sxs-lookup"><span data-stu-id="45f0c-180">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="45f0c-181">По завершении нажмите кнопку **создать эту политику**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-181">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="45f0c-182">Нажмите кнопку **ОК** в появившемся диалоговом окне подтверждения.</span><span class="sxs-lookup"><span data-stu-id="45f0c-182">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="45f0c-183">После создания политики защиты от фишинга с помощью этих общих параметров политики используйте инструкции, приведенные в следующем разделе, для настройки параметров защиты в политике.</span><span class="sxs-lookup"><span data-stu-id="45f0c-183">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="45f0c-184">Использование центра безопасности & соответствия требованиям для изменения политик защиты от фишинговых атак</span><span class="sxs-lookup"><span data-stu-id="45f0c-184">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="45f0c-185">Используйте следующие процедуры для изменения политик защиты от фишинга: созданной вами новой политики или существующей ранее настроенной политики.</span><span class="sxs-lookup"><span data-stu-id="45f0c-185">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="45f0c-186">Если вы еще не сделали это, откройте центр безопасности & соответствия требованиям и перейдите к **антифишингу** \> **политики** \> **управления угрозами** .</span><span class="sxs-lookup"><span data-stu-id="45f0c-186">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="45f0c-187">Выберите настраиваемую политику защиты от фишинга, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="45f0c-187">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="45f0c-188">Если он уже выбран, отмените его выбор и снова выберите его.</span><span class="sxs-lookup"><span data-stu-id="45f0c-188">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="45f0c-189">Откроется всплывающее окно \*\* \<изменение\> имени политики\*\* .</span><span class="sxs-lookup"><span data-stu-id="45f0c-189">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="45f0c-190">Если щелкнуть **изменить** в любом разделе, вы получите доступ к параметрам в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="45f0c-190">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="45f0c-191">Следующие действия представлены в порядке их появления, но не являются последовательными (можно выбирать и изменять разделы в любом порядке).</span><span class="sxs-lookup"><span data-stu-id="45f0c-191">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="45f0c-192">После нажатия кнопки **изменить** в разделе Доступные параметры отображаются в формате мастера, но можно переходить между страницами в любом порядке, а можно нажать кнопку **сохранить** на любой странице (или **отменить** или **Закрыть** ![значок](../../media/scc-remove-icon.png) закрыть, чтобы вернуться на страницу **изменение имени \<\> политики** (не обязательно посещать последнюю страницу мастера, чтобы сохранить или оставить).</span><span class="sxs-lookup"><span data-stu-id="45f0c-192">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="45f0c-193">**Параметр политики**: нажмите кнопку **изменить** , чтобы изменить параметры, которые были доступны при [создании политики](#use-the-security--compliance-center-to-create-anti-phishing-policies) , описанной в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="45f0c-193">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="45f0c-194">**Название**</span><span class="sxs-lookup"><span data-stu-id="45f0c-194">**Name**</span></span>
   - <span data-ttu-id="45f0c-195">**Описание**</span><span class="sxs-lookup"><span data-stu-id="45f0c-195">**Description**</span></span>
   - <span data-ttu-id="45f0c-196">**Применяется к**</span><span class="sxs-lookup"><span data-stu-id="45f0c-196">**Applied to**</span></span>
   - <span data-ttu-id="45f0c-197">**Проверка параметров**</span><span class="sxs-lookup"><span data-stu-id="45f0c-197">**Review your settings**</span></span>

   <span data-ttu-id="45f0c-198">По завершении нажмите кнопку **сохранить** на любой странице.</span><span class="sxs-lookup"><span data-stu-id="45f0c-198">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="45f0c-199">**Подделка**: нажмите кнопку **изменить** , чтобы включить или отключить логику операций подделки, Отключить идентификацию отправителей, не прошедших проверку подлинности, в Outlook, а также настроить действие, применяемое к сообщениям от заблокированных поддельных отправителей.</span><span class="sxs-lookup"><span data-stu-id="45f0c-199">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="45f0c-200">Дополнительные сведения см в разделе [Параметры подделки в политиках защиты от фишинга](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="45f0c-200">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="45f0c-201">Обратите внимание, что эти же параметры также доступны в политиках защиты от фишинга ATP.</span><span class="sxs-lookup"><span data-stu-id="45f0c-201">Note that these same settings are also available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="45f0c-202">**Параметры фильтра подделки**: значение по умолчанию — **включено**, и мы рекомендуем оставить его.</span><span class="sxs-lookup"><span data-stu-id="45f0c-202">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="45f0c-203">Чтобы отключить его, установите переключатель в значение **выкл**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-203">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="45f0c-204">Дополнительные сведения см. в статье [Настройка аналитики подделки в Office 365](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="45f0c-204">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="45f0c-205">Отключение защиты от спуфинга не требуется, если запись MX не указывает на Office 365; Вместо этого вы включите расширенную фильтрацию для соединителей.</span><span class="sxs-lookup"><span data-stu-id="45f0c-205">You don't need to disable anti-spoofing protection if your MX record doesn't point to Office 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="45f0c-206">Инструкции см в разделе [Расширенная фильтрация соединителей в Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="45f0c-206">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="45f0c-207">**Включить функцию отправителя, не прошедший проверку подлинности**: значение по умолчанию: **включено**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-207">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="45f0c-208">Чтобы отключить его, установите переключатель в значение **выкл**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-208">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="45f0c-209">**Действия**: укажите действие, которое следует предпринять для сообщений, не прошедших анализ подделки:</span><span class="sxs-lookup"><span data-stu-id="45f0c-209">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="45f0c-210">**Если сообщение электронной почты отправлено пользователем, который не может подменить ваш домен**:</span><span class="sxs-lookup"><span data-stu-id="45f0c-210">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="45f0c-211">**Перемещение сообщения в папки "Нежелательная почта" получателей**</span><span class="sxs-lookup"><span data-stu-id="45f0c-211">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="45f0c-212">**Помещать сообщение в карантин**</span><span class="sxs-lookup"><span data-stu-id="45f0c-212">**Quarantine the message**</span></span>

   - <span data-ttu-id="45f0c-213">**Проверьте параметры**: вместо того, чтобы щелкать каждый отдельный шаг, параметры отображаются в сводке.</span><span class="sxs-lookup"><span data-stu-id="45f0c-213">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="45f0c-214">Вы можете щелкнуть **изменить** в каждом разделе, чтобы вернуться на соответствующую страницу.</span><span class="sxs-lookup"><span data-stu-id="45f0c-214">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="45f0c-215">Вы можете включать и **отключать** следующие параметры **непосредственно на этой** странице:</span><span class="sxs-lookup"><span data-stu-id="45f0c-215">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="45f0c-216">**Включение защиты от спуфинга**</span><span class="sxs-lookup"><span data-stu-id="45f0c-216">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="45f0c-217">**Включение функции отправителя без проверки подлинности**</span><span class="sxs-lookup"><span data-stu-id="45f0c-217">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="45f0c-218">По завершении нажмите кнопку **сохранить** на любой странице.</span><span class="sxs-lookup"><span data-stu-id="45f0c-218">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="45f0c-219">Вернитесь на страницу **изменение имени\> политики \<** , проверьте параметры и нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-219">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="45f0c-220">Использование центра безопасности & соответствия требованиям для изменения политики защиты от фишинга по умолчанию</span><span class="sxs-lookup"><span data-stu-id="45f0c-220">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="45f0c-221">По умолчанию политика защиты от фишинга называется Office365 по умолчанию и не отображается в списке политик.</span><span class="sxs-lookup"><span data-stu-id="45f0c-221">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="45f0c-222">Чтобы изменить политику защиты от фишинга по умолчанию, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="45f0c-222">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="45f0c-223">В центре безопасности & соответствия требованиям перейдите к разделу \> **Политика** \> **управления угрозами** : **Защита от фишинга**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-223">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="45f0c-224">На странице **Защита от фишинга** щелкните **Политика по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-224">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="45f0c-225">Откроется страница **изменение политики Office365 антифишинга по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="45f0c-225">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="45f0c-226">Доступны следующие разделы, которые содержат идентичные параметры при [изменении настраиваемой политики](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="45f0c-226">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="45f0c-227">**Олицетворение**</span><span class="sxs-lookup"><span data-stu-id="45f0c-227">**Impersonation**</span></span>
   - <span data-ttu-id="45f0c-228">**Спуфинг**</span><span class="sxs-lookup"><span data-stu-id="45f0c-228">**Spoof**</span></span>
   - <span data-ttu-id="45f0c-229">**Дополнительные параметры**</span><span class="sxs-lookup"><span data-stu-id="45f0c-229">**Advanced settings**</span></span>

   <span data-ttu-id="45f0c-230">При изменении политики по умолчанию недоступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="45f0c-230">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="45f0c-231">Вы можете увидеть раздел и значения **параметра политики** , но нет ссылки для **редактирования** , поэтому вы не можете изменить параметры (имя политики, описание и пользователей, к которым применяется политика (она применяется ко всем получателям)).</span><span class="sxs-lookup"><span data-stu-id="45f0c-231">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="45f0c-232">Вы не можете удалить политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="45f0c-232">You can't delete the default policy.</span></span>
   - <span data-ttu-id="45f0c-233">Невозможно изменить приоритет политики по умолчанию (всегда применяется последний).</span><span class="sxs-lookup"><span data-stu-id="45f0c-233">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="45f0c-234">На странице **изменение политики Office365 Антифишинг по умолчанию** проверьте параметры и нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-234">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="45f0c-235">Включение и отключение настраиваемых политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="45f0c-235">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="45f0c-236">В центре безопасности & соответствия требованиям перейдите к разделу \> **Политика** \> **управления угрозами** : **Защита от фишинга**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-236">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="45f0c-237">Обратите внимание на значение в столбце **состояние** :</span><span class="sxs-lookup"><span data-stu-id="45f0c-237">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="45f0c-238">Чтобы отключить политику, на слайде переключитесь в режим **выключен** .</span><span class="sxs-lookup"><span data-stu-id="45f0c-238">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="45f0c-239">Чтобы включить политику, на слайде установите переключатель в значение **вкл** .</span><span class="sxs-lookup"><span data-stu-id="45f0c-239">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="45f0c-240">Отключить политику защиты от фишинга по умолчанию невозможно.</span><span class="sxs-lookup"><span data-stu-id="45f0c-240">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="45f0c-241">Установка приоритета настраиваемых политик защиты от фишинговых фишинговых атак</span><span class="sxs-lookup"><span data-stu-id="45f0c-241">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="45f0c-242">По умолчанию политикам защиты от фишинга назначается приоритет, основанный на порядке их создания (более новые политики имеют более низкий приоритет, чем старые политики).</span><span class="sxs-lookup"><span data-stu-id="45f0c-242">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="45f0c-243">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="45f0c-243">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="45f0c-244">Приоритеты двух политик не могут совпадать.</span><span class="sxs-lookup"><span data-stu-id="45f0c-244">No two policies can have the same priority.</span></span>

<span data-ttu-id="45f0c-245">Настраиваемые политики защиты от фишинга отображаются в порядке их обработки (первая политика имеет значение **приоритета** 0).</span><span class="sxs-lookup"><span data-stu-id="45f0c-245">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="45f0c-246">По умолчанию политика защиты от фишинга с именем Office365 по умолчанию имеет **самый низкий**приоритет, и вы не можете изменить его.</span><span class="sxs-lookup"><span data-stu-id="45f0c-246">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="45f0c-247">**Note**: в центре безопасности & соответствия требованиям можно изменить приоритет политики защиты от фишинга после ее создания.</span><span class="sxs-lookup"><span data-stu-id="45f0c-247">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="45f0c-248">В PowerShell можно переопределить приоритет по умолчанию при создании правила защиты от фишинга (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="45f0c-248">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="45f0c-249">Чтобы изменить приоритет политики, щелкните **увеличить** или **уменьшить** приоритет в свойствах политики (нельзя напрямую изменить номер **приоритета** в центре безопасности & соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="45f0c-249">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="45f0c-250">Изменение приоритета политики имеет смысл только в том случае, если у вас есть несколько политик.</span><span class="sxs-lookup"><span data-stu-id="45f0c-250">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="45f0c-251">В центре безопасности & соответствия требованиям перейдите к разделу \> **Политика** \> **управления угрозами** для **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-251">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="45f0c-252">Выберите политику, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="45f0c-252">Select the policy that you want to modify.</span></span> <span data-ttu-id="45f0c-253">Если он уже выбран, отмените его выбор и снова выберите его.</span><span class="sxs-lookup"><span data-stu-id="45f0c-253">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="45f0c-254">Откроется всплывающее окно \*\* \<изменение\> имени политики\*\* .</span><span class="sxs-lookup"><span data-stu-id="45f0c-254">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="45f0c-255">Для настраиваемой политики защиты от фишинга со значением **приоритета** **0** будет доступна только кнопка " **уменьшить приоритет** ".</span><span class="sxs-lookup"><span data-stu-id="45f0c-255">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="45f0c-256">Для настраиваемой политики защиты от фишинга с наименьшим значением **приоритета** (например, **3**) доступна только кнопка **повышения приоритета** .</span><span class="sxs-lookup"><span data-stu-id="45f0c-256">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="45f0c-257">При наличии трех или более настраиваемых политик защиты от фишинга для политик между максимальным и минимальным значениями приоритета доступны кнопки **увеличить приоритет** и **уменьшить приоритет** .</span><span class="sxs-lookup"><span data-stu-id="45f0c-257">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="45f0c-258">Щелкните **увеличить** или **уменьшить** приоритет, чтобы изменить значение **приоритета** .</span><span class="sxs-lookup"><span data-stu-id="45f0c-258">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="45f0c-259">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-259">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="45f0c-260">Использование центра безопасности & соответствия требованиям для просмотра политик защиты от фишинговых фишинговых атак</span><span class="sxs-lookup"><span data-stu-id="45f0c-260">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="45f0c-261">В центре безопасности & соответствия требованиям и перейдите к **антифишингу** \> **политики** \> **управления угрозами** .</span><span class="sxs-lookup"><span data-stu-id="45f0c-261">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="45f0c-262">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="45f0c-262">Do one of the following steps:</span></span>

   - <span data-ttu-id="45f0c-263">Выберите настраиваемую политику защиты от фишинга, которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="45f0c-263">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="45f0c-264">Если он уже выбран, отмените его выбор и снова выберите его.</span><span class="sxs-lookup"><span data-stu-id="45f0c-264">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="45f0c-265">Щелкните **политику по умолчанию** , чтобы просмотреть политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="45f0c-265">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="45f0c-266">Откроется всплывающее окно \*\* \<изменение\> имени политики\*\* , в котором можно просмотреть параметры и значения.</span><span class="sxs-lookup"><span data-stu-id="45f0c-266">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="45f0c-267">Использование центра безопасности & соответствия требованиям для удаления политик защиты от фишинговых атак</span><span class="sxs-lookup"><span data-stu-id="45f0c-267">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="45f0c-268">В центре безопасности & соответствия требованиям перейдите к разделу \> **Политика** \> **управления угрозами** : **Защита от фишинга**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-268">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="45f0c-269">Выберите политику, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="45f0c-269">Select the policy that you want to remove.</span></span> <span data-ttu-id="45f0c-270">Если он уже выбран, отмените его выбор и снова выберите его.</span><span class="sxs-lookup"><span data-stu-id="45f0c-270">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="45f0c-271">В появившемся всплывающем окне **изменение имени \<\> политики** щелкните **удалить политику**, а затем нажмите кнопку **Да** в появившемся диалоговом окне предупреждения.</span><span class="sxs-lookup"><span data-stu-id="45f0c-271">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="45f0c-272">Политику по умолчанию удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="45f0c-272">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="45f0c-273">Настройка политик защиты от фишинга с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="45f0c-273">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="45f0c-274">Следующие процедуры недоступны в автономных организациях EOP.</span><span class="sxs-lookup"><span data-stu-id="45f0c-274">The following procedures aren't available in standalone EOP organizations.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="45f0c-275">Создание политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="45f0c-275">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="45f0c-276">Создание политики защиты от фишинга в PowerShell состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="45f0c-276">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="45f0c-277">Создайте политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="45f0c-277">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="45f0c-278">Создайте правило защиты от фишинга, которое определяет политику защиты от фишинга, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="45f0c-278">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="45f0c-279">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="45f0c-279">**Notes**:</span></span>

- <span data-ttu-id="45f0c-280">Вы можете создать новое правило защиты от фишинга и назначить для него существующую, несвязанную политику защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="45f0c-280">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="45f0c-281">Правило защиты от фишинга не может быть связано с несколькими политиками защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="45f0c-281">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="45f0c-282">Вы можете настроить следующие параметры для новых политик защиты от фишинга в PowerShell, которые недоступны в центре безопасности & соответствия требованиям, пока не будет создана политика:</span><span class="sxs-lookup"><span data-stu-id="45f0c-282">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="45f0c-283">Создайте новую политику как отключенную (_включена_ `$false` в командлете **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="45f0c-283">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="45f0c-284">Задайте приоритет политики во время создания (_приоритет_ _ \<\>) для_командлета **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="45f0c-284">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="45f0c-285">Новая политика защиты от фишинга, созданная в PowerShell, не отображается в центре безопасности & соответствия требованиям, пока вы не назначите политику для правила защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="45f0c-285">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="45f0c-286">Шаг 1: использование PowerShell для создания политики защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="45f0c-286">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="45f0c-287">Чтобы создать политику защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="45f0c-287">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="45f0c-288">В этом примере создается политика защиты от фишинга с именем Research карантин со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="45f0c-288">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="45f0c-289">Политика включена (параметр _Enabled_ не используется, а значение по умолчанию — `$true`).</span><span class="sxs-lookup"><span data-stu-id="45f0c-289">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="45f0c-290">Описание: "политика отделов исследований".</span><span class="sxs-lookup"><span data-stu-id="45f0c-290">The description is: Research department policy.</span></span>
- <span data-ttu-id="45f0c-291">Изменение действия по умолчанию для подмены в карантине.</span><span class="sxs-lookup"><span data-stu-id="45f0c-291">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="45f0c-292">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="45f0c-292">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="45f0c-293">Шаг 2: использование PowerShell для создания правила защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="45f0c-293">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="45f0c-294">Чтобы создать правило защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="45f0c-294">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="45f0c-295">В этом примере создается правило защиты от фишинга с именем "Отдел исследований" со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="45f0c-295">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="45f0c-296">Правило связано с политикой защиты от фишинга с именем "карантин исследований".</span><span class="sxs-lookup"><span data-stu-id="45f0c-296">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="45f0c-297">Правило применяется к членам группы "Research Department".</span><span class="sxs-lookup"><span data-stu-id="45f0c-297">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="45f0c-298">Так как мы не используем параметр _Priority_ , используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="45f0c-298">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="45f0c-299">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="45f0c-299">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="45f0c-300">Просмотр политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="45f0c-300">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="45f0c-301">Чтобы просмотреть существующие политики защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="45f0c-301">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="45f0c-302">В этом примере возвращается сводный список всех политик защиты от фишинга вместе с заданными свойствами.</span><span class="sxs-lookup"><span data-stu-id="45f0c-302">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="45f0c-303">В этом примере возвращаются все значения свойств для политики защиты от фишинга под названием "руководители".</span><span class="sxs-lookup"><span data-stu-id="45f0c-303">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="45f0c-304">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="45f0c-304">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="45f0c-305">Просмотр правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="45f0c-305">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="45f0c-306">Чтобы просмотреть существующие правила защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="45f0c-306">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="45f0c-307">В этом примере возвращается сводный список всех правил защиты от фишинга вместе с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="45f0c-307">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="45f0c-308">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="45f0c-308">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="45f0c-309">В этом примере возвращаются все значения свойств для правила защиты от фишинга Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="45f0c-309">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="45f0c-310">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="45f0c-310">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="45f0c-311">Использование PowerShell для изменения политик защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="45f0c-311">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="45f0c-312">Кроме следующих элементов, одни и те же параметры доступны при изменении политики защиты от фишинга в PowerShell, как при создании политики, как описано в [шаге 1: с помощью PowerShell создайте раздел политики защиты от фишинга](#step-1-use-powershell-to-create-an-anti-phish-policy) , приведенный ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="45f0c-312">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="45f0c-313">Переключатель _македефаулт_ , который включает указанную политику в политику по умолчанию (применяется ко всем, всегда **самый низкий** приоритет и не может удалить его), доступна только при изменении политики защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="45f0c-313">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="45f0c-314">Вы не можете переименовать политику защиты от фишинга (командлет **Set-AntiPhishPolicy** не имеет параметра _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="45f0c-314">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="45f0c-315">При переименовании политики защиты от фишинга в центре безопасности & соответствия требованиям Вы переименовываете только _правило_защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="45f0c-315">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="45f0c-316">Чтобы изменить политику защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="45f0c-316">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="45f0c-317">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="45f0c-317">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="45f0c-318">Использование PowerShell для изменения правил защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="45f0c-318">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="45f0c-319">Единственный параметр, недоступный при изменении правила защиты от фишинга в PowerShell — это параметр _Enabled_ , позволяющий создать отключенное правило.</span><span class="sxs-lookup"><span data-stu-id="45f0c-319">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="45f0c-320">Чтобы включить или отключить существующие правила защиты от фишинга, ознакомьтесь со статьей в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="45f0c-320">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="45f0c-321">В противном случае дополнительные параметры не будут доступны при изменении правила защиты от фишинга в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="45f0c-321">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="45f0c-322">Те же параметры доступны при создании правила, как описано в [шаге 2: используйте PowerShell для создания раздела правила защиты от фишинга](#step-2-use-powershell-to-create-an-anti-phish-rule) , приведенного ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="45f0c-322">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="45f0c-323">Чтобы изменить правило защиты от фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="45f0c-323">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="45f0c-324">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="45f0c-324">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="45f0c-325">Включение и отключение правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="45f0c-325">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="45f0c-326">Включение или отключение правила защиты от фишинга в PowerShell включает или отключает всю политику защиты от фишинга (правило защиты от фишинга и назначенную политику защиты от фишинга).</span><span class="sxs-lookup"><span data-stu-id="45f0c-326">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="45f0c-327">Вы не можете включать или отключать политику защиты от фишинга по умолчанию (всегда применяется ко всем получателям).</span><span class="sxs-lookup"><span data-stu-id="45f0c-327">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="45f0c-328">Чтобы включить или отключить правило защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="45f0c-328">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="45f0c-329">В этом примере отключается правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="45f0c-329">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="45f0c-330">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="45f0c-330">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="45f0c-331">Подробные сведения о синтаксисе и параметрах можно найти в статье [Enable – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) and [Disable – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="45f0c-331">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="45f0c-332">Настройка приоритета правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="45f0c-332">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="45f0c-333">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="45f0c-333">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="45f0c-334">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="45f0c-334">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="45f0c-335">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="45f0c-335">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="45f0c-336">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="45f0c-336">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="45f0c-337">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="45f0c-337">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="45f0c-338">Чтобы задать приоритет правила защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="45f0c-338">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="45f0c-p137">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="45f0c-p137">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="45f0c-341">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="45f0c-341">**Notes**:</span></span>

- <span data-ttu-id="45f0c-342">Чтобы задать приоритет нового правила при его создании, используйте параметр _Priority_ в командлете **New – AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="45f0c-342">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="45f0c-343">По умолчанию политика защиты от фишинга не имеет соответствующего правила защиты от фишинга и имеет **самое низкое**значение приоритета.</span><span class="sxs-lookup"><span data-stu-id="45f0c-343">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="45f0c-344">Удаление политик защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="45f0c-344">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="45f0c-345">При использовании PowerShell для удаления политики защиты от фишинга соответствующее правило защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="45f0c-345">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="45f0c-346">Чтобы удалить политику защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="45f0c-346">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="45f0c-347">В этом примере удаляется политика защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="45f0c-347">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="45f0c-348">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="45f0c-348">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="45f0c-349">Удаление правил защиты от фишинга с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="45f0c-349">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="45f0c-350">При использовании PowerShell для удаления правила защиты от фишинга соответствующая политика защиты от фишинга не удаляется.</span><span class="sxs-lookup"><span data-stu-id="45f0c-350">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="45f0c-351">Чтобы удалить правило защиты от фишинга в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="45f0c-351">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="45f0c-352">В этом примере удаляется правило защиты от фишинга с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="45f0c-352">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="45f0c-353">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="45f0c-353">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="45f0c-354">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="45f0c-354">How do you know these procedures worked?</span></span>

<span data-ttu-id="45f0c-355">Чтобы убедиться в успешной настройке политик защиты от фишинга ATP, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="45f0c-355">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="45f0c-356">В центре безопасности & соответствия требованиям перейдите к разделу \> **Политика** \> **управления угрозами** : **Защита от фишинга**.</span><span class="sxs-lookup"><span data-stu-id="45f0c-356">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="45f0c-357">Проверьте список политик, их значения **состояния** и значения **приоритета** .</span><span class="sxs-lookup"><span data-stu-id="45f0c-357">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="45f0c-358">Чтобы просмотреть дополнительные сведения, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="45f0c-358">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="45f0c-359">Выберите политику из списка и просмотрите сведения в всплывающем меню.</span><span class="sxs-lookup"><span data-stu-id="45f0c-359">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="45f0c-360">Щелкните **Политика по умолчанию** и просмотрите сведения в всплывающем меню.</span><span class="sxs-lookup"><span data-stu-id="45f0c-360">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="45f0c-361">В Exchange Online PowerShell замените \<имя\> именем политики или правила и выполните следующую команду и проверьте параметры:</span><span class="sxs-lookup"><span data-stu-id="45f0c-361">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
