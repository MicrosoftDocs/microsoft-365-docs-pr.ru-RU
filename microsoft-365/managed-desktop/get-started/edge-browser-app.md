---
title: Новая версия Microsoft Edge
description: Объясняется, как развертывается и обновляется новый браузер Edge
keywords: браузер, компьютер под управлением Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 42ff665e8ba9c369e29eeeafd27affff04b40966
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841343"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="e134b-104">Новое приложение Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e134b-104">New Microsoft Edge app</span></span>

<span data-ttu-id="e134b-105">Новый браузер [Microsoft Edge](https://www.microsoft.com/edge) обеспечивает производительность мирового класса благодаря большей конфиденциальности, повышению производительности и большему значению во время просмотра.</span><span class="sxs-lookup"><span data-stu-id="e134b-105">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="e134b-106">Компьютеры, управляемые Майкрософт, предлагают общедоступный предварительный просмотр развертывания нового браузера Edge в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="e134b-106">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="e134b-107">Начальное развертывание</span><span class="sxs-lookup"><span data-stu-id="e134b-107">Initial deployment</span></span>

<span data-ttu-id="e134b-108">Чтобы перенести настольные устройства, управляемые Майкрософт, в новый браузер Microsoft Edge, подайте заявку в службу поддержки ИТ-службы на портале microsoft Managed Desktop Portal.</span><span class="sxs-lookup"><span data-stu-id="e134b-108">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="e134b-109">Мы развернем канал Edge Stable в тестовой группе при подаче заявки, а затем развернем его в каждой последующей группе развертывания каждые 24 часа.</span><span class="sxs-lookup"><span data-stu-id="e134b-109">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="e134b-110">Чтобы приостановить развертывание, подайте еще один запрос на удержание operations.</span><span class="sxs-lookup"><span data-stu-id="e134b-110">To pause the deployment, file another ticket asking Operations to hold.</span></span>

<span data-ttu-id="e134b-111">Канал [Beta также](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) доступен по запросу на представительную проверку в организации.</span><span class="sxs-lookup"><span data-stu-id="e134b-111">The [Beta Channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) is also available upon request for representative validation within your organization.</span></span> <span data-ttu-id="e134b-112">Компьютеры, управляемые Майкрософт, будут развертывать приложение по мере необходимости в группах "Тестирование" и "Первые группы", чтобы у всех этих пользователей был не только канал Stable, но и канал Beta.</span><span class="sxs-lookup"><span data-stu-id="e134b-112">Microsoft Managed Desktop will deploy the application as required to the Test and First Groups so that all of those users have the Beta Channel in addition to the Stable Channel.</span></span> <span data-ttu-id="e134b-113">Для всех других пользователей, которым нужен доступ к каналу Beta, добавьте их в группу "Современные рабочие места **—** пользователи бета-версии edge" и установите ее на портале компании</span><span class="sxs-lookup"><span data-stu-id="e134b-113">For any other users who need access to the Beta Channel, add them to the **Modern Workplace - Edge Beta Users** group and have them install it from the Company Portal</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="e134b-114">Обновления Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e134b-114">Updates to Microsoft Edge</span></span>

<span data-ttu-id="e134b-115">Компьютеры, управляемые Майкрософт, развертывают канал [Stable](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) в Microsoft Edge, который обновляется автоматически каждые шесть недель.</span><span class="sxs-lookup"><span data-stu-id="e134b-115">Microsoft Managed Desktop deploys the [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge, which is auto-updated about every six weeks.</span></span> <span data-ttu-id="e134b-116">Обновления в канале Stable последовательно [](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) обновляются группой продуктов Microsoft Edge, чтобы обеспечить наилучшее качество работы клиентов.</span><span class="sxs-lookup"><span data-stu-id="e134b-116">Updates on the Stable channel are rolled out [progressively](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> 

<span data-ttu-id="e134b-117">Канал [Beta развертывается](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) на устройствах в группах Test и First для представительной проверки в организации.</span><span class="sxs-lookup"><span data-stu-id="e134b-117">The [Beta Channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) is deployed to devices in both the Test and First groups for representative validation within the organization.</span></span> <span data-ttu-id="e134b-118">Этот канал полностью поддерживается и автоматически обновляется с помощью новых функций приблизительно каждые шесть недель.</span><span class="sxs-lookup"><span data-stu-id="e134b-118">This channel is fully supported and is auto-updated with new features approximately every six weeks.</span></span>

<span data-ttu-id="e134b-119">Чтобы убедиться, что Microsoft Edge обновляется правильно, не изменяйте политики [обновления](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="e134b-119">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>



## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="e134b-120">Параметры, управляемые компьютером, управляемым Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e134b-120">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="e134b-121">На компьютере, управляемом Майкрософт, создан набор политик по умолчанию для Microsoft Edge для защиты браузера.</span><span class="sxs-lookup"><span data-stu-id="e134b-121">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="e134b-122">Параметры браузера по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="e134b-122">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="e134b-123">Расширения Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e134b-123">Microsoft Edge extensions</span></span>

<span data-ttu-id="e134b-124">Базовые параметры безопасности Microsoft Edge на настольных устройствах, управляемых Майкрософт, устанавливают две политики для отключения всех расширений Chrome и защиты пользователей.</span><span class="sxs-lookup"><span data-stu-id="e134b-124">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure users.</span></span> <span data-ttu-id="e134b-125">Чтобы включить и развернуть расширения в своей среде, см. "Параметры", которые вы управляете.</span><span class="sxs-lookup"><span data-stu-id="e134b-125">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="e134b-126">Список блок-блоков установки расширения</span><span class="sxs-lookup"><span data-stu-id="e134b-126">Extension installation blocklist</span></span>
<span data-ttu-id="e134b-127">**Значение по умолчанию:** Все</span><span class="sxs-lookup"><span data-stu-id="e134b-127">**Default value:** All</span></span>

<span data-ttu-id="e134b-128">Компьютеры, управляемые Майкрософт, устанавливают эту политику, чтобы запретить установку расширений Chrome на управляемых конечных точках.</span><span class="sxs-lookup"><span data-stu-id="e134b-128">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="e134b-129">С моделью расширения Chromium связаны известные риски, включая защиту от потери данных, конфиденциальность и другие риски, которые могут нарушить безопасность устройств.</span><span class="sxs-lookup"><span data-stu-id="e134b-129">There are known risks associated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="e134b-130">Разрешить точки обмена сообщениями на уровне пользователя (установленные без разрешений администратора)</span><span class="sxs-lookup"><span data-stu-id="e134b-130">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="e134b-131">**Значение по умолчанию:** Отключено</span><span class="sxs-lookup"><span data-stu-id="e134b-131">**Default value:** Disabled</span></span>

<span data-ttu-id="e134b-132">Отключив эту политику, Microsoft Edge будет использовать только ведущие приложения обмена сообщениями, установленные на уровне системы.</span><span class="sxs-lookup"><span data-stu-id="e134b-132">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="e134b-133">Ведущие приложения для обмена сообщениями — это часть расширений Chrome, которые позволяют браузеру взаимодействовать с другими частями конечной точки пользователя, создавая различные вопросы безопасности.</span><span class="sxs-lookup"><span data-stu-id="e134b-133">Native messaging hosts are a part of Chrome extensions, which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-tlsssl"></a><span data-ttu-id="e134b-134">Secure Sockets Layer (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="e134b-134">Secure Sockets Layer (TLS/SSL)</span></span>

#### <a name="minimum-tls-version"></a><span data-ttu-id="e134b-135">Минимальная версия TLS</span><span class="sxs-lookup"><span data-stu-id="e134b-135">Minimum TLS version</span></span>

<span data-ttu-id="e134b-136">**Значение по умолчанию:** Минимальная поддерживаемая TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="e134b-136">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="e134b-137">Если вы хотите использовать менее безопасный TLS 1.1, вы можете подать запрос на это.</span><span class="sxs-lookup"><span data-stu-id="e134b-137">If you want to use the less secure TLS 1.1, you can file a request to do so.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="e134b-138">Позволяет пользователям перейти со страницы предупреждения SSL</span><span class="sxs-lookup"><span data-stu-id="e134b-138">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="e134b-139">**Значение по умолчанию:** Отключено</span><span class="sxs-lookup"><span data-stu-id="e134b-139">**Default value:** Disabled</span></span>

<span data-ttu-id="e134b-140">Не рекомендуется использовать этот параметр, так как он позволяет пользователям посещать сайты с ошибками TSL.</span><span class="sxs-lookup"><span data-stu-id="e134b-140">We don't recommend enabling this setting since it allows users to visit sites with TSL errors.</span></span>

### <a name="microsoft-defender-smartscreen"></a><span data-ttu-id="e134b-141">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="e134b-141">Microsoft Defender SmartScreen</span></span>

#### <a name="configure-windows-defender-smartscreen"></a><span data-ttu-id="e134b-142">Настройка Защитник Windows SmartScreen</span><span class="sxs-lookup"><span data-stu-id="e134b-142">Configure Windows Defender SmartScreen</span></span>

<span data-ttu-id="e134b-143">**Значение по умолчанию:** Включено</span><span class="sxs-lookup"><span data-stu-id="e134b-143">**Default value:** Enabled</span></span>

<span data-ttu-id="e134b-144">Включено по умолчанию для защиты пользователей.</span><span class="sxs-lookup"><span data-stu-id="e134b-144">Enabled by default to help protect users.</span></span>

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="e134b-145">Защитник Windows smartScreen для сайтов</span><span class="sxs-lookup"><span data-stu-id="e134b-145">Windows Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="e134b-146">**Значение по умолчанию:** Включено</span><span class="sxs-lookup"><span data-stu-id="e134b-146">**Default value:** Enabled</span></span>

<span data-ttu-id="e134b-147">Мы не рекомендуем отключать этот параметр, так как это позволит пользователям игнорировать предупреждения и продолжать работу с потенциально вредоносными сайтами.</span><span class="sxs-lookup"><span data-stu-id="e134b-147">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="e134b-148">Предотвращение обхода Защитник Windows smartScreen о загрузках</span><span class="sxs-lookup"><span data-stu-id="e134b-148">Prevent bypassing of Windows Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="e134b-149">**Значение по умолчанию:** Включено</span><span class="sxs-lookup"><span data-stu-id="e134b-149">**Default value:** Enabled</span></span>

<span data-ttu-id="e134b-150">Не рекомендуется отключать этот параметр, так как это позволит пользователям игнорировать предупреждения и завершать непроверенные загрузки.</span><span class="sxs-lookup"><span data-stu-id="e134b-150">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="e134b-151">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="e134b-151">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="e134b-152">Настройка Adobe Flash по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e134b-152">Default Adobe Flash setting</span></span>

<span data-ttu-id="e134b-153">**Значение по умолчанию:** Отключено</span><span class="sxs-lookup"><span data-stu-id="e134b-153">**Default value:** Disabled</span></span>

<span data-ttu-id="e134b-154">Не рекомендуется использовать Flash из-за связанных с ним рисков безопасности.</span><span class="sxs-lookup"><span data-stu-id="e134b-154">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="e134b-155">Если у вас по-прежнему есть процессы, которые зависят от Flash, установите политику **[PluginsAllowedForUrls,](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** чтобы включить Flash для сайтов, которые в ней нуждаются.</span><span class="sxs-lookup"><span data-stu-id="e134b-155">If you still have processes that depend on Flash, set the **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites that need it.</span></span> <span data-ttu-id="e134b-156">Если вы не можете сохранить список разрешенных сайтов для использования Flash, подайте запрос на изменение значения на "Нажми и играй", что позволяет пользователям выбирать, когда следует запускать Flash.</span><span class="sxs-lookup"><span data-stu-id="e134b-156">If you can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="e134b-157">Диспетчер паролей</span><span class="sxs-lookup"><span data-stu-id="e134b-157">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="e134b-158">Включить сохранение паролей в диспетчере паролей</span><span class="sxs-lookup"><span data-stu-id="e134b-158">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="e134b-159">**Значение по умолчанию:** Отключено</span><span class="sxs-lookup"><span data-stu-id="e134b-159">**Default value:** Disabled</span></span>

<span data-ttu-id="e134b-160">Не рекомендуется разрешать пользователям сохранять пароли на своем устройстве.</span><span class="sxs-lookup"><span data-stu-id="e134b-160">We do not recommend allowing users to save passwords on their device.</span></span>

### <a name="internet-explorer-mode-in-microsoft-edge"></a><span data-ttu-id="e134b-161">Режим Internet Explorer в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e134b-161">Internet Explorer Mode in Microsoft Edge</span></span>
<span data-ttu-id="e134b-162">Режим IE в Microsoft Edge позволяет с легкостью использовать все нужные организации сайты в одном браузере.</span><span class="sxs-lookup"><span data-stu-id="e134b-162">IE mode on Microsoft Edge makes it easy to use all of the sites your organization needs in a single browser.</span></span> <span data-ttu-id="e134b-163">Он использует интегрированный механизм Chromium для сайтов, совместимых с механизмом отрисовки Chromium, и механизм Trident MSHTML из Internet Explorer 11 (IE11) для сайтов, которые не имеют зависимостей от функциональности IE.</span><span class="sxs-lookup"><span data-stu-id="e134b-163">It uses the integrated Chromium engine for sites that are compatible with the Chromium rendering engine and it uses the Trident MSHTML engine from Internet Explorer 11 (IE11) for sites that aren't or have dependencies on IE functionality.</span></span> <span data-ttu-id="e134b-164">[Подробнее] (https://docs.microsoft.com/DeployEdge/edge-ie-mode)</span><span class="sxs-lookup"><span data-stu-id="e134b-164">[Learn more] (https://docs.microsoft.com/DeployEdge/edge-ie-mode)</span></span> 

<span data-ttu-id="e134b-165">Компьютер под управлением Майкрософт включает режим Internet Explorer для устройств по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e134b-165">Microsoft Managed Desktop enables Internet Explorer mode for your devices by default</span></span> 

#### <a name="internet-explorer-mode-integration"></a><span data-ttu-id="e134b-166">Интеграция режима Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="e134b-166">Internet Explorer mode integration</span></span>
<span data-ttu-id="e134b-167">**Значение по умолчанию:** Режим Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="e134b-167">**Default Value:** Internet Explorer mode</span></span>

<span data-ttu-id="e134b-168">По умолчанию устройства настроены на использование режима Internet Explorer, но вместо этого их можно настроить на открытие сайтов в автономных окнах Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="e134b-168">By default, devices are set to use Internet Explorer mode, but you can set them to open sites in a standalone Internet Explorer 11 window instead.</span></span> <span data-ttu-id="e134b-169">Чтобы изменить это поведение, подав запрос в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="e134b-169">To change this behavior, file a support request.</span></span>

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a><span data-ttu-id="e134b-170">Добавление сайтов в список сайтов в режиме предприятия</span><span class="sxs-lookup"><span data-stu-id="e134b-170">Add sites to the Enterprise Mode Site list</span></span>
<span data-ttu-id="e134b-171">Чтобы сайты открывали в режиме Internet Explorer, их необходимо включить в список [корпоративных сайтов.](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist)</span><span class="sxs-lookup"><span data-stu-id="e134b-171">For sites to open in Internet Explorer mode you must include them on the [Enterprise Site list](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist).</span></span> <span data-ttu-id="e134b-172">За обслуживание и развертывание списка корпоративных сайтов отвечаете вы.</span><span class="sxs-lookup"><span data-stu-id="e134b-172">Maintaining and deploying the Enterprise Site list is your responsibility.</span></span> <span data-ttu-id="e134b-173">Подробные сведения [см. в настройках с помощью](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy) политики "Настройка списка сайтов в режиме предприятия"</span><span class="sxs-lookup"><span data-stu-id="e134b-173">For details, see [Configure using the Configure Enterprise Mode Site List policy](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span></span>

### <a name="other-settings"></a><span data-ttu-id="e134b-174">Другие параметры</span><span class="sxs-lookup"><span data-stu-id="e134b-174">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="e134b-175">Включить изоляцию сайта для каждого сайта</span><span class="sxs-lookup"><span data-stu-id="e134b-175">Enable site isolation for every site</span></span>

<span data-ttu-id="e134b-176">**Значение по умолчанию:** Включено</span><span class="sxs-lookup"><span data-stu-id="e134b-176">**Default value:** Enabled</span></span>

<span data-ttu-id="e134b-177">Если эта политика включена, пользователи не могут отказаться от поведения по умолчанию, в котором каждый сайт выполняется в своем собственном процессе.</span><span class="sxs-lookup"><span data-stu-id="e134b-177">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="e134b-178">Поддерживаемые схемы проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="e134b-178">Supported authentication schemes</span></span>

<span data-ttu-id="e134b-179">**Значение по умолчанию:** NTLM, согласование</span><span class="sxs-lookup"><span data-stu-id="e134b-179">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="e134b-180">Компьютеры, управляемые Майкрософт, не поддерживают схемы базовой или дайджест-проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e134b-180">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="e134b-181">Автоматически импортировать данные и параметры другого браузера при первом запуске</span><span class="sxs-lookup"><span data-stu-id="e134b-181">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="e134b-182">**Значение по умолчанию:** Автоматически импортировать все поддерживаемые типы данных и параметры из браузера по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e134b-182">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="e134b-183">При применении этой политики интерфейс первого запуска пропускает раздел импорта, минимизируя взаимодействие с пользователем.</span><span class="sxs-lookup"><span data-stu-id="e134b-183">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="e134b-184">Данные браузера из более старых версий Microsoft Edge всегда будут автоматически перенесены при первом запуске независимо от этого параметра.</span><span class="sxs-lookup"><span data-stu-id="e134b-184">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="e134b-185">Параметры, которые вы управляете</span><span class="sxs-lookup"><span data-stu-id="e134b-185">Settings you manage</span></span>

<span data-ttu-id="e134b-186">Вы можете развернуть любые параметры Microsoft Edge, не описанные ранее, с помощью профиля административных шаблонов в Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="e134b-186">You can deploy any Microsoft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="e134b-187">Подробные сведения см. в настройке параметров политики [Microsoft Edge с помощью Microsoft Intune.](https://docs.microsoft.com/deployedge/configure-edge-with-intune)</span><span class="sxs-lookup"><span data-stu-id="e134b-187">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="e134b-188">Если вы хотите оценить политику, которая в настоящее время не включена в административные шаблоны Microsoft Edge в Intune, можно использовать пользовательские параметры для устройств с Windows 10 в Intune.</span><span class="sxs-lookup"><span data-stu-id="e134b-188">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune, you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="e134b-189">Включение определенных расширений Chrome</span><span class="sxs-lookup"><span data-stu-id="e134b-189">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="e134b-190">Административный шаблон предлагает параметр для развертывания определенных расширений Chrome с помощью Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="e134b-190">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="e134b-191">Его можно найти в конфигурации **компьютера > Microsoft Edge > extensions > Allow Specific Extensions to be installed.**</span><span class="sxs-lookup"><span data-stu-id="e134b-191">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="e134b-192">Установка расширений в тихом режиме</span><span class="sxs-lookup"><span data-stu-id="e134b-192">Install extensions silently</span></span>

<span data-ttu-id="e134b-193">Вы также можете использовать административный шаблон, чтобы настроить Microsoft Edge на установку расширений, не оповещая пользователя.</span><span class="sxs-lookup"><span data-stu-id="e134b-193">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="e134b-194">Его можно найти в конфигурации **компьютера > Microsoft Edge > Extensions > Control,** какие расширения устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="e134b-194">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="microsoft-edge-update-policies"></a><span data-ttu-id="e134b-195">Политики обновления Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e134b-195">Microsoft Edge update policies</span></span>
<span data-ttu-id="e134b-196">Чтобы убедиться, что Microsoft Edge обновляется правильно, не изменяйте политики [обновления](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="e134b-196">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="e134b-197">Другие распространенные корпоративные политики</span><span class="sxs-lookup"><span data-stu-id="e134b-197">Other common enterprise policies</span></span>

<span data-ttu-id="e134b-198">Microsoft Edge предлагает множество других политик.</span><span class="sxs-lookup"><span data-stu-id="e134b-198">Microsoft Edge offers a great many other policies.</span></span> <span data-ttu-id="e134b-199">Вот некоторые из наиболее распространенных:</span><span class="sxs-lookup"><span data-stu-id="e134b-199">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="e134b-200">Настройка сайтов в списке корпоративных сайтов и режиме IE</span><span class="sxs-lookup"><span data-stu-id="e134b-200">Configure Sites on the Enterprise Site List and IE Mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="e134b-201">Настройка параметров страницы запуска, домашней страницы и новой вкладки</span><span class="sxs-lookup"><span data-stu-id="e134b-201">Configure start-up, home page, and new tab page settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="e134b-202">Настройка параметра игры "Просмотр"</span><span class="sxs-lookup"><span data-stu-id="e134b-202">Configure Surf game setting</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="e134b-203">Настройка параметров прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="e134b-203">Configure proxy server settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

