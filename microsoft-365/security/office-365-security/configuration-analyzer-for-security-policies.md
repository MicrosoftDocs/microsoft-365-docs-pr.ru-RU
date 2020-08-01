---
title: Анализатор конфигурации для политик безопасности
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как использовать анализатор конфигураций для поиска и исправления политик безопасности, которые находятся ниже стандартной защиты и предварительно настроенных политик безопасности с ограниченной защитой.
ms.openlocfilehash: 259d498646ecf893a57a608a37e3b771083716cc
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533993"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="d7fc5-103">Анализатор конфигурации для политик защиты в EOP и Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="d7fc5-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="d7fc5-104">Функции, описанные в этой статье, в предварительной версии, недоступны во всех организациях и могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span>

<span data-ttu-id="d7fc5-105">Configuration Analyzer в центре безопасности & соответствия требованиям — это центральное место для поиска и исправления любых политик безопасности, которые содержат параметры, которые ниже стандартных параметров защиты и усиленной защиты профилей в [предустановленных политиках безопасности](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d7fc5-105">Configuration analyzer in the Security & Compliance center provides a central location to find and fix any of your security policies that contain settings that are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="d7fc5-106">Анализатором конфигурации анализируются следующие типы политик:</span><span class="sxs-lookup"><span data-stu-id="d7fc5-106">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="d7fc5-107">**Политики Exchange Online Protection (EOP)**: Это включает в себя организации Microsoft 365 с почтовыми ящиками Exchange Online и автономными организациями EOP без почтовых ящиков Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="d7fc5-107">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="d7fc5-108">[Политики защиты от нежелательной почты](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d7fc5-108">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="d7fc5-109">[Политики защиты от вредоносных программ](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d7fc5-109">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="d7fc5-110">[EOP политики защиты от фишинга](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="d7fc5-110">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="d7fc5-111">**Политики Office 365 Advanced Threat protection (ATP)**: включает в себя организации с Microsoft 365 или Office 365 дополнительные подписки на надстройки:</span><span class="sxs-lookup"><span data-stu-id="d7fc5-111">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="d7fc5-112">Политики защиты от фишинга ATP, которые включают:</span><span class="sxs-lookup"><span data-stu-id="d7fc5-112">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="d7fc5-113">[Параметры подделки](set-up-anti-phishing-policies.md#spoof-settings) , доступные в политиках защиты от фишинга EOP.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-113">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="d7fc5-114">Параметры олицетворения</span><span class="sxs-lookup"><span data-stu-id="d7fc5-114">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="d7fc5-115">Расширенные пороговые значения фишинга</span><span class="sxs-lookup"><span data-stu-id="d7fc5-115">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="d7fc5-116">[Политики безопасных ссылок](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="d7fc5-116">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span></span>

  - <span data-ttu-id="d7fc5-117">[Политики безопасных вложений](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="d7fc5-117">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span></span>

<span data-ttu-id="d7fc5-118">Значения **стандартных** и **ограниченных** параметров политики, используемые в качестве базовых, описаны в разделе [Рекомендуемые параметры для безопасности EOP и Office 365 ATP](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="d7fc5-118">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d7fc5-119">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="d7fc5-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d7fc5-120">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d7fc5-121">Чтобы перейти непосредственно на страницу **анализатора конфигурации** , используйте <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="d7fc5-121">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="d7fc5-122">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d7fc5-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="d7fc5-123">Чтобы вы могли выполнить процедуры, упомянутые в этой теме, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-123">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="d7fc5-124">Чтобы использовать анализатор конфигурации **и** внести изменения в политики безопасности, необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="d7fc5-124">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d7fc5-125">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d7fc5-125">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d7fc5-126">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="d7fc5-126">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="d7fc5-127">Для доступа только для чтения к анализатору конфигурации необходимо быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="d7fc5-127">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d7fc5-128">**Средство считывания сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d7fc5-128">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d7fc5-129">**Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="d7fc5-129">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="d7fc5-130">Использование анализатора конфигурации в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="d7fc5-130">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="d7fc5-131">В центре безопасности & соответствия требованиям откройте **Threat management** \> **Policy** \> **анализатор настройки**политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Мини-приложение "анализатор конфигурации" на странице "политика управления угрозой" \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="d7fc5-133">У анализатора конфигурации есть две основные вкладки:</span><span class="sxs-lookup"><span data-stu-id="d7fc5-133">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="d7fc5-134">**Параметры и рекомендации**: вы выбираете параметры Standard или Option и сравните эти параметры с существующими политиками безопасности.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-134">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="d7fc5-135">В результаты вы можете скорректировать значения параметров, чтобы они выстроили на тот же уровень, что и стандартный или ограниченный.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-135">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="d7fc5-136">**Анализ и история смещений конфигурации**: это представление позволяет отслеживать изменения, внесенные в политики на основе результатов анализатора конфигурации с течением времени.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-136">**Configuration drift analysis and history**: This view allows to track the changes that you've made to your policies based on the results of the configuration analyzer over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="d7fc5-137">Вкладка "Настройка и рекомендации" в анализаторе конфигурации</span><span class="sxs-lookup"><span data-stu-id="d7fc5-137">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="d7fc5-138">По умолчанию вкладка открывается при сравнении со стандартным профилем защиты.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-138">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="d7fc5-139">Чтобы переключиться на сравнение профиля с помощью ограниченной защиты, нажмите кнопку **Показать рекомендации**.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-139">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="d7fc5-140">Для обратного переключения выберите **Просмотр стандартных рекомендаций**.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-140">To switch back, select **View Standard recommendations**.</span></span>

![Представление "Параметры и рекомендации" в анализаторе конфигурации](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="d7fc5-142">По умолчанию столбец **Группа политик/имя параметра** содержит свернутое представление различных типов политик безопасности и число параметров в этих политиках, требующих улучшения (при их наличии).</span><span class="sxs-lookup"><span data-stu-id="d7fc5-142">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security polices and the number of settings in those policies that need improvement (if any).</span></span> <span data-ttu-id="d7fc5-143">Типы политик:</span><span class="sxs-lookup"><span data-stu-id="d7fc5-143">The types of policies are:</span></span>

- <span data-ttu-id="d7fc5-144">**Защита от нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="d7fc5-144">**Anti-spam**</span></span>
- <span data-ttu-id="d7fc5-145">**Защита от фишинга**</span><span class="sxs-lookup"><span data-stu-id="d7fc5-145">**Anti-phishing**</span></span>
- <span data-ttu-id="d7fc5-146">**Защита от вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="d7fc5-146">**Anti-malware**</span></span>
- <span data-ttu-id="d7fc5-147">**Безопасные вложения ATP** (если ваша подписка включает ATP)</span><span class="sxs-lookup"><span data-stu-id="d7fc5-147">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="d7fc5-148">**Безопасные ссылки ATP** (если ваша подписка включает ATP)</span><span class="sxs-lookup"><span data-stu-id="d7fc5-148">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="d7fc5-149">В представлении по умолчанию все свернуты.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-149">In the default view, everything is collapsed.</span></span> <span data-ttu-id="d7fc5-150">Рядом с каждой политикой отображается сводка результатов сравнения политик (которые можно изменить), а также параметры соответствующих политик для стандартных или ограниченных профилей (которые вы не можете изменить).</span><span class="sxs-lookup"><span data-stu-id="d7fc5-150">Next to each policy, a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify) are displayed.</span></span> <span data-ttu-id="d7fc5-151">Вы увидите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d7fc5-151">You'll see the following information:</span></span>

- <span data-ttu-id="d7fc5-152">**Зеленый**: все параметры во всех существующих политиках имеют по крайней мере такой же уровень безопасности, как и профиль защиты, с которым выполняется сравнение.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-152">**Green**: All settings in all existing policies are at least as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="d7fc5-153">**Оранжевый**: небольшое количество параметров в существующих политиках не является безопасным для профиля защиты, к которому выполняется сравнение.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-153">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="d7fc5-154">**Red**: значительное количество параметров в существующих политиках не является безопасным для профиля защиты, к которому выполняется сравнение.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-154">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span> <span data-ttu-id="d7fc5-155">Это может быть несколько параметров во многих политиках или нескольких параметрах в одной политике.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-155">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="d7fc5-156">Для получения наиболее благоприятных сравнений вы увидите текст: **All Settings следуйте** \<**Standard** or **Strict**\> **рекомендациям**.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-156">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="d7fc5-157">В противном случае вы увидите число рекомендуемых параметров для изменения.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-157">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="d7fc5-158">Если вы развернете **имя группы или параметра политики**, все политики и связанные с ними параметры в каждой политике, требующей внимания, будут отображены.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-158">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="d7fc5-159">Кроме того, можно развернуть определенный тип политики (например, **Защита от нежелательной почты**), чтобы увидеть только те параметры политик, которые требуют вашего внимания.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-159">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="d7fc5-160">Если сравнение не имеет рекомендаций по улучшению (зеленый), то расширение политики не открывает ничего.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-160">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="d7fc5-161">Если имеется любое количество рекомендаций по улучшению (оранжевый или красный), то параметры, требующие внимания, будут отображены, а соответствующая информация отображается в следующих столбцах:</span><span class="sxs-lookup"><span data-stu-id="d7fc5-161">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="d7fc5-162">Имя параметра, требующего вашего внимания.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-162">The name of the setting that requires your attention.</span></span> <span data-ttu-id="d7fc5-163">Например, на предыдущем снимке экрана это **пороговое значение групповой электронной почты** в политике защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-163">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="d7fc5-164">**Политика**: имя затронутой политики, содержащей параметр.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-164">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="d7fc5-165">**Применяется к**: количество пользователей, к которым применяются затронутые политики.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-165">**Applied to**: The number of user that the affected policies are applied to.</span></span>

- <span data-ttu-id="d7fc5-166">**Текущая конфигурация**: текущее значение параметра.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-166">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="d7fc5-167">Дата **последнего изменения**: Дата последнего изменения политики.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-167">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="d7fc5-168">**Рекомендации**: значение параметра в стандартном или ограниченном профиле защиты.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-168">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="d7fc5-169">Чтобы изменить значение параметра в политике в значение, соответствующее рекомендуемому значению в профиле защиты, нажмите кнопку **принять**.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-169">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="d7fc5-170">Если изменение прошло успешно, вы увидите сообщение: **рекомендации успешно приняты**.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-170">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="d7fc5-171">Нажмите кнопку **Обновить** , чтобы увидеть уменьшенное количество рекомендаций и удалить определенную строку параметров или политик из результатов.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-171">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="d7fc5-172">Вкладка "анализ и анализ сведений о смещении конфигурации" в анализаторе конфигурации</span><span class="sxs-lookup"><span data-stu-id="d7fc5-172">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="d7fc5-173">Эта вкладка позволяет отслеживать изменения, внесенные в пользовательские политики безопасности на основе сведений в анализаторе безопасности.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-173">This tab allows you to track the changes that you've made to your custom security policies based on the information in the security analyzer.</span></span> <span data-ttu-id="d7fc5-174">По умолчанию отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d7fc5-174">By default, the following information is displayed:</span></span>

- <span data-ttu-id="d7fc5-175">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="d7fc5-175">**Last modified**</span></span>
- <span data-ttu-id="d7fc5-176">**Кем изменено**</span><span class="sxs-lookup"><span data-stu-id="d7fc5-176">**Modified by**</span></span>
- <span data-ttu-id="d7fc5-177">**Имя параметра**</span><span class="sxs-lookup"><span data-stu-id="d7fc5-177">**Setting Name**</span></span>
- <span data-ttu-id="d7fc5-178">**Политика**</span><span class="sxs-lookup"><span data-stu-id="d7fc5-178">**Policy**</span></span>
- <span data-ttu-id="d7fc5-179">**Тип**</span><span class="sxs-lookup"><span data-stu-id="d7fc5-179">**Type**</span></span>

<span data-ttu-id="d7fc5-180">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-180">To filter the results, click **Filter**.</span></span> <span data-ttu-id="d7fc5-181">В появившемся всплывающем окне **фильтры** можно выбрать следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="d7fc5-181">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="d7fc5-182">Время **начала** и **время окончания** (дата)</span><span class="sxs-lookup"><span data-stu-id="d7fc5-182">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="d7fc5-183">**Стандартная защита** или **ограниченная защита**</span><span class="sxs-lookup"><span data-stu-id="d7fc5-183">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="d7fc5-184">Чтобы экспортировать результаты в CSV-файл, нажмите кнопку **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="d7fc5-184">To export the results to a .csv file, click **Export**.</span></span>

![Анализ и Просмотр сведений о смещении конфигурации в анализаторе конфигурации](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
