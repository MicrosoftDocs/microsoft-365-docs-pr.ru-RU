---
title: Анализатор конфигураций для политик безопасности
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
description: Администраторы могут узнать, как использовать анализатор конфигураций для поиска и устранения политик безопасности, содержащих параметры, которые распространяются ниже стандартных политик безопасности защиты и строгих мер защиты.
ms.openlocfilehash: 4515efcd73d40eae93523c6ef139553420e48677
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825777"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="fedcc-103">Анализатор конфигураций для политик защиты в eop и Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="fedcc-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="fedcc-104">Функции, описанные в этой статье, входят в версию Preview, недоступны во всех организациях и могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="fedcc-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span>

<span data-ttu-id="fedcc-105">Анализатор конфигураций в Центре соответствия требованиям безопасности & представляет собой централизованное расположение для поиска и исправления любых политик безопасности, содержащих параметры, не включающие параметры профиля стандартной защиты и строгой [защиты, в стандартных политиках безопасности.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="fedcc-105">Configuration analyzer in the Security & Compliance center provides a central location to find and fix any of your security policies that contain settings that are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="fedcc-106">Анализатор конфигурации анализирует следующие типы политик:</span><span class="sxs-lookup"><span data-stu-id="fedcc-106">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="fedcc-107">**Политики Exchange Online Protection (EOP).** Сюда входят организации Microsoft 365 с почтовыми ящиками Exchange Online, а также автономные организации EOP без почтовых ящиков Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="fedcc-107">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="fedcc-108">[Политики защиты от нежелательной почты.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="fedcc-108">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="fedcc-109">[Политики защиты от вредоносных программ.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="fedcc-109">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="fedcc-110">[Политики защиты от фишинга EOP.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="fedcc-110">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="fedcc-111">**Политики Office 365 Advanced Threat Protection (ATP). К**ним относятся организации с дополнительными подписками Microsoft 365 E5 или Office 365 ATP:</span><span class="sxs-lookup"><span data-stu-id="fedcc-111">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="fedcc-112">Политики защиты от фишинга atP, в ключа которые входят:</span><span class="sxs-lookup"><span data-stu-id="fedcc-112">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="fedcc-113">Такие же [параметры спуфинга,](set-up-anti-phishing-policies.md#spoof-settings) что и в политиках eop для защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="fedcc-113">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="fedcc-114">Параметры олицетворения</span><span class="sxs-lookup"><span data-stu-id="fedcc-114">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="fedcc-115">Расширенные пороговые значения фишинга</span><span class="sxs-lookup"><span data-stu-id="fedcc-115">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="fedcc-116">[Политики безопасных ссылок.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users)</span><span class="sxs-lookup"><span data-stu-id="fedcc-116">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span></span>

  - <span data-ttu-id="fedcc-117">[Политики безопасных вложений.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users)</span><span class="sxs-lookup"><span data-stu-id="fedcc-117">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span></span>

<span data-ttu-id="fedcc-118">Значения **стандартных** **и строгих** параметров политики, используемые в качестве базовых параметров, описаны в рекомендуемых параметрах для [безопасности EOP и Office 365 ATP.](recommended-settings-for-eop-and-office365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="fedcc-118">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fedcc-119">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="fedcc-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fedcc-120">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="fedcc-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="fedcc-121">Чтобы перейти непосредственно на страницу **анализатора** конфигураций, используйте <https://protection.office.com/configurationAnalyzer> этот параметр.</span><span class="sxs-lookup"><span data-stu-id="fedcc-121">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="fedcc-122">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="fedcc-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="fedcc-123">Чтобы вы могли выполнить процедуры, упомянутые в этой теме, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="fedcc-123">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="fedcc-124">Чтобы использовать анализатор конфигурации **и обновлять** политики безопасности, вы должны быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="fedcc-124">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="fedcc-125">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fedcc-125">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="fedcc-126">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="fedcc-126">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="fedcc-127">Для доступа только для чтения к анализатору конфигураций вы должны быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="fedcc-127">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="fedcc-128">**Средство считывания сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fedcc-128">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="fedcc-129">**Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="fedcc-129">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="fedcc-130">Использование анализатора конфигураций в Центре безопасности & центра соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="fedcc-130">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="fedcc-131">В Центре безопасности & **Threat management** выберите анализатор \> **настройки** \> **политики управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="fedcc-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Мини-приложение анализатора конфигурации на странице "Политика \> управления угрозами"](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="fedcc-133">Анализатор конфигурации имеет две основные вкладки:</span><span class="sxs-lookup"><span data-stu-id="fedcc-133">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="fedcc-134">**Параметры и рекомендации: выбирается**стандартная или строгосовая и сравниваются эти параметры с существующими политиками безопасности.</span><span class="sxs-lookup"><span data-stu-id="fedcc-134">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="fedcc-135">В результатах можно настроить значения параметров так, чтобы они были на тот же уровень, что и стандартный или строгий.</span><span class="sxs-lookup"><span data-stu-id="fedcc-135">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="fedcc-136">**Анализ и история проектов**конфигураций: это представление позволяет отслеживать изменения, внесенные в политики на основе результатов анализатора конфигурации со временем.</span><span class="sxs-lookup"><span data-stu-id="fedcc-136">**Configuration drift analysis and history**: This view allows to track the changes that you've made to your policies based on the results of the configuration analyzer over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="fedcc-137">Вкладка "Настройка и рекомендации" в анализаторе конфигураций</span><span class="sxs-lookup"><span data-stu-id="fedcc-137">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="fedcc-138">По умолчанию вкладка по умолчанию по умолчанию по умолчанию по умолчанию отображается с рамки стандартной защиты.</span><span class="sxs-lookup"><span data-stu-id="fedcc-138">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="fedcc-139">Можно переключиться на сравнение профиля строгой защиты, **щелкнув рекомендации "Вид строгих элементов".**</span><span class="sxs-lookup"><span data-stu-id="fedcc-139">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="fedcc-140">Чтобы вернуться к другому, **выберите рекомендации по стандартному просмотру.**</span><span class="sxs-lookup"><span data-stu-id="fedcc-140">To switch back, select **View Standard recommendations**.</span></span>

![Представление параметров и рекомендаций в анализаторе конфигураций](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="fedcc-142">По умолчанию **столбец "Имя группы/параметр"** содержит свернутое представление разных типов политик безопасности и количество параметров в этих политиках, которые нуждаются в улучшении (если применимо).</span><span class="sxs-lookup"><span data-stu-id="fedcc-142">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security polices and the number of settings in those policies that need improvement (if any).</span></span> <span data-ttu-id="fedcc-143">Ниже перечислены типы политик.</span><span class="sxs-lookup"><span data-stu-id="fedcc-143">The types of policies are:</span></span>

- <span data-ttu-id="fedcc-144">**Защита от нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="fedcc-144">**Anti-spam**</span></span>
- <span data-ttu-id="fedcc-145">**Защита от фишинга**</span><span class="sxs-lookup"><span data-stu-id="fedcc-145">**Anti-phishing**</span></span>
- <span data-ttu-id="fedcc-146">**Защита от вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="fedcc-146">**Anti-malware**</span></span>
- <span data-ttu-id="fedcc-147">**Безопасные вложения ATP** (если ваша подписка включает ATP)</span><span class="sxs-lookup"><span data-stu-id="fedcc-147">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="fedcc-148">**Безопасные ссылки ATP** (если ваша подписка включает ATP)</span><span class="sxs-lookup"><span data-stu-id="fedcc-148">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="fedcc-149">В представлении по умолчанию все свернуто.</span><span class="sxs-lookup"><span data-stu-id="fedcc-149">In the default view, everything is collapsed.</span></span> <span data-ttu-id="fedcc-150">Рядом с каждой политикой отображается сводка результатов сравнения для политик (которые можно изменить) и параметры в соответствующих политиках для профилей стандартной или строгой защиты (которые нельзя изменить).</span><span class="sxs-lookup"><span data-stu-id="fedcc-150">Next to each policy, a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify) are displayed.</span></span> <span data-ttu-id="fedcc-151">Посмотрены следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="fedcc-151">You'll see the following information:</span></span>

- <span data-ttu-id="fedcc-152">**Зеленый:** все параметры в существующих политиках являются как минимум безопасным, таким и безопасным профилем защиты, с которым вы сравниваете.</span><span class="sxs-lookup"><span data-stu-id="fedcc-152">**Green**: All settings in all existing policies are at least as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="fedcc-153">**Амбда-авандр.** Небольшое количество параметров в существующих политиках не является безопасным, таким как профиль защиты, с которым вы сравниваете.</span><span class="sxs-lookup"><span data-stu-id="fedcc-153">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="fedcc-154">**Красный:** существенное число параметров в существующих политиках не является безопасным, таким как сравниваемый профиль защиты.</span><span class="sxs-lookup"><span data-stu-id="fedcc-154">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span> <span data-ttu-id="fedcc-155">Это могут быть несколько параметров в нескольких политиках или множестве параметров в одной политике.</span><span class="sxs-lookup"><span data-stu-id="fedcc-155">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="fedcc-156">Для избранных сравнений вы увидите текст: **Все настройки следуют** \<**Standard** or **Strict**\> **рекомендациям.**</span><span class="sxs-lookup"><span data-stu-id="fedcc-156">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="fedcc-157">В противном случае будет отображено число рекомендуемых параметров, которые нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="fedcc-157">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="fedcc-158">Если развернуть имя **группы или параметра политики,** будут доступны все политики и связанные с ней параметры в каждой конкретной политике, требующие внимания.</span><span class="sxs-lookup"><span data-stu-id="fedcc-158">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="fedcc-159">Кроме того, вы можете расширить политику определенного типа (например, **"Защита от нежелательной**почты"), чтобы просмотреть только параметры в политиках такого типа, применяемой к вашему вмедению.</span><span class="sxs-lookup"><span data-stu-id="fedcc-159">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="fedcc-160">Если рекомендации по улучшению (зеленые), расширение политики ничего не проявляет.</span><span class="sxs-lookup"><span data-stu-id="fedcc-160">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="fedcc-161">При наличии нескольких рекомендаций по улучшению (абзацам или красному), то параметры, требующие внимания, будут показаны, и соответствующие сведения отображаются в следующих столбцах:</span><span class="sxs-lookup"><span data-stu-id="fedcc-161">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="fedcc-162">Имя параметра, требующий вашего внимания.</span><span class="sxs-lookup"><span data-stu-id="fedcc-162">The name of the setting that requires your attention.</span></span> <span data-ttu-id="fedcc-163">Например, на предыдущем снимке экрана порог **массовой рассылки** указан в политике защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="fedcc-163">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="fedcc-164">**Policy**: имя затронутой политики, которая содержит данный параметр.</span><span class="sxs-lookup"><span data-stu-id="fedcc-164">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="fedcc-165">**Применяется к:** количество пользователей, к которым применяются затронутые политики.</span><span class="sxs-lookup"><span data-stu-id="fedcc-165">**Applied to**: The number of user that the affected policies are applied to.</span></span>

- <span data-ttu-id="fedcc-166">**Текущая конфигурация:** текущее значение параметра.</span><span class="sxs-lookup"><span data-stu-id="fedcc-166">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="fedcc-167">**Дата**последнего изменения: дата последнего изменения политики.</span><span class="sxs-lookup"><span data-stu-id="fedcc-167">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="fedcc-168">**Рекомендации:** значение параметра в стандартной или строгой защите профиля.</span><span class="sxs-lookup"><span data-stu-id="fedcc-168">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="fedcc-169">Чтобы изменить значение параметра политики в соответствии с рекомендуемым значением в профиле защиты, щелкните **"Примет".**</span><span class="sxs-lookup"><span data-stu-id="fedcc-169">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="fedcc-170">Если изменение прошло успешно, отобразится сообщение **"Рекомендации успешно внедряются".**</span><span class="sxs-lookup"><span data-stu-id="fedcc-170">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="fedcc-171">Нажмите **кнопку** "Обновить", чтобы уменьшить число рекомендаций и удалить строку конкретного параметра или политики из результатов.</span><span class="sxs-lookup"><span data-stu-id="fedcc-171">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="fedcc-172">Вкладка анализа проектов и истории конфигурации в анализаторе конфигураций</span><span class="sxs-lookup"><span data-stu-id="fedcc-172">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="fedcc-173">Эта вкладка позволяет отслеживать изменения, внесенные в настраиваемые политики безопасности, в соответствии с информацией анализатора безопасности.</span><span class="sxs-lookup"><span data-stu-id="fedcc-173">This tab allows you to track the changes that you've made to your custom security policies based on the information in the security analyzer.</span></span> <span data-ttu-id="fedcc-174">По умолчанию отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="fedcc-174">By default, the following information is displayed:</span></span>

- <span data-ttu-id="fedcc-175">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="fedcc-175">**Last modified**</span></span>
- <span data-ttu-id="fedcc-176">**Автор изменений.**</span><span class="sxs-lookup"><span data-stu-id="fedcc-176">**Modified by**</span></span>
- <span data-ttu-id="fedcc-177">**Имя параметра**</span><span class="sxs-lookup"><span data-stu-id="fedcc-177">**Setting Name**</span></span>
- <span data-ttu-id="fedcc-178">**Политика**</span><span class="sxs-lookup"><span data-stu-id="fedcc-178">**Policy**</span></span>
- <span data-ttu-id="fedcc-179">**Тип**</span><span class="sxs-lookup"><span data-stu-id="fedcc-179">**Type**</span></span>

<span data-ttu-id="fedcc-180">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="fedcc-180">To filter the results, click **Filter**.</span></span> <span data-ttu-id="fedcc-181">Во **всплывающем** окне "Фильтры" можно выбрать один из следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="fedcc-181">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="fedcc-182">**Время начала и** **окончания** (дата)</span><span class="sxs-lookup"><span data-stu-id="fedcc-182">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="fedcc-183">**Стандартная защита** **или строгая защита**</span><span class="sxs-lookup"><span data-stu-id="fedcc-183">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="fedcc-184">Чтобы экспортировать результаты в CSV-файл, нажмите кнопку **Экспорт.**</span><span class="sxs-lookup"><span data-stu-id="fedcc-184">To export the results to a .csv file, click **Export**.</span></span>

![Анализ проектов конфигураций и история конфигурации в анализаторе конфигураций](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
