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
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как использовать анализатор конфигураций для поиска и исправления политик безопасности, которые находятся ниже стандартных политик защиты и предварительно установленных политик безопасности с ограниченной защитой.
ms.openlocfilehash: 1429bddc5ae5f8409ad4f3593f7ea236b13f854c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846476"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="b9d21-103">Анализатор конфигурации для политик защиты в EOP и защитнике Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="b9d21-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="b9d21-104">Функции, описанные в этой статье, в предварительной версии, недоступны во всех организациях и могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="b9d21-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span> <span data-ttu-id="b9d21-105">За сведениями о расписании выпуска, ознакомьтесь с [планом Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span><span class="sxs-lookup"><span data-stu-id="b9d21-105">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span></span>

<span data-ttu-id="b9d21-106">Configuration Analyzer в центре безопасности & соответствия требованиям — централизованное расположение для поиска и исправления политик безопасности, в которых параметры находятся ниже стандартных параметров защиты и усиленной защиты профилей в [предустановленных политиках безопасности](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b9d21-106">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="b9d21-107">Анализатором конфигурации анализируются следующие типы политик:</span><span class="sxs-lookup"><span data-stu-id="b9d21-107">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="b9d21-108">**Политики Exchange Online Protection (EOP)** : Это включает в себя организации Microsoft 365 с почтовыми ящиками Exchange Online и автономными организациями EOP без почтовых ящиков Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="b9d21-108">**Exchange Online Protection (EOP) policies** : This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="b9d21-109">[Политики защиты от нежелательной почты](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b9d21-109">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="b9d21-110">[Политики защиты от вредоносных программ](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b9d21-110">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="b9d21-111">[EOP политики защиты от фишинга](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="b9d21-111">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="b9d21-112">**Защитник Майкрософт для office 365 политики** : Это включает в себя организации с Microsoft 365 или защитник для Office 365 подписки на надстройки:</span><span class="sxs-lookup"><span data-stu-id="b9d21-112">**Microsoft Defender for Office 365 policies** : This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="b9d21-113">Политики защиты от фишинга в защитнике Microsoft для Office 365, которые включают:</span><span class="sxs-lookup"><span data-stu-id="b9d21-113">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="b9d21-114">[Параметры подделки](set-up-anti-phishing-policies.md#spoof-settings) , доступные в политиках защиты от фишинга EOP.</span><span class="sxs-lookup"><span data-stu-id="b9d21-114">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="b9d21-115">Параметры олицетворения</span><span class="sxs-lookup"><span data-stu-id="b9d21-115">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="b9d21-116">Расширенные пороговые значения фишинга</span><span class="sxs-lookup"><span data-stu-id="b9d21-116">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="b9d21-117">[Политики безопасных ссылок](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b9d21-117">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="b9d21-118">[Политики безопасных вложений](set-up-atp-safe-attachments-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b9d21-118">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="b9d21-119">Значения **стандартных** и **ограниченных** параметров политики, используемые в качестве базовых, описаны в разделе [Рекомендуемые параметры для безопасности EOP и Microsoft Defender для Office 365](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="b9d21-119">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b9d21-120">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="b9d21-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b9d21-121">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b9d21-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b9d21-122">Чтобы перейти непосредственно на страницу **анализатора конфигурации** , используйте <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="b9d21-122">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="b9d21-123">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b9d21-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="b9d21-124">Прежде чем выполнять процедуры, описанные в этой статье, необходимо назначить разрешения.</span><span class="sxs-lookup"><span data-stu-id="b9d21-124">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="b9d21-125">Чтобы использовать анализатор конфигурации **и** внести изменения в политики безопасности, необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="b9d21-125">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="b9d21-126">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b9d21-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="b9d21-127">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="b9d21-127">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="b9d21-128">Для доступа только для чтения к анализатору конфигурации необходимо быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="b9d21-128">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="b9d21-129">**Средство считывания сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b9d21-129">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="b9d21-130">**Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="b9d21-130">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="b9d21-131">Использование анализатора конфигурации в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="b9d21-131">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="b9d21-132">В центре безопасности & соответствия требованиям откройте **Threat management** \> **Policy** \> **анализатор настройки** политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="b9d21-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Мини-приложение "анализатор конфигурации" на странице "политика управления угрозой" \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="b9d21-134">У анализатора конфигурации есть две основные вкладки:</span><span class="sxs-lookup"><span data-stu-id="b9d21-134">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="b9d21-135">**Параметры и рекомендации** : вы выбираете параметры Standard или Option и сравните эти параметры с существующими политиками безопасности.</span><span class="sxs-lookup"><span data-stu-id="b9d21-135">**Settings and recommendations** : You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="b9d21-136">В результаты вы можете скорректировать значения параметров, чтобы они выстроили на тот же уровень, что и стандартный или ограниченный.</span><span class="sxs-lookup"><span data-stu-id="b9d21-136">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="b9d21-137">**Анализ и история смещений конфигурации** : это представление позволяет отслеживать изменения политики с течением времени.</span><span class="sxs-lookup"><span data-stu-id="b9d21-137">**Configuration drift analysis and history** : This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="b9d21-138">Вкладка "Настройка и рекомендации" в анализаторе конфигурации</span><span class="sxs-lookup"><span data-stu-id="b9d21-138">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="b9d21-139">По умолчанию вкладка открывается при сравнении со стандартным профилем защиты.</span><span class="sxs-lookup"><span data-stu-id="b9d21-139">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="b9d21-140">Чтобы переключиться на сравнение профиля с помощью ограниченной защиты, нажмите кнопку **Показать рекомендации**.</span><span class="sxs-lookup"><span data-stu-id="b9d21-140">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="b9d21-141">Для обратного переключения выберите **Просмотр стандартных рекомендаций**.</span><span class="sxs-lookup"><span data-stu-id="b9d21-141">To switch back, select **View Standard recommendations**.</span></span>

![Представление "Параметры и рекомендации" в анализаторе конфигурации](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="b9d21-143">По умолчанию столбец **Группа политик/имя параметра** содержит свернутое представление различных типов политик безопасности и число параметров, требующих улучшения (если они есть).</span><span class="sxs-lookup"><span data-stu-id="b9d21-143">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="b9d21-144">Типы политик:</span><span class="sxs-lookup"><span data-stu-id="b9d21-144">The types of policies are:</span></span>

- <span data-ttu-id="b9d21-145">**Защита от нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="b9d21-145">**Anti-spam**</span></span>
- <span data-ttu-id="b9d21-146">**Защита от фишинга**</span><span class="sxs-lookup"><span data-stu-id="b9d21-146">**Anti-phishing**</span></span>
- <span data-ttu-id="b9d21-147">**Защита от вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="b9d21-147">**Anti-malware**</span></span>
- <span data-ttu-id="b9d21-148">**Безопасное вложение ATP** (если ваша подписка включает защитник Майкрософт для Office 365)</span><span class="sxs-lookup"><span data-stu-id="b9d21-148">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="b9d21-149">**Безопасные ссылки ATP** (если ваша подписка включает защитник Майкрософт для Office 365)</span><span class="sxs-lookup"><span data-stu-id="b9d21-149">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="b9d21-150">В представлении по умолчанию все свернуты.</span><span class="sxs-lookup"><span data-stu-id="b9d21-150">In the default view, everything is collapsed.</span></span> <span data-ttu-id="b9d21-151">Рядом с каждой политикой есть сводка результатов сравнения политик (которые можно изменить), а также параметров соответствующих политик для стандартных или ограниченных профилей защиты (которые невозможно изменить).</span><span class="sxs-lookup"><span data-stu-id="b9d21-151">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="b9d21-152">Для профиля защиты, к которому выполняется сравнение, отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="b9d21-152">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="b9d21-153">**Зеленый** : все параметры во всех существующих политиках имеют по крайней мере такой же уровень безопасности, что и профиль защиты.</span><span class="sxs-lookup"><span data-stu-id="b9d21-153">**Green** : All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="b9d21-154">**Оранжевый** : небольшое количество параметров в существующих политиках не является безопасным для профиля защиты.</span><span class="sxs-lookup"><span data-stu-id="b9d21-154">**Amber** : A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="b9d21-155">**Red** : значительное количество параметров в существующих политиках не является безопасным для профиля защиты.</span><span class="sxs-lookup"><span data-stu-id="b9d21-155">**Red** : A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="b9d21-156">Это может быть несколько параметров во многих политиках или нескольких параметрах в одной политике.</span><span class="sxs-lookup"><span data-stu-id="b9d21-156">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="b9d21-157">Для получения наиболее благоприятных сравнений вы увидите текст: **All Settings следуйте** \<**Standard** or **Strict**\> **рекомендациям**.</span><span class="sxs-lookup"><span data-stu-id="b9d21-157">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="b9d21-158">В противном случае вы увидите число рекомендуемых параметров для изменения.</span><span class="sxs-lookup"><span data-stu-id="b9d21-158">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="b9d21-159">Если вы развернете **имя группы или параметра политики** , все политики и связанные с ними параметры в каждой политике, требующей внимания, будут отображены.</span><span class="sxs-lookup"><span data-stu-id="b9d21-159">If you expand **Policy group/setting name** , all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="b9d21-160">Кроме того, можно развернуть определенный тип политики (например, **Защита от нежелательной почты** ), чтобы увидеть только те параметры политик, которые требуют вашего внимания.</span><span class="sxs-lookup"><span data-stu-id="b9d21-160">Or, you can expand a specific type of policy (for example, **Anti-spam** ) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="b9d21-161">Если сравнение не имеет рекомендаций по улучшению (зеленый), то расширение политики не открывает ничего.</span><span class="sxs-lookup"><span data-stu-id="b9d21-161">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="b9d21-162">Если имеется любое количество рекомендаций по улучшению (оранжевый или красный), то параметры, требующие внимания, будут отображены, а соответствующая информация отображается в следующих столбцах:</span><span class="sxs-lookup"><span data-stu-id="b9d21-162">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="b9d21-163">Имя параметра, требующего вашего внимания.</span><span class="sxs-lookup"><span data-stu-id="b9d21-163">The name of the setting that requires your attention.</span></span> <span data-ttu-id="b9d21-164">Например, на предыдущем снимке экрана это **пороговое значение групповой электронной почты** в политике защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="b9d21-164">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="b9d21-165">**Политика** : имя затронутой политики, содержащей параметр.</span><span class="sxs-lookup"><span data-stu-id="b9d21-165">**Policy** : The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="b9d21-166">**Применяется к** : количество пользователей, к которым применяются затронутые политики.</span><span class="sxs-lookup"><span data-stu-id="b9d21-166">**Applied to** : The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="b9d21-167">**Текущая конфигурация** : текущее значение параметра.</span><span class="sxs-lookup"><span data-stu-id="b9d21-167">**Current configuration** : The current value of the setting.</span></span>

- <span data-ttu-id="b9d21-168">Дата **последнего изменения** : Дата последнего изменения политики.</span><span class="sxs-lookup"><span data-stu-id="b9d21-168">**Last modified** : The date that the policy was last modified.</span></span>

- <span data-ttu-id="b9d21-169">**Рекомендации** : значение параметра в стандартном или ограниченном профиле защиты.</span><span class="sxs-lookup"><span data-stu-id="b9d21-169">**Recommendations** : The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="b9d21-170">Чтобы изменить значение параметра в политике в значение, соответствующее рекомендуемому значению в профиле защиты, нажмите кнопку **принять**.</span><span class="sxs-lookup"><span data-stu-id="b9d21-170">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="b9d21-171">Если изменение прошло успешно, вы увидите сообщение: **рекомендации успешно приняты**.</span><span class="sxs-lookup"><span data-stu-id="b9d21-171">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="b9d21-172">Нажмите кнопку **Обновить** , чтобы увидеть уменьшенное количество рекомендаций и удалить определенную строку параметров или политик из результатов.</span><span class="sxs-lookup"><span data-stu-id="b9d21-172">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="b9d21-173">Вкладка "анализ и анализ сведений о смещении конфигурации" в анализаторе конфигурации</span><span class="sxs-lookup"><span data-stu-id="b9d21-173">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="b9d21-174">Эта вкладка позволяет отслеживать изменения, внесенные в пользовательские политики безопасности.</span><span class="sxs-lookup"><span data-stu-id="b9d21-174">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="b9d21-175">По умолчанию отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="b9d21-175">By default, the following information is displayed:</span></span>

- <span data-ttu-id="b9d21-176">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="b9d21-176">**Last modified**</span></span>
- <span data-ttu-id="b9d21-177">**Кем изменено**</span><span class="sxs-lookup"><span data-stu-id="b9d21-177">**Modified by**</span></span>
- <span data-ttu-id="b9d21-178">**Имя параметра**</span><span class="sxs-lookup"><span data-stu-id="b9d21-178">**Setting Name**</span></span>
- <span data-ttu-id="b9d21-179">**Политика**</span><span class="sxs-lookup"><span data-stu-id="b9d21-179">**Policy**</span></span>
- <span data-ttu-id="b9d21-180">**Тип**</span><span class="sxs-lookup"><span data-stu-id="b9d21-180">**Type**</span></span>

<span data-ttu-id="b9d21-181">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="b9d21-181">To filter the results, click **Filter**.</span></span> <span data-ttu-id="b9d21-182">В появившемся всплывающем окне **фильтры** можно выбрать следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="b9d21-182">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="b9d21-183">Время **начала** и **время окончания** (дата)</span><span class="sxs-lookup"><span data-stu-id="b9d21-183">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="b9d21-184">**Стандартная защита** или **ограниченная защита**</span><span class="sxs-lookup"><span data-stu-id="b9d21-184">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="b9d21-185">Чтобы экспортировать результаты в CSV-файл, нажмите кнопку **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="b9d21-185">To export the results to a .csv file, click **Export**.</span></span>

![Анализ и Просмотр сведений о смещении конфигурации в анализаторе конфигурации](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
