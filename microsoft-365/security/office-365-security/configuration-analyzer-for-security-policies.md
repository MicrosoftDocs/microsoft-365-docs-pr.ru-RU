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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как использовать анализатор конфигурации для поиска и исправления политик безопасности, которые ниже стандартных политик безопасности и строгой защиты.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0d2ad1449730f392adc27c8ed2a8fc8e9ecc7a04
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789320"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="f8770-103">Анализатор конфигурации для политик защиты в EOP и Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="f8770-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f8770-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="f8770-104">**Applies to**</span></span>
- [<span data-ttu-id="f8770-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f8770-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f8770-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="f8770-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f8770-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8770-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f8770-108">Анализатор конфигурации в центре Microsoft 365 безопасности предоставляет центральное расположение для поиска и исправления политик безопасности, в которых параметры находятся ниже параметров стандартных и строгих параметров профилей защиты в заранее заданная политика [безопасности.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f8770-108">Configuration analyzer in the Microsoft 365 security center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="f8770-109">Анализатор конфигурации анализирует следующие типы политик:</span><span class="sxs-lookup"><span data-stu-id="f8770-109">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="f8770-110">**политики Exchange Online Protection (EOP):** Это включает Microsoft 365 с Exchange Online почтовыми ящиками и автономными организациями EOP без Exchange Online почтовых ящиков:</span><span class="sxs-lookup"><span data-stu-id="f8770-110">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="f8770-111">[Политики по борьбе со спамом](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f8770-111">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="f8770-112">[Политики по борьбе с вредоносными программами.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f8770-112">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="f8770-113">[Антифишинговые политики EOP](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="f8770-113">[EOP anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="f8770-114">**Microsoft Defender для Office 365** политик: это организации с Microsoft 365 E5 или Defender для Office 365 надстройки:</span><span class="sxs-lookup"><span data-stu-id="f8770-114">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="f8770-115">Политики защиты от фишинга в Microsoft Defender для Office 365, включающие:</span><span class="sxs-lookup"><span data-stu-id="f8770-115">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>
    - <span data-ttu-id="f8770-116">Те же [параметры подмены,](set-up-anti-phishing-policies.md#spoof-settings) которые доступны в антифишинговых политиках EOP.</span><span class="sxs-lookup"><span data-stu-id="f8770-116">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="f8770-117">Параметры обезличения</span><span class="sxs-lookup"><span data-stu-id="f8770-117">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="f8770-118">Расширенные пороговые значения фишинга</span><span class="sxs-lookup"><span data-stu-id="f8770-118">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - <span data-ttu-id="f8770-119">[Сейф ссылки политики](set-up-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f8770-119">[Safe Links policies](set-up-safe-links-policies.md).</span></span>
  - <span data-ttu-id="f8770-120">[Сейф политики вложений](set-up-safe-attachments-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f8770-120">[Safe Attachments policies](set-up-safe-attachments-policies.md).</span></span>

<span data-ttu-id="f8770-121">Значения **стандартных** и строгих параметров политики, которые используются в качестве базовых значений, описаны в рекомендуемых параметрах для EOP и [Microsoft Defender для Office 365 безопасности.](recommended-settings-for-eop-and-office365.md) </span><span class="sxs-lookup"><span data-stu-id="f8770-121">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f8770-122">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="f8770-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f8770-123">Открытие Центра безопасности производится в <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="f8770-123">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="f8770-124">Чтобы перейти непосредственно на страницу **Анализатор конфигурации,** используйте <https://security.microsoft.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="f8770-124">To go directly to the **Configuration analyzer** page, use <https://security.microsoft.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="f8770-125">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f8770-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="f8770-126">Вам необходимо получить разрешения в центре безопасности, прежде чем вы сможете сделать процедуры в этой статье:</span><span class="sxs-lookup"><span data-stu-id="f8770-126">You need to be assigned permissions in the security center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f8770-127">Чтобы использовать анализатор  конфигурации и обновлять политики безопасности, необходимо быть членом групп ролей **администратора** организации или **администратора** безопасности.</span><span class="sxs-lookup"><span data-stu-id="f8770-127">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="f8770-128">Для доступа только для чтения к анализатору конфигурации необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="f8770-128">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f8770-129">Дополнительные сведения см. [в дополнительных сведениях в центре Microsoft 365 permissions.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="f8770-129">For more information, see [Permissions in the Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="f8770-130">Добавление пользователей к соответствующей роли Azure Active Directory дает пользователям необходимые разрешения  в центре безопасности и разрешения на другие функции в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f8770-130">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the security center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f8770-131">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f8770-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="f8770-132">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="f8770-132">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security-center"></a><span data-ttu-id="f8770-133">Используйте анализатор конфигурации в центре безопасности</span><span class="sxs-lookup"><span data-stu-id="f8770-133">Use the configuration analyzer in the security center</span></span>

<span data-ttu-id="f8770-134">В центре безопасности перейдите в раздел **Email & политики** совместной & политики угрозы Шаблонные политики \>  \>  \>  \> **анализатор конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="f8770-134">In the security center, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Templated policies** section \> **Configuration analyzer**.</span></span>

<span data-ttu-id="f8770-135">Анализатор конфигурации имеет две основные вкладки:</span><span class="sxs-lookup"><span data-stu-id="f8770-135">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="f8770-136">**Параметры рекомендации.** Вы выбираете **стандартные** или строгие параметры и сравниваете их с существующими политиками безопасности. </span><span class="sxs-lookup"><span data-stu-id="f8770-136">**Settings and recommendations**: You pick **Standard** or **Strict** and compare those settings to your existing security policies.</span></span> <span data-ttu-id="f8770-137">В результатах можно настроить значения параметров, чтобы вывести их на тот же уровень, что и Стандартный или Строгий.</span><span class="sxs-lookup"><span data-stu-id="f8770-137">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>
- <span data-ttu-id="f8770-138">**Анализ и история смещения** конфигурации. Это представление позволяет отслеживать изменения политики с течением времени.</span><span class="sxs-lookup"><span data-stu-id="f8770-138">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="f8770-139">Настройка и вкладка рекомендации в анализаторе конфигурации</span><span class="sxs-lookup"><span data-stu-id="f8770-139">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="f8770-140">По умолчанию вкладка открывается по сравнению со стандартным профилем защиты.</span><span class="sxs-lookup"><span data-stu-id="f8770-140">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="f8770-141">Вы можете перейти к сопоставлению профиля строгой защиты, выбрав **рекомендации View Strict.**</span><span class="sxs-lookup"><span data-stu-id="f8770-141">You can switch to the comparison of the Strict protection profile by selecting **View Strict recommendations**.</span></span> <span data-ttu-id="f8770-142">Чтобы перейти назад, выберите **рекомендации View Standard**.</span><span class="sxs-lookup"><span data-stu-id="f8770-142">To switch back, select **View Standard recommendations**.</span></span>

![Параметры и рекомендации в анализаторе конфигурации](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="f8770-144">По умолчанию столбец **"Группа/настройка** политики" содержит свернутые представления о различных типах политик безопасности и количестве параметров, которые требуют улучшения (если таковые есть).</span><span class="sxs-lookup"><span data-stu-id="f8770-144">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="f8770-145">Типы политик:</span><span class="sxs-lookup"><span data-stu-id="f8770-145">The types of policies are:</span></span>

- <span data-ttu-id="f8770-146">**Противодействие нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="f8770-146">**Anti-spam**</span></span>
- <span data-ttu-id="f8770-147">**Anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="f8770-147">**Anti-phishing**</span></span>
- <span data-ttu-id="f8770-148">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="f8770-148">**Anti-malware**</span></span>
- <span data-ttu-id="f8770-149">**Сейф вложения** (если ваша подписка включает Microsoft Defender для Office 365)</span><span class="sxs-lookup"><span data-stu-id="f8770-149">**Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="f8770-150">**Сейф ссылки** (если ваша подписка включает Microsoft Defender для Office 365)</span><span class="sxs-lookup"><span data-stu-id="f8770-150">**Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="f8770-151">В представлении по умолчанию все свернуто.</span><span class="sxs-lookup"><span data-stu-id="f8770-151">In the default view, everything is collapsed.</span></span> <span data-ttu-id="f8770-152">Рядом с каждой политикой приводится сводка результатов сравнения политик (которые можно изменить) и параметров соответствующих политик для стандартных или строгих профилей защиты (которые нельзя изменить).</span><span class="sxs-lookup"><span data-stu-id="f8770-152">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="f8770-153">Вы увидите следующие сведения для профиля защиты, который вы сравниваете с:</span><span class="sxs-lookup"><span data-stu-id="f8770-153">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="f8770-154">**Зеленый.** Все параметры во всех существующих политиках по крайней мере так же безопасны, как и профиль защиты.</span><span class="sxs-lookup"><span data-stu-id="f8770-154">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="f8770-155">**Amber.** Небольшое число параметров в существующих политиках не так защищено, как профиль защиты.</span><span class="sxs-lookup"><span data-stu-id="f8770-155">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="f8770-156">**Красный** цвет. Значительное число параметров существующих политик не так защищено, как профиль защиты.</span><span class="sxs-lookup"><span data-stu-id="f8770-156">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="f8770-157">Это может быть несколько параметров во многих политиках или множество параметров в одной политике.</span><span class="sxs-lookup"><span data-stu-id="f8770-157">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="f8770-158">Для благоприятных сравнений вы увидите текст: **все параметры следуют** \<**Standard** or **Strict**\> **рекомендациям.**</span><span class="sxs-lookup"><span data-stu-id="f8770-158">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="f8770-159">В противном случае вы увидите количество рекомендуемых параметров для изменения.</span><span class="sxs-lookup"><span data-stu-id="f8770-159">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="f8770-160">При **расширении имени группы и** настройки политики раскрываются все политики и связанные параметры в каждой конкретной политике, которая требует внимания.</span><span class="sxs-lookup"><span data-stu-id="f8770-160">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="f8770-161">Или вы можете расширить определенный тип политики (например, **anti-spam),** чтобы увидеть только те параметры в тех типах политик, которые требуют вашего внимания.</span><span class="sxs-lookup"><span data-stu-id="f8770-161">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="f8770-162">Если в сопоставлении нет рекомендаций по улучшению (зеленый цвет), расширение политики ничего не показывает.</span><span class="sxs-lookup"><span data-stu-id="f8770-162">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="f8770-163">Если существует ряд рекомендаций по улучшению (янтарный или красный), раскрываются параметры, которые требуют внимания, и соответствующая информация раскрывается в следующих столбцах:</span><span class="sxs-lookup"><span data-stu-id="f8770-163">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="f8770-164">**Группа политики/имя** параметра: имя параметра, требуемого вашего внимания.</span><span class="sxs-lookup"><span data-stu-id="f8770-164">**Policy group/setting name**: The name of the setting that requires your attention.</span></span> <span data-ttu-id="f8770-165">Например, на предыдущем скриншоте это параметры в политике по умолчанию по борьбе со спамом.</span><span class="sxs-lookup"><span data-stu-id="f8770-165">For example, in the previous screenshot, it's the settings in the default anti-spam policy.</span></span>
- <span data-ttu-id="f8770-166">**Политика.** Имя затрагиваемой политики, содержаной параметр.</span><span class="sxs-lookup"><span data-stu-id="f8770-166">**Policy**: The name of the affected policy that contains the setting.</span></span>
- <span data-ttu-id="f8770-167">**Применяется к**: Число пользователей, к числу которых применяются затронутые политики.</span><span class="sxs-lookup"><span data-stu-id="f8770-167">**Applied to**: The number of users that the affected policies are applied to.</span></span>
- <span data-ttu-id="f8770-168">**Текущая конфигурация.** Текущее значение параметра.</span><span class="sxs-lookup"><span data-stu-id="f8770-168">**Current configuration**: The current value of the setting.</span></span> <span data-ttu-id="f8770-169">Для политики по умолчанию этого типа, применяемой ко всем получателям, это значение является пустым.</span><span class="sxs-lookup"><span data-stu-id="f8770-169">For the default policy of that type that applies to all recipients, this value is blank.</span></span>
- <span data-ttu-id="f8770-170">**Последнее изменение.** Дата последнего изменения политики.</span><span class="sxs-lookup"><span data-stu-id="f8770-170">**Last modified**: The date that the policy was last modified.</span></span>
- <span data-ttu-id="f8770-171">**Рекомендации:** значение параметра в профиле Standard или Strict protection.</span><span class="sxs-lookup"><span data-stu-id="f8770-171">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="f8770-172">Чтобы изменить значение параметра в политике в соответствие с рекомендуемой величиной в профиле защиты, нажмите **Кнопку Принять**.</span><span class="sxs-lookup"><span data-stu-id="f8770-172">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="f8770-173">Если изменение будет успешным, вы увидите сообщение: Рекомендации **успешно принят**.</span><span class="sxs-lookup"><span data-stu-id="f8770-173">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="f8770-174">Щелкните **Обновление,** чтобы увидеть уменьшение числа рекомендаций и удаление определенной строки параметра/политики из результатов.</span><span class="sxs-lookup"><span data-stu-id="f8770-174">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="f8770-175">Анализ смещения конфигурации и вкладка история в анализаторе конфигурации</span><span class="sxs-lookup"><span data-stu-id="f8770-175">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="f8770-176">Эта вкладка позволяет отслеживать изменения, внесенные в настраиваемые политики безопасности.</span><span class="sxs-lookup"><span data-stu-id="f8770-176">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="f8770-177">По умолчанию отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="f8770-177">By default, the following information is displayed:</span></span>

- <span data-ttu-id="f8770-178">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="f8770-178">**Last modified**</span></span>
- <span data-ttu-id="f8770-179">**Изменено путем**</span><span class="sxs-lookup"><span data-stu-id="f8770-179">**Modified by**</span></span>
- <span data-ttu-id="f8770-180">**Настройка имени**</span><span class="sxs-lookup"><span data-stu-id="f8770-180">**Setting Name**</span></span>
- <span data-ttu-id="f8770-181">**Политика**</span><span class="sxs-lookup"><span data-stu-id="f8770-181">**Policy**</span></span>
- <span data-ttu-id="f8770-182">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f8770-182">**Type**</span></span>
- <span data-ttu-id="f8770-183">**Изменение конфигурации**</span><span class="sxs-lookup"><span data-stu-id="f8770-183">**Configuration change**</span></span>
- <span data-ttu-id="f8770-184">**Смещение конфигурации:** увеличение **или** **уменьшение значения**.</span><span class="sxs-lookup"><span data-stu-id="f8770-184">**Configuration drift**: The value **Increase** or **Decrease**.</span></span>

<span data-ttu-id="f8770-185">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="f8770-185">To filter the results, click **Filter**.</span></span> <span data-ttu-id="f8770-186">В **вылете Filters,** который отображается, можно выбрать из следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="f8770-186">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="f8770-187">**Время начала и** **время окончания** (дата)</span><span class="sxs-lookup"><span data-stu-id="f8770-187">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="f8770-188">**Стандартная защита** или **строгая защита**</span><span class="sxs-lookup"><span data-stu-id="f8770-188">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="f8770-189">Чтобы экспортировать результаты в файл .csv, нажмите кнопку **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="f8770-189">To export the results to a .csv file, click **Export**.</span></span>

![Анализ дрейфа конфигурации и представление истории в анализаторе конфигурации](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
