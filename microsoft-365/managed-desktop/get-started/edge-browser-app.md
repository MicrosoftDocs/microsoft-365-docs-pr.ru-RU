---
title: Новая версия Microsoft Edge
description: Объясняет, как развертывается и обновляется новый браузер Edge
keywords: браузер, Microsoft Managed Desktop, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 033826a7f82278f6e36b422284a1076cba57d584
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921982"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="b7b0d-104">Новое приложение Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b7b0d-104">New Microsoft Edge app</span></span>

<span data-ttu-id="b7b0d-105">Новый браузер [Microsoft Edge обеспечивает](https://www.microsoft.com/edge) производительность мирового класса с большей конфиденциальностью, большей производительностью и большей ценностью во время просмотра.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-105">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="b7b0d-106">Microsoft Managed Desktop предлагает общедоступный предварительный просмотр развертывания нового браузера Edge в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-106">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="b7b0d-107">Начальное развертывание</span><span class="sxs-lookup"><span data-stu-id="b7b0d-107">Initial deployment</span></span>

<span data-ttu-id="b7b0d-108">Чтобы перенести устройства Microsoft Managed Desktop в новый браузер Microsoft Edge, необходимо подать билет на ИТ-поддержку с помощью портала управляемых настольных компьютеров Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-108">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="b7b0d-109">При подаче билета мы развернем канал Edge Stable в тестовой группе, а затем раз в 24 часа развертываем его в каждой последующей группе развертывания.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-109">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="b7b0d-110">Чтобы приостановить развертывание, задайте другой билет с просьбой о проведении операций.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-110">To pause the deployment, file another ticket asking Operations to hold.</span></span>

<span data-ttu-id="b7b0d-111">[Бета-канал](/deployedge/microsoft-edge-channels#beta-channel) также доступен по запросу на представительную проверку в организации.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-111">The [Beta Channel](/deployedge/microsoft-edge-channels#beta-channel) is also available upon request for representative validation within your organization.</span></span> <span data-ttu-id="b7b0d-112">Управляемый настольный компьютер Microsoft развертывает приложение по мере необходимости в группах Test и First, чтобы у всех этих пользователей был бета-канал в дополнение к стабильному каналу.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-112">Microsoft Managed Desktop will deploy the application as required to the Test and First Groups so that all of those users have the Beta Channel in addition to the Stable Channel.</span></span> <span data-ttu-id="b7b0d-113">Для всех остальных пользователей, которым необходим доступ к бета-каналу, добавьте их в группу **"Современные** рабочие места - edge beta Users" и установите ее на портале компании.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-113">For any other users who need access to the Beta Channel, add them to the **Modern Workplace - Edge Beta Users** group and have them install it from the Company Portal</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="b7b0d-114">Обновления до Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b7b0d-114">Updates to Microsoft Edge</span></span>

<span data-ttu-id="b7b0d-115">Microsoft Managed Desktop развертывает [стабильный канал](/deployedge/microsoft-edge-channels#stable-channel) Microsoft Edge, который обновляется автоматически каждые шесть недель.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-115">Microsoft Managed Desktop deploys the [Stable channel](/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge, which is auto-updated about every six weeks.</span></span> <span data-ttu-id="b7b0d-116">Обновления на канале Stable постепенно [](/deployedge/microsoft-edge-update-progressive-rollout) выкатываются группой продуктов Microsoft Edge для обеспечения наилучшего опыта для клиентов.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-116">Updates on the Stable channel are rolled out [progressively](/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> 

<span data-ttu-id="b7b0d-117">[Бета-канал](/deployedge/microsoft-edge-channels#beta-channel) развертывается на устройствах в группах Test и First для представительской проверки в организации.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-117">The [Beta Channel](/deployedge/microsoft-edge-channels#beta-channel) is deployed to devices in both the Test and First groups for representative validation within the organization.</span></span> <span data-ttu-id="b7b0d-118">Этот канал полностью поддерживается и обновляется автоматически с новыми функциями примерно каждые шесть недель.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-118">This channel is fully supported and is auto-updated with new features approximately every six weeks.</span></span>

<span data-ttu-id="b7b0d-119">Чтобы убедиться, что Microsoft Edge обновляется правильно, не измените политики обновления Microsoft [Edge.](/deployedge/microsoft-edge-update-policies)</span><span class="sxs-lookup"><span data-stu-id="b7b0d-119">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](/deployedge/microsoft-edge-update-policies).</span></span>



## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="b7b0d-120">Параметры, управляемые Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="b7b0d-120">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="b7b0d-121">Microsoft Managed Desktop создала по умолчанию набор политик для Microsoft Edge для обеспечения безопасности браузера.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-121">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="b7b0d-122">Параметры браузера по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="b7b0d-122">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="b7b0d-123">Расширения Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b7b0d-123">Microsoft Edge extensions</span></span>

<span data-ttu-id="b7b0d-124">Базовый уровень безопасности для Microsoft Edge на управляемых настольных устройствах Microsoft задает две политики, чтобы отключить все расширения Chrome и обеспечить безопасность пользователей.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-124">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure users.</span></span> <span data-ttu-id="b7b0d-125">Чтобы включить и развернуть расширения в вашей среде, см. в руб. Параметры, которые вы управляете.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-125">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="b7b0d-126">Блок-лист установки расширения</span><span class="sxs-lookup"><span data-stu-id="b7b0d-126">Extension installation blocklist</span></span>
<span data-ttu-id="b7b0d-127">**Значение по умолчанию:** Все</span><span class="sxs-lookup"><span data-stu-id="b7b0d-127">**Default value:** All</span></span>

<span data-ttu-id="b7b0d-128">Microsoft Managed Desktop задает эту политику, чтобы не допустить установки расширений Chrome на управляемые конечные точки.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-128">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="b7b0d-129">Известны риски, связанные с моделью расширения Chromium, включая защиту от потери данных, конфиденциальность и другие риски, которые могут привести к компрометации устройств.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-129">There are known risks associated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="b7b0d-130">Разрешить родных хостов обмена сообщениями на уровне пользователей (установленных без разрешений администратора)</span><span class="sxs-lookup"><span data-stu-id="b7b0d-130">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="b7b0d-131">**Значение по умолчанию:** Отключено</span><span class="sxs-lookup"><span data-stu-id="b7b0d-131">**Default value:** Disabled</span></span>

<span data-ttu-id="b7b0d-132">Отключив эту политику, Microsoft Edge будет использовать только родных хостов обмена сообщениями, установленных на уровне системы.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-132">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="b7b0d-133">Родной хост обмена сообщениями является частью расширений Chrome, которые позволяют браузеру взаимодействовать с другими частями конечной точки пользователя, создавая различные проблемы безопасности.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-133">Native messaging hosts are a part of Chrome extensions, which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-tlsssl"></a><span data-ttu-id="b7b0d-134">Безопасный слой розеток (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="b7b0d-134">Secure Sockets Layer (TLS/SSL)</span></span>

#### <a name="minimum-tls-version"></a><span data-ttu-id="b7b0d-135">Минимальная версия TLS</span><span class="sxs-lookup"><span data-stu-id="b7b0d-135">Minimum TLS version</span></span>

<span data-ttu-id="b7b0d-136">**Значение по умолчанию:** Минимальная поддержка TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="b7b0d-136">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="b7b0d-137">Если вы хотите использовать менее безопасный TLS 1.1, для этого можно подать запрос.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-137">If you want to use the less secure TLS 1.1, you can file a request to do so.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="b7b0d-138">Позволяет пользователям перейти со страницы предупреждения SSL</span><span class="sxs-lookup"><span data-stu-id="b7b0d-138">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="b7b0d-139">**Значение по умолчанию:** Отключено</span><span class="sxs-lookup"><span data-stu-id="b7b0d-139">**Default value:** Disabled</span></span>

<span data-ttu-id="b7b0d-140">Мы не рекомендуем включить этот параметр, так как он позволяет пользователям посещать сайты с ошибками TSL.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-140">We don't recommend enabling this setting since it allows users to visit sites with TSL errors.</span></span>

### <a name="microsoft-defender-smartscreen"></a><span data-ttu-id="b7b0d-141">SmartScreen защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b7b0d-141">Microsoft Defender SmartScreen</span></span>

#### <a name="configure-windows-defender-smartscreen"></a><span data-ttu-id="b7b0d-142">Настройка Защитник Windows SmartScreen</span><span class="sxs-lookup"><span data-stu-id="b7b0d-142">Configure Windows Defender SmartScreen</span></span>

<span data-ttu-id="b7b0d-143">**Значение по умолчанию:** Включено</span><span class="sxs-lookup"><span data-stu-id="b7b0d-143">**Default value:** Enabled</span></span>

<span data-ttu-id="b7b0d-144">Включено по умолчанию для защиты пользователей.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-144">Enabled by default to help protect users.</span></span>

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="b7b0d-145">Защитник Windows SmartScreen подсказок для сайтов</span><span class="sxs-lookup"><span data-stu-id="b7b0d-145">Windows Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="b7b0d-146">**Значение по умолчанию:** Включено</span><span class="sxs-lookup"><span data-stu-id="b7b0d-146">**Default value:** Enabled</span></span>

<span data-ttu-id="b7b0d-147">Мы не рекомендуем отключать этот параметр, так как это позволит пользователям игнорировать предупреждения и продолжать потенциально вредоносные сайты.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-147">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="b7b0d-148">Предотвращение обхода Защитник Windows smartScreen предупреждений о загрузках</span><span class="sxs-lookup"><span data-stu-id="b7b0d-148">Prevent bypassing of Windows Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="b7b0d-149">**Значение по умолчанию:** Включено</span><span class="sxs-lookup"><span data-stu-id="b7b0d-149">**Default value:** Enabled</span></span>

<span data-ttu-id="b7b0d-150">Мы не рекомендуем отключать этот параметр, так как это позволит пользователям игнорировать предупреждения и завершать непроверенные скачивания.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-150">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="b7b0d-151">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="b7b0d-151">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="b7b0d-152">Параметр Adobe Flash по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b7b0d-152">Default Adobe Flash setting</span></span>

<span data-ttu-id="b7b0d-153">**Значение по умолчанию:** Отключено</span><span class="sxs-lookup"><span data-stu-id="b7b0d-153">**Default value:** Disabled</span></span>

<span data-ttu-id="b7b0d-154">Мы не рекомендуем использовать Flash из-за связанных рисков безопасности.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-154">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="b7b0d-155">Если у вас еще есть процессы, зависят от Flash, установите политику **[PluginsAllowedForUrls,](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** чтобы включить Flash для сайтов, которые в ней нуждаются.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-155">If you still have processes that depend on Flash, set the **[PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites that need it.</span></span> <span data-ttu-id="b7b0d-156">Если вы не можете сохранить разрешенный список сайтов для использования Flash, пойдите на запрос изменения, чтобы изменить значение **Click to Play,** что позволяет пользователям выбирать, когда это уместно для запуска Flash.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-156">If you can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="b7b0d-157">Менеджер паролей</span><span class="sxs-lookup"><span data-stu-id="b7b0d-157">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="b7b0d-158">Включить сохранение паролей для диспетчера паролей</span><span class="sxs-lookup"><span data-stu-id="b7b0d-158">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="b7b0d-159">**Значение по умолчанию:** Отключено</span><span class="sxs-lookup"><span data-stu-id="b7b0d-159">**Default value:** Disabled</span></span>

<span data-ttu-id="b7b0d-160">Мы не рекомендуем разрешать пользователям сохранять пароли на своем устройстве.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-160">We do not recommend allowing users to save passwords on their device.</span></span>

### <a name="internet-explorer-mode-in-microsoft-edge"></a><span data-ttu-id="b7b0d-161">Режим Internet Explorer в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b7b0d-161">Internet Explorer Mode in Microsoft Edge</span></span>
<span data-ttu-id="b7b0d-162">Режим IE в Microsoft Edge позволяет с легкостью использовать все нужные организации сайты в одном браузере.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-162">IE mode on Microsoft Edge makes it easy to use all of the sites your organization needs in a single browser.</span></span> <span data-ttu-id="b7b0d-163">Он использует интегрированный двигатель Chromium для сайтов, совместимых с движком визуализации Chromium, и использует двигатель MSHTML Trident из Internet Explorer 11 (IE11) для сайтов, которые не имеют зависимостей от функций IE.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-163">It uses the integrated Chromium engine for sites that are compatible with the Chromium rendering engine and it uses the Trident MSHTML engine from Internet Explorer 11 (IE11) for sites that aren't or have dependencies on IE functionality.</span></span> <span data-ttu-id="b7b0d-164">[Подробнее] (https://docs.microsoft.com/DeployEdge/edge-ie-mode)</span><span class="sxs-lookup"><span data-stu-id="b7b0d-164">[Learn more] (https://docs.microsoft.com/DeployEdge/edge-ie-mode)</span></span> 

<span data-ttu-id="b7b0d-165">Microsoft Managed Desktop включает режим Internet Explorer для устройств по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b7b0d-165">Microsoft Managed Desktop enables Internet Explorer mode for your devices by default</span></span> 

#### <a name="internet-explorer-mode-integration"></a><span data-ttu-id="b7b0d-166">Интеграция режима Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="b7b0d-166">Internet Explorer mode integration</span></span>
<span data-ttu-id="b7b0d-167">**Значение по умолчанию:** Режим Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="b7b0d-167">**Default Value:** Internet Explorer mode</span></span>

<span data-ttu-id="b7b0d-168">По умолчанию устройства должны использовать режим Internet Explorer, но вместо этого их можно настроить для открытия сайтов в окне Автономный internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-168">By default, devices are set to use Internet Explorer mode, but you can set them to open sites in a standalone Internet Explorer 11 window instead.</span></span> <span data-ttu-id="b7b0d-169">Чтобы изменить это поведение, необходимо подать запрос на поддержку.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-169">To change this behavior, file a support request.</span></span>

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a><span data-ttu-id="b7b0d-170">Добавление сайтов в список сайтов режима предприятия</span><span class="sxs-lookup"><span data-stu-id="b7b0d-170">Add sites to the Enterprise Mode Site list</span></span>
<span data-ttu-id="b7b0d-171">Чтобы сайты открывали в режиме Internet Explorer, их необходимо включить в список [корпоративных сайтов.](/DeployEdge/edge-ie-mode-sitelist)</span><span class="sxs-lookup"><span data-stu-id="b7b0d-171">For sites to open in Internet Explorer mode you must include them on the [Enterprise Site list](/DeployEdge/edge-ie-mode-sitelist).</span></span> <span data-ttu-id="b7b0d-172">Ведение и развертывание списка корпоративных сайтов — это ваша ответственность.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-172">Maintaining and deploying the Enterprise Site list is your responsibility.</span></span> <span data-ttu-id="b7b0d-173">Подробные сведения см. [в материале Настройка с помощью политики Настройка](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy) списка сайтов режима предприятия</span><span class="sxs-lookup"><span data-stu-id="b7b0d-173">For details, see [Configure using the Configure Enterprise Mode Site List policy](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span></span>

### <a name="other-settings"></a><span data-ttu-id="b7b0d-174">Другие параметры</span><span class="sxs-lookup"><span data-stu-id="b7b0d-174">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="b7b0d-175">Включить изоляцию сайта для каждого сайта</span><span class="sxs-lookup"><span data-stu-id="b7b0d-175">Enable site isolation for every site</span></span>

<span data-ttu-id="b7b0d-176">**Значение по умолчанию:** Включено</span><span class="sxs-lookup"><span data-stu-id="b7b0d-176">**Default value:** Enabled</span></span>

<span data-ttu-id="b7b0d-177">Когда эта политика включена, пользователи не могут отказаться от поведения по умолчанию, в котором каждый сайт выполняется в своем собственном процессе.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-177">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="b7b0d-178">Поддерживаемые схемы проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="b7b0d-178">Supported authentication schemes</span></span>

<span data-ttu-id="b7b0d-179">**Значение по умолчанию:** NTLM, согласование</span><span class="sxs-lookup"><span data-stu-id="b7b0d-179">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="b7b0d-180">Microsoft Managed Desktop не поддерживает базовые или дайджест-схемы проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-180">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="b7b0d-181">Автоматически импортировать данные и параметры другого браузера при первом запуске</span><span class="sxs-lookup"><span data-stu-id="b7b0d-181">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="b7b0d-182">**Значение по умолчанию:** Автоматически импортировать все поддерживаемые типы и параметры данных из браузера по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b7b0d-182">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="b7b0d-183">При применении этой политики первый запуск будет пропускать раздел импорта, сводя к минимуму взаимодействие пользователей.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-183">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="b7b0d-184">Данные браузера из более старых версий Microsoft Edge всегда будут безмолвно перенесены при первом запуске, независимо от этого параметра.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-184">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="b7b0d-185">Параметры, которые вы управляете</span><span class="sxs-lookup"><span data-stu-id="b7b0d-185">Settings you manage</span></span>

<span data-ttu-id="b7b0d-186">Вы можете развернуть все параметры Microsoft Edge, ранее не описанные с помощью профиля административных шаблонов в Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-186">You can deploy any Microsoft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="b7b0d-187">Подробные сведения см. [в материале Настройка параметров политики Microsoft Edge с помощью Microsoft Intune.](/deployedge/configure-edge-with-intune)</span><span class="sxs-lookup"><span data-stu-id="b7b0d-187">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="b7b0d-188">Если вы хотите оценить политику, которая в настоящее время не включена в административные шаблоны Microsoft Edge в Intune, можно использовать настраиваемые параметры для устройств Windows 10 в Intune.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-188">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune, you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="b7b0d-189">Включение определенных расширений Chrome</span><span class="sxs-lookup"><span data-stu-id="b7b0d-189">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="b7b0d-190">Административный шаблон предлагает параметр для развертывания определенных расширений Chrome с помощью Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-190">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="b7b0d-191">Его можно найти в > Microsoft Edge > расширения > Разрешить установку **специальных расширений.**</span><span class="sxs-lookup"><span data-stu-id="b7b0d-191">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="b7b0d-192">Установка расширений в режиме бесшумной установки</span><span class="sxs-lookup"><span data-stu-id="b7b0d-192">Install extensions silently</span></span>

<span data-ttu-id="b7b0d-193">Можно также использовать административный шаблон для установки расширений Microsoft Edge без оповещения пользователя.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-193">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="b7b0d-194">Вы можете найти его в **конфигурации компьютера > Microsoft Edge > расширения**> управления, которые расширения устанавливаются молча .</span><span class="sxs-lookup"><span data-stu-id="b7b0d-194">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="microsoft-edge-update-policies"></a><span data-ttu-id="b7b0d-195">Политики обновления Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b7b0d-195">Microsoft Edge update policies</span></span>
<span data-ttu-id="b7b0d-196">Чтобы убедиться, что Microsoft Edge обновляется правильно, не измените политики обновления Microsoft [Edge.](/deployedge/microsoft-edge-update-policies)</span><span class="sxs-lookup"><span data-stu-id="b7b0d-196">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](/deployedge/microsoft-edge-update-policies).</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="b7b0d-197">Другие общие корпоративные политики</span><span class="sxs-lookup"><span data-stu-id="b7b0d-197">Other common enterprise policies</span></span>

<span data-ttu-id="b7b0d-198">Microsoft Edge предлагает множество других политик.</span><span class="sxs-lookup"><span data-stu-id="b7b0d-198">Microsoft Edge offers a great many other policies.</span></span> <span data-ttu-id="b7b0d-199">Вот некоторые из наиболее распространенных из них:</span><span class="sxs-lookup"><span data-stu-id="b7b0d-199">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="b7b0d-200">Настройка сайтов в корпоративном списке сайтов и режиме IE</span><span class="sxs-lookup"><span data-stu-id="b7b0d-200">Configure Sites on the Enterprise Site List and IE Mode</span></span>](/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="b7b0d-201">Настройка параметров страницы запуска, домашней страницы и новых вкладок</span><span class="sxs-lookup"><span data-stu-id="b7b0d-201">Configure start-up, home page, and new tab page settings</span></span>](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="b7b0d-202">Настройка параметра игры Surf</span><span class="sxs-lookup"><span data-stu-id="b7b0d-202">Configure Surf game setting</span></span>](/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="b7b0d-203">Настройка параметров прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="b7b0d-203">Configure proxy server settings</span></span>](/deployedge/microsoft-edge-policies#proxy-server)