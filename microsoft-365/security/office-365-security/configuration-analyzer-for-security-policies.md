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
ms.openlocfilehash: 5a57e16dcac6afee910ce546d3a40c2c9c669f2d
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616156"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="58e7a-103">Анализатор конфигурации для политик защиты в EOP и защитнике Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="58e7a-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="58e7a-104">Функции, описанные в этой статье, в предварительной версии, недоступны во всех организациях и могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="58e7a-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span> <span data-ttu-id="58e7a-105">За сведениями о расписании выпуска, ознакомьтесь с [планом Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span><span class="sxs-lookup"><span data-stu-id="58e7a-105">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span></span>

<span data-ttu-id="58e7a-106">Configuration Analyzer в центре безопасности & соответствия требованиям — централизованное расположение для поиска и исправления политик безопасности, в которых параметры находятся ниже стандартных параметров защиты и усиленной защиты профилей в [предустановленных политиках безопасности](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="58e7a-106">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="58e7a-107">Анализатором конфигурации анализируются следующие типы политик:</span><span class="sxs-lookup"><span data-stu-id="58e7a-107">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="58e7a-108">**Политики Exchange Online Protection (EOP)**: Это включает в себя организации Microsoft 365 с почтовыми ящиками Exchange Online и автономными организациями EOP без почтовых ящиков Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="58e7a-108">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="58e7a-109">[Политики защиты от нежелательной почты](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="58e7a-109">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="58e7a-110">[Политики защиты от вредоносных программ](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="58e7a-110">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="58e7a-111">[EOP политики защиты от фишинга](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="58e7a-111">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="58e7a-112">**Защитник Майкрософт для office 365 политики**: Это включает в себя организации с Microsoft 365 или защитник для Office 365 подписки на надстройки:</span><span class="sxs-lookup"><span data-stu-id="58e7a-112">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="58e7a-113">Политики защиты от фишинга в защитнике Microsoft для Office 365, которые включают:</span><span class="sxs-lookup"><span data-stu-id="58e7a-113">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="58e7a-114">[Параметры подделки](set-up-anti-phishing-policies.md#spoof-settings) , доступные в политиках защиты от фишинга EOP.</span><span class="sxs-lookup"><span data-stu-id="58e7a-114">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="58e7a-115">Параметры олицетворения</span><span class="sxs-lookup"><span data-stu-id="58e7a-115">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="58e7a-116">Расширенные пороговые значения фишинга</span><span class="sxs-lookup"><span data-stu-id="58e7a-116">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="58e7a-117">[Политики безопасных ссылок](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="58e7a-117">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="58e7a-118">[Политики безопасных вложений](set-up-atp-safe-attachments-policies.md).</span><span class="sxs-lookup"><span data-stu-id="58e7a-118">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="58e7a-119">Значения **стандартных** и **ограниченных** параметров политики, используемые в качестве базовых, описаны в разделе [Рекомендуемые параметры для безопасности EOP и Microsoft Defender для Office 365](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="58e7a-119">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="58e7a-120">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="58e7a-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="58e7a-121">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="58e7a-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="58e7a-122">Чтобы перейти непосредственно на страницу **анализатора конфигурации** , используйте <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="58e7a-122">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="58e7a-123">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="58e7a-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="58e7a-124">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="58e7a-124">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="58e7a-125">Чтобы использовать анализатор конфигурации **и** внести изменения в политики безопасности, необходимо быть участником группы ролей " **Управление организацией** " или " **администратор безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="58e7a-125">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="58e7a-126">Для доступа только для чтения к анализатору конфигурации необходимо быть членом группы ролей " **глобальный читатель** " или " **читатель безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="58e7a-126">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="58e7a-127">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="58e7a-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="58e7a-128">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="58e7a-128">**Notes**:</span></span>

  - <span data-ttu-id="58e7a-129">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="58e7a-129">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="58e7a-130">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="58e7a-130">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="58e7a-131">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="58e7a-131">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="58e7a-132">Использование анализатора конфигурации в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="58e7a-132">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="58e7a-133">В центре безопасности & соответствия требованиям откройте  \>  \> **анализатор настройки** политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="58e7a-133">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Мини-приложение "анализатор конфигурации" на странице "политика управления угрозой" \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="58e7a-135">У анализатора конфигурации есть две основные вкладки:</span><span class="sxs-lookup"><span data-stu-id="58e7a-135">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="58e7a-136">**Параметры и рекомендации**: вы выбираете параметры Standard или Option и сравните эти параметры с существующими политиками безопасности.</span><span class="sxs-lookup"><span data-stu-id="58e7a-136">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="58e7a-137">В результаты вы можете скорректировать значения параметров, чтобы они выстроили на тот же уровень, что и стандартный или ограниченный.</span><span class="sxs-lookup"><span data-stu-id="58e7a-137">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="58e7a-138">**Анализ и история смещений конфигурации**: это представление позволяет отслеживать изменения политики с течением времени.</span><span class="sxs-lookup"><span data-stu-id="58e7a-138">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="58e7a-139">Вкладка "Настройка и рекомендации" в анализаторе конфигурации</span><span class="sxs-lookup"><span data-stu-id="58e7a-139">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="58e7a-140">По умолчанию вкладка открывается при сравнении со стандартным профилем защиты.</span><span class="sxs-lookup"><span data-stu-id="58e7a-140">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="58e7a-141">Чтобы переключиться на сравнение профиля с помощью ограниченной защиты, нажмите кнопку **Показать рекомендации**.</span><span class="sxs-lookup"><span data-stu-id="58e7a-141">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="58e7a-142">Для обратного переключения выберите **Просмотр стандартных рекомендаций**.</span><span class="sxs-lookup"><span data-stu-id="58e7a-142">To switch back, select **View Standard recommendations**.</span></span>

![Представление "Параметры и рекомендации" в анализаторе конфигурации](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="58e7a-144">По умолчанию столбец **Группа политик/имя параметра** содержит свернутое представление различных типов политик безопасности и число параметров, требующих улучшения (если они есть).</span><span class="sxs-lookup"><span data-stu-id="58e7a-144">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="58e7a-145">Типы политик:</span><span class="sxs-lookup"><span data-stu-id="58e7a-145">The types of policies are:</span></span>

- <span data-ttu-id="58e7a-146">**Защита от нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="58e7a-146">**Anti-spam**</span></span>
- <span data-ttu-id="58e7a-147">**Защита от фишинга**</span><span class="sxs-lookup"><span data-stu-id="58e7a-147">**Anti-phishing**</span></span>
- <span data-ttu-id="58e7a-148">**Защита от вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="58e7a-148">**Anti-malware**</span></span>
- <span data-ttu-id="58e7a-149">**Безопасное вложение ATP** (если ваша подписка включает защитник Майкрософт для Office 365)</span><span class="sxs-lookup"><span data-stu-id="58e7a-149">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="58e7a-150">**Безопасные ссылки ATP** (если ваша подписка включает защитник Майкрософт для Office 365)</span><span class="sxs-lookup"><span data-stu-id="58e7a-150">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="58e7a-151">В представлении по умолчанию все свернуты.</span><span class="sxs-lookup"><span data-stu-id="58e7a-151">In the default view, everything is collapsed.</span></span> <span data-ttu-id="58e7a-152">Рядом с каждой политикой есть сводка результатов сравнения политик (которые можно изменить), а также параметров соответствующих политик для стандартных или ограниченных профилей защиты (которые невозможно изменить).</span><span class="sxs-lookup"><span data-stu-id="58e7a-152">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="58e7a-153">Для профиля защиты, к которому выполняется сравнение, отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="58e7a-153">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="58e7a-154">**Зеленый**: все параметры во всех существующих политиках имеют по крайней мере такой же уровень безопасности, что и профиль защиты.</span><span class="sxs-lookup"><span data-stu-id="58e7a-154">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="58e7a-155">**Оранжевый**: небольшое количество параметров в существующих политиках не является безопасным для профиля защиты.</span><span class="sxs-lookup"><span data-stu-id="58e7a-155">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="58e7a-156">**Red**: значительное количество параметров в существующих политиках не является безопасным для профиля защиты.</span><span class="sxs-lookup"><span data-stu-id="58e7a-156">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="58e7a-157">Это может быть несколько параметров во многих политиках или нескольких параметрах в одной политике.</span><span class="sxs-lookup"><span data-stu-id="58e7a-157">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="58e7a-158">Для получения наиболее благоприятных сравнений вы увидите текст: **All Settings следуйте** \<**Standard** or **Strict**\> **рекомендациям**.</span><span class="sxs-lookup"><span data-stu-id="58e7a-158">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="58e7a-159">В противном случае вы увидите число рекомендуемых параметров для изменения.</span><span class="sxs-lookup"><span data-stu-id="58e7a-159">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="58e7a-160">Если вы развернете **имя группы или параметра политики**, все политики и связанные с ними параметры в каждой политике, требующей внимания, будут отображены.</span><span class="sxs-lookup"><span data-stu-id="58e7a-160">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="58e7a-161">Кроме того, можно развернуть определенный тип политики (например, **Защита от нежелательной почты**), чтобы увидеть только те параметры политик, которые требуют вашего внимания.</span><span class="sxs-lookup"><span data-stu-id="58e7a-161">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="58e7a-162">Если сравнение не имеет рекомендаций по улучшению (зеленый), то расширение политики не открывает ничего.</span><span class="sxs-lookup"><span data-stu-id="58e7a-162">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="58e7a-163">Если имеется любое количество рекомендаций по улучшению (оранжевый или красный), то параметры, требующие внимания, будут отображены, а соответствующая информация отображается в следующих столбцах:</span><span class="sxs-lookup"><span data-stu-id="58e7a-163">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="58e7a-164">Имя параметра, требующего вашего внимания.</span><span class="sxs-lookup"><span data-stu-id="58e7a-164">The name of the setting that requires your attention.</span></span> <span data-ttu-id="58e7a-165">Например, на предыдущем снимке экрана это **пороговое значение групповой электронной почты** в политике защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="58e7a-165">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="58e7a-166">**Политика**: имя затронутой политики, содержащей параметр.</span><span class="sxs-lookup"><span data-stu-id="58e7a-166">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="58e7a-167">**Применяется к**: количество пользователей, к которым применяются затронутые политики.</span><span class="sxs-lookup"><span data-stu-id="58e7a-167">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="58e7a-168">**Текущая конфигурация**: текущее значение параметра.</span><span class="sxs-lookup"><span data-stu-id="58e7a-168">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="58e7a-169">Дата **последнего изменения**: Дата последнего изменения политики.</span><span class="sxs-lookup"><span data-stu-id="58e7a-169">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="58e7a-170">**Рекомендации**: значение параметра в стандартном или ограниченном профиле защиты.</span><span class="sxs-lookup"><span data-stu-id="58e7a-170">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="58e7a-171">Чтобы изменить значение параметра в политике в значение, соответствующее рекомендуемому значению в профиле защиты, нажмите кнопку **принять**.</span><span class="sxs-lookup"><span data-stu-id="58e7a-171">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="58e7a-172">Если изменение прошло успешно, вы увидите сообщение: **рекомендации успешно приняты**.</span><span class="sxs-lookup"><span data-stu-id="58e7a-172">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="58e7a-173">Нажмите кнопку **Обновить** , чтобы увидеть уменьшенное количество рекомендаций и удалить определенную строку параметров или политик из результатов.</span><span class="sxs-lookup"><span data-stu-id="58e7a-173">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="58e7a-174">Вкладка "анализ и анализ сведений о смещении конфигурации" в анализаторе конфигурации</span><span class="sxs-lookup"><span data-stu-id="58e7a-174">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="58e7a-175">Эта вкладка позволяет отслеживать изменения, внесенные в пользовательские политики безопасности.</span><span class="sxs-lookup"><span data-stu-id="58e7a-175">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="58e7a-176">По умолчанию отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="58e7a-176">By default, the following information is displayed:</span></span>

- <span data-ttu-id="58e7a-177">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="58e7a-177">**Last modified**</span></span>
- <span data-ttu-id="58e7a-178">**Кем изменено**</span><span class="sxs-lookup"><span data-stu-id="58e7a-178">**Modified by**</span></span>
- <span data-ttu-id="58e7a-179">**Имя параметра**</span><span class="sxs-lookup"><span data-stu-id="58e7a-179">**Setting Name**</span></span>
- <span data-ttu-id="58e7a-180">**Политика**</span><span class="sxs-lookup"><span data-stu-id="58e7a-180">**Policy**</span></span>
- <span data-ttu-id="58e7a-181">**Тип**</span><span class="sxs-lookup"><span data-stu-id="58e7a-181">**Type**</span></span>

<span data-ttu-id="58e7a-182">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="58e7a-182">To filter the results, click **Filter**.</span></span> <span data-ttu-id="58e7a-183">В появившемся всплывающем окне **фильтры** можно выбрать следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="58e7a-183">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="58e7a-184">Время **начала** и **время окончания** (дата)</span><span class="sxs-lookup"><span data-stu-id="58e7a-184">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="58e7a-185">**Стандартная защита** или **ограниченная защита**</span><span class="sxs-lookup"><span data-stu-id="58e7a-185">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="58e7a-186">Чтобы экспортировать результаты в CSV-файл, нажмите кнопку **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="58e7a-186">To export the results to a .csv file, click **Export**.</span></span>

![Анализ и Просмотр сведений о смещении конфигурации в анализаторе конфигурации](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
