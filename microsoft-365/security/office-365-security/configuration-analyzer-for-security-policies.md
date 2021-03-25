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
ms.openlocfilehash: 65fd67c93711dc847a25be485b4b016af55e4a31
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205061"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="57f7c-103">Анализатор конфигурации для политик защиты в EOP и Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="57f7c-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="57f7c-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="57f7c-104">**Applies to**</span></span>
- [<span data-ttu-id="57f7c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="57f7c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="57f7c-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="57f7c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="57f7c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="57f7c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="57f7c-108">Анализатор конфигурации в центре & соответствия требованиям безопасности предоставляет центральное расположение для поиска и исправления политик безопасности, в которых параметры ниже параметров стандартных и строгих параметров профилей защиты в заранее установленных политиках [безопасности.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="57f7c-108">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="57f7c-109">Анализатор конфигурации анализирует следующие типы политик:</span><span class="sxs-lookup"><span data-stu-id="57f7c-109">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="57f7c-110">**Политики Exchange Online Protection (EOP):** Это включает организации Microsoft 365 с почтовыми ящиками Exchange Online и автономные организации EOP без почтовых ящиков Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="57f7c-110">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="57f7c-111">[Политики по борьбе со спамом](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="57f7c-111">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="57f7c-112">[Политики по борьбе с вредоносными программами.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="57f7c-112">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="57f7c-113">[Политики защиты от фишинга EOP](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="57f7c-113">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="57f7c-114">Политики Microsoft Defender для **Office 365:** это организации с подписками на надстройки Microsoft 365 E5 или Defender для Office 365:</span><span class="sxs-lookup"><span data-stu-id="57f7c-114">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="57f7c-115">Политики защиты от фишинга в Microsoft Defender для Office 365, включающие:</span><span class="sxs-lookup"><span data-stu-id="57f7c-115">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="57f7c-116">Те же [параметры подмены,](set-up-anti-phishing-policies.md#spoof-settings) которые доступны в антифишинговых политиках EOP.</span><span class="sxs-lookup"><span data-stu-id="57f7c-116">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="57f7c-117">Параметры обезличения</span><span class="sxs-lookup"><span data-stu-id="57f7c-117">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="57f7c-118">Расширенные пороговые значения фишинга</span><span class="sxs-lookup"><span data-stu-id="57f7c-118">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="57f7c-119">[Политики безопасных ссылок](set-up-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="57f7c-119">[Safe Links policies](set-up-safe-links-policies.md).</span></span>

  - <span data-ttu-id="57f7c-120">[Политики безопасных вложений](set-up-safe-attachments-policies.md).</span><span class="sxs-lookup"><span data-stu-id="57f7c-120">[Safe Attachments policies](set-up-safe-attachments-policies.md).</span></span>

<span data-ttu-id="57f7c-121">Значения **стандартных** **и** строгих политик, которые используются в качестве базовых значений, описаны в рекомендуемых параметрах безопасности EOP и Microsoft Defender для Office [365.](recommended-settings-for-eop-and-office365.md)</span><span class="sxs-lookup"><span data-stu-id="57f7c-121">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="57f7c-122">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="57f7c-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="57f7c-123">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="57f7c-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="57f7c-124">Чтобы перейти непосредственно на страницу **Анализатор конфигурации,** используйте <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="57f7c-124">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="57f7c-125">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="57f7c-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="57f7c-126">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="57f7c-126">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="57f7c-127">Чтобы использовать анализатор  конфигурации и обновлять политики безопасности, необходимо быть членом групп ролей **администратора** организации или **администратора** безопасности.</span><span class="sxs-lookup"><span data-stu-id="57f7c-127">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="57f7c-128">Для доступа только для чтения к анализатору конфигурации необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="57f7c-128">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="57f7c-129">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="57f7c-129">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="57f7c-130">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="57f7c-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="57f7c-131">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="57f7c-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="57f7c-132">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="57f7c-132">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="57f7c-133">Используйте анализатор конфигурации в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="57f7c-133">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="57f7c-134">В Центре & безопасности перейдите к **анализатору** конфигурации политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="57f7c-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Виджет анализатора конфигурации на странице Политика управления \> угрозами](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="57f7c-136">Анализатор конфигурации имеет две основные вкладки:</span><span class="sxs-lookup"><span data-stu-id="57f7c-136">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="57f7c-137">**Параметры и рекомендации.** Вы выбираете стандартные или строгие параметры и сравниваете их с существующими политиками безопасности.</span><span class="sxs-lookup"><span data-stu-id="57f7c-137">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="57f7c-138">В результатах можно настроить значения параметров, чтобы вывести их на тот же уровень, что и Стандартный или Строгий.</span><span class="sxs-lookup"><span data-stu-id="57f7c-138">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="57f7c-139">**Анализ и история смещения** конфигурации. Это представление позволяет отслеживать изменения политики с течением времени.</span><span class="sxs-lookup"><span data-stu-id="57f7c-139">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="57f7c-140">Настройка и вкладка рекомендации в анализаторе конфигурации</span><span class="sxs-lookup"><span data-stu-id="57f7c-140">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="57f7c-141">По умолчанию вкладка открывается по сравнению со стандартным профилем защиты.</span><span class="sxs-lookup"><span data-stu-id="57f7c-141">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="57f7c-142">Вы можете перейти к сопоставлению профиля строгой защиты, щелкнув **рекомендации View Strict.**</span><span class="sxs-lookup"><span data-stu-id="57f7c-142">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="57f7c-143">Чтобы перейти назад, выберите **рекомендации View Standard**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-143">To switch back, select **View Standard recommendations**.</span></span>

![Просмотр параметров и рекомендаций в анализаторе Конфигурация](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="57f7c-145">По умолчанию столбец **"Группа/настройка** политики" содержит свернутые представления о различных типах политик безопасности и количестве параметров, которые требуют улучшения (если таковые есть).</span><span class="sxs-lookup"><span data-stu-id="57f7c-145">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="57f7c-146">Типы политик:</span><span class="sxs-lookup"><span data-stu-id="57f7c-146">The types of policies are:</span></span>

- <span data-ttu-id="57f7c-147">**Противодействие нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="57f7c-147">**Anti-spam**</span></span>
- <span data-ttu-id="57f7c-148">**Anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="57f7c-148">**Anti-phishing**</span></span>
- <span data-ttu-id="57f7c-149">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="57f7c-149">**Anti-malware**</span></span>
- <span data-ttu-id="57f7c-150">**Безопасные вложения ATP** (если ваша подписка включает Microsoft Defender для Office 365)</span><span class="sxs-lookup"><span data-stu-id="57f7c-150">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="57f7c-151">**Безопасные ссылки ATP** (если ваша подписка включает Microsoft Defender для Office 365)</span><span class="sxs-lookup"><span data-stu-id="57f7c-151">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="57f7c-152">В представлении по умолчанию все свернуто.</span><span class="sxs-lookup"><span data-stu-id="57f7c-152">In the default view, everything is collapsed.</span></span> <span data-ttu-id="57f7c-153">Рядом с каждой политикой приводится сводка результатов сравнения политик (которые можно изменить) и параметров соответствующих политик для стандартных или строгих профилей защиты (которые нельзя изменить).</span><span class="sxs-lookup"><span data-stu-id="57f7c-153">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="57f7c-154">Вы увидите следующие сведения для профиля защиты, который вы сравниваете с:</span><span class="sxs-lookup"><span data-stu-id="57f7c-154">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="57f7c-155">**Зеленый.** Все параметры во всех существующих политиках по крайней мере так же безопасны, как и профиль защиты.</span><span class="sxs-lookup"><span data-stu-id="57f7c-155">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="57f7c-156">**Amber.** Небольшое число параметров в существующих политиках не так защищено, как профиль защиты.</span><span class="sxs-lookup"><span data-stu-id="57f7c-156">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="57f7c-157">**Красный** цвет. Значительное число параметров существующих политик не так защищено, как профиль защиты.</span><span class="sxs-lookup"><span data-stu-id="57f7c-157">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="57f7c-158">Это может быть несколько параметров во многих политиках или множество параметров в одной политике.</span><span class="sxs-lookup"><span data-stu-id="57f7c-158">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="57f7c-159">Для благоприятных сравнений вы увидите текст: **все параметры следуют** \<**Standard** or **Strict**\> **рекомендациям.**</span><span class="sxs-lookup"><span data-stu-id="57f7c-159">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="57f7c-160">В противном случае вы увидите количество рекомендуемых параметров для изменения.</span><span class="sxs-lookup"><span data-stu-id="57f7c-160">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="57f7c-161">При **расширении имени группы и** настройки политики раскрываются все политики и связанные параметры в каждой конкретной политике, которая требует внимания.</span><span class="sxs-lookup"><span data-stu-id="57f7c-161">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="57f7c-162">Или вы можете расширить определенный тип политики (например, **anti-spam),** чтобы увидеть только те параметры в тех типах политик, которые требуют вашего внимания.</span><span class="sxs-lookup"><span data-stu-id="57f7c-162">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="57f7c-163">Если в сопоставлении нет рекомендаций по улучшению (зеленый цвет), расширение политики ничего не показывает.</span><span class="sxs-lookup"><span data-stu-id="57f7c-163">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="57f7c-164">Если существует ряд рекомендаций по улучшению (янтарный или красный), раскрываются параметры, которые требуют внимания, и соответствующая информация раскрывается в следующих столбцах:</span><span class="sxs-lookup"><span data-stu-id="57f7c-164">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="57f7c-165">Имя параметра, требуемого вашего внимания.</span><span class="sxs-lookup"><span data-stu-id="57f7c-165">The name of the setting that requires your attention.</span></span> <span data-ttu-id="57f7c-166">Например, на предыдущем скриншоте это пороговое значение для массовой почты **в** политике борьбы со спамом.</span><span class="sxs-lookup"><span data-stu-id="57f7c-166">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="57f7c-167">**Политика.** Имя затрагиваемой политики, содержаной параметр.</span><span class="sxs-lookup"><span data-stu-id="57f7c-167">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="57f7c-168">**Применяется к**: Число пользователей, к числу которых применяются затронутые политики.</span><span class="sxs-lookup"><span data-stu-id="57f7c-168">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="57f7c-169">**Текущая конфигурация.** Текущее значение параметра.</span><span class="sxs-lookup"><span data-stu-id="57f7c-169">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="57f7c-170">**Последнее изменение.** Дата последнего изменения политики.</span><span class="sxs-lookup"><span data-stu-id="57f7c-170">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="57f7c-171">**Рекомендации.** Значение параметра в профиле Стандартная или Строгая защита.</span><span class="sxs-lookup"><span data-stu-id="57f7c-171">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="57f7c-172">Чтобы изменить значение параметра в политике в соответствие с рекомендуемой величиной в профиле защиты, нажмите **Кнопку Принять**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-172">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="57f7c-173">Если изменение будет успешным, вы увидите сообщение: **Рекомендации успешно приняты**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-173">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="57f7c-174">Щелкните **Обновление,** чтобы увидеть уменьшение числа рекомендаций и удаление определенной строки параметра/политики из результатов.</span><span class="sxs-lookup"><span data-stu-id="57f7c-174">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="57f7c-175">Анализ смещения конфигурации и вкладка история в анализаторе конфигурации</span><span class="sxs-lookup"><span data-stu-id="57f7c-175">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="57f7c-176">Эта вкладка позволяет отслеживать изменения, внесенные в настраиваемые политики безопасности.</span><span class="sxs-lookup"><span data-stu-id="57f7c-176">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="57f7c-177">По умолчанию отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="57f7c-177">By default, the following information is displayed:</span></span>

- <span data-ttu-id="57f7c-178">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="57f7c-178">**Last modified**</span></span>
- <span data-ttu-id="57f7c-179">**Изменено путем**</span><span class="sxs-lookup"><span data-stu-id="57f7c-179">**Modified by**</span></span>
- <span data-ttu-id="57f7c-180">**Настройка имени**</span><span class="sxs-lookup"><span data-stu-id="57f7c-180">**Setting Name**</span></span>
- <span data-ttu-id="57f7c-181">**Policy**</span><span class="sxs-lookup"><span data-stu-id="57f7c-181">**Policy**</span></span>
- <span data-ttu-id="57f7c-182">**Тип**</span><span class="sxs-lookup"><span data-stu-id="57f7c-182">**Type**</span></span>

<span data-ttu-id="57f7c-183">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-183">To filter the results, click **Filter**.</span></span> <span data-ttu-id="57f7c-184">В **вылете Filters,** который отображается, можно выбрать из следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="57f7c-184">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="57f7c-185">**Время начала и** **время окончания** (дата)</span><span class="sxs-lookup"><span data-stu-id="57f7c-185">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="57f7c-186">**Стандартная защита** или **строгая защита**</span><span class="sxs-lookup"><span data-stu-id="57f7c-186">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="57f7c-187">Чтобы экспортировать результаты в файл csv, нажмите кнопку **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="57f7c-187">To export the results to a .csv file, click **Export**.</span></span>

![Анализ дрейфа конфигурации и представление истории в анализаторе конфигурации](../../media/configuration-analyzer-configuration-drift-analysis-view.png)