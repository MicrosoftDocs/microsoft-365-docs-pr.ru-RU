---
title: Повышенная безопасность Microsoft 365 для тестовой среды Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Используйте это руководство по лаборатории тестирования для включения дополнительных параметров безопасности Microsoft 365 для тестовой среды Microsoft 365 Enterprise.
ms.openlocfilehash: 54e05122dcbe5d4e24f092536897f2a8ad449e05
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283659"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f905c-103">Повышенная безопасность Microsoft 365 для тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="f905c-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f905c-104">С помощью инструкций, описанных в этой статье, вы настраиваете дополнительные параметры Microsoft 365 для повышения безопасности в тестовой среде Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f905c-104">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="f905c-106">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="f905c-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f905c-107">Этап 1: создание тестовой среды Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f905c-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f905c-108">Если вы просто хотите настроить усиленную безопасность Microsoft 365 в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="f905c-108">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="f905c-109">Если вы хотите настроить усиленную безопасность Microsoft 365 на имитации предприятия, следуйте инструкциям в сквозной [проверке](pass-through-auth-m365-ent-test-environment.md)подлинности.</span><span class="sxs-lookup"><span data-stu-id="f905c-109">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f905c-110">При тестировании повышенной безопасности Microsoft 365 не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="f905c-110">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="f905c-111">Он предоставляется в качестве параметра, чтобы можно было протестировать автоматизированное членство и членство в группах и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="f905c-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="f905c-112">Этап 2: Настройка усиленной безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f905c-112">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="f905c-113">На этом этапе вы включите повышенную безопасность Microsoft 365 для тестовой среды Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f905c-113">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="f905c-114">Дополнительные сведения и параметры можно найти [в статье Настройка клиента Office 365 для повышения безопасности](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="f905c-114">For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="f905c-115">Настройка SharePoint Online для блокирования приложений, не поддерживающих современные проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f905c-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="f905c-116">Приложения, не поддерживающие современные проверки подлинности, не могут иметь примененные к ним [конфигурации удостоверений и доступа](microsoft-365-policies-configurations.md) к устройствам, которые являются важным элементом защиты подписки Microsoft 365 и ее цифровых активов.</span><span class="sxs-lookup"><span data-stu-id="f905c-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="f905c-117">Перейдите на портал Office ([https://office.com](https://office.com)) и войдите в пробную подписку на Office 365 с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="f905c-117">Go to the Office portal ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="f905c-118">Если вы используете упрощенную тестовую среду Microsoft 365, войдите с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="f905c-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="f905c-119">Если вы используете имитируемую тестовую среду Microsoft 365, используйте [портал Azure](https://portal.azure.com) , чтобы подключиться к ВИРТУАЛЬНОЙ машине CLIENT1, а затем выполните вход с компьютера CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="f905c-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="f905c-120">На вкладке **центра администрирования Microsoft 365** щелкните элемент **Администратор**.</span><span class="sxs-lookup"><span data-stu-id="f905c-120">From the **Microsoft 365 admin center** tab, click **Admin**.</span></span>
3. <span data-ttu-id="f905c-121">На новой вкладке **центра администрирования Microsoft 365** выберите пункт **центры администрирования _гт_ SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f905c-121">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
4. <span data-ttu-id="f905c-122">На вкладке Новая **центр администрирования SharePoint** выберите **Управление доступом**.</span><span class="sxs-lookup"><span data-stu-id="f905c-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
5. <span data-ttu-id="f905c-123">В разделе **приложения, для которых не поддерживается современная проверка**подлинности, выберите пункт **блокировать**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f905c-123">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="f905c-124">Включение расширенной защиты от угроз для SharePoint, OneDrive для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f905c-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="f905c-125">Office 365 Advanced Threat protection (ATP) для SharePoint, OneDrive и Microsoft Teams защищает организацию от случайного предоставления вредоносных файлов.</span><span class="sxs-lookup"><span data-stu-id="f905c-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="f905c-126">Перейдите в [Центр безопасности Office 365 Security _амп_](https://protection.office.com) и войдите с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="f905c-126">Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="f905c-127">В левой области навигации в разделе **Управление угрозами**выберите пункт **Политика _гт_ безопасные вложения**.</span><span class="sxs-lookup"><span data-stu-id="f905c-127">In the left navigation pane, under **Threat management**, choose **Policy > Safe Attachments**.</span></span> 

3. <span data-ttu-id="f905c-128">Выберите **включить ATP для SharePoint, OneDrive и Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="f905c-128">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="f905c-129">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f905c-129">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="f905c-130">Включение защиты от вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="f905c-130">Enable anti-malware</span></span>

<span data-ttu-id="f905c-131">Вредоносные программы состоят из вирусов и программ-шпионов.</span><span class="sxs-lookup"><span data-stu-id="f905c-131">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="f905c-132">Вирусы заражают другие программы и данные, а также распространяются по компьютеру в поисках программ, которые можно заразить.</span><span class="sxs-lookup"><span data-stu-id="f905c-132">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="f905c-133">Программы-шпионы относятся к вредоносным программам, которые собирают личные сведения пользователей, например данные для входа и персональные данные, и отправляют их обратно создателю этих программ.</span><span class="sxs-lookup"><span data-stu-id="f905c-133">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="f905c-134">В Office 365 имеются встроенные возможности фильтрации вредоносных программ и нежелательной почты, которые помогают защитить входящие и исходящие сообщения от вредоносных программ и защищать вас от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="f905c-134">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="f905c-135">Дополнительные сведения содержатся в статье [Защита от нежелательной почты _Амп_ для защиты от вредоносных программ в Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="f905c-135">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="f905c-136">Чтобы обеспечить выполнение защиты от вредоносных программ для файлов с распространенными типами файлов вложений:</span><span class="sxs-lookup"><span data-stu-id="f905c-136">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="f905c-137">Нажмите кнопку "назад" в браузере, чтобы вернуться на страницу " **Политика** ".</span><span class="sxs-lookup"><span data-stu-id="f905c-137">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="f905c-138">Нажмите кнопку **Защита от вредоносных программ**.</span><span class="sxs-lookup"><span data-stu-id="f905c-138">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="f905c-139">Дважды щелкните политику с именем **Default**.</span><span class="sxs-lookup"><span data-stu-id="f905c-139">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="f905c-140">В окне **Политика защиты от вредоносных программ** нажмите кнопку **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="f905c-140">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="f905c-141">В разделе **общий фильтр типов вложений**нажмите кнопку **_Гт_ Save (сохранить**).</span><span class="sxs-lookup"><span data-stu-id="f905c-141">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a><span data-ttu-id="f905c-142">Этап 3: изучение журналов и средств безопасности Office 365</span><span class="sxs-lookup"><span data-stu-id="f905c-142">Phase 3: Examine Office 365 security tools and logs</span></span>

<span data-ttu-id="f905c-143">На этом этапе вы проучите встроенные службы, которые сообщают о событиях безопасности и измеряют общий уровень безопасности.</span><span class="sxs-lookup"><span data-stu-id="f905c-143">In this phase, you look at built-in services that inform you about security events and measure your overall security posture.</span></span>

### <a name="threat-management-dashboard"></a><span data-ttu-id="f905c-144">Панель мониторинга управления угрозами</span><span class="sxs-lookup"><span data-stu-id="f905c-144">Threat management dashboard</span></span>

<span data-ttu-id="f905c-145">Управление угрозами Office 365 помогает управлять доступом мобильных устройств к данным вашей организации, защитить организацию от потери данных и защищать входящие и исходящие сообщения от вредоносных программ и спама.</span><span class="sxs-lookup"><span data-stu-id="f905c-145">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="f905c-146">Кроме того, управление угрозами используется для защиты репутации домена и определения того, являются ли отправители неумышленно подложными учетными записями из вашего домена.</span><span class="sxs-lookup"><span data-stu-id="f905c-146">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> <span data-ttu-id="f905c-147">Дополнительные сведения см в разделе [Управление угрозами в центре безопасности Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span><span class="sxs-lookup"><span data-stu-id="f905c-147">For more information, see [Threat management in the Microsoft 365 security center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>


### <a name="office-365-cloud-app-security-dashboard"></a><span data-ttu-id="f905c-148">Панель мониторинга Cloud App Security для Office 365</span><span class="sxs-lookup"><span data-stu-id="f905c-148">Office 365 Cloud App Security dashboard</span></span>

<span data-ttu-id="f905c-149">Office 365 Cloud App Security (предыдущее название — расширенное управление безопасностью Office 365) позволяет создавать политики, которые отслеживают подозрительные действия в вашей подписке на Office 365 и сообщают вам о них, чтобы вы могли исследовать и исправить проблему.</span><span class="sxs-lookup"><span data-stu-id="f905c-149">Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action.</span></span> <span data-ttu-id="f905c-150">Дополнительные сведения можно найти в статье [Обзор Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span><span class="sxs-lookup"><span data-stu-id="f905c-150">For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span></span>

<!--
### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a><span data-ttu-id="f905c-151">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="f905c-151">Next steps</span></span>

<span data-ttu-id="f905c-152">Сведения и ссылки для настройки этих параметров в рабочей среде можно найти в статье [Настройка повышенной безопасности для Microsoft 365](infoprotect-configure-increased-security-office-365.md) на этапе **защиты информации** .</span><span class="sxs-lookup"><span data-stu-id="f905c-152">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="f905c-153">Узнайте о дополнительных возможностях и возможностях [защиты информации](m365-enterprise-test-lab-guides.md#information-protection) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="f905c-153">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f905c-154">См. также</span><span class="sxs-lookup"><span data-stu-id="f905c-154">See also</span></span>

[<span data-ttu-id="f905c-155">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="f905c-155">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f905c-156">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="f905c-156">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f905c-157">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="f905c-157">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

