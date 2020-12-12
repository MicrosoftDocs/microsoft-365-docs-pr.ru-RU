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
description: Администраторы могут узнать, как использовать анализатор конфигурации для поиска и исправления политик безопасности, которые находятся ниже стандартных политик безопасности и строгих политик безопасности.
ms.openlocfilehash: af7cf269151c7e947a0a2f653ce8638d46ccd905
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658665"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="dbad9-103">Анализатор конфигурации для политик защиты в EOP и Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="dbad9-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="dbad9-104">Функции, описанные в этой статье, доступны в предварительной версии, доступны не во всех организациях и могут быть измениться.</span><span class="sxs-lookup"><span data-stu-id="dbad9-104">The features described in this article are in Preview, aren't available in all organizations, and are subject to change.</span></span> <span data-ttu-id="dbad9-105">Сведения о расписании выпусков можно узнать в [плане развития Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer)</span><span class="sxs-lookup"><span data-stu-id="dbad9-105">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span></span>

<span data-ttu-id="dbad9-106">Анализатор конфигурации в Центре безопасности и соответствия требованиям & обеспечивает централизованное расположение для поиска и исправления политик безопасности, где параметры находятся ниже параметров профиля "Стандартная защита" и "Строгая защита" в предустановленных политиках [безопасности.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="dbad9-106">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="dbad9-107">Анализатор конфигурации анализирует следующие типы политик:</span><span class="sxs-lookup"><span data-stu-id="dbad9-107">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="dbad9-108">**Политики Exchange Online Protection (EOP):** к ним относятся организации Microsoft 365 с почтовыми ящиками Exchange Online и автономные организации EOP без почтовых ящиков Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="dbad9-108">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="dbad9-109">[Политики нежелательной почты.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="dbad9-109">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="dbad9-110">[Политики для борьбы с вредоносными программами.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="dbad9-110">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="dbad9-111">[Политики защиты от фишинга EOP.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="dbad9-111">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="dbad9-112">Политики Microsoft Defender для **Office 365:** к ним относятся организации с подписками на надстройки Microsoft 365 E5 или Defender для Office 365:</span><span class="sxs-lookup"><span data-stu-id="dbad9-112">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="dbad9-113">Политики защиты от фишинга в Microsoft Defender для Office 365, в том числе:</span><span class="sxs-lookup"><span data-stu-id="dbad9-113">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="dbad9-114">Те же [параметры подмены,](set-up-anti-phishing-policies.md#spoof-settings) которые доступны в политиках защиты от фишинга EOP.</span><span class="sxs-lookup"><span data-stu-id="dbad9-114">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="dbad9-115">Параметры обезличения</span><span class="sxs-lookup"><span data-stu-id="dbad9-115">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="dbad9-116">Расширенные пороговые значения фишинга</span><span class="sxs-lookup"><span data-stu-id="dbad9-116">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="dbad9-117">[Политики безопасных ссылок.](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="dbad9-117">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="dbad9-118">[Политики безопасных вложений.](set-up-atp-safe-attachments-policies.md)</span><span class="sxs-lookup"><span data-stu-id="dbad9-118">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="dbad9-119">Значения **параметров** политики Standard и **Strict,** используемые в качестве базовых значений, описаны в рекомендуемых параметрах для EOP и Microsoft Defender для системы безопасности [Office 365.](recommended-settings-for-eop-and-office365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="dbad9-119">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="dbad9-120">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="dbad9-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="dbad9-121">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="dbad9-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="dbad9-122">Чтобы перейти непосредственно на **страницу анализатора конфигурации,** используйте <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="dbad9-122">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="dbad9-123">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="dbad9-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="dbad9-124">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="dbad9-124">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="dbad9-125">Чтобы использовать анализатор  конфигурации и обновлять политики безопасности, необходимо быть  членом группы ролей "Управление организацией" или "Администратор **безопасности".**</span><span class="sxs-lookup"><span data-stu-id="dbad9-125">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="dbad9-126">Для доступа только для чтения к анализатору конфигурации необходимо быть  членом группы ролей **"Глобальное** чтение" или "Читатель безопасности".</span><span class="sxs-lookup"><span data-stu-id="dbad9-126">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="dbad9-127">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="dbad9-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="dbad9-128">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="dbad9-128">**Notes**:</span></span>

  - <span data-ttu-id="dbad9-129">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dbad9-129">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="dbad9-130">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="dbad9-130">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="dbad9-131">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="dbad9-131">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="dbad9-132">Использование анализатора конфигурации в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="dbad9-132">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="dbad9-133">В Центре безопасности & соответствия требованиям перейдите **к** анализатору конфигурации политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="dbad9-133">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Мини-приложения анализатора конфигурации на странице \> "Политика управления угрозами"](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="dbad9-135">Анализатор конфигурации имеет две основные вкладки:</span><span class="sxs-lookup"><span data-stu-id="dbad9-135">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="dbad9-136">**Параметры и рекомендации:** вы выбираете стандартный или строгий и сравниваете эти параметры с существующими политиками безопасности.</span><span class="sxs-lookup"><span data-stu-id="dbad9-136">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="dbad9-137">В результате вы можете изменить значения параметров, чтобы они были на том же уровне, что и стандартные или строгие.</span><span class="sxs-lookup"><span data-stu-id="dbad9-137">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="dbad9-138">**Анализ и история смещения** конфигурации: это представление позволяет отслеживать изменения политики с течением времени.</span><span class="sxs-lookup"><span data-stu-id="dbad9-138">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="dbad9-139">Вкладка "Настройка и рекомендации" в анализаторе конфигурации</span><span class="sxs-lookup"><span data-stu-id="dbad9-139">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="dbad9-140">По умолчанию вкладка открывается при сравнении со стандартным профилем защиты.</span><span class="sxs-lookup"><span data-stu-id="dbad9-140">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="dbad9-141">Вы можете переключиться на сравнение профиля строгой защиты, щелкнув **"Просмотреть строгие рекомендации".**</span><span class="sxs-lookup"><span data-stu-id="dbad9-141">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="dbad9-142">Чтобы переключиться назад, **выберите "Просмотреть стандартные рекомендации".**</span><span class="sxs-lookup"><span data-stu-id="dbad9-142">To switch back, select **View Standard recommendations**.</span></span>

![Представление параметров и рекомендаций в анализаторе конфигурации](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="dbad9-144">По умолчанию столбец имени группы **и** параметра политики содержит свернутые представления различных типов политик безопасности и количества параметров, которые требуют улучшения (если таковые есть).</span><span class="sxs-lookup"><span data-stu-id="dbad9-144">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="dbad9-145">Типы политик:</span><span class="sxs-lookup"><span data-stu-id="dbad9-145">The types of policies are:</span></span>

- <span data-ttu-id="dbad9-146">**Anti-spam**</span><span class="sxs-lookup"><span data-stu-id="dbad9-146">**Anti-spam**</span></span>
- <span data-ttu-id="dbad9-147">**Anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="dbad9-147">**Anti-phishing**</span></span>
- <span data-ttu-id="dbad9-148">**Антивредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="dbad9-148">**Anti-malware**</span></span>
- <span data-ttu-id="dbad9-149">**Безопасные вложения ATP** (если ваша подписка включает Microsoft Defender для Office 365)</span><span class="sxs-lookup"><span data-stu-id="dbad9-149">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="dbad9-150">**Безопасные ссылки ATP** (если ваша подписка включает Microsoft Defender для Office 365)</span><span class="sxs-lookup"><span data-stu-id="dbad9-150">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="dbad9-151">В представлении по умолчанию все свернуто.</span><span class="sxs-lookup"><span data-stu-id="dbad9-151">In the default view, everything is collapsed.</span></span> <span data-ttu-id="dbad9-152">Рядом с каждой политикой приводится сводка результатов сравнения политик (которые можно изменить) и параметров в соответствующих политиках для профилей защиты Standard или Strict (которые нельзя изменить).</span><span class="sxs-lookup"><span data-stu-id="dbad9-152">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="dbad9-153">Вы увидите следующие сведения для профиля защиты, с чем сравниваем:</span><span class="sxs-lookup"><span data-stu-id="dbad9-153">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="dbad9-154">**Зеленый** цвет: все параметры во всех существующих политиках по крайней мере так же защищены, как и профиль защиты.</span><span class="sxs-lookup"><span data-stu-id="dbad9-154">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="dbad9-155">**Amber**: небольшое количество параметров в существующих политиках не так защищено, как профиль защиты.</span><span class="sxs-lookup"><span data-stu-id="dbad9-155">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="dbad9-156">**Красный**— значительное количество параметров в существующих политиках не так защищено, как профиль защиты.</span><span class="sxs-lookup"><span data-stu-id="dbad9-156">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="dbad9-157">Это может быть несколько параметров во многих политиках или несколько параметров в одной политике.</span><span class="sxs-lookup"><span data-stu-id="dbad9-157">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="dbad9-158">Для сравнения вы увидите текст: все **параметры** следуют \<**Standard** or **Strict**\> **рекомендациям.**</span><span class="sxs-lookup"><span data-stu-id="dbad9-158">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="dbad9-159">В противном случае вы увидите число рекомендуемых параметров, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="dbad9-159">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="dbad9-160">При **расширении имени группы и параметра** политики будут раскрыт все политики и связанные параметры в каждой конкретной политике, требуя внимания.</span><span class="sxs-lookup"><span data-stu-id="dbad9-160">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="dbad9-161">Вы также можете развернуть политику определенного типа (например, **"Anti-spam"),** чтобы увидеть только эти параметры в политиках тех типов, которые требуют вашего внимания.</span><span class="sxs-lookup"><span data-stu-id="dbad9-161">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="dbad9-162">Если в сравнении нет рекомендаций по улучшению (зеленый цвет), то при расширении политики ничего не будет.</span><span class="sxs-lookup"><span data-stu-id="dbad9-162">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="dbad9-163">Если имеется ряд рекомендаций по улучшению (ярму или красный цвет), параметры, которые требуют внимания, будут раскрыты и соответствующие сведения будут открыть в следующих столбцах:</span><span class="sxs-lookup"><span data-stu-id="dbad9-163">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="dbad9-164">Имя параметра, который требует вашего внимания.</span><span class="sxs-lookup"><span data-stu-id="dbad9-164">The name of the setting that requires your attention.</span></span> <span data-ttu-id="dbad9-165">Например, на предыдущем снимке экрана  это пороговое значение массовой рассылки в политике борьбы с нежелательной почтой.</span><span class="sxs-lookup"><span data-stu-id="dbad9-165">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="dbad9-166">**Политика**: имя затронутой политики, которая содержит параметр.</span><span class="sxs-lookup"><span data-stu-id="dbad9-166">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="dbad9-167">**Применяется к**: количество пользователей, к которых применяются затронутые политики.</span><span class="sxs-lookup"><span data-stu-id="dbad9-167">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="dbad9-168">**Текущая** конфигурация: текущее значение параметра.</span><span class="sxs-lookup"><span data-stu-id="dbad9-168">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="dbad9-169">**Дата последнего** изменения: дата последнего изменения политики.</span><span class="sxs-lookup"><span data-stu-id="dbad9-169">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="dbad9-170">**Рекомендации:** значение параметра в профиле стандартной или строгой защиты.</span><span class="sxs-lookup"><span data-stu-id="dbad9-170">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="dbad9-171">Чтобы изменить значение параметра в политике в соответствие с рекомендованным значением в профиле защиты, нажмите кнопку **"Принять".**</span><span class="sxs-lookup"><span data-stu-id="dbad9-171">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="dbad9-172">Если изменение успешно, вы увидите сообщение "Рекомендации **успешно приняты".**</span><span class="sxs-lookup"><span data-stu-id="dbad9-172">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="dbad9-173">Нажмите **кнопку** "Обновить", чтобы увидеть сокращенный номер рекомендаций и удаление определенной строки параметров или политики из результатов.</span><span class="sxs-lookup"><span data-stu-id="dbad9-173">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="dbad9-174">Анализ смещения конфигурации и вкладка "История" в анализаторе конфигурации</span><span class="sxs-lookup"><span data-stu-id="dbad9-174">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="dbad9-175">Эта вкладка позволяет отслеживать изменения, внесенные в пользовательские политики безопасности.</span><span class="sxs-lookup"><span data-stu-id="dbad9-175">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="dbad9-176">По умолчанию отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="dbad9-176">By default, the following information is displayed:</span></span>

- <span data-ttu-id="dbad9-177">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="dbad9-177">**Last modified**</span></span>
- <span data-ttu-id="dbad9-178">**Изменено**</span><span class="sxs-lookup"><span data-stu-id="dbad9-178">**Modified by**</span></span>
- <span data-ttu-id="dbad9-179">**Имя параметра**</span><span class="sxs-lookup"><span data-stu-id="dbad9-179">**Setting Name**</span></span>
- <span data-ttu-id="dbad9-180">**Политика**</span><span class="sxs-lookup"><span data-stu-id="dbad9-180">**Policy**</span></span>
- <span data-ttu-id="dbad9-181">**Тип**</span><span class="sxs-lookup"><span data-stu-id="dbad9-181">**Type**</span></span>

<span data-ttu-id="dbad9-182">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="dbad9-182">To filter the results, click **Filter**.</span></span> <span data-ttu-id="dbad9-183">В **отобраанной** области фильтров можно выбрать один из следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="dbad9-183">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="dbad9-184">**Время начала и** **время окончания** (дата)</span><span class="sxs-lookup"><span data-stu-id="dbad9-184">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="dbad9-185">**Стандартная или** **строгая защита**</span><span class="sxs-lookup"><span data-stu-id="dbad9-185">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="dbad9-186">Чтобы экспортировать результаты в CSV-файл, нажмите кнопку **"Экспорт".**</span><span class="sxs-lookup"><span data-stu-id="dbad9-186">To export the results to a .csv file, click **Export**.</span></span>

![Анализ смещения конфигурации и представление истории в анализаторе конфигурации](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
