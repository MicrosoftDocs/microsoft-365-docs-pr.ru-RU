---
title: Повышенная безопасность Microsoft 365 для тестовой среды Microsoft 365 для предприятий
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Используйте это руководство по лаборатории тестирования, чтобы включить дополнительные параметры безопасности Microsoft 365 в тестовой среде Microsoft 365 для предприятий.
ms.openlocfilehash: d385688a6e59ee500442bcf1b815dfd165102242
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847004"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="721a9-103">Повышенная безопасность Microsoft 365 для тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="721a9-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="721a9-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для корпоративных тестовых сред.*</span><span class="sxs-lookup"><span data-stu-id="721a9-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="721a9-105">С помощью инструкций в этой статье вы настроите дополнительные параметры Microsoft 365 для повышения безопасности в тестовой среде Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="721a9-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="721a9-107">Щелкните [здесь](../downloads/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 для крупных предприятий.</span><span class="sxs-lookup"><span data-stu-id="721a9-107">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="721a9-108">Этап 1. Создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="721a9-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="721a9-109">Если вы просто хотите настроить повышенную безопасность Microsoft 365 облегченным способом с минимальными требованиями, следуйте инструкциям в базовой конфигурации [Lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="721a9-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="721a9-110">Если вы хотите настроить повышенную безопасность Microsoft 365 на имитированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="721a9-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="721a9-111">Для тестирования повышенной безопасности Microsoft 365 не требуется среда тестирования имитированной организации, которая включает имитированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="721a9-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="721a9-112">Он предоставляется здесь в качестве варианта, чтобы вы могли протестировать автоматическое лицензирование и членство в группах и поэкспериментировать с ним в типичной для организации среде.</span><span class="sxs-lookup"><span data-stu-id="721a9-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="721a9-113">Этап 2. Настройка повышенной безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="721a9-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="721a9-114">На этом этапе вы включаете повышенную безопасность Microsoft 365 для тестовой среды Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="721a9-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="721a9-115">Дополнительные сведения и параметры см. в [подстройке "Настройка клиента для повышения безопасности".](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)</span><span class="sxs-lookup"><span data-stu-id="721a9-115">For additional details and settings, see [Configure your tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="721a9-116">Настройка SharePoint Online для блокировки приложений, которые не поддерживают современную проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="721a9-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="721a9-117">К приложениям, которые не [](../security/office-365-security/microsoft-365-policies-configurations.md) поддерживают современную проверку подлинности, не могут применяться конфигурации доступа к удостоверениям и устройствам, что является важным элементом защиты подписки Microsoft 365 и ее цифровых активов.</span><span class="sxs-lookup"><span data-stu-id="721a9-117">Apps that do not support modern authentication cannot have [identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="721a9-118">Перейдите в Центр администрирования Microsoft 365 () и войдите в свою подписку лаборатории тестирования Microsoft 365 с помощью учетной записи [https://portal.microsoft.com](https://portal.microsoft.com) глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="721a9-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="721a9-119">Если вы используете облегченной тестовой среды Microsoft 365, во sign in from your local computer.</span><span class="sxs-lookup"><span data-stu-id="721a9-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="721a9-120">Если вы используете тестовую среду Microsoft 365 с имитацией предприятия, воспользуйтесь порталом [Azure,](https://portal.azure.com) чтобы подключиться к виртуальной машине CLIENT1, а затем во sign in from CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="721a9-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="721a9-121">На новой  **вкладке Центра администрирования Microsoft 365** в центре администрирования в левой области навигации щелкните **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="721a9-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="721a9-122">На новой **вкладке Центра администрирования SharePoint** щелкните **"Политики > управления доступом".**</span><span class="sxs-lookup"><span data-stu-id="721a9-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="721a9-123">Щелкните **приложения, которые не поддерживают современную** проверку подлинности, выберите "Заблокировать **доступ"** и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="721a9-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="721a9-124">Включить Защитник для Office 365 для SharePoint, OneDrive для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="721a9-124">Enable Defender for Office 365 for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="721a9-125">Защитник Office 365 для SharePoint, OneDrive и Microsoft Teams защищает организацию от случайного совместного использования вредоносных файлов.</span><span class="sxs-lookup"><span data-stu-id="721a9-125">Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="721a9-126">Перейдите в [Центр безопасности & соответствия](https://protection.office.com) требованиям и войдите с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="721a9-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="721a9-127">В левой области навигации в области управления угрозами **щелкните** **"Политика"** и выберите "Безопасные **вложения".**</span><span class="sxs-lookup"><span data-stu-id="721a9-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **Safe Attachments**.</span></span> 

3. <span data-ttu-id="721a9-128">В **области "Защита файлов" в SharePoint, OneDrive и Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="721a9-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="721a9-129">выберите **"Включить ATP для SharePoint, OneDrive и Microsoft Teams".**</span><span class="sxs-lookup"><span data-stu-id="721a9-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="721a9-130">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="721a9-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="721a9-131">Включить антивредоносную программу</span><span class="sxs-lookup"><span data-stu-id="721a9-131">Enable anti-malware</span></span>

<span data-ttu-id="721a9-132">Вредоносные программы состоят из вирусов и программ-шпионов.</span><span class="sxs-lookup"><span data-stu-id="721a9-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="721a9-133">Вирусы заражают другие программы и данные, а также распространяются по компьютеру в поисках программ, которые можно заразить.</span><span class="sxs-lookup"><span data-stu-id="721a9-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="721a9-134">Программы-шпионы относятся к вредоносным программам, которые собирают личные сведения пользователей, например данные для входа и персональные данные, и отправляют их обратно создателю этих программ.</span><span class="sxs-lookup"><span data-stu-id="721a9-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="721a9-135">Microsoft 365 имеет встроенные возможности фильтрации нежелательной почты и вредоносных программ, которые помогают защитить входящие и исходящие сообщения от вредоносных программ и защитить вас от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="721a9-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="721a9-136">Дополнительные сведения см. в & защиты от [вредоносных программ.](../security/office-365-security/anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="721a9-136">For more information, see [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="721a9-137">Чтобы убедиться, что обработка вредоносных программ выполняется для файлов с общими типами файлов вложений:</span><span class="sxs-lookup"><span data-stu-id="721a9-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="721a9-138">Нажмите кнопку "Назад" в браузере, чтобы вернуться на **страницу "Политика".**</span><span class="sxs-lookup"><span data-stu-id="721a9-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="721a9-139">Щелкните **"Антивредоносная программа".**</span><span class="sxs-lookup"><span data-stu-id="721a9-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="721a9-140">Дважды щелкните политику с именем **Default**.</span><span class="sxs-lookup"><span data-stu-id="721a9-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="721a9-141">В **окне политики "Антивредоносная** программа" щелкните **"Параметры".**</span><span class="sxs-lookup"><span data-stu-id="721a9-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="721a9-142">В **области фильтра "Общие типы вложений"** выберите **"В"** и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="721a9-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="721a9-143">Этап 3. Изучение панели мониторинга безопасности</span><span class="sxs-lookup"><span data-stu-id="721a9-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="721a9-144">Управление угрозами в Microsoft 365 помогает контролировать доступ с мобильных устройств к данным организации, защищать организацию от потери данных и защищать входящие и исходящие сообщения от вредоносных программ и спама.</span><span class="sxs-lookup"><span data-stu-id="721a9-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="721a9-145">Вы также можете использовать управление угрозами, чтобы защитить репутацию домена и определить, являются ли отправителю вредоносно спуфингом учетных записей из вашего домена.</span><span class="sxs-lookup"><span data-stu-id="721a9-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="721a9-146">Чтобы увидеть панель мониторинга безопасности:</span><span class="sxs-lookup"><span data-stu-id="721a9-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="721a9-147">При необходимости перейдите в Центр безопасности [& соответствия](https://protection.office.com) требованиям и войдите с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="721a9-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="721a9-148">В левой области навигации в области управления **угрозами** щелкните **"Информационная панель".**</span><span class="sxs-lookup"><span data-stu-id="721a9-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="721a9-149">Внимательно ознакомьтесь со всеми карточками на панели мониторинга, чтобы ознакомиться с предоставленной информацией.</span><span class="sxs-lookup"><span data-stu-id="721a9-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="721a9-150">Дополнительные сведения см. в [панели мониторинга безопасности.](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard)</span><span class="sxs-lookup"><span data-stu-id="721a9-150">For more information, see [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="721a9-151">Этап 4. Изучение оценки безопасности (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="721a9-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="721a9-152">Оценка безопасности (Майкрософт) показывает уровень безопасности в качестве числа, который указывает текущий уровень относительно функций, доступных в вашей подписке.</span><span class="sxs-lookup"><span data-stu-id="721a9-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="721a9-153">Кроме того, здесь вы можете получить список действий по улучшению показателей.</span><span class="sxs-lookup"><span data-stu-id="721a9-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="721a9-154">Создайте новую вкладку в браузере и перейдите в Центр безопасности [Microsoft 365](https://security.microsoft.com/)и щелкните "Оценка **безопасности".**</span><span class="sxs-lookup"><span data-stu-id="721a9-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="721a9-155">На **вкладке "Обзор"**  обратите внимание на текущую оценку безопасности и ее сравнение с глобальным средним значением и количеством подписок с одинаковым количеством лицензий.</span><span class="sxs-lookup"><span data-stu-id="721a9-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="721a9-156">На **вкладке "Действия** по улучшению" прочитайте список действий, которые можно принять, чтобы увеличить свой показатель.</span><span class="sxs-lookup"><span data-stu-id="721a9-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="721a9-157">Дополнительные сведения см. в [записи "Оценка безопасности (Майкрософт)".](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)</span><span class="sxs-lookup"><span data-stu-id="721a9-157">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="next-steps"></a><span data-ttu-id="721a9-158">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="721a9-158">Next steps</span></span>

<span data-ttu-id="721a9-159">Изучите [дополнительные функции](m365-enterprise-test-lab-guides.md#information-protection) и возможности защиты информации в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="721a9-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="721a9-160">См. также</span><span class="sxs-lookup"><span data-stu-id="721a9-160">See also</span></span>

[<span data-ttu-id="721a9-161">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="721a9-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="721a9-162">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="721a9-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="721a9-163">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="721a9-163">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
