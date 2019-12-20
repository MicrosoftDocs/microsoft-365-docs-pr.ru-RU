---
title: Повышенная безопасность Microsoft 365 для тестовой среды Microsoft 365 корпоративный
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
description: Используйте это руководство по лаборатории тестирования для включения дополнительных параметров безопасности Microsoft 365 для тестовой среды Microsoft 365 Enterprise.
ms.openlocfilehash: 8e8e05f223faedd60ea53683b3531964b3220291
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801694"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c045d-103">Повышенная безопасность Microsoft 365 для тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="c045d-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c045d-104">*Это руководство по лаборатории тестирования можно использовать только для тестовых сред Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="c045d-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="c045d-105">С помощью инструкций, описанных в этой статье, вы настраиваете дополнительные параметры Microsoft 365 для повышения безопасности в тестовой среде Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c045d-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="c045d-107">Щелкните [здесь](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="c045d-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c045d-108">Этап 1. Создание собственной тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="c045d-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c045d-109">Если вы просто хотите настроить усиленную безопасность Microsoft 365 в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="c045d-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="c045d-110">Если вы хотите настроить усиленную безопасность Microsoft 365 на имитации предприятия, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="c045d-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c045d-111">При тестировании повышенной безопасности Microsoft 365 не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="c045d-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="c045d-112">Он предоставляется в качестве параметра, чтобы можно было протестировать автоматизированное членство и членство в группах и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="c045d-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="c045d-113">Этап 2: Настройка усиленной безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c045d-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="c045d-114">На этом этапе вы включите повышенную безопасность Microsoft 365 для тестовой среды Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c045d-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="c045d-115">Дополнительные сведения и параметры можно найти [в статье Настройка клиента Office 365 для повышения безопасности](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="c045d-115">For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="c045d-116">Настройка SharePoint Online для блокирования приложений, не поддерживающих современные проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="c045d-116">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="c045d-117">Приложения, не поддерживающие современные проверки подлинности, не могут иметь примененные к ним [конфигурации удостоверений и доступа к устройствам](microsoft-365-policies-configurations.md) , которые являются важным элементом защиты подписки Microsoft 365 и ее цифровых активов.</span><span class="sxs-lookup"><span data-stu-id="c045d-117">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="c045d-118">Перейдите в центр администрирования Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)) и войдите в свою подписку на тестовую лаборатория Microsoft 365 с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="c045d-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="c045d-119">Если вы используете упрощенную тестовую среду Microsoft 365, войдите с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="c045d-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="c045d-120">Если вы используете имитируемую тестовую среду Microsoft 365, используйте [портал Azure](https://portal.azure.com) , чтобы подключиться к ВИРТУАЛЬНОЙ машине CLIENT1, а затем выполните вход с компьютера CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="c045d-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="c045d-121">На новой вкладке **центра администрирования Microsoft 365** в разделе **центры администрирования** в левой области навигации щелкните элемент **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="c045d-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="c045d-122">На вкладке Новая **центр администрирования SharePoint** выберите **Управление доступом**.</span><span class="sxs-lookup"><span data-stu-id="c045d-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
4. <span data-ttu-id="c045d-123">Щелкните **приложения, не поддерживающие современные проверки подлинности**, выберите **блокировать доступ**и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c045d-123">Click **Apps that don’t support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="c045d-124">Включение расширенной защиты от угроз для SharePoint, OneDrive для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c045d-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="c045d-125">Office 365 Advanced Threat protection (ATP) для SharePoint, OneDrive и Microsoft Teams защищает организацию от случайного предоставления вредоносных файлов.</span><span class="sxs-lookup"><span data-stu-id="c045d-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="c045d-126">Перейдите в [Центр безопасности & безопасности Office 365](https://protection.office.com) и войдите в свою учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="c045d-126">Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="c045d-127">В левой области навигации в разделе **Управление угрозами**щелкните **Политика**, а затем щелкните **безопасные вложения ATP**.</span><span class="sxs-lookup"><span data-stu-id="c045d-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **ATP safe attachments**.</span></span> 

3. <span data-ttu-id="c045d-128">В разделе **Защита файлов в SharePoint, OneDrive и Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="c045d-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="c045d-129">Выберите **включить ATP для SharePoint, OneDrive и Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="c045d-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="c045d-130">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c045d-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="c045d-131">Включение защиты от вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="c045d-131">Enable anti-malware</span></span>

<span data-ttu-id="c045d-132">Вредоносные программы состоят из вирусов и программ-шпионов.</span><span class="sxs-lookup"><span data-stu-id="c045d-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="c045d-133">Вирусы заражают другие программы и данные, а также распространяются по компьютеру в поисках программ, которые можно заразить.</span><span class="sxs-lookup"><span data-stu-id="c045d-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="c045d-134">Программы-шпионы относятся к вредоносным программам, которые собирают личные сведения пользователей, например данные для входа и персональные данные, и отправляют их обратно создателю этих программ.</span><span class="sxs-lookup"><span data-stu-id="c045d-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="c045d-135">В Microsoft 365 имеются встроенные возможности фильтрации вредоносных программ и нежелательной почты, которые помогают защитить входящие и исходящие сообщения от вредоносных программ и защищать вас от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="c045d-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="c045d-136">Дополнительные сведения содержатся в статье [Защита от нежелательной почты & вредоносных программ в Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="c045d-136">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="c045d-137">Чтобы обеспечить выполнение защиты от вредоносных программ для файлов с распространенными типами файлов вложений:</span><span class="sxs-lookup"><span data-stu-id="c045d-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="c045d-138">Нажмите кнопку "назад" в браузере, чтобы вернуться на страницу " **Политика** ".</span><span class="sxs-lookup"><span data-stu-id="c045d-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="c045d-139">Нажмите кнопку **Защита от вредоносных программ**.</span><span class="sxs-lookup"><span data-stu-id="c045d-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="c045d-140">Дважды щелкните политику с именем **Default**.</span><span class="sxs-lookup"><span data-stu-id="c045d-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="c045d-141">В окне **Политика защиты от вредоносных программ** нажмите кнопку **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="c045d-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="c045d-142">В разделе **общий фильтр типов вложений**выберите **включено**и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c045d-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="c045d-143">Этап 3: Проверка панели мониторинга безопасности</span><span class="sxs-lookup"><span data-stu-id="c045d-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="c045d-144">Управление угрозами Office 365 помогает управлять доступом мобильных устройств к данным вашей организации, защитить организацию от потери данных и защищать входящие и исходящие сообщения от вредоносных программ и спама.</span><span class="sxs-lookup"><span data-stu-id="c045d-144">Office 365 threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="c045d-145">Кроме того, управление угрозами используется для защиты репутации домена и определения того, являются ли отправители неумышленно подложными учетными записями из вашего домена.</span><span class="sxs-lookup"><span data-stu-id="c045d-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="c045d-146">Чтобы просмотреть панель мониторинга безопасности:</span><span class="sxs-lookup"><span data-stu-id="c045d-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="c045d-147">При необходимости перейдите в [Центр безопасности & безопасности Office 365](https://protection.office.com) и войдите в свою учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="c045d-147">If needed, go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="c045d-148">В левой области навигации в разделе **Управление угрозами**щелкните **панель мониторинга**.</span><span class="sxs-lookup"><span data-stu-id="c045d-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="c045d-149">Взгляните на все карточки на панели мониторинга, чтобы ознакомиться с предоставленными сведениями.</span><span class="sxs-lookup"><span data-stu-id="c045d-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="c045d-150">Более подробную информацию можно узнать в статье [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span><span class="sxs-lookup"><span data-stu-id="c045d-150">For more information, see [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="c045d-151">Этап 4: Проверка оценки безопасности Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c045d-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="c045d-152">Microsoft Secure Score (Майкрософт) показывает уровень безопасности в виде числа, который указывает на текущий уровень в соответствии с функциями, доступными в вашей подписке.</span><span class="sxs-lookup"><span data-stu-id="c045d-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="c045d-153">Он также предоставляет список действий по улучшению, которые можно предпринять для улучшения оценки.</span><span class="sxs-lookup"><span data-stu-id="c045d-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="c045d-154">Создайте новую вкладку в браузере и перейдите в [Центр безопасности Microsoft 365](https://security.microsoft.com/), а затем щелкните **показатель безопасности**.</span><span class="sxs-lookup"><span data-stu-id="c045d-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="c045d-155">На вкладке **Обзор** Запишите текущий показатель безопасности и сравните его с глобальным средним и подпиской с аналогичным количеством лицензий.</span><span class="sxs-lookup"><span data-stu-id="c045d-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="c045d-156">На вкладке **действия по улучшению** прочтите список действий, которые можно предпринять для увеличения оценки.</span><span class="sxs-lookup"><span data-stu-id="c045d-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="c045d-157">Более подробную информацию можно узнать в [статье Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span><span class="sxs-lookup"><span data-stu-id="c045d-157">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c045d-158">Дальнейшие действия:</span><span class="sxs-lookup"><span data-stu-id="c045d-158">Next steps</span></span>

<span data-ttu-id="c045d-159">Сведения и ссылки для настройки этих параметров в рабочей среде можно найти в статье [Настройка повышенной безопасности для Microsoft 365](infoprotect-configure-increased-security-office-365.md) на этапе **защиты информации** .</span><span class="sxs-lookup"><span data-stu-id="c045d-159">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="c045d-160">Узнайте о дополнительных возможностях и возможностях [защиты информации](m365-enterprise-test-lab-guides.md#information-protection) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="c045d-160">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c045d-161">См. также</span><span class="sxs-lookup"><span data-stu-id="c045d-161">See also</span></span>

[<span data-ttu-id="c045d-162">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="c045d-162">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c045d-163">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="c045d-163">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="c045d-164">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="c045d-164">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
