---
title: Усиленная защита Office 365 для вашей тестовой среды Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Используйте в этом документе Test Lab Guide, чтобы включить дополнительные параметры безопасности Office 365 тестовой среды Microsoft 365 для предприятия.
ms.openlocfilehash: 62cf2347d3e003e9368c987912e7748029241501
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870706"
---
# <a name="increased-office-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a5b92-103">Усиленная защита Office 365 для вашей тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="a5b92-103">Increased Office 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a5b92-104">С помощью инструкции в этом разделе Настройка дополнительных параметров Office 365 для повышения безопасности в тестовой среде Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="a5b92-104">With the instructions in this article, you configure additional Office 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="a5b92-106">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="a5b92-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a5b92-107">Этап 1: Создание масштабирование тестовой среды Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="a5b92-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a5b92-108">Если необходимо настроить повышения уровня безопасности Office 365 в облегченный путь с минимальным требованиям, следуйте инструкциям в [упрощенной базовой конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="a5b92-108">If you just want to configure increased Office 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a5b92-109">Если вы хотите настроить повышения уровня безопасности Office 365 имитации enterprise, следуйте инструкциям в [сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a5b92-109">If you want to configure increased Office 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5b92-p101">Тестирование повышения уровня безопасности Office 365 не требует тестовой среды имитации предприятия, включающая имитации интрасети, подключенных к Интернету и синхронизации каталогов для леса Windows Server AD. Предоставляется здесь как вариант, чтобы проверка автоматической лицензирования и членство в группах и экспериментировать с его в среде, которая представляет типичное организации.</span><span class="sxs-lookup"><span data-stu-id="a5b92-p101">Testing increased Office 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-office-365-security"></a><span data-ttu-id="a5b92-112">Этап 2: Настройка повышения уровня безопасности Office 365</span><span class="sxs-lookup"><span data-stu-id="a5b92-112">Phase 2: Configure increased Office 365 security</span></span>

<span data-ttu-id="a5b92-p102">На этом этапе можно включить повышения уровня безопасности Office 365 для тестовой среды Microsoft 365 для предприятия. Дополнительные сведения и параметры содержатся в разделе [Настройка клиента Office 365 для повышения уровня безопасности](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="a5b92-p102">In this phase, you enable increased Office 365 security for your Microsoft 365 Enterprise test environment. For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="a5b92-115">Настройка SharePoint Online, чтобы блокировать приложения, которые не поддерживают современных проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="a5b92-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="a5b92-116">Приложения, которые не поддерживают современных проверки подлинности не могут иметь [удостоверения и устройства для доступа к конфигурации](microsoft-365-policies-configurations.md) , примененных к ним, которая является важным элементом защиты Microsoft 365 подписки и его цифровых активов.</span><span class="sxs-lookup"><span data-stu-id="a5b92-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="a5b92-117">Последовательно выберите пункты портала Office ([https://office.com](https://office.com)) и войти в систему с учетной записью глобального администратора пробной подписки Office 365.</span><span class="sxs-lookup"><span data-stu-id="a5b92-117">Go to the Office portal ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="a5b92-118">При использовании lightweight тестовой среды Microsoft 365 вход с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="a5b92-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="a5b92-119">При использовании тестовой среды имитации enterprise Microsoft 365 [Azure портала](https://portal.azure.com) используйте для подключения на виртуальную машину CLIENT1 и затем вход из CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="a5b92-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="a5b92-120">На вкладке **Microsoft 365 центра администрирования** щелкните **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-120">From the **Microsoft 365 admin center** tab, click **Admin**.</span></span>
3. <span data-ttu-id="a5b92-121">На вкладке Создать **Центр администрирования Microsoft 365** щелкните **центры администрирования > SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-121">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
4. <span data-ttu-id="a5b92-122">На вкладке Создать **Центр администрирования SharePoint** щелкните **Управление доступом**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
5. <span data-ttu-id="a5b92-123">В разделе **приложения, которые не поддерживают современных проверки подлинности**выберите пункт **заблокировать**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-123">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="a5b92-124">Включить расширенную защиту от угроз) для SharePoint, OneDrive для бизнеса и группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a5b92-124">Enable Advanced Threat Protection) for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="a5b92-p103">Office 365 расширенного угроз защиты анализа — это компонент из Exchange Online Protection (EOP), которая позволяет сохранить вредоносных программ из него электронной почты. С помощью анализа создания политики в центре администрирования Exchange (EAC) или безопасности & центре соответствия требованиям, помочь обеспечить пользователям доступ к только ссылки или вложения в сообщениях, которые считаются не вредоносных. Для получения дополнительных сведений см [расширенной защитой для вложений надежных и безопасных ссылок](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).</span><span class="sxs-lookup"><span data-stu-id="a5b92-p103">Office 365 Advanced Threat Protection (ATP) is a feature of Exchange Online Protection (EOP) that helps keep malware out of your email. With ATP, you create policies in the Exchange Admin center (EAC) or the Security & Compliance center that help ensure your users access only links or attachments in emails that are identified as not malicious. For more information, see [Advanced threat protection for safe attachments and safe links](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).</span></span>

1. <span data-ttu-id="a5b92-128">На вкладке **Центр администрирования Microsoft 365** браузера щелкните **центры администрирования > Безопасность и соответствие требованиям**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-128">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="a5b92-129">На новую вкладку **Безопасность и соответствие требованиям** , нажмите кнопку **угроз управления > политики**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-129">On the new **Security & Compliance** tab, click **Threat management > Policy**.</span></span>
3. <span data-ttu-id="a5b92-130">Нажмите кнопку **ATP безопасные вложения**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-130">Click **ATP safe attachments**.</span></span>
4. <span data-ttu-id="a5b92-131">На левой панели **безопасные вложения** выберите **Включить ATP для SharePoint, OneDrive и группами Майкрософт**и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-131">In the **Safe attachments** pane, select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**, and then click **Save**.</span></span>

### <a name="enable-anti-malware"></a><span data-ttu-id="a5b92-132">Включение защиты от вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="a5b92-132">Enable anti-malware</span></span>

<span data-ttu-id="a5b92-p104">Вредоносные программы включает в себя вирусов и шпионских программ. Вирусов заражение других программ и данных, и они распределены по всему ищете программы для заражения компьютера. Шпионских программ относится к вредоносных программ, которое собирает личные сведения, такие как данные для входа и персональных данных и отправляет его автор вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="a5b92-p104">Malware is comprised of viruses and spyware. Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect. Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="a5b92-p105">Office 365 имеет встроенные вредоносных программ фильтрации нежелательной почты и возможности, которые защиты входящих и исходящих сообщений от вредоносного программного обеспечения и защиты от нежелательной почты. Для получения дополнительных сведений см [защиты от нежелательной почты и вредоносных программ в Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="a5b92-p105">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam. For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="a5b92-138">Чтобы убедиться, что вредоносных программ выполняется на файлы, общие типы файлов вложений:</span><span class="sxs-lookup"><span data-stu-id="a5b92-138">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="a5b92-139">Нажмите кнопку возврата в вашем браузере, чтобы вернуться на страницу **политики** .</span><span class="sxs-lookup"><span data-stu-id="a5b92-139">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="a5b92-140">Нажмите кнопку **вредоносных программ**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-140">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="a5b92-141">Дважды щелкните политику с именем **по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-141">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="a5b92-142">В окне **Политика защиты от вредоносных программ** нажмите кнопку **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-142">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="a5b92-143">В разделе **Общие типы вложений фильтра**, нажмите кнопку **на > Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-143">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a><span data-ttu-id="a5b92-144">Этап 3: Просмотрите журналы и средств безопасности в Office 365</span><span class="sxs-lookup"><span data-stu-id="a5b92-144">Phase 3: Examine Office 365 security tools and logs</span></span>

<span data-ttu-id="a5b92-145">На этом этапе вы откроете встроенные службы, информирующее о событиях безопасности и оценки общего уровня безопасности.</span><span class="sxs-lookup"><span data-stu-id="a5b92-145">In this phase, you look at built-in services that inform you about security events and measure your overall security posture.</span></span>

### <a name="threat-management-dashboard"></a><span data-ttu-id="a5b92-146">Панель мониторинга Threat management</span><span class="sxs-lookup"><span data-stu-id="a5b92-146">Threat management dashboard</span></span>

<span data-ttu-id="a5b92-p106">Office 365 Threat management помогут вам управлять и управление доступом мобильных устройств к данным вашей организации, позволяет защитить организацию от потери данных и защиты входящих и исходящих сообщений от нежелательной почты и вредоносных программ. Вы также использовать угроз управления для защиты репутации для вашего домена и для определения ли отправителей намеренно подмену данных учетных записей из вашего домена. Для получения дополнительных сведений см [Threat management в Office 365 безопасности & центре соответствия требованиям](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span><span class="sxs-lookup"><span data-stu-id="a5b92-p106">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam. You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain. For more information, see [Threat management in the Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>

<span data-ttu-id="a5b92-150">Выполните следующие действия для просмотра панели мониторинга Office 365 Threat management.</span><span class="sxs-lookup"><span data-stu-id="a5b92-150">Use these steps to view the Office 365 Threat management dashboard:</span></span>

1. <span data-ttu-id="a5b92-151">На вкладке **Центр администрирования Microsoft 365** браузера щелкните **центры администрирования > Безопасность и соответствие требованиям**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-151">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="a5b92-152">На новую вкладку **Безопасность и соответствие требованиям** , нажмите кнопку **угроз управления > Панель мониторинга**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-152">On the new **Security & Compliance** tab, click **Threat management > Dashboard**.</span></span>
3. <span data-ttu-id="a5b92-153">На новой вкладке **панели мониторинга** в браузере Обратите внимание на то тенденций вредоносных программ, полезные сведения о и других разделах панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="a5b92-153">On the new **Dashboard** tab in your browser, note the malware trends, insights, and other sections of the dashboard.</span></span>

### <a name="office-365-cloud-app-security-dashboard"></a><span data-ttu-id="a5b92-154">Панель мониторинга безопасности облаке приложения Office 365</span><span class="sxs-lookup"><span data-stu-id="a5b92-154">Office 365 Cloud App Security dashboard</span></span>

<span data-ttu-id="a5b92-p107">Безопасности приложения Office 365 облаке, ранее — Office 365 расширенного управления безопасностью, позволяет создавать политики, которые наблюдения за и сообщить о подозрительных действий в вашей подписки Office 365, чтобы исследовать и занять возможных Действие по исправлению. Для получения дополнительных сведений см [Overview of Office 365 облачных безопасности приложения](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span><span class="sxs-lookup"><span data-stu-id="a5b92-p107">Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span></span>

1. <span data-ttu-id="a5b92-157">На вкладке **Центр администрирования Microsoft 365** браузера щелкните **центры администрирования > Безопасность и соответствие требованиям**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-157">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="a5b92-158">На новую вкладку **Безопасность и соответствие требованиям** , нажмите кнопку **оповещения > Управление расширенного оповещения > Перейти к безопасности Office 365 облаке приложения**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-158">On the new **Security & Compliance** tab, click **Alerts > Manage advanced alerts > Go to Office 365 Cloud App Security**.</span></span>
3. <span data-ttu-id="a5b92-159">На вкладке **Безопасность приложения облаке** новый Обратите внимание на то, представление панели мониторинга и список политики по умолчанию, которые наблюдения за различных действий в подписки Office 365.</span><span class="sxs-lookup"><span data-stu-id="a5b92-159">On the new **Cloud App Security** tab, note the dashboard view and the list of default policies that that monitor for various activities in your Office 365 subscription.</span></span>
4. <span data-ttu-id="a5b92-160">Щелкните значок панели мониторинга, чтобы просмотреть сводку безопасности приложения облачных действий, которые отслеживаются.</span><span class="sxs-lookup"><span data-stu-id="a5b92-160">Click the dashboard icon to see a summary of Cloud App Security activities that are being tracked.</span></span>
5. <span data-ttu-id="a5b92-161">Щелкните **Проверить** (значок очков), а затем **Журнал активности** , чтобы просмотреть список последних войти в систему и другие действия.</span><span class="sxs-lookup"><span data-stu-id="a5b92-161">Click **Investigate** (the eyeglasses icon) and then **Activity log** to see the list of recent sign-ins and other activities.</span></span>

### <a name="secure-score"></a><span data-ttu-id="a5b92-162">Secure счета</span><span class="sxs-lookup"><span data-stu-id="a5b92-162">Secure Score</span></span>

1. <span data-ttu-id="a5b92-163">Создать новую вкладку в браузере и перейти к **securescore.office.com**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-163">Create a new tab in your browser and go to **securescore.office.com**.</span></span>
2. <span data-ttu-id="a5b92-164">На **вкладке панели мониторинга**Обратите внимание на то, ваш текущий отчет безопасного и список действий в очереди для увеличения результатов.</span><span class="sxs-lookup"><span data-stu-id="a5b92-164">On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.</span></span>

<span data-ttu-id="a5b92-165">**Сведения о** защите сведения и ссылки для настройки этих параметров в рабочей среде см раздел этап [настроить повышение безопасности для Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) .</span><span class="sxs-lookup"><span data-stu-id="a5b92-165">See the [Configure increased security for Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="a5b92-166">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="a5b92-166">Next step</span></span>

<span data-ttu-id="a5b92-167">Изучите дополнительные [сведения о защите](m365-enterprise-test-lab-guides.md#information-protection) функций и возможностей в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="a5b92-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5b92-168">См. также</span><span class="sxs-lookup"><span data-stu-id="a5b92-168">See also</span></span>

[<span data-ttu-id="a5b92-169">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="a5b92-169">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a5b92-170">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="a5b92-170">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a5b92-171">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="a5b92-171">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

