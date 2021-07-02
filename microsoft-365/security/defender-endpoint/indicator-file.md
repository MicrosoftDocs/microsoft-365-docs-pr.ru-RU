---
title: Создание индикаторов для файлов
ms.reviewer: ''
description: Создание индикаторов для файла, определяющих обнаружение, предотвращение и исключение сущностями.
keywords: файл, hash, manage, allowed, blocked, block, clean, malicious, file hash, ip address, URL-адрес, домен
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
ms.openlocfilehash: b56a18e1b35b65629318ab29f2189ef1f73373f5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256919"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="90935-104">Создание индикаторов для файлов</span><span class="sxs-lookup"><span data-stu-id="90935-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="90935-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="90935-105">**Applies to:**</span></span>
- [<span data-ttu-id="90935-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="90935-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="90935-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90935-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="90935-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="90935-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="90935-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="90935-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="90935-110">Предотвращение дальнейшего распространения атаки в организации, запретив потенциально вредоносные файлы или подозрительные вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="90935-110">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="90935-111">Если вы знаете потенциально вредоносный переносной файл(PE), его можно заблокировать.</span><span class="sxs-lookup"><span data-stu-id="90935-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="90935-112">Эта операция предотвратит чтение, написание или выполнение на устройствах в организации.</span><span class="sxs-lookup"><span data-stu-id="90935-112">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="90935-113">Существует три способа создания индикаторов для файлов:</span><span class="sxs-lookup"><span data-stu-id="90935-113">There are three ways you can create indicators for files:</span></span>

- <span data-ttu-id="90935-114">Создание индикатора на странице параметры</span><span class="sxs-lookup"><span data-stu-id="90935-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="90935-115">Создание контекстного индикатора с помощью кнопки добавить индикатор со страницы сведений о файле</span><span class="sxs-lookup"><span data-stu-id="90935-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>
- <span data-ttu-id="90935-116">Создание индикатора с помощью [API индикатора](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="90935-116">By creating an indicator through the [Indicator API](ti-indicator.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="90935-117">Подготовка</span><span class="sxs-lookup"><span data-stu-id="90935-117">Before you begin</span></span>

<span data-ttu-id="90935-118">Важно понимать следующие предпосылки перед созданием индикаторов для файлов:</span><span class="sxs-lookup"><span data-stu-id="90935-118">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="90935-119">Эта функция доступна, если в организации **антивирусная программа в Microsoft Defender (в** активном режиме) и включена **облачная защита.**</span><span class="sxs-lookup"><span data-stu-id="90935-119">This feature is available if your organization uses **Microsoft Defender Antivirus (in active mode)** and **Cloud-based protection is enabled**.</span></span> <span data-ttu-id="90935-120">Дополнительные сведения см. в [сведениях Управление облачной защитой.](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="90935-120">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>

- <span data-ttu-id="90935-121">Клиентская версия antimalware должна быть 4.18.1901.x или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="90935-121">The Antimalware client version must be 4.18.1901.x or later.</span></span> <span data-ttu-id="90935-122">См. [ежемесячные версии платформы и двигателя](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span><span class="sxs-lookup"><span data-stu-id="90935-122">See [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span></span>

- <span data-ttu-id="90935-123">Поддерживается на устройствах Windows 10 версии 1703 или более поздней версии Windows Server 2016 и 2019.</span><span class="sxs-lookup"><span data-stu-id="90935-123">Supported on devices with Windows 10, version 1703 or later, Windows Server 2016 and 2019.</span></span>

- <span data-ttu-id="90935-124">Чтобы начать блокировать файлы, сначала необходимо включить функцию "заблокировать или [разрешить"](advanced-features.md) в Параметры.</span><span class="sxs-lookup"><span data-stu-id="90935-124">To start blocking files, you first need to [turn on the "block or allow" feature](advanced-features.md) in Settings.</span></span>

<span data-ttu-id="90935-125">Эта функция предназначена для предотвращения скачивания из Интернета подозрительных вредоносных программ (или потенциально вредоносных файлов).</span><span class="sxs-lookup"><span data-stu-id="90935-125">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="90935-126">В настоящее время он поддерживает переносные исполняемые (PE) файлы, включая .exe и .dll файлы.</span><span class="sxs-lookup"><span data-stu-id="90935-126">It currently supports portable executable (PE) files, including .exe and .dll files.</span></span> <span data-ttu-id="90935-127">Со временем охват будет расширен.</span><span class="sxs-lookup"><span data-stu-id="90935-127">The coverage will be extended over time.</span></span>

## <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="90935-128">Создание индикатора для файлов со страницы параметры</span><span class="sxs-lookup"><span data-stu-id="90935-128">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="90935-129">В области навигации выберите **Параметры > Индикаторы**.</span><span class="sxs-lookup"><span data-stu-id="90935-129">In the navigation pane, select **Settings > Indicators**.</span></span>

2. <span data-ttu-id="90935-130">Выберите **вкладку "Hash**   File".</span><span class="sxs-lookup"><span data-stu-id="90935-130">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="90935-131">Выберите **индикатор Добавить**.</span><span class="sxs-lookup"><span data-stu-id="90935-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="90935-132">Укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="90935-132">Specify the following details:</span></span>
    - <span data-ttu-id="90935-133">Индикатор . Укажите сведения об объекте и определите срок действия индикатора.</span><span class="sxs-lookup"><span data-stu-id="90935-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
    - <span data-ttu-id="90935-134">Действие . Укажите действия, которые необходимо принять, и укажите описание.</span><span class="sxs-lookup"><span data-stu-id="90935-134">Action - Specify the action to be taken and provide a description.</span></span>
    - <span data-ttu-id="90935-135">Область — определите область действия группы устройств.</span><span class="sxs-lookup"><span data-stu-id="90935-135">Scope - Define the scope of the device group.</span></span>

5. <span data-ttu-id="90935-136">Просмотрите сведения в вкладке Сводка, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="90935-136">Review the details in the Summary tab, then select **Save**.</span></span>

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="90935-137">Создание контекстного индикатора на странице сведения о файле</span><span class="sxs-lookup"><span data-stu-id="90935-137">Create a contextual indicator from the file details page</span></span>

<span data-ttu-id="90935-138">Одним из вариантов при принятии ответных [действий в файле](respond-file-alerts.md)является добавление   индикатора для файла.</span><span class="sxs-lookup"><span data-stu-id="90935-138">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> <span data-ttu-id="90935-139">При добавлении hash индикатора для файла можно поднять оповещение и заблокировать файл всякий раз, когда устройство в организации пытается запустить его.</span><span class="sxs-lookup"><span data-stu-id="90935-139">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="90935-140">Файлы, автоматически заблокированные индикатором, не будут показываться в центре действий файла, но оповещения по-прежнему будут видны в очереди Оповещения.</span><span class="sxs-lookup"><span data-stu-id="90935-140">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="90935-141">Обычно блоки файлов применяются и удаляются в течение нескольких минут, но могут занять более 30 минут.</span><span class="sxs-lookup"><span data-stu-id="90935-141">Typically, file blocks are enforced and removed within a couple of minutes, but can take upwards of 30 minutes.</span></span>
> 
>- <span data-ttu-id="90935-142">Если существуют противоречивые политики IoC-файлов с одним типом и целевой целью, будет применена политика более безопасного хаши.</span><span class="sxs-lookup"><span data-stu-id="90935-142">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure hash will be applied.</span></span> <span data-ttu-id="90935-143">Политика IoC-файла SHA-256 выигрывает политику IoC-хаша файла SHA-1, которая будет выигрывать политику IoC-хаша файла MD5, если типы hash определяют один и тот же файл.</span><span class="sxs-lookup"><span data-stu-id="90935-143">An SHA-256 file hash IoC policy will win over an SHA-1 file hash IoC policy, which will win over an MD5 file hash IoC policy if the hash types define the same file.</span></span> <span data-ttu-id="90935-144">Это всегда верно независимо от группы устройств.</span><span class="sxs-lookup"><span data-stu-id="90935-144">This is always true regardless of the device group.</span></span> 
>   <span data-ttu-id="90935-145">Во всех остальных случаях, если на всех устройствах и группе устройства применяются конфликтующие политики IoC-файлов с одной и той же целью, то для устройства политика в группе устройств выигрывает.</span><span class="sxs-lookup"><span data-stu-id="90935-145">In all other cases, if conflicting file IoC policies with the same enforcement target are applied to all devices and to the device’s group, then for a device, the policy in the device group will win.</span></span> 
>   
>- <span data-ttu-id="90935-146">Если политика группы EnableFileHashComputation отключена, точность блокировки IoC файла снижается.</span><span class="sxs-lookup"><span data-stu-id="90935-146">If the EnableFileHashComputation group policy is disabled, the blocking accuracy of the file IoC is reduced.</span></span> <span data-ttu-id="90935-147">Однако включение может `EnableFileHashComputation` повлиять на производительность устройства.</span><span class="sxs-lookup"><span data-stu-id="90935-147">However, enabling `EnableFileHashComputation` may impact device performance.</span></span> <span data-ttu-id="90935-148">Например, копирование больших файлов из сетевой доли на локальное устройство, особенно через VPN-подключение, может сказаться на производительности устройства.</span><span class="sxs-lookup"><span data-stu-id="90935-148">For example, copying large files from a network share onto your local device, especially over a VPN connection, might have an effect on device performance.</span></span>
>
>   <span data-ttu-id="90935-149">Дополнительные сведения о групповой политике EnableFileHashComputation см. в группе [Defender CSP](/windows/client-management/mdm/defender-csp)</span><span class="sxs-lookup"><span data-stu-id="90935-149">For more information about the EnableFileHashComputation group policy, see [Defender CSP](/windows/client-management/mdm/defender-csp)</span></span>

## <a name="policy-conflict-handling"></a><span data-ttu-id="90935-150">Обработка конфликтов политик</span><span class="sxs-lookup"><span data-stu-id="90935-150">Policy conflict handling</span></span>  

<span data-ttu-id="90935-151">Конфликт обработки политики Cert и File IoC будет выполняться следующим образом:</span><span class="sxs-lookup"><span data-stu-id="90935-151">Cert and File IoC policy handling conflict will follow the below order:</span></span>

- <span data-ttu-id="90935-152">Если файл не разрешен управлением Защитник Windows приложениями и политиками режима AppLocker, блок </span><span class="sxs-lookup"><span data-stu-id="90935-152">If the file is not allowed by Windows Defender Application Control and AppLocker enforce mode policy/policies, then **Block**</span></span>

- <span data-ttu-id="90935-153">Кроме того, если файл разрешен исключением антивирусная программа в Microsoft Defender, </span><span class="sxs-lookup"><span data-stu-id="90935-153">Else if the file is allowed by the Microsoft Defender Antivirus exclusion, then **Allow**</span></span>

- <span data-ttu-id="90935-154">Кроме того, если файл блокируется или предупреждается блоком или предупреждает IoC файла, затем **Block/Warn**</span><span class="sxs-lookup"><span data-stu-id="90935-154">Else if the file is blocked or warned by a block or warn file IoC, then **Block/Warn**</span></span>

- <span data-ttu-id="90935-155">Кроме того, если файл разрешен политикой IoC допустимого файла, </span><span class="sxs-lookup"><span data-stu-id="90935-155">Else if the file is allowed by an allow file IoC policy, then **Allow**</span></span>

- <span data-ttu-id="90935-156">Кроме того, если файл заблокирован по правилам ASR, CFA, AV, SmartScreen, затем **блок**</span><span class="sxs-lookup"><span data-stu-id="90935-156">Else if the file is blocked by ASR rules, CFA, AV, SmartScreen, then **Block**</span></span>  

- <span data-ttu-id="90935-157">Else **Allow** (передает Защитник Windows политики & AppLocker, к ней не применяются правила IoC)</span><span class="sxs-lookup"><span data-stu-id="90935-157">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span></span>

<span data-ttu-id="90935-158">Если существуют конфликтующие политики IoC-файлов с одинаковым типом и целевой целью, будет применена политика более безопасного (то есть более длительного) hash.</span><span class="sxs-lookup"><span data-stu-id="90935-158">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure (meaning longer) hash will be applied.</span></span> <span data-ttu-id="90935-159">Например, политика IoC-файла SHA-256 получит контроль над политикой IoC-хаша файла MD5, если оба типа hash определяют один и тот же файл.</span><span class="sxs-lookup"><span data-stu-id="90935-159">For example, an SHA-256 file hash IoC policy will win over an MD5 file hash IoC policy if both hash types define the same file.</span></span>

<span data-ttu-id="90935-160">Функции управление уязвимостями и управление уязвимостями приложения используют IoCs-файл для обеспечения соблюдения и будут следовать вышеуказанному порядку обработки конфликтов.</span><span class="sxs-lookup"><span data-stu-id="90935-160">Threat and vulnerability management's block vulnerable application features uses the file IoCs for enforcement and will follow the above conflict handling order.</span></span>

### <a name="examples"></a><span data-ttu-id="90935-161">Примеры</span><span class="sxs-lookup"><span data-stu-id="90935-161">Examples</span></span>

|<span data-ttu-id="90935-162">Компонент</span><span class="sxs-lookup"><span data-stu-id="90935-162">Component</span></span> |<span data-ttu-id="90935-163">Правоприменители компонентов</span><span class="sxs-lookup"><span data-stu-id="90935-163">Component enforcement</span></span> |<span data-ttu-id="90935-164">Действие индикатора файла</span><span class="sxs-lookup"><span data-stu-id="90935-164">File indicator Action</span></span> |<span data-ttu-id="90935-165">Результат</span><span class="sxs-lookup"><span data-stu-id="90935-165">Result</span></span>
|--|--|--|--|
|<span data-ttu-id="90935-166">Исключение пути уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="90935-166">Attack surface reduction file path exclusion</span></span> |<span data-ttu-id="90935-167">Разрешить</span><span class="sxs-lookup"><span data-stu-id="90935-167">Allow</span></span> |<span data-ttu-id="90935-168">Блокировка</span><span class="sxs-lookup"><span data-stu-id="90935-168">Block</span></span> |<span data-ttu-id="90935-169">Блокировка</span><span class="sxs-lookup"><span data-stu-id="90935-169">Block</span></span>
|<span data-ttu-id="90935-170">Правило уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="90935-170">Attack surface reduction rule</span></span> |<span data-ttu-id="90935-171">Блокировка</span><span class="sxs-lookup"><span data-stu-id="90935-171">Block</span></span> |<span data-ttu-id="90935-172">Разрешить</span><span class="sxs-lookup"><span data-stu-id="90935-172">Allow</span></span> |<span data-ttu-id="90935-173">Разрешить</span><span class="sxs-lookup"><span data-stu-id="90935-173">Allow</span></span>
|<span data-ttu-id="90935-174">Управление приложениями в Защитнике Windows</span><span class="sxs-lookup"><span data-stu-id="90935-174">Windows Defender Application Control</span></span> |<span data-ttu-id="90935-175">Разрешить</span><span class="sxs-lookup"><span data-stu-id="90935-175">Allow</span></span> |<span data-ttu-id="90935-176">Блокировка</span><span class="sxs-lookup"><span data-stu-id="90935-176">Block</span></span> |<span data-ttu-id="90935-177">Разрешить</span><span class="sxs-lookup"><span data-stu-id="90935-177">Allow</span></span> |
|<span data-ttu-id="90935-178">Управление приложениями в Защитнике Windows</span><span class="sxs-lookup"><span data-stu-id="90935-178">Windows Defender Application Control</span></span> |<span data-ttu-id="90935-179">Блокировка</span><span class="sxs-lookup"><span data-stu-id="90935-179">Block</span></span> |<span data-ttu-id="90935-180">Разрешить</span><span class="sxs-lookup"><span data-stu-id="90935-180">Allow</span></span> |<span data-ttu-id="90935-181">Блокировка</span><span class="sxs-lookup"><span data-stu-id="90935-181">Block</span></span>
|<span data-ttu-id="90935-182">антивирусная программа в Microsoft Defender исключения</span><span class="sxs-lookup"><span data-stu-id="90935-182">Microsoft Defender Antivirus exclusion</span></span> |<span data-ttu-id="90935-183">Разрешить</span><span class="sxs-lookup"><span data-stu-id="90935-183">Allow</span></span> |<span data-ttu-id="90935-184">Блокировка</span><span class="sxs-lookup"><span data-stu-id="90935-184">Block</span></span> |<span data-ttu-id="90935-185">Разрешить</span><span class="sxs-lookup"><span data-stu-id="90935-185">Allow</span></span>

## <a name="see-also"></a><span data-ttu-id="90935-186">См. также</span><span class="sxs-lookup"><span data-stu-id="90935-186">See also</span></span>

- [<span data-ttu-id="90935-187">Создание индикаторов</span><span class="sxs-lookup"><span data-stu-id="90935-187">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="90935-188">Создание индикаторов для протоколов IP и URL-адресов или доменов</span><span class="sxs-lookup"><span data-stu-id="90935-188">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="90935-189">Создание индикаторов на основе сертификатов</span><span class="sxs-lookup"><span data-stu-id="90935-189">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="90935-190">Управление индикаторами</span><span class="sxs-lookup"><span data-stu-id="90935-190">Manage indicators</span></span>](indicator-manage.md)
