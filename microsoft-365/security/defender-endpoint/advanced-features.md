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
ms.openlocfilehash: 2448b95e5c5c5da25a916b659f6b49d04ba8f0c1
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339578"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a><span data-ttu-id="d4c77-104">Настройка расширенных функций в Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d4c77-104">Configure advanced features in Defender for Endpoint</span></span>

<span data-ttu-id="d4c77-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d4c77-105">**Applies to:**</span></span>
- [<span data-ttu-id="d4c77-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d4c77-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d4c77-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4c77-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> <span data-ttu-id="d4c77-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="d4c77-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d4c77-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="d4c77-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="d4c77-110">В зависимости от продуктов безопасности Майкрософт, которые вы используете, для интеграции Defender для конечной точки могут быть доступны некоторые расширенные функции.</span><span class="sxs-lookup"><span data-stu-id="d4c77-110">Depending on the Microsoft security products that you use, some advanced features might be available for you to integrate Defender for Endpoint with.</span></span>

## <a name="enable-advanced-features"></a><span data-ttu-id="d4c77-111">Включить расширенные функции</span><span class="sxs-lookup"><span data-stu-id="d4c77-111">Enable advanced features</span></span>

1. <span data-ttu-id="d4c77-112">В области навигации выберите **Параметры настройки**  >  **Расширенные функции**.</span><span class="sxs-lookup"><span data-stu-id="d4c77-112">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="d4c77-113">Выберите расширенный элемент, который необходимо настроить и переключить параметр между **"Включи"** и **"Выключен".**</span><span class="sxs-lookup"><span data-stu-id="d4c77-113">Select the advanced feature you want to configure and toggle the setting between **On** and **Off**.</span></span>
3. <span data-ttu-id="d4c77-114">Нажмите **кнопку Сохранить предпочтения**.</span><span class="sxs-lookup"><span data-stu-id="d4c77-114">Click **Save preferences**.</span></span>

<span data-ttu-id="d4c77-115">Используйте следующие расширенные функции, чтобы лучше защититься от потенциально вредоносных файлов и получить более глубокое представление во время расследований по безопасности.</span><span class="sxs-lookup"><span data-stu-id="d4c77-115">Use the following advanced features to get better protected from potentially malicious files and gain better insight during security investigations.</span></span>

## <a name="automated-investigation"></a><span data-ttu-id="d4c77-116">Автоматическое расследование</span><span class="sxs-lookup"><span data-stu-id="d4c77-116">Automated investigation</span></span>

<span data-ttu-id="d4c77-117">Включи эту функцию, чтобы воспользоваться функциями автоматического расследования и восстановления службы.</span><span class="sxs-lookup"><span data-stu-id="d4c77-117">Turn on this feature to take advantage of the automated investigation and remediation features of the service.</span></span> <span data-ttu-id="d4c77-118">Дополнительные сведения см. в [автоматическом расследовании.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="d4c77-118">For more information, see [Automated investigation](automated-investigations.md).</span></span>

## <a name="live-response"></a><span data-ttu-id="d4c77-119">Живой ответ</span><span class="sxs-lookup"><span data-stu-id="d4c77-119">Live response</span></span>

<span data-ttu-id="d4c77-120">Включите эту функцию, чтобы пользователи с соответствующими разрешениями могли начать сеанс живого ответа на устройствах.</span><span class="sxs-lookup"><span data-stu-id="d4c77-120">Turn on this feature so that users with the appropriate permissions can start a live response session on devices.</span></span>

<span data-ttu-id="d4c77-121">Дополнительные сведения о назначениях ролей см. в дополнительных [сведениях о создании и управлении ролями.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="d4c77-121">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>

## <a name="live-response-for-servers"></a><span data-ttu-id="d4c77-122">Live response for servers</span><span class="sxs-lookup"><span data-stu-id="d4c77-122">Live response for servers</span></span>
<span data-ttu-id="d4c77-123">Включите эту функцию, чтобы пользователи с соответствующими разрешениями могли начать сеанс живого ответа на серверах.</span><span class="sxs-lookup"><span data-stu-id="d4c77-123">Turn on this feature so that users with the appropriate permissions can start a live response session on servers.</span></span>

<span data-ttu-id="d4c77-124">Дополнительные сведения о назначениях ролей см. в дополнительных [сведениях о создании и управлении ролями.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="d4c77-124">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>


## <a name="live-response-unsigned-script-execution"></a><span data-ttu-id="d4c77-125">Live response unsigned script execution</span><span class="sxs-lookup"><span data-stu-id="d4c77-125">Live response unsigned script execution</span></span>

<span data-ttu-id="d4c77-126">Включение этой функции позволяет запускать неподписаные скрипты в сеансе живого ответа.</span><span class="sxs-lookup"><span data-stu-id="d4c77-126">Enabling this feature allows you to run unsigned scripts in a live response session.</span></span>

## <a name="always-remediate-pua"></a><span data-ttu-id="d4c77-127">Всегда исправление PUA</span><span class="sxs-lookup"><span data-stu-id="d4c77-127">Always remediate PUA</span></span>
<span data-ttu-id="d4c77-128">Потенциально нежелательные приложения (PUA) — это категория программного обеспечения, которое может вызвать медленную работу вашего компьютера, отображение непредвиденной рекламы или, в худшем случае, установку другого программного обеспечения, которое может быть неожиданным или нежелательным.</span><span class="sxs-lookup"><span data-stu-id="d4c77-128">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software which might be unexpected or unwanted.</span></span> 

<span data-ttu-id="d4c77-129">Включите эту функцию, чтобы потенциально нежелательные приложения (PUA) были исправлены на всех устройствах в клиенте, даже если защита PUA не настроена на устройствах.</span><span class="sxs-lookup"><span data-stu-id="d4c77-129">Turn on this feature so that potentially unwanted applications (PUA) are remediated on all devices in your tenant even if PUA protection is not configured on the devices.</span></span> <span data-ttu-id="d4c77-130">Это поможет защитить пользователей от случайной установки нежелательных приложений на своем устройстве.</span><span class="sxs-lookup"><span data-stu-id="d4c77-130">This will help protect users from inadvertently installing unwanted applications on their device.</span></span> <span data-ttu-id="d4c77-131">При отключении исправление зависит от конфигурации устройства.</span><span class="sxs-lookup"><span data-stu-id="d4c77-131">When turned off, remediation is dependent on the device configuration.</span></span> 


## <a name="restrict-correlation-to-within-scoped-device-groups"></a><span data-ttu-id="d4c77-132">Ограничение корреляции для групп устройств с масштабами</span><span class="sxs-lookup"><span data-stu-id="d4c77-132">Restrict correlation to within scoped device groups</span></span>
<span data-ttu-id="d4c77-133">Эта конфигурация может использоваться для сценариев, в которых локальные операции SOC хотели бы ограничить корреляции оповещений только группам устройств, к которые они могут получить доступ.</span><span class="sxs-lookup"><span data-stu-id="d4c77-133">This configuration can be used for scenarios where local SOC operations would like to limit alert correlations only to device groups that they can access.</span></span> <span data-ttu-id="d4c77-134">Включив этот параметр, инцидент, состоящий из оповещений, которые пересекают группы устройств, больше не будет считаться одним инцидентом.</span><span class="sxs-lookup"><span data-stu-id="d4c77-134">By turning this setting on, an incident composed of alerts that cross device groups will no longer be considered a single incident.</span></span> <span data-ttu-id="d4c77-135">Затем локальный SOC может принять меры по инциденту, так как у них есть доступ к одной из групп устройств, участвующих в инциденте.</span><span class="sxs-lookup"><span data-stu-id="d4c77-135">The local SOC can then take action on the incident because they have access to one of the device groups involved.</span></span> <span data-ttu-id="d4c77-136">Однако глобальный SOC будет видеть несколько различных инцидентов по группе устройств вместо одного инцидента.</span><span class="sxs-lookup"><span data-stu-id="d4c77-136">However, global SOC will see several different incidents by device group instead of one incident.</span></span> <span data-ttu-id="d4c77-137">Мы не рекомендуем включить этот параметр, если это не перевешивает преимущества корреляции инцидентов во всей организации</span><span class="sxs-lookup"><span data-stu-id="d4c77-137">We do not recommend turning this setting on unless doing so outweighs the benefits of incident correlation across the entire organization</span></span>
>[!NOTE]
><span data-ttu-id="d4c77-138">Изменение этого параметра влияет только на будущие корреляции оповещений.</span><span class="sxs-lookup"><span data-stu-id="d4c77-138">Changing this setting impacts future alert correlations only.</span></span>

## <a name="enable-edr-in-block-mode"></a><span data-ttu-id="d4c77-139">Включить EDR в режиме блокировки</span><span class="sxs-lookup"><span data-stu-id="d4c77-139">Enable EDR in block mode</span></span>
<span data-ttu-id="d4c77-140">Обнаружение и ответ конечной точки (EDR) в режиме блокировки обеспечивает защиту от вредоносных артефактов, даже если антивирусная программа в Microsoft Defender работает в пассивном режиме.</span><span class="sxs-lookup"><span data-stu-id="d4c77-140">Endpoint detection and response (EDR) in block mode provides protection from malicious artifacts, even when Microsoft Defender Antivirus is running in passive mode.</span></span> <span data-ttu-id="d4c77-141">При включенном EDR режиме блоки блокируют вредоносные артефакты или поведение, обнаруженные на устройстве.</span><span class="sxs-lookup"><span data-stu-id="d4c77-141">When turned on, EDR in block mode blocks malicious artifacts or behaviors that are detected on a device.</span></span> <span data-ttu-id="d4c77-142">EDR режиме блокировки работает за кулисами для устранения вредоносных артефактов, обнаруженных после нарушения.</span><span class="sxs-lookup"><span data-stu-id="d4c77-142">EDR in block mode works behind the scenes to remediate malicious artifacts that are detected post breach.</span></span>


## <a name="autoresolve-remediated-alerts"></a><span data-ttu-id="d4c77-143">Автоматическое исправление оповещений</span><span class="sxs-lookup"><span data-stu-id="d4c77-143">Autoresolve remediated alerts</span></span>

<span data-ttu-id="d4c77-144">Для клиентов, созданных в Windows 10, версия 1809 или после этого, возможность автоматического расследования и устранения по умолчанию настраивается для устранения оповещений, в которых состояние результатов автоматического анализа — "Угрозы не найдены" или "Исправлены".</span><span class="sxs-lookup"><span data-stu-id="d4c77-144">For tenants created on or after Windows 10, version 1809, the automated investigation and remediation capability is configured by default to resolve alerts where the automated analysis result status is "No threats found" or "Remediated".</span></span>  <span data-ttu-id="d4c77-145">Если не требуется автоматическое решение оповещений, необходимо вручную отключить функцию.</span><span class="sxs-lookup"><span data-stu-id="d4c77-145">If you don't want to have alerts auto-resolved, you'll need to manually turn off the feature.</span></span>

> [!TIP]
> <span data-ttu-id="d4c77-146">Для клиентов, созданных до этой версии, необходимо вручную включить эту функцию со страницы [Расширенные функции.](https://securitycenter.windows.com/preferences2/integration)</span><span class="sxs-lookup"><span data-stu-id="d4c77-146">For tenants created prior to that version, you'll need to manually turn this feature on from the [Advanced features](https://securitycenter.windows.com/preferences2/integration) page.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="d4c77-147">Результат действия автоматического решения может повлиять на вычисление уровня риска устройства, основанное на активных оповещениях, найденных на устройстве.</span><span class="sxs-lookup"><span data-stu-id="d4c77-147">The result of the auto-resolve action may influence the Device risk level calculation which is based on the active alerts found on a device.</span></span>
> - <span data-ttu-id="d4c77-148">Если аналитик операций безопасности вручную задает состояние оповещений "В процессе" или "Разрешено", возможность автоматического разрешения не будет перезаписывать его.</span><span class="sxs-lookup"><span data-stu-id="d4c77-148">If a security operations analyst manually sets the status of an alert to "In progress" or "Resolved" the auto-resolve capability will not overwrite it.</span></span>

## <a name="allow-or-block-file"></a><span data-ttu-id="d4c77-149">Разрешить или заблокировать файл</span><span class="sxs-lookup"><span data-stu-id="d4c77-149">Allow or block file</span></span>

<span data-ttu-id="d4c77-150">Блокировка доступна только в том случае, если ваша организация выполнит эти требования:</span><span class="sxs-lookup"><span data-stu-id="d4c77-150">Blocking is only available if your organization fulfills these requirements:</span></span>

- <span data-ttu-id="d4c77-151">Использует антивирусная программа в Microsoft Defender в качестве активного решения для борьбы с антивирусом и,</span><span class="sxs-lookup"><span data-stu-id="d4c77-151">Uses Microsoft Defender Antivirus as the active antimalware solution and,</span></span>
- <span data-ttu-id="d4c77-152">Включена функция защиты на облачной основе</span><span class="sxs-lookup"><span data-stu-id="d4c77-152">The cloud-based protection feature is enabled</span></span>

<span data-ttu-id="d4c77-153">Эта функция позволяет блокировать потенциально вредоносные файлы в сети.</span><span class="sxs-lookup"><span data-stu-id="d4c77-153">This feature enables you to block potentially malicious files in your network.</span></span> <span data-ttu-id="d4c77-154">Блокировка файла не позволит ему читать, писать или выполнять его на устройствах в организации.</span><span class="sxs-lookup"><span data-stu-id="d4c77-154">Blocking a file will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="d4c77-155">Чтобы включить **разрешить или заблокировать** файлы, включив:</span><span class="sxs-lookup"><span data-stu-id="d4c77-155">To turn **Allow or block** files on:</span></span>

1. <span data-ttu-id="d4c77-156">В области навигации выберите **Параметры**  >  **Конечные** точки Общие расширенные функции  >    >    >  **Разрешить или заблокировать файл.**</span><span class="sxs-lookup"><span data-stu-id="d4c77-156">In the navigation pane, select **Settings** > **Endpoints** > **General** > **Advanced features** > **Allow or block file**.</span></span>

1. <span data-ttu-id="d4c77-157">Переключить параметр между **включаемой** и **отключенной**.</span><span class="sxs-lookup"><span data-stu-id="d4c77-157">Toggle the setting between **On** and **Off**.</span></span>

    ![Изображение расширенных параметров для функции файла блока](images/atp-preferences-setup.png)

1. <span data-ttu-id="d4c77-159">Выберите **Сохранить предпочтения** в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="d4c77-159">Select **Save preferences** at the bottom of the page.</span></span>

<span data-ttu-id="d4c77-160">После включения этой функции можно заблокировать файлы с [помощью](respond-file-alerts.md#allow-or-block-file) вкладки **Add Indicator** на странице профиля файла.</span><span class="sxs-lookup"><span data-stu-id="d4c77-160">After turning on this feature, you can [block files](respond-file-alerts.md#allow-or-block-file) via the **Add Indicator** tab on a file's profile page.</span></span>

## <a name="custom-network-indicators"></a><span data-ttu-id="d4c77-161">Настраиваемые сетевые индикаторы</span><span class="sxs-lookup"><span data-stu-id="d4c77-161">Custom network indicators</span></span>

<span data-ttu-id="d4c77-162">Включение этой функции позволяет создавать индикаторы для IP-адресов, доменов или URL-адресов, которые определяют, будут ли они разрешены или заблокированы на основе настраиваемой списка индикаторов.</span><span class="sxs-lookup"><span data-stu-id="d4c77-162">Turning on this feature allows you to create indicators for IP addresses, domains, or URLs, which determine whether they will be allowed or blocked based on your custom indicator list.</span></span>

<span data-ttu-id="d4c77-163">Чтобы использовать эту функцию, устройства должны запускаться Windows 10 версии 1709 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="d4c77-163">To use this feature, devices must be running Windows 10 version 1709 or later.</span></span> <span data-ttu-id="d4c77-164">Они также должны иметь защиту сети в режиме блокировки и версии 4.18.1906.3 или более поздней версии платформы антивирусных программ см. [в KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).</span><span class="sxs-lookup"><span data-stu-id="d4c77-164">They should also have network protection in block mode and version 4.18.1906.3 or later of the antimalware platform [see KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).</span></span>

<span data-ttu-id="d4c77-165">Дополнительные сведения см. в [руб. Управление индикаторами.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="d4c77-165">For more information, see [Manage indicators](manage-indicators.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d4c77-166">Защита сети использует службы репутации, которые обрабатывает запросы в местах, которые могут быть за пределами выбранного вами расположения для данных Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="d4c77-166">Network protection leverages reputation services that process requests in locations that might be outside of the location you have selected for your Defender for Endpoint data.</span></span>

## <a name="tamper-protection"></a><span data-ttu-id="d4c77-167">Защита от взлома</span><span class="sxs-lookup"><span data-stu-id="d4c77-167">Tamper protection</span></span>
<span data-ttu-id="d4c77-168">Во время некоторых видов кибератак злоумышленники пытаются отключить функции безопасности, такие как антивирусная защита, на компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d4c77-168">During some kinds of cyber attacks, bad actors try to disable security features, such as anti-virus protection, on your machines.</span></span> <span data-ttu-id="d4c77-169">Злоумышленникам нравится отключать функции безопасности, чтобы упростить доступ к данным, установить вредоносные программы или иным образом использовать данные, удостоверения и устройства.</span><span class="sxs-lookup"><span data-stu-id="d4c77-169">Bad actors like to disable your security features to get easier access to your data, to install malware, or to otherwise exploit your data, identity, and devices.</span></span>

<span data-ttu-id="d4c77-170">Защита от взлома по сути блокирует антивирусная программа в Microsoft Defender и предотвращает изменения параметров безопасности с помощью приложений и методов.</span><span class="sxs-lookup"><span data-stu-id="d4c77-170">Tamper protection essentially locks Microsoft Defender Antivirus and prevents your security settings from being changed through apps and methods.</span></span>

<span data-ttu-id="d4c77-171">Эта функция доступна, если в организации используется антивирусная программа в Microsoft Defender и включена облачная защита.</span><span class="sxs-lookup"><span data-stu-id="d4c77-171">This feature is available if your organization uses Microsoft Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="d4c77-172">Дополнительные сведения см. в следующих сведениях: использование технологий следующего поколения [в антивирусная программа в Microsoft Defender с помощью облачной защиты.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d4c77-172">For more information, see [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="d4c77-173">Сохраняйте включенную защиту от взлома, чтобы предотвратить нежелательные изменения в решении безопасности и его основных функций.</span><span class="sxs-lookup"><span data-stu-id="d4c77-173">Keep tamper protection turned on to prevent unwanted changes to your security solution and its essential features.</span></span>


## <a name="show-user-details"></a><span data-ttu-id="d4c77-174">Демонстрация сведений о пользователях</span><span class="sxs-lookup"><span data-stu-id="d4c77-174">Show user details</span></span>

<span data-ttu-id="d4c77-175">Включи эту функцию, чтобы вы могли видеть сведения пользователей, хранимые в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d4c77-175">Turn on this feature so that you can see user details stored in Azure Active Directory.</span></span> <span data-ttu-id="d4c77-176">При расследовании сущностями учетных записей пользователей сведения включают сведения о пользователе, его имени, названии и сведениях о отделах.</span><span class="sxs-lookup"><span data-stu-id="d4c77-176">Details include a user's picture, name, title, and department information  when investigating user account entities.</span></span> <span data-ttu-id="d4c77-177">Сведения о учетной записи пользователей можно найти в следующих представлениях:</span><span class="sxs-lookup"><span data-stu-id="d4c77-177">You can find user account information in the following views:</span></span>

- <span data-ttu-id="d4c77-178">Панель мониторинга операций безопасности</span><span class="sxs-lookup"><span data-stu-id="d4c77-178">Security operations dashboard</span></span>
- <span data-ttu-id="d4c77-179">Очередь оповещений</span><span class="sxs-lookup"><span data-stu-id="d4c77-179">Alert queue</span></span>
- <span data-ttu-id="d4c77-180">Страница сведения об устройстве</span><span class="sxs-lookup"><span data-stu-id="d4c77-180">Device details page</span></span>

<span data-ttu-id="d4c77-181">Дополнительные сведения см. в [дополнительных сведениях о расследовании учетной записи пользователя.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="d4c77-181">For more information, see [Investigate a user account](investigate-user.md).</span></span>


## <a name="skype-for-business-integration"></a><span data-ttu-id="d4c77-182">Skype для бизнеса интеграции</span><span class="sxs-lookup"><span data-stu-id="d4c77-182">Skype for Business integration</span></span>

<span data-ttu-id="d4c77-183">Включение интеграции Skype для бизнеса позволяет общаться с пользователями с помощью Skype для бизнеса, электронной почты или телефона.</span><span class="sxs-lookup"><span data-stu-id="d4c77-183">Enabling the Skype for Business integration gives you the ability to communicate with users using Skype for Business, email, or phone.</span></span> <span data-ttu-id="d4c77-184">Это может быть удобно при общении с пользователем и смягчении рисков.</span><span class="sxs-lookup"><span data-stu-id="d4c77-184">This can be handy when you need to communicate with the user and mitigate risks.</span></span>

> [!NOTE]
> <span data-ttu-id="d4c77-185">Когда устройство изолировано от сети, есть всплывающее всплывающее сообщение, в котором можно включить Outlook и Skype, что позволяет использовать связь с пользователем во время отключения от сети.</span><span class="sxs-lookup"><span data-stu-id="d4c77-185">When a device is being isolated from the network, there's a pop-up where you can choose to enable Outlook and Skype communications which allows communications to the user while they are disconnected from the network.</span></span> <span data-ttu-id="d4c77-186">Этот параметр применяется к Skype и Outlook, когда устройства находятся в изолированном режиме.</span><span class="sxs-lookup"><span data-stu-id="d4c77-186">This setting applies to Skype and Outlook communication when devices are in isolation mode.</span></span>

## <a name="microsoft-defender-for-identity-integration"></a><span data-ttu-id="d4c77-187">Microsoft Defender для интеграции удостоверений</span><span class="sxs-lookup"><span data-stu-id="d4c77-187">Microsoft Defender for Identity integration</span></span>

<span data-ttu-id="d4c77-188">Интеграция с Microsoft Defender для identity позволяет напрямую перейти в другой продукт безопасности Microsoft Identity.</span><span class="sxs-lookup"><span data-stu-id="d4c77-188">The integration with Microsoft Defender for Identity allows you to pivot directly into another Microsoft Identity security product.</span></span> <span data-ttu-id="d4c77-189">Microsoft Defender for Identity дополняет расследование дополнительными сведениями о предполагаемой взломаемой учетной записи и связанных с ней ресурсах.</span><span class="sxs-lookup"><span data-stu-id="d4c77-189">Microsoft Defender for Identity augments an investigation with additional insights about a suspected compromised account and related resources.</span></span> <span data-ttu-id="d4c77-190">Включив эту функцию, вы обогатите возможности исследования на основе устройств, выключив по сети с точки зрения идентификации.</span><span class="sxs-lookup"><span data-stu-id="d4c77-190">By enabling this feature, you'll enrich the device-based investigation capability by pivoting across the network from an identify point of view.</span></span>

> [!NOTE]
> <span data-ttu-id="d4c77-191">Чтобы включить эту функцию, вам потребуется соответствующая лицензия.</span><span class="sxs-lookup"><span data-stu-id="d4c77-191">You'll need to have the appropriate license to enable this feature.</span></span>

## <a name="office-365-threat-intelligence-connection"></a><span data-ttu-id="d4c77-192">Office 365 Подключение к сведениям об угрозах</span><span class="sxs-lookup"><span data-stu-id="d4c77-192">Office 365 Threat Intelligence connection</span></span>

<span data-ttu-id="d4c77-193">Эта функция доступна только при наличии активной Office 365 E5 или надстройки Threat Intelligence.</span><span class="sxs-lookup"><span data-stu-id="d4c77-193">This feature is only available if you have an active Office 365 E5 or the Threat Intelligence add-on.</span></span> <span data-ttu-id="d4c77-194">Дополнительные сведения см. на странице Office 365 корпоративный E5.</span><span class="sxs-lookup"><span data-stu-id="d4c77-194">For more information, see the Office 365 Enterprise E5 product page.</span></span>

<span data-ttu-id="d4c77-195">При включив эту функцию, вы сможете включить данные из Microsoft Defender Office 365 в Microsoft 365 Defender для проведения комплексного расследования безопасности в Office 365 почтовых ящиках и Windows устройствах.</span><span class="sxs-lookup"><span data-stu-id="d4c77-195">When you turn this feature on, you'll be able to incorporate data from Microsoft Defender for Office 365 into Microsoft 365 Defender to conduct a comprehensive security investigation across Office 365 mailboxes and Windows devices.</span></span>

> [!NOTE]
> <span data-ttu-id="d4c77-196">Чтобы включить эту функцию, вам потребуется соответствующая лицензия.</span><span class="sxs-lookup"><span data-stu-id="d4c77-196">You'll need to have the appropriate license to enable this feature.</span></span>

<span data-ttu-id="d4c77-197">Чтобы получить контекстную интеграцию устройств в Office 365 Threat Intelligence, необходимо включить параметры Defender для конечных точек в панели мониторинга & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d4c77-197">To receive contextual device integration in Office 365 Threat Intelligence, you'll need to enable the Defender for Endpoint settings in the Security & Compliance dashboard.</span></span> <span data-ttu-id="d4c77-198">Дополнительные сведения см. в [дополнительных сведениях о расследовании угрозы и ответах.](/microsoft-365/security/office-365-security/office-365-ti)</span><span class="sxs-lookup"><span data-stu-id="d4c77-198">For more information, see [Threat investigation and response](/microsoft-365/security/office-365-security/office-365-ti).</span></span>

## <a name="microsoft-threat-experts---targeted-attack-notifications"></a><span data-ttu-id="d4c77-199">эксперты Майкрософт по угрозам — целевые уведомления об атаках</span><span class="sxs-lookup"><span data-stu-id="d4c77-199">Microsoft Threat Experts - Targeted Attack Notifications</span></span>

<span data-ttu-id="d4c77-200">Из двух компонентов Microsoft Threat Expert целевое уведомление об атаке в общем доступе.</span><span class="sxs-lookup"><span data-stu-id="d4c77-200">Out of the two Microsoft Threat Expert components, targeted attack notification is in general availability.</span></span> <span data-ttu-id="d4c77-201">Возможности экспертов по запросу по-прежнему находятся в предварительном просмотре.</span><span class="sxs-lookup"><span data-stu-id="d4c77-201">Experts-on-demand capability is still in preview.</span></span> <span data-ttu-id="d4c77-202">Вы можете использовать возможности экспертов по запросу только в том случае, если вы подали заявку на предварительное просмотр и ваше приложение было утверждено.</span><span class="sxs-lookup"><span data-stu-id="d4c77-202">You can only use the experts-on-demand capability if you have applied for preview and your application has been approved.</span></span> <span data-ttu-id="d4c77-203">Вы можете получать целевые уведомления об атаке из эксперты Майкрософт по угрозам через панель оповещений портала Защитник для конечных точек и по электронной почте, если ее настроить.</span><span class="sxs-lookup"><span data-stu-id="d4c77-203">You can receive targeted attack notifications from Microsoft Threat Experts through your Defender for Endpoint portal's alerts dashboard and via email if you configure it.</span></span>

> [!NOTE]
> <span data-ttu-id="d4c77-204">Возможность эксперты Майкрософт по угрозам в Defender для конечной точки доступна с лицензией E5 для [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security).</span><span class="sxs-lookup"><span data-stu-id="d4c77-204">The Microsoft Threat Experts capability in Defender for Endpoint is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security).</span></span>
## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="d4c77-205">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d4c77-205">Microsoft Cloud App Security</span></span>

<span data-ttu-id="d4c77-206">Включение этого параметра передает сигналы Defender для конечной точки Microsoft Cloud App Security для обеспечения более глубокой видимости использования облачных приложений.</span><span class="sxs-lookup"><span data-stu-id="d4c77-206">Enabling this setting forwards Defender for Endpoint signals to Microsoft Cloud App Security to provide deeper visibility into cloud application usage.</span></span> <span data-ttu-id="d4c77-207">Переададные данные хранятся и обрабатываются в том же месте, что и Cloud App Security данных.</span><span class="sxs-lookup"><span data-stu-id="d4c77-207">Forwarded data is stored and processed in the same location as your Cloud App Security data.</span></span>

> [!NOTE]
> <span data-ttu-id="d4c77-208">Эта функция будет доступна с лицензией E5 для Enterprise Mobility + Security [на](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) устройствах с Windows 10, версия 1709 (СБОРКА ОС 16299.1085 с [KB4493441),](https://support.microsoft.com/help/4493441)Windows 10, версия 1803 (OS Build 17134.704 с [KB4493464),](https://support.microsoft.com/help/4493464)Windows 10, версия 1809 (OS Build 17763.379 с [KB4489899),](https://support.microsoft.com/help/4489899)или более поздние версии Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d4c77-208">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)), or later Windows 10 versions.</span></span>

## <a name="microsoft-secure-score"></a><span data-ttu-id="d4c77-209">Оценка безопасности (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="d4c77-209">Microsoft Secure Score</span></span>

<span data-ttu-id="d4c77-210">Передает сигналы Microsoft Defender для конечных точек в Microsoft Secure Score в центре Microsoft 365 безопасности.</span><span class="sxs-lookup"><span data-stu-id="d4c77-210">Forwards Microsoft Defender for Endpoint signals to Microsoft Secure Score in the Microsoft 365 security center.</span></span> <span data-ttu-id="d4c77-211">Включение этой функции обеспечивает видимость Microsoft Secure Score в области безопасности устройства.</span><span class="sxs-lookup"><span data-stu-id="d4c77-211">Turning on this feature gives Microsoft Secure Score visibility into the device's security posture.</span></span> <span data-ttu-id="d4c77-212">Переададные данные хранятся и обрабатываются в том же месте, что и данные Microsoft Secure Score.</span><span class="sxs-lookup"><span data-stu-id="d4c77-212">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>


### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a><span data-ttu-id="d4c77-213">Включение интеграции Microsoft Defender для конечной точки с портала Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="d4c77-213">Enable the Microsoft Defender for Endpoint integration from the Microsoft Defender for Identity portal</span></span>

<span data-ttu-id="d4c77-214">Чтобы получить контекстную интеграцию устройств в Microsoft Defender for Identity, необходимо также включить эту функцию на портале Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="d4c77-214">To receive contextual device integration in Microsoft Defender for Identity, you'll also need to enable the feature in the Microsoft Defender for Identity portal.</span></span>

1. <span data-ttu-id="d4c77-215">Войдите на портал [Microsoft Defender for Identity](https://portal.atp.azure.com/) с ролью глобального администратора или администратора безопасности.</span><span class="sxs-lookup"><span data-stu-id="d4c77-215">Log in to the [Microsoft Defender for Identity portal](https://portal.atp.azure.com/) with a Global Administrator or Security Administrator role.</span></span>

2. <span data-ttu-id="d4c77-216">Нажмите **кнопку Создать экземпляр**.</span><span class="sxs-lookup"><span data-stu-id="d4c77-216">Click **Create your instance**.</span></span>

3. <span data-ttu-id="d4c77-217">Настройка интеграции для **параметра On** и нажмите **кнопку Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d4c77-217">Toggle the Integration setting to **On** and click **Save**.</span></span>

<span data-ttu-id="d4c77-218">После завершения этапов интеграции на обоих порталах вы сможете увидеть соответствующие оповещения на странице сведения об устройстве или сведения о пользователе.</span><span class="sxs-lookup"><span data-stu-id="d4c77-218">After completing the integration steps on both portals, you'll be able to see relevant alerts in the device details or user details page.</span></span>

## <a name="web-content-filtering"></a><span data-ttu-id="d4c77-219">Фильтрация веб-содержимого</span><span class="sxs-lookup"><span data-stu-id="d4c77-219">Web content filtering</span></span>
<span data-ttu-id="d4c77-220">Блокировка доступа к веб-сайтам, содержащим нежелательный контент, и отслеживание веб-активности во всех доменах.</span><span class="sxs-lookup"><span data-stu-id="d4c77-220">Block access to websites containing unwanted content and track web activity across all domains.</span></span> <span data-ttu-id="d4c77-221">Чтобы указать категории веб-контента, которые необходимо заблокировать, создайте политику [фильтрации веб-контента.](https://security.microsoft.com/preferences2/web_content_filtering_policy)</span><span class="sxs-lookup"><span data-stu-id="d4c77-221">To specify the web content categories you want to block, create a [web content filtering policy](https://security.microsoft.com/preferences2/web_content_filtering_policy).</span></span> <span data-ttu-id="d4c77-222">Убедитесь, что у вас есть защита сети в режиме блокировки при развертывании базовой базы безопасности [Microsoft Defender для конечной точки.](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2)</span><span class="sxs-lookup"><span data-stu-id="d4c77-222">Ensure you have network protection in block mode when deploying the [Microsoft Defender for Endpoint security baseline](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2).</span></span>


## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a><span data-ttu-id="d4c77-223">Share endpoint alerts with Microsoft Compliance Center</span><span class="sxs-lookup"><span data-stu-id="d4c77-223">Share endpoint alerts with Microsoft Compliance Center</span></span>
<span data-ttu-id="d4c77-224">Перенаправление оповещений о безопасности конечной точки и их состояния в Центр соответствия требованиям Майкрософт, что позволяет повысить внутреннюю политику управления рисками с помощью оповещений и устранять внутренние риски, прежде чем они причинят вред.</span><span class="sxs-lookup"><span data-stu-id="d4c77-224">Forwards endpoint security alerts and their triage status to Microsoft Compliance Center, allowing you to enhance insider risk management policies with alerts and remediate internal risks before they cause harm.</span></span> <span data-ttu-id="d4c77-225">Переададные данные обрабатываются и хранятся в том же месте, что и Office 365 данных.</span><span class="sxs-lookup"><span data-stu-id="d4c77-225">Forwarded data is processed and stored in the same location as your Office 365 data.</span></span>

<span data-ttu-id="d4c77-226">После настройки [](/microsoft-365/compliance/insider-risk-management-settings#indicators) индикаторов нарушений политики безопасности в параметрах управления рисками, оповещения Defender for Endpoint будут совместно использовать для управления рисками для соответствующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="d4c77-226">After configuring the [Security policy violation indicators](/microsoft-365/compliance/insider-risk-management-settings#indicators) in the insider risk management settings, Defender for Endpoint alerts will be shared with insider risk management for applicable users.</span></span>



## <a name="microsoft-intune-connection"></a><span data-ttu-id="d4c77-227">Microsoft Intune подключения</span><span class="sxs-lookup"><span data-stu-id="d4c77-227">Microsoft Intune connection</span></span>

<span data-ttu-id="d4c77-228">Defender for Endpoint можно интегрировать с [Microsoft Intune,](/intune/what-is-intune) чтобы включить условный доступ к устройству на основе [риска.](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)</span><span class="sxs-lookup"><span data-stu-id="d4c77-228">Defender for Endpoint can be integrated with [Microsoft Intune](/intune/what-is-intune) to [enable device risk-based conditional access](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span> <span data-ttu-id="d4c77-229">[Включив эту](configure-conditional-access.md)функцию, вы сможете обмениваться сведениями о устройствах Defender для конечных точек с Помощью Intune, что повышает правоприменение политики.</span><span class="sxs-lookup"><span data-stu-id="d4c77-229">When you [turn on this feature](configure-conditional-access.md), you'll be able to share Defender for Endpoint device information with Intune, enhancing policy enforcement.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4c77-230">Вам потребуется включить интеграцию в Intune и Defender для конечной точки, чтобы использовать эту функцию.</span><span class="sxs-lookup"><span data-stu-id="d4c77-230">You'll need to enable the integration on both Intune and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="d4c77-231">Дополнительные сведения о конкретных действиях см. в дополнительных сведениях [о настройке условного доступа в Defender для конечной точки.](configure-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="d4c77-231">For more information on specific steps, see [Configure Conditional Access in Defender for Endpoint](configure-conditional-access.md).</span></span>

<span data-ttu-id="d4c77-232">Эта функция доступна только в том случае, если у вас есть следующие функции:</span><span class="sxs-lookup"><span data-stu-id="d4c77-232">This feature is only available if you have the following:</span></span>

- <span data-ttu-id="d4c77-233">Лицензированный клиент для Enterprise Mobility + Security E3 и Windows E5 (или Microsoft 365 корпоративный E5)</span><span class="sxs-lookup"><span data-stu-id="d4c77-233">A licensed tenant for Enterprise Mobility + Security E3, and Windows E5 (or Microsoft 365 Enterprise E5)</span></span>
- <span data-ttu-id="d4c77-234">Активная Microsoft Intune, с управляемыми intune Windows 10 [устройствами Azure AD-joined.](/azure/active-directory/devices/concept-azure-ad-join/)</span><span class="sxs-lookup"><span data-stu-id="d4c77-234">An active Microsoft Intune environment, with Intune-managed Windows 10 devices [Azure AD-joined](/azure/active-directory/devices/concept-azure-ad-join/).</span></span>


### <a name="conditional-access-policy"></a><span data-ttu-id="d4c77-235">Политика условного доступа</span><span class="sxs-lookup"><span data-stu-id="d4c77-235">Conditional Access policy</span></span>

<span data-ttu-id="d4c77-236">Если включить интеграцию Intune, Intune автоматически создаст классическую политику условного доступа (CA).</span><span class="sxs-lookup"><span data-stu-id="d4c77-236">When you enable Intune integration, Intune will automatically create a classic Conditional Access (CA) policy.</span></span> <span data-ttu-id="d4c77-237">Эта классическая политика ЦС является обязательным условием для настройки отчетов о состоянии в Intune.</span><span class="sxs-lookup"><span data-stu-id="d4c77-237">This classic CA policy is a prerequisite for setting up status reports to Intune.</span></span> <span data-ttu-id="d4c77-238">Его не следует удалять.</span><span class="sxs-lookup"><span data-stu-id="d4c77-238">It should not be deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="d4c77-239">Классическая политика ЦС, созданная Intune, отличается от современных политик условного [доступа,](/azure/active-directory/conditional-access/overview/)которые используются для настройки конечных точек.</span><span class="sxs-lookup"><span data-stu-id="d4c77-239">The classic CA policy created by Intune is distinct from modern [Conditional Access policies](/azure/active-directory/conditional-access/overview/), which are used for configuring endpoints.</span></span>


## <a name="device-discovery"></a><span data-ttu-id="d4c77-240">Обнаружение устройств</span><span class="sxs-lookup"><span data-stu-id="d4c77-240">Device discovery</span></span>
<span data-ttu-id="d4c77-241">Помогает находить неустановленные устройства, подключенные к корпоративной сети без необходимости дополнительных устройств или громоздких изменений процесса.</span><span class="sxs-lookup"><span data-stu-id="d4c77-241">Helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span> <span data-ttu-id="d4c77-242">С помощью бортовых устройств можно найти неугодные устройства в сети и оценить уязвимости и риски.</span><span class="sxs-lookup"><span data-stu-id="d4c77-242">Using onboarded devices, you can find unmanaged devices in your network and assess vulnerabilities and risks.</span></span> <span data-ttu-id="d4c77-243">Дополнительные сведения см. в [дополнительных сведениях об обнаружении устройства.](device-discovery.md)</span><span class="sxs-lookup"><span data-stu-id="d4c77-243">For more information, see [Device discovery](device-discovery.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d4c77-244">Вы всегда можете применить фильтры, чтобы исключить неугодные устройства из списка инвентаризации устройств.</span><span class="sxs-lookup"><span data-stu-id="d4c77-244">You can always apply filters to exclude unmanaged devices from the device inventory list.</span></span> <span data-ttu-id="d4c77-245">Вы также можете использовать столбец состояния в запросах API для фильтрации неугодных устройств.</span><span class="sxs-lookup"><span data-stu-id="d4c77-245">You can also use the onboarding status column on API queries to filter out unmanaged devices.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="d4c77-246">Функции предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="d4c77-246">Preview features</span></span>

<span data-ttu-id="d4c77-247">Узнайте о новых функциях в выпуске предварительного просмотра Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d4c77-247">Learn about new features in the Defender for Endpoint preview release.</span></span> <span data-ttu-id="d4c77-248">Попробуйте предстоящие функции, включив функции предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="d4c77-248">Try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="d4c77-249">Вы будете иметь доступ к предстоящим функциям, которые можно предоставить отзывы, чтобы помочь улучшить общий опыт, прежде чем функции будут доступны в целом.</span><span class="sxs-lookup"><span data-stu-id="d4c77-249">You'll have access to upcoming features, which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>




## <a name="related-topics"></a><span data-ttu-id="d4c77-250">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d4c77-250">Related topics</span></span>

- [<span data-ttu-id="d4c77-251">Обновление параметров хранения данных</span><span class="sxs-lookup"><span data-stu-id="d4c77-251">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="d4c77-252">Настройка уведомлений оповещений</span><span class="sxs-lookup"><span data-stu-id="d4c77-252">Configure alert notifications</span></span>](configure-email-notifications.md)
