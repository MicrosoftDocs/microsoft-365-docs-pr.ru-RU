---
title: Повышенная безопасность Microsoft 365 для microsoft 365 для тестовой среды предприятия
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
description: Используйте это руководство по тестовой лаборатории, чтобы включить дополнительные параметры безопасности Microsoft 365 в microsoft 365 для корпоративной тестовой среды.
ms.openlocfilehash: 186452396af4227a94a7f6cd0fa0109e9d6a7e17
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051274"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="cb1c8-103">Повышенная безопасность Microsoft 365 для microsoft 365 для тестовой среды предприятия</span><span class="sxs-lookup"><span data-stu-id="cb1c8-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="cb1c8-104">*Это руководство по тестовой лаборатории можно использовать только для Microsoft 365 для корпоративных тестовых сред.*</span><span class="sxs-lookup"><span data-stu-id="cb1c8-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="cb1c8-105">С помощью инструкций в этой статье вы настроите дополнительные параметры Microsoft 365 для повышения безопасности в microsoft 365 для корпоративной тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="cb1c8-107">Щелкните [здесь](../downloads/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 для крупных предприятий.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-107">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="cb1c8-108">Этап 1. Создание microsoft 365 для корпоративной тестовой среды</span><span class="sxs-lookup"><span data-stu-id="cb1c8-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="cb1c8-109">Если вы просто хотите настроить повышенную безопасность Microsoft 365 легким способом с минимальными требованиями, следуйте инструкциям в [легкой базовой конфигурации.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="cb1c8-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="cb1c8-110">Если вы хотите настроить повышенную безопасность Microsoft 365 в смоделированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="cb1c8-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb1c8-111">Для тестирования повышенной безопасности Microsoft 365 не требуется смоделированная корпоративная тестовая среда, которая включает смоделированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса служб домена Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="cb1c8-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="cb1c8-112">Он предоставляется здесь в качестве параметра, чтобы можно было протестировать автоматическое лицензирование и членство в группе и поэкспериментировать с ним в среде, которая представляет типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="cb1c8-113">Этап 2. Настройка повышенной безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb1c8-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="cb1c8-114">На этом этапе вы включаете повышенную безопасность Microsoft 365 для microsoft 365 для корпоративной тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="cb1c8-115">Дополнительные сведения и параметры см. в [материале Configure your tenant for increased security.](/office365/securitycompliance/tenant-wide-setup-for-increased-security)</span><span class="sxs-lookup"><span data-stu-id="cb1c8-115">For additional details and settings, see [Configure your tenant for increased security](/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="cb1c8-116">Настройка SharePoint Online для блокировки приложений, не поддерживаюных современную проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="cb1c8-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="cb1c8-117">Приложения, не поддерживаюющие современную [](../security/defender-365-security/microsoft-365-policies-configurations.md) проверку подлинности, не могут применять к ним конфигурации доступа к удостоверениям и устройствам, что является важным элементом обеспечения безопасности подписки Microsoft 365 и ее цифровых активов.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-117">Apps that do not support modern authentication cannot have [identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="cb1c8-118">Перейдите в центр администрирования Microsoft 365 и войдите в свою тестовую лабораторную подписку [https://portal.microsoft.com](https://portal.microsoft.com) Microsoft 365 с учетной записью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="cb1c8-119">Если вы используете легкую тестовую среду Microsoft 365, вопишитесь с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="cb1c8-120">Если вы используете смоделированную тестовую среду Microsoft 365, используйте портал [Azure](https://portal.azure.com) для подключения к виртуальной машине CLIENT1, а затем впишитесь из CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="cb1c8-121">На новой вкладке Центр администрирования Microsoft  **365** в центре администрирования в центре администрирования в левой области навигации щелкните **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="cb1c8-122">На новой **вкладке Центр администрирования SharePoint** нажмите **кнопку Политики > управления доступом.**</span><span class="sxs-lookup"><span data-stu-id="cb1c8-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="cb1c8-123">Щелкните **приложения, которые не поддерживают современную проверку** подлинности, выберите **блок-доступ** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="cb1c8-124">Включить Defender для Office 365 для SharePoint, OneDrive для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cb1c8-124">Enable Defender for Office 365 for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="cb1c8-125">Defender for Office 365 для SharePoint, OneDrive и Microsoft Teams защищает организацию от непреднамеренного обмена вредоносными файлами.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-125">Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="cb1c8-126">Перейдите в [Центр & безопасности](https://protection.office.com) и войдите в глобальную учетную запись администратора.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="cb1c8-127">В левой области навигации в области **управления угрозами** нажмите кнопку **Политика** и нажмите кнопку **Безопасные вложения**.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **Safe Attachments**.</span></span> 

3. <span data-ttu-id="cb1c8-128">В **статье Protect files in SharePoint, OneDrive и Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="cb1c8-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="cb1c8-129">выберите **включить ATP для SharePoint, OneDrive и Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="cb1c8-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="cb1c8-130">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="cb1c8-131">Включить антивирусную программу</span><span class="sxs-lookup"><span data-stu-id="cb1c8-131">Enable anti-malware</span></span>

<span data-ttu-id="cb1c8-132">Вредоносные программы состоят из вирусов и программ-шпионов.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="cb1c8-133">Вирусы заражают другие программы и данные, а также распространяются по компьютеру в поисках программ, которые можно заразить.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="cb1c8-134">Программы-шпионы относятся к вредоносным программам, которые собирают личные сведения пользователей, например данные для входа и персональные данные, и отправляют их обратно создателю этих программ.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="cb1c8-135">Microsoft 365 обладает встроенными возможностями фильтрации вредоносных программ и спама, которые помогают защитить входящие и исходящие сообщения от вредоносных программ и защитить вас от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="cb1c8-136">Дополнительные сведения см. в [& защиты от нежелательной почты.](../security/defender-365-security/anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="cb1c8-136">For more information, see [Anti-spam & anti-malware protection](../security/defender-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="cb1c8-137">Чтобы убедиться, что обработка вредоносных программ выполняется в файлах с общими типами файлов вложений:</span><span class="sxs-lookup"><span data-stu-id="cb1c8-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="cb1c8-138">Нажмите кнопку "Назад" в браузере, чтобы вернуться на страницу **Политика.**</span><span class="sxs-lookup"><span data-stu-id="cb1c8-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="cb1c8-139">Нажмите **кнопку Anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="cb1c8-140">Дважды щелкните политику с именем **Default**.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="cb1c8-141">В **окне политики по борьбе с вредоносными программами** щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="cb1c8-142">В **соответствии с общими типами вложений фильтр,** выберите **На**, а затем нажмите **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="cb1c8-143">Этап 3. Изучение панели мониторинга безопасности</span><span class="sxs-lookup"><span data-stu-id="cb1c8-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="cb1c8-144">Управление угрозами в Microsoft 365 позволяет контролировать и управлять доступом мобильных устройств к данным организации, защищать организацию от потери данных и защищать входящие и исходящие сообщения от вредоносных программ и нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="cb1c8-145">Вы также используете управление угрозами для защиты репутации домена и определения того, являются ли отправители вредоносными подменами учетных записей из вашего домена.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="cb1c8-146">Чтобы увидеть панель мониторинга безопасности:</span><span class="sxs-lookup"><span data-stu-id="cb1c8-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="cb1c8-147">При необходимости перейдите в [Центр & безопасности](https://protection.office.com) и войдите в свою учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="cb1c8-148">В левой области навигации в области **управления угрозами** щелкните **Панель мониторинга**.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="cb1c8-149">Внимательно ознакомьтесь со всеми картами на панели мониторинга, чтобы ознакомиться с предоставленной информацией.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="cb1c8-150">Дополнительные сведения см. в [странице Панель мониторинга безопасности.](../security/defender-365-security/security-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="cb1c8-150">For more information, see [Security Dashboard](../security/defender-365-security/security-dashboard.md).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="cb1c8-151">Этап 4. Изучение показателей безопасности Майкрософт</span><span class="sxs-lookup"><span data-stu-id="cb1c8-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="cb1c8-152">Microsoft Secure Score показывает вашу позицию безопасности как номер, который указывает текущий уровень относительно функций, доступных в вашей подписке.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="cb1c8-153">В нем также приводится список действий по улучшению, которые можно принять для улучшения показателей.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="cb1c8-154">Создайте новую вкладку в браузере и перейдите в [центр безопасности Microsoft 365,](https://security.microsoft.com/)а затем нажмите **кнопку Secure score**.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="cb1c8-155">На **вкладке Обзор**  обратите внимание на текущую безопасную оценку и ее сравнение с глобальным средним показателем и подписками с аналогичным числом лицензий.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="cb1c8-156">На **вкладке Действия по улучшению** ознакомьтесь со списком действий, которые можно принять для увеличения балла.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="cb1c8-157">Дополнительные сведения см. в [сайте Microsoft Secure Score.](../security/defender/microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="cb1c8-157">For more information, see [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="cb1c8-158">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="cb1c8-158">Next steps</span></span>

<span data-ttu-id="cb1c8-159">Ознакомьтесь [с дополнительными функциями](m365-enterprise-test-lab-guides.md#information-protection) и возможностями защиты информации в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb1c8-160">См. также</span><span class="sxs-lookup"><span data-stu-id="cb1c8-160">See also</span></span>

[<span data-ttu-id="cb1c8-161">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="cb1c8-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="cb1c8-162">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="cb1c8-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="cb1c8-163">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="cb1c8-163">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)