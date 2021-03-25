---
title: Настройка расширенных функций в Microsoft Defender для конечной точки
description: Включаем расширенные функции, такие как блок-файл в Microsoft Defender для конечной точки.
keywords: расширенные функции, параметры, блок-файл, автоматическое расследование, автоматическое разрешение, skype, защитник Майкрософт для удостоверений, Office 365, защита информации azure, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 059cfbf37c79ff9f99b5e46c8d4329c203aa9665
ms.sourcegitcommit: 3d2261af22bebbbf7efa8a0d3135225a15bd6ba8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51215539"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a><span data-ttu-id="ae78e-104">Настройка расширенных функций в Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ae78e-104">Configure advanced features in Defender for Endpoint</span></span>

<span data-ttu-id="ae78e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ae78e-105">**Applies to:**</span></span>
- [<span data-ttu-id="ae78e-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ae78e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ae78e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ae78e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> <span data-ttu-id="ae78e-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ae78e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ae78e-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ae78e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="ae78e-110">В зависимости от продуктов безопасности Майкрософт, которые вы используете, для интеграции Defender для конечной точки могут быть доступны некоторые расширенные функции.</span><span class="sxs-lookup"><span data-stu-id="ae78e-110">Depending on the Microsoft security products that you use, some advanced features might be available for you to integrate Defender for Endpoint with.</span></span>

## <a name="enable-advanced-features"></a><span data-ttu-id="ae78e-111">Включить расширенные функции</span><span class="sxs-lookup"><span data-stu-id="ae78e-111">Enable advanced features</span></span>

1. <span data-ttu-id="ae78e-112">В области навигации выберите **Параметры настройки**  >  **Расширенные функции**.</span><span class="sxs-lookup"><span data-stu-id="ae78e-112">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="ae78e-113">Выберите расширенный элемент, который необходимо настроить и переключить параметр между **"Включи"** и **"Выключен".**</span><span class="sxs-lookup"><span data-stu-id="ae78e-113">Select the advanced feature you want to configure and toggle the setting between **On** and **Off**.</span></span>
3. <span data-ttu-id="ae78e-114">Нажмите **кнопку Сохранить предпочтения**.</span><span class="sxs-lookup"><span data-stu-id="ae78e-114">Click **Save preferences**.</span></span>

<span data-ttu-id="ae78e-115">Используйте следующие расширенные функции, чтобы лучше защититься от потенциально вредоносных файлов и получить более глубокое представление во время расследований по безопасности.</span><span class="sxs-lookup"><span data-stu-id="ae78e-115">Use the following advanced features to get better protected from potentially malicious files and gain better insight during security investigations.</span></span>

## <a name="automated-investigation"></a><span data-ttu-id="ae78e-116">Автоматическое расследование</span><span class="sxs-lookup"><span data-stu-id="ae78e-116">Automated investigation</span></span>

<span data-ttu-id="ae78e-117">Включи эту функцию, чтобы воспользоваться функциями автоматического расследования и восстановления службы.</span><span class="sxs-lookup"><span data-stu-id="ae78e-117">Turn on this feature to take advantage of the automated investigation and remediation features of the service.</span></span> <span data-ttu-id="ae78e-118">Дополнительные сведения см. в [автоматическом расследовании.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="ae78e-118">For more information, see [Automated investigation](automated-investigations.md).</span></span>

## <a name="live-response"></a><span data-ttu-id="ae78e-119">Живой ответ</span><span class="sxs-lookup"><span data-stu-id="ae78e-119">Live response</span></span>

<span data-ttu-id="ae78e-120">Включите эту функцию, чтобы пользователи с соответствующими разрешениями могли начать сеанс живого ответа на устройствах.</span><span class="sxs-lookup"><span data-stu-id="ae78e-120">Turn on this feature so that users with the appropriate permissions can start a live response session on devices.</span></span>

<span data-ttu-id="ae78e-121">Дополнительные сведения о назначениях ролей см. в дополнительных [сведениях о создании и управлении ролями.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="ae78e-121">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>

## <a name="live-response-for-servers"></a><span data-ttu-id="ae78e-122">Live response for servers</span><span class="sxs-lookup"><span data-stu-id="ae78e-122">Live response for servers</span></span>
<span data-ttu-id="ae78e-123">Включите эту функцию, чтобы пользователи с соответствующими разрешениями могли начать сеанс живого ответа на серверах.</span><span class="sxs-lookup"><span data-stu-id="ae78e-123">Turn on this feature so that users with the appropriate permissions can start a live response session on servers.</span></span>

<span data-ttu-id="ae78e-124">Дополнительные сведения о назначениях ролей см. в дополнительных [сведениях о создании и управлении ролями.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="ae78e-124">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>


## <a name="live-response-unsigned-script-execution"></a><span data-ttu-id="ae78e-125">Live response unsigned script execution</span><span class="sxs-lookup"><span data-stu-id="ae78e-125">Live response unsigned script execution</span></span>

<span data-ttu-id="ae78e-126">Включение этой функции позволяет запускать неподписаные скрипты в сеансе живого ответа.</span><span class="sxs-lookup"><span data-stu-id="ae78e-126">Enabling this feature allows you to run unsigned scripts in a live response session.</span></span>

## <a name="autoresolve-remediated-alerts"></a><span data-ttu-id="ae78e-127">Автоматическое исправление оповещений</span><span class="sxs-lookup"><span data-stu-id="ae78e-127">Autoresolve remediated alerts</span></span>

<span data-ttu-id="ae78e-128">Для клиентов, созданных в Windows 10 версии 1809 или после нее, возможность автоматического расследования и устранения настроена по умолчанию для устранения оповещений, в которых состояние результатов автоматического анализа является "Угрозы не найдены" или "Исправлено".</span><span class="sxs-lookup"><span data-stu-id="ae78e-128">For tenants created on or after Windows 10, version 1809, the automated investigation and remediation capability is configured by default to resolve alerts where the automated analysis result status is "No threats found" or "Remediated".</span></span>  <span data-ttu-id="ae78e-129">Если не требуется автоматическое решение оповещений, необходимо вручную отключить функцию.</span><span class="sxs-lookup"><span data-stu-id="ae78e-129">If you don't want to have alerts auto-resolved, you'll need to manually turn off the feature.</span></span>

> [!TIP]
> <span data-ttu-id="ae78e-130">Для клиентов, созданных до этой версии, необходимо вручную включить эту функцию со страницы [Расширенные функции.](https://securitycenter.windows.com/preferences2/integration)</span><span class="sxs-lookup"><span data-stu-id="ae78e-130">For tenants created prior to that version, you'll need to manually turn this feature on from the [Advanced features](https://securitycenter.windows.com/preferences2/integration) page.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="ae78e-131">Результат действия автоматического решения может повлиять на вычисление уровня риска устройства, основанное на активных оповещениях, найденных на устройстве.</span><span class="sxs-lookup"><span data-stu-id="ae78e-131">The result of the auto-resolve action may influence the Device risk level calculation which is based on the active alerts found on a device.</span></span>
> - <span data-ttu-id="ae78e-132">Если аналитик операций безопасности вручную задает состояние оповещений "В процессе" или "Разрешено", возможность автоматического разрешения не будет перезаписывать его.</span><span class="sxs-lookup"><span data-stu-id="ae78e-132">If a security operations analyst manually sets the status of an alert to "In progress" or "Resolved" the auto-resolve capability will not overwrite it.</span></span>

## <a name="allow-or-block-file"></a><span data-ttu-id="ae78e-133">Разрешить или заблокировать файл</span><span class="sxs-lookup"><span data-stu-id="ae78e-133">Allow or block file</span></span>

<span data-ttu-id="ae78e-134">Блокировка доступна только в том случае, если ваша организация выполнит эти требования:</span><span class="sxs-lookup"><span data-stu-id="ae78e-134">Blocking is only available if your organization fulfills these requirements:</span></span>

- <span data-ttu-id="ae78e-135">Использует антивирус Microsoft Defender в качестве активного решения для борьбы с вирусами и,</span><span class="sxs-lookup"><span data-stu-id="ae78e-135">Uses Microsoft Defender Antivirus as the active antimalware solution and,</span></span>
- <span data-ttu-id="ae78e-136">Включена функция защиты на облачной основе</span><span class="sxs-lookup"><span data-stu-id="ae78e-136">The cloud-based protection feature is enabled</span></span>

<span data-ttu-id="ae78e-137">Эта функция позволяет блокировать потенциально вредоносные файлы в сети.</span><span class="sxs-lookup"><span data-stu-id="ae78e-137">This feature enables you to block potentially malicious files in your network.</span></span> <span data-ttu-id="ae78e-138">Блокировка файла не позволит ему читать, писать или выполнять его на устройствах в организации.</span><span class="sxs-lookup"><span data-stu-id="ae78e-138">Blocking a file will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="ae78e-139">Чтобы включить **разрешить или заблокировать** файлы, включив:</span><span class="sxs-lookup"><span data-stu-id="ae78e-139">To turn **Allow or block** files on:</span></span>

1. <span data-ttu-id="ae78e-140">В области навигации выберите **Параметры**  >  **Расширенные функции**  >  **Разрешить или заблокировать файл.**</span><span class="sxs-lookup"><span data-stu-id="ae78e-140">In the navigation pane, select **Settings** > **Advanced features** > **Allow or block file**.</span></span>

1. <span data-ttu-id="ae78e-141">Переключить параметр между **включаемой** и **отключенной**.</span><span class="sxs-lookup"><span data-stu-id="ae78e-141">Toggle the setting between **On** and **Off**.</span></span>

    ![Изображение расширенных параметров для функции файла блока](images/atp-preferences-setup.png)

1. <span data-ttu-id="ae78e-143">Выберите **Сохранить предпочтения** в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="ae78e-143">Select **Save preferences** at the bottom of the page.</span></span>

<span data-ttu-id="ae78e-144">После включения этой функции можно заблокировать файлы с [помощью](respond-file-alerts.md#allow-or-block-file) вкладки **Add Indicator** на странице профиля файла.</span><span class="sxs-lookup"><span data-stu-id="ae78e-144">After turning on this feature, you can [block files](respond-file-alerts.md#allow-or-block-file) via the **Add Indicator** tab on a file's profile page.</span></span>

## <a name="custom-network-indicators"></a><span data-ttu-id="ae78e-145">Настраиваемые сетевые индикаторы</span><span class="sxs-lookup"><span data-stu-id="ae78e-145">Custom network indicators</span></span>

<span data-ttu-id="ae78e-146">Включение этой функции позволяет создавать индикаторы для IP-адресов, доменов или URL-адресов, которые определяют, будут ли они разрешены или заблокированы на основе настраиваемой списка индикаторов.</span><span class="sxs-lookup"><span data-stu-id="ae78e-146">Turning on this feature allows you to create indicators for IP addresses, domains, or URLs, which determine whether they will be allowed or blocked based on your custom indicator list.</span></span>

<span data-ttu-id="ae78e-147">Чтобы использовать эту функцию, устройства должны запускать Windows 10 версии 1709 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="ae78e-147">To use this feature, devices must be running Windows 10 version 1709 or later.</span></span> <span data-ttu-id="ae78e-148">Они также должны иметь защиту сети в режиме блокировки и версии 4.18.1906.3 или более поздней версии платформы антивирусных программ см. [в KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).</span><span class="sxs-lookup"><span data-stu-id="ae78e-148">They should also have network protection in block mode and version 4.18.1906.3 or later of the antimalware platform [see KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).</span></span>

<span data-ttu-id="ae78e-149">Дополнительные сведения см. в [руб. Управление индикаторами.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="ae78e-149">For more information, see [Manage indicators](manage-indicators.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ae78e-150">Защита сети использует службы репутации, которые обрабатывает запросы в местах, которые могут быть за пределами выбранного вами расположения для данных Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="ae78e-150">Network protection leverages reputation services that process requests in locations that might be outside of the location you have selected for your Defender for Endpoint data.</span></span>

## <a name="show-user-details"></a><span data-ttu-id="ae78e-151">Демонстрация сведений о пользователях</span><span class="sxs-lookup"><span data-stu-id="ae78e-151">Show user details</span></span>

<span data-ttu-id="ae78e-152">Включи эту функцию, чтобы вы могли видеть сведения пользователей, хранимые в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ae78e-152">Turn on this feature so that you can see user details stored in Azure Active Directory.</span></span> <span data-ttu-id="ae78e-153">При расследовании сущностями учетных записей пользователей сведения включают сведения о пользователе, его имени, названии и сведениях о отделах.</span><span class="sxs-lookup"><span data-stu-id="ae78e-153">Details include a user's picture, name, title, and department information  when investigating user account entities.</span></span> <span data-ttu-id="ae78e-154">Сведения о учетной записи пользователей можно найти в следующих представлениях:</span><span class="sxs-lookup"><span data-stu-id="ae78e-154">You can find user account information in the following views:</span></span>

- <span data-ttu-id="ae78e-155">Панель мониторинга операций безопасности</span><span class="sxs-lookup"><span data-stu-id="ae78e-155">Security operations dashboard</span></span>
- <span data-ttu-id="ae78e-156">Очередь оповещений</span><span class="sxs-lookup"><span data-stu-id="ae78e-156">Alert queue</span></span>
- <span data-ttu-id="ae78e-157">Страница сведения об устройстве</span><span class="sxs-lookup"><span data-stu-id="ae78e-157">Device details page</span></span>

<span data-ttu-id="ae78e-158">Дополнительные сведения см. в [дополнительных сведениях о расследовании учетной записи пользователя.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="ae78e-158">For more information, see [Investigate a user account](investigate-user.md).</span></span>

## <a name="skype-for-business-integration"></a><span data-ttu-id="ae78e-159">Интеграция Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ae78e-159">Skype for Business integration</span></span>

<span data-ttu-id="ae78e-160">Включение интеграции Skype для бизнеса позволяет общаться с пользователями с помощью Skype для бизнеса, электронной почты или телефона.</span><span class="sxs-lookup"><span data-stu-id="ae78e-160">Enabling the Skype for Business integration gives you the ability to communicate with users using Skype for Business, email, or phone.</span></span> <span data-ttu-id="ae78e-161">Это может быть удобно при общении с пользователем и смягчении рисков.</span><span class="sxs-lookup"><span data-stu-id="ae78e-161">This can be handy when you need to communicate with the user and mitigate risks.</span></span>

> [!NOTE]
> <span data-ttu-id="ae78e-162">Когда устройство изолировано от сети, есть всплывающее сообщение, в котором можно включить связь Outlook и Skype, которая позволяет использовать связь с пользователем при отключении от сети.</span><span class="sxs-lookup"><span data-stu-id="ae78e-162">When a device is being isolated from the network, there's a pop-up where you can choose to enable Outlook and Skype communications which allows communications to the user while they are disconnected from the network.</span></span> <span data-ttu-id="ae78e-163">Этот параметр применяется к связи Skype и Outlook, когда устройства находятся в изолированном режиме.</span><span class="sxs-lookup"><span data-stu-id="ae78e-163">This setting applies to Skype and Outlook communication when devices are in isolation mode.</span></span>

## <a name="azure-advanced-threat-protection-integration"></a><span data-ttu-id="ae78e-164">Интеграция с расширенными средствами защиты от угроз Azure</span><span class="sxs-lookup"><span data-stu-id="ae78e-164">Azure Advanced Threat Protection integration</span></span>

<span data-ttu-id="ae78e-165">Интеграция с Azure Advanced Threat Protection позволяет напрямую перейти в другой продукт безопасности Microsoft Identity.</span><span class="sxs-lookup"><span data-stu-id="ae78e-165">The integration with Azure Advanced Threat Protection allows you to pivot directly into another Microsoft Identity security product.</span></span> <span data-ttu-id="ae78e-166">Расширенная защита от угроз Azure дополняет расследование дополнительными сведениями о предполагаемой скомпрометированной учетной записи и связанных с ней ресурсах.</span><span class="sxs-lookup"><span data-stu-id="ae78e-166">Azure Advanced Threat Protection augments an investigation with additional insights about a suspected compromised account and related resources.</span></span> <span data-ttu-id="ae78e-167">Включив эту функцию, вы обогатите возможности исследования на основе устройств, выключив по сети с точки зрения идентификации.</span><span class="sxs-lookup"><span data-stu-id="ae78e-167">By enabling this feature, you'll enrich the device-based investigation capability by pivoting across the network from an identify point of view.</span></span>

> [!NOTE]
> <span data-ttu-id="ae78e-168">Чтобы включить эту функцию, вам потребуется соответствующая лицензия.</span><span class="sxs-lookup"><span data-stu-id="ae78e-168">You'll need to have the appropriate license to enable this feature.</span></span>

## <a name="office-365-threat-intelligence-connection"></a><span data-ttu-id="ae78e-169">Подключение к office 365 Threat Intelligence</span><span class="sxs-lookup"><span data-stu-id="ae78e-169">Office 365 Threat Intelligence connection</span></span>

<span data-ttu-id="ae78e-170">Эта функция доступна только при наличии активной надстройки Office 365 E5 или надстройки Threat Intelligence.</span><span class="sxs-lookup"><span data-stu-id="ae78e-170">This feature is only available if you have an active Office 365 E5 or the Threat Intelligence add-on.</span></span> <span data-ttu-id="ae78e-171">Дополнительные сведения см. на странице продукта Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="ae78e-171">For more information, see the Office 365 Enterprise E5 product page.</span></span>

<span data-ttu-id="ae78e-172">При включив эту функцию, вы сможете включить данные из Office 365 Advanced Threat Protection в Центр безопасности Microsoft Defender для проведения комплексного расследования безопасности на почтовых ящиках Office 365 и устройствах Windows.</span><span class="sxs-lookup"><span data-stu-id="ae78e-172">When you turn this feature on, you'll be able to incorporate data from Office 365 Advanced Threat Protection into Microsoft Defender Security Center to conduct a comprehensive security investigation across Office 365 mailboxes and Windows devices.</span></span>

> [!NOTE]
> <span data-ttu-id="ae78e-173">Чтобы включить эту функцию, вам потребуется соответствующая лицензия.</span><span class="sxs-lookup"><span data-stu-id="ae78e-173">You'll need to have the appropriate license to enable this feature.</span></span>

<span data-ttu-id="ae78e-174">Чтобы получить контекстную интеграцию устройств в Office 365 Threat Intelligence, необходимо включить параметры Defender для конечной точки в панели мониторинга & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ae78e-174">To receive contextual device integration in Office 365 Threat Intelligence, you'll need to enable the Defender for Endpoint settings in the Security & Compliance dashboard.</span></span> <span data-ttu-id="ae78e-175">Дополнительные сведения см. в [дополнительных сведениях о расследовании угрозы и ответах.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)</span><span class="sxs-lookup"><span data-stu-id="ae78e-175">For more information, see [Threat investigation and response](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti).</span></span>

## <a name="microsoft-threat-experts"></a><span data-ttu-id="ae78e-176">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="ae78e-176">Microsoft Threat Experts</span></span>

<span data-ttu-id="ae78e-177">Из двух компонентов Microsoft Threat Expert целевое уведомление об атаке в общем доступе.</span><span class="sxs-lookup"><span data-stu-id="ae78e-177">Out of the two Microsoft Threat Expert components, targeted attack notification is in general availability.</span></span> <span data-ttu-id="ae78e-178">Возможности экспертов по запросу по-прежнему находятся в предварительном просмотре.</span><span class="sxs-lookup"><span data-stu-id="ae78e-178">Experts-on-demand capability is still in preview.</span></span> <span data-ttu-id="ae78e-179">Вы можете использовать возможности экспертов по запросу только в том случае, если вы подали заявку на предварительное просмотр и ваше приложение было утверждено.</span><span class="sxs-lookup"><span data-stu-id="ae78e-179">You can only use the experts-on-demand capability if you have applied for preview and your application has been approved.</span></span> <span data-ttu-id="ae78e-180">При настройке можно получать целевые уведомления об атаке от экспертов Microsoft Threat с помощью панели оповещений портала Защитник для конечных точек и по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="ae78e-180">You can receive targeted attack notifications from Microsoft Threat Experts through your Defender for Endpoint portal's alerts dashboard and via email if you configure it.</span></span>

> [!NOTE]
> <span data-ttu-id="ae78e-181">Возможность экспертов по угрозам Майкрософт в Defender for Endpoint доступна с лицензией E5 для корпоративной [мобильности и безопасности.](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)</span><span class="sxs-lookup"><span data-stu-id="ae78e-181">The Microsoft Threat Experts capability in Defender for Endpoint is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security).</span></span>

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="ae78e-182">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ae78e-182">Microsoft Cloud App Security</span></span>

<span data-ttu-id="ae78e-183">Включение этого параметра передает сигналы Defender for Endpoint в Microsoft Cloud App Security, чтобы обеспечить более глубокую видимость использования облачных приложений.</span><span class="sxs-lookup"><span data-stu-id="ae78e-183">Enabling this setting forwards Defender for Endpoint signals to Microsoft Cloud App Security to provide deeper visibility into cloud application usage.</span></span> <span data-ttu-id="ae78e-184">Переададные данные хранятся и обрабатываются в том же месте, что и данные безопасности облачных приложений.</span><span class="sxs-lookup"><span data-stu-id="ae78e-184">Forwarded data is stored and processed in the same location as your Cloud App Security data.</span></span>

> [!NOTE]
> <span data-ttu-id="ae78e-185">Эта функция будет доступна с лицензией E5 для корпоративной мобильности [и](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) безопасности на устройствах под управлением Windows 10, версии 1709 (СБОРКА ОС 16299.1085 с [KB4493441),](https://support.microsoft.com/help/4493441)Windows 10, версия 1803 (сборка ОС 17134.704 с [KB4493464),](https://support.microsoft.com/help/4493464)Windows 10, версия 1809 (OS Build 17763.379 с [KB4489899),](https://support.microsoft.com/help/4489899)или более поздние версии Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ae78e-185">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)), or later Windows 10 versions.</span></span>

## <a name="azure-information-protection"></a><span data-ttu-id="ae78e-186">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="ae78e-186">Azure Information Protection</span></span>

<span data-ttu-id="ae78e-187">Включение этого параметра позволяет переадлить сигналы в Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="ae78e-187">Turning on this setting allows signals to be forwarded to Azure Information Protection.</span></span> <span data-ttu-id="ae78e-188">Это дает владельцам и администраторам данных видимость защищенных данных на бортовых устройствах и оценках рисков устройств.</span><span class="sxs-lookup"><span data-stu-id="ae78e-188">It gives data owners and administrators visibility into protected data on onboarded devices and device risk ratings.</span></span>

## <a name="microsoft-secure-score"></a><span data-ttu-id="ae78e-189">Оценка безопасности (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="ae78e-189">Microsoft Secure Score</span></span>

<span data-ttu-id="ae78e-190">Передает сигналы Microsoft Defender для конечных точек в Центр безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae78e-190">Forwards Microsoft Defender for Endpoint signals to Microsoft Secure Score in the Microsoft 365 security center.</span></span> <span data-ttu-id="ae78e-191">Включение этой функции обеспечивает видимость Microsoft Secure Score в области безопасности устройства.</span><span class="sxs-lookup"><span data-stu-id="ae78e-191">Turning on this feature gives Microsoft Secure Score visibility into the device's security posture.</span></span> <span data-ttu-id="ae78e-192">Переададные данные хранятся и обрабатываются в том же месте, что и данные Microsoft Secure Score.</span><span class="sxs-lookup"><span data-stu-id="ae78e-192">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>

### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a><span data-ttu-id="ae78e-193">Включение интеграции Microsoft Defender для конечной точки с портала Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="ae78e-193">Enable the Microsoft Defender for Endpoint integration from the Microsoft Defender for Identity portal</span></span>

<span data-ttu-id="ae78e-194">Чтобы получить контекстную интеграцию устройств в Microsoft Defender for Identity, необходимо также включить эту функцию на портале Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="ae78e-194">To receive contextual device integration in Microsoft Defender for Identity, you'll also need to enable the feature in the Microsoft Defender for Identity portal.</span></span>

1. <span data-ttu-id="ae78e-195">Войдите на портал [Microsoft Defender for Identity](https://portal.atp.azure.com/) с ролью глобального администратора или администратора безопасности.</span><span class="sxs-lookup"><span data-stu-id="ae78e-195">Log in to the [Microsoft Defender for Identity portal](https://portal.atp.azure.com/) with a Global Administrator or Security Administrator role.</span></span>

2. <span data-ttu-id="ae78e-196">Нажмите **кнопку Создать экземпляр**.</span><span class="sxs-lookup"><span data-stu-id="ae78e-196">Click **Create your instance**.</span></span>

3. <span data-ttu-id="ae78e-197">Настройка интеграции для **параметра On** и нажмите **кнопку Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ae78e-197">Toggle the Integration setting to **On** and click **Save**.</span></span>

<span data-ttu-id="ae78e-198">После завершения этапов интеграции на обоих порталах вы сможете увидеть соответствующие оповещения на странице сведения об устройстве или сведения о пользователе.</span><span class="sxs-lookup"><span data-stu-id="ae78e-198">After completing the integration steps on both portals, you'll be able to see relevant alerts in the device details or user details page.</span></span>

## <a name="microsoft-intune-connection"></a><span data-ttu-id="ae78e-199">Подключение Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ae78e-199">Microsoft Intune connection</span></span>

<span data-ttu-id="ae78e-200">Defender for Endpoint можно интегрировать с [Microsoft Intune,](https://docs.microsoft.com/intune/what-is-intune) чтобы включить условный доступ к устройству на основе [риска.](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)</span><span class="sxs-lookup"><span data-stu-id="ae78e-200">Defender for Endpoint can be integrated with [Microsoft Intune](https://docs.microsoft.com/intune/what-is-intune) to [enable device risk-based conditional access](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span> <span data-ttu-id="ae78e-201">[Включив эту](configure-conditional-access.md)функцию, вы сможете обмениваться сведениями о устройствах Defender для конечных точек с Помощью Intune, что повышает правоприменение политики.</span><span class="sxs-lookup"><span data-stu-id="ae78e-201">When you [turn on this feature](configure-conditional-access.md), you'll be able to share Defender for Endpoint device information with Intune, enhancing policy enforcement.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae78e-202">Вам потребуется включить интеграцию в Intune и Defender для конечной точки, чтобы использовать эту функцию.</span><span class="sxs-lookup"><span data-stu-id="ae78e-202">You'll need to enable the integration on both Intune and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="ae78e-203">Дополнительные сведения о конкретных действиях см. в дополнительных сведениях [о настройке условного доступа в Defender для конечной точки.](configure-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="ae78e-203">For more information on specific steps, see [Configure Conditional Access in Defender for Endpoint](configure-conditional-access.md).</span></span>

<span data-ttu-id="ae78e-204">Эта функция доступна только в том случае, если у вас есть следующие функции:</span><span class="sxs-lookup"><span data-stu-id="ae78e-204">This feature is only available if you have the following:</span></span>

- <span data-ttu-id="ae78e-205">Лицензированный клиент для корпоративной мобильности и безопасности E3 и Windows E5 (или Microsoft 365 Корпоративный E5)</span><span class="sxs-lookup"><span data-stu-id="ae78e-205">A licensed tenant for Enterprise Mobility + Security E3, and Windows E5 (or Microsoft 365 Enterprise E5)</span></span>
- <span data-ttu-id="ae78e-206">Активная среда Microsoft Intune с управляемыми Intune устройствами Windows 10 [Azure AD-joined.](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/)</span><span class="sxs-lookup"><span data-stu-id="ae78e-206">An active Microsoft Intune environment, with Intune-managed Windows 10 devices [Azure AD-joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/).</span></span>

### <a name="conditional-access-policy"></a><span data-ttu-id="ae78e-207">Политика условного доступа</span><span class="sxs-lookup"><span data-stu-id="ae78e-207">Conditional Access policy</span></span>

<span data-ttu-id="ae78e-208">Если включить интеграцию Intune, Intune автоматически создаст классическую политику условного доступа (CA).</span><span class="sxs-lookup"><span data-stu-id="ae78e-208">When you enable Intune integration, Intune will automatically create a classic Conditional Access (CA) policy.</span></span> <span data-ttu-id="ae78e-209">Эта классическая политика ЦС является обязательным условием для настройки отчетов о состоянии в Intune.</span><span class="sxs-lookup"><span data-stu-id="ae78e-209">This classic CA policy is a prerequisite for setting up status reports to Intune.</span></span> <span data-ttu-id="ae78e-210">Его не следует удалять.</span><span class="sxs-lookup"><span data-stu-id="ae78e-210">It should not be deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="ae78e-211">Классическая политика ЦС, созданная Intune, отличается от современных политик условного [доступа,](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/)которые используются для настройки конечных точек.</span><span class="sxs-lookup"><span data-stu-id="ae78e-211">The classic CA policy created by Intune is distinct from modern [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/), which are used for configuring endpoints.</span></span>

## <a name="preview-features"></a><span data-ttu-id="ae78e-212">Предварительные функции</span><span class="sxs-lookup"><span data-stu-id="ae78e-212">Preview features</span></span>

<span data-ttu-id="ae78e-213">Узнайте о новых функциях в выпуске предварительного просмотра Defender для конечной точки и одними из первых попробуйте новые функции, включив функцию предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="ae78e-213">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="ae78e-214">Вы будете иметь доступ к предстоящим функциям, которые можно предоставить отзывы, чтобы помочь улучшить общий опыт, прежде чем функции будут доступны в целом.</span><span class="sxs-lookup"><span data-stu-id="ae78e-214">You'll have access to upcoming features, which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a><span data-ttu-id="ae78e-215">Share endpoint alerts with Microsoft Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ae78e-215">Share endpoint alerts with Microsoft Compliance Center</span></span>

<span data-ttu-id="ae78e-216">Перенаправление оповещений о безопасности конечной точки и их состояния в Центр соответствия требованиям Майкрософт, что позволяет повысить внутреннюю политику управления рисками с помощью оповещений и устранять внутренние риски, прежде чем они причинят вред.</span><span class="sxs-lookup"><span data-stu-id="ae78e-216">Forwards endpoint security alerts and their triage status to Microsoft Compliance Center, allowing you to enhance insider risk management policies with alerts and remediate internal risks before they cause harm.</span></span> <span data-ttu-id="ae78e-217">Переададные данные обрабатываются и хранятся в том же месте, что и данные Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae78e-217">Forwarded data is processed and stored in the same location as your Office 365 data.</span></span>

<span data-ttu-id="ae78e-218">После настройки [](/microsoft-365/compliance/insider-risk-management-settings#indicators) индикаторов нарушений политики безопасности в параметрах управления рисками, оповещения Defender for Endpoint будут совместно использовать для управления рисками для соответствующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="ae78e-218">After configuring the [Security policy violation indicators](/microsoft-365/compliance/insider-risk-management-settings#indicators) in the insider risk management settings, Defender for Endpoint alerts will be shared with insider risk management for applicable users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ae78e-219">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ae78e-219">Related topics</span></span>

- [<span data-ttu-id="ae78e-220">Обновление параметров хранения данных</span><span class="sxs-lookup"><span data-stu-id="ae78e-220">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="ae78e-221">Настройка уведомлений оповещений</span><span class="sxs-lookup"><span data-stu-id="ae78e-221">Configure alert notifications</span></span>](configure-email-notifications.md)
