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
ms.openlocfilehash: 103f5d0ad9d12a37f3a3b8065f39c24d592cc252
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995061"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="418c8-104">Создание индикаторов для файлов</span><span class="sxs-lookup"><span data-stu-id="418c8-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="418c8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="418c8-105">**Applies to:**</span></span>
- [<span data-ttu-id="418c8-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="418c8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="418c8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="418c8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="418c8-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="418c8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="418c8-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="418c8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="418c8-110">Предотвращение дальнейшего распространения атаки в организации, запретив потенциально вредоносные файлы или подозрительные вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="418c8-110">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="418c8-111">Если вы знаете потенциально вредоносный переносной файл(PE), его можно заблокировать.</span><span class="sxs-lookup"><span data-stu-id="418c8-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="418c8-112">Эта операция предотвратит чтение, написание или выполнение на устройствах в организации.</span><span class="sxs-lookup"><span data-stu-id="418c8-112">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="418c8-113">Существует три способа создания индикаторов для файлов:</span><span class="sxs-lookup"><span data-stu-id="418c8-113">There are three ways you can create indicators for files:</span></span>

- <span data-ttu-id="418c8-114">Создание индикатора на странице параметры</span><span class="sxs-lookup"><span data-stu-id="418c8-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="418c8-115">Создание контекстного индикатора с помощью кнопки добавить индикатор со страницы сведений о файле</span><span class="sxs-lookup"><span data-stu-id="418c8-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>
- <span data-ttu-id="418c8-116">Создание индикатора с помощью [API индикатора](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="418c8-116">By creating an indicator through the [Indicator API](ti-indicator.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="418c8-117">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="418c8-117">Before you begin</span></span>

<span data-ttu-id="418c8-118">Важно понимать следующие предпосылки перед созданием индикаторов для файлов:</span><span class="sxs-lookup"><span data-stu-id="418c8-118">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="418c8-119">Эта функция доступна, если в организации используется **антивирус Microsoft Defender (в** активном режиме) и включена **облачная защита.**</span><span class="sxs-lookup"><span data-stu-id="418c8-119">This feature is available if your organization uses **Microsoft Defender Antivirus (in active mode)** and **Cloud-based protection is enabled**.</span></span> <span data-ttu-id="418c8-120">Дополнительные сведения см. в [сведениях Управление облачной защитой.](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="418c8-120">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>

- <span data-ttu-id="418c8-121">Клиентская версия antimalware должна быть 4.18.1901.x или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="418c8-121">The Antimalware client version must be 4.18.1901.x or later.</span></span> <span data-ttu-id="418c8-122">См. [ежемесячные версии платформы и двигателя](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span><span class="sxs-lookup"><span data-stu-id="418c8-122">See [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span></span>

- <span data-ttu-id="418c8-123">Поддерживается на устройствах с Windows 10, версии 1703 или более поздней версии, Windows Server 2016 и 2019.</span><span class="sxs-lookup"><span data-stu-id="418c8-123">Supported on devices with Windows 10, version 1703 or later, Windows Server 2016 and 2019.</span></span>

- <span data-ttu-id="418c8-124">Чтобы начать блокировать файлы, сначала необходимо включить функцию "заблокировать или [разрешить"](advanced-features.md) в параметрах.</span><span class="sxs-lookup"><span data-stu-id="418c8-124">To start blocking files, you first need to [turn on the "block or allow" feature](advanced-features.md) in Settings.</span></span>

<span data-ttu-id="418c8-125">Эта функция предназначена для предотвращения скачивания из Интернета подозрительных вредоносных программ (или потенциально вредоносных файлов).</span><span class="sxs-lookup"><span data-stu-id="418c8-125">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="418c8-126">В настоящее время он поддерживает переносные исполняемые (PE) файлы, включая файлы .exe и .dll.</span><span class="sxs-lookup"><span data-stu-id="418c8-126">It currently supports portable executable (PE) files, including .exe and .dll files.</span></span> <span data-ttu-id="418c8-127">Со временем охват будет расширен.</span><span class="sxs-lookup"><span data-stu-id="418c8-127">The coverage will be extended over time.</span></span>

## <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="418c8-128">Создание индикатора для файлов со страницы параметры</span><span class="sxs-lookup"><span data-stu-id="418c8-128">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="418c8-129">В области навигации выберите **Параметры > Индикаторы**.</span><span class="sxs-lookup"><span data-stu-id="418c8-129">In the navigation pane, select **Settings > Indicators**.</span></span>

2. <span data-ttu-id="418c8-130">Выберите **вкладку "Hash**   File".</span><span class="sxs-lookup"><span data-stu-id="418c8-130">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="418c8-131">Выберите **индикатор Добавить**.</span><span class="sxs-lookup"><span data-stu-id="418c8-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="418c8-132">Укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="418c8-132">Specify the following details:</span></span>
    - <span data-ttu-id="418c8-133">Индикатор . Укажите сведения об объекте и определите срок действия индикатора.</span><span class="sxs-lookup"><span data-stu-id="418c8-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
    - <span data-ttu-id="418c8-134">Действие . Укажите действия, которые необходимо принять, и укажите описание.</span><span class="sxs-lookup"><span data-stu-id="418c8-134">Action - Specify the action to be taken and provide a description.</span></span>
    - <span data-ttu-id="418c8-135">Область — определите область действия группы устройств.</span><span class="sxs-lookup"><span data-stu-id="418c8-135">Scope - Define the scope of the device group.</span></span>

5. <span data-ttu-id="418c8-136">Просмотрите сведения в вкладке Сводка, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="418c8-136">Review the details in the Summary tab, then select **Save**.</span></span>

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="418c8-137">Создание контекстного индикатора на странице сведения о файле</span><span class="sxs-lookup"><span data-stu-id="418c8-137">Create a contextual indicator from the file details page</span></span>

<span data-ttu-id="418c8-138">Одним из вариантов при принятии ответных [действий в файле](respond-file-alerts.md)является добавление   индикатора для файла.</span><span class="sxs-lookup"><span data-stu-id="418c8-138">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> <span data-ttu-id="418c8-139">При добавлении hash индикатора для файла можно поднять оповещение и заблокировать файл всякий раз, когда устройство в организации пытается запустить его.</span><span class="sxs-lookup"><span data-stu-id="418c8-139">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="418c8-140">Файлы, автоматически заблокированные индикатором, не будут показываться в центре действий файла, но оповещения по-прежнему будут видны в очереди Оповещения.</span><span class="sxs-lookup"><span data-stu-id="418c8-140">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="418c8-141">Обычно блоки файлов применяются и удаляются в течение нескольких минут, но могут занять более 30 минут.</span><span class="sxs-lookup"><span data-stu-id="418c8-141">Typically, file blocks are enforced and removed within a couple of minutes, but can take upwards of 30 minutes.</span></span>
>- <span data-ttu-id="418c8-142">Если существуют противоречивые политики индикатора файлов, применяется политика обеспечения безопасности более безопасной политики.</span><span class="sxs-lookup"><span data-stu-id="418c8-142">If there are conflicting file indicator policies, the enforcement policy of the more secure policy is applied.</span></span> <span data-ttu-id="418c8-143">Например, политика индикатора hash-индикатора файлов SHA-256 имеет приоритет над политикой индикатора hash файла MD5, если оба типа hash определяют один и тот же файл.</span><span class="sxs-lookup"><span data-stu-id="418c8-143">For example, a SHA-256 file hash indicator policy takes precedence over an MD5 file hash indicator policy if both hash types define the same file.</span></span>
>- <span data-ttu-id="418c8-144">Если политика группы EnableFileHashComputation отключена, точность блокировки IoC файла снижается.</span><span class="sxs-lookup"><span data-stu-id="418c8-144">If EnableFileHashComputation group policy is disabled, the blocking accuracy of the file IoC is reduced.</span></span> <span data-ttu-id="418c8-145">Однако включение EnableFileHashComputation может повлиять на производительность устройства.</span><span class="sxs-lookup"><span data-stu-id="418c8-145">However, enabling EnableFileHashComputation may impact device performance.</span></span>
>    - <span data-ttu-id="418c8-146">Например, копирование больших файлов из сетевой доли на локальное устройство, особенно через VPN-подключение, может иметь влияние на производительность устройства.</span><span class="sxs-lookup"><span data-stu-id="418c8-146">For example, copying large files from a network share onto your local device, especially over a VPN connection, may have an effect on device performance.</span></span>
>    - <span data-ttu-id="418c8-147">Дополнительные сведения о групповой политике EnableFileHashComputation см. в группе [Defender CSP](/windows/client-management/mdm/defender-csp)</span><span class="sxs-lookup"><span data-stu-id="418c8-147">For more information about the EnableFileHashComputation group policy, see [Defender CSP](/windows/client-management/mdm/defender-csp)</span></span>

## <a name="policy-conflict-handling"></a><span data-ttu-id="418c8-148">Обработка конфликтов политик</span><span class="sxs-lookup"><span data-stu-id="418c8-148">Policy conflict handling</span></span>  

<span data-ttu-id="418c8-149">Конфликт обработки политики Cert и File IoC будет выполняться следующим образом:</span><span class="sxs-lookup"><span data-stu-id="418c8-149">Cert and File IoC policy handling conflict will follow the below order:</span></span>

- <span data-ttu-id="418c8-150">Если файл не разрешен управлением приложениями и Защитник Windows AppLocker, применяет политику режима/политики, **блок**</span><span class="sxs-lookup"><span data-stu-id="418c8-150">If the file is not allowed by Windows Defender Application Control and AppLocker enforce mode policy/policies, then **Block**</span></span>

- <span data-ttu-id="418c8-151">Кроме того, если файл разрешен антивирусным исключением Defender, </span><span class="sxs-lookup"><span data-stu-id="418c8-151">Else if the file is allowed by the Defender Anti-Virus Exclusion, then **Allow**</span></span>

- <span data-ttu-id="418c8-152">Кроме того, если файл блокируется или предупреждается блоком или предупреждает IoC файла, затем **Block/Warn**</span><span class="sxs-lookup"><span data-stu-id="418c8-152">Else if the file is blocked or warned by a block or warn file IoC, then **Block/Warn**</span></span>

- <span data-ttu-id="418c8-153">Кроме того, если файл разрешен политикой МОК разрешить файл, </span><span class="sxs-lookup"><span data-stu-id="418c8-153">Else if the file is allowed by an allow file IOC policy, then **Allow**</span></span>

- <span data-ttu-id="418c8-154">Кроме того, если файл заблокирован по правилам ASR, CFA, AV, SmartScreen, затем **блок**</span><span class="sxs-lookup"><span data-stu-id="418c8-154">Else if the file is blocked by ASR rules, CFA, AV, SmartScreen, then **Block**</span></span>  

- <span data-ttu-id="418c8-155">Else **Allow** (Защитник Windows политики управления приложениями & AppLocker, к ней не применяются правила IoC)</span><span class="sxs-lookup"><span data-stu-id="418c8-155">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span></span>

<span data-ttu-id="418c8-156">Если существуют конфликтующие политики IoC-файлов с одинаковым типом и целевой целью, будет применена политика более безопасного (то есть более длительного) hash.</span><span class="sxs-lookup"><span data-stu-id="418c8-156">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure (meaning longer) hash will be applied.</span></span> <span data-ttu-id="418c8-157">Например, политика IoC-файла SHA-256 выигрывает политику IoC-хаша файла MD5, если оба типа hash определяют один и тот же файл.</span><span class="sxs-lookup"><span data-stu-id="418c8-157">For example, a SHA-256 file hash IoC policy will win over a MD5 file hash IoC policy if both hash types define the same file.</span></span>

<span data-ttu-id="418c8-158">Обратите внимание, что заблокированные функции управления уязвимыми приложениями управления угрозами и уязвимостей используют IoCs-файлы для обеспечения соблюдения и будут следовать вышеуказанному порядку обработки конфликтов.</span><span class="sxs-lookup"><span data-stu-id="418c8-158">Note that threat and vulnerability management's block vulnerable application features uses the file IoCs for enforcement and will follow the above conflict handling order.</span></span>

### <a name="examples"></a><span data-ttu-id="418c8-159">Примеры</span><span class="sxs-lookup"><span data-stu-id="418c8-159">Examples</span></span>

|<span data-ttu-id="418c8-160">Компонент</span><span class="sxs-lookup"><span data-stu-id="418c8-160">Component</span></span> |<span data-ttu-id="418c8-161">Правоприменители компонентов</span><span class="sxs-lookup"><span data-stu-id="418c8-161">Component enforcement</span></span> |<span data-ttu-id="418c8-162">Действие индикатора файла</span><span class="sxs-lookup"><span data-stu-id="418c8-162">File indicator Action</span></span> |<span data-ttu-id="418c8-163">Результат</span><span class="sxs-lookup"><span data-stu-id="418c8-163">Result</span></span>
|--|--|--|--|
|<span data-ttu-id="418c8-164">Исключение пути уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="418c8-164">Attack surface reduction file path exclusion</span></span> |<span data-ttu-id="418c8-165">Разрешить</span><span class="sxs-lookup"><span data-stu-id="418c8-165">Allow</span></span> |<span data-ttu-id="418c8-166">Блокировка</span><span class="sxs-lookup"><span data-stu-id="418c8-166">Block</span></span> |<span data-ttu-id="418c8-167">Блокировка</span><span class="sxs-lookup"><span data-stu-id="418c8-167">Block</span></span>
|<span data-ttu-id="418c8-168">Правило уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="418c8-168">Attack surface reduction rule</span></span> |<span data-ttu-id="418c8-169">Блокировка</span><span class="sxs-lookup"><span data-stu-id="418c8-169">Block</span></span> |<span data-ttu-id="418c8-170">Разрешить</span><span class="sxs-lookup"><span data-stu-id="418c8-170">Allow</span></span> |<span data-ttu-id="418c8-171">Разрешить</span><span class="sxs-lookup"><span data-stu-id="418c8-171">Allow</span></span>
|<span data-ttu-id="418c8-172">Управление приложениями в Защитнике Windows</span><span class="sxs-lookup"><span data-stu-id="418c8-172">Windows Defender Application Control</span></span> |<span data-ttu-id="418c8-173">Разрешить</span><span class="sxs-lookup"><span data-stu-id="418c8-173">Allow</span></span> |<span data-ttu-id="418c8-174">Блокировка</span><span class="sxs-lookup"><span data-stu-id="418c8-174">Block</span></span> |<span data-ttu-id="418c8-175">Разрешить</span><span class="sxs-lookup"><span data-stu-id="418c8-175">Allow</span></span> |
|<span data-ttu-id="418c8-176">Управление приложениями в Защитнике Windows</span><span class="sxs-lookup"><span data-stu-id="418c8-176">Windows Defender Application Control</span></span> |<span data-ttu-id="418c8-177">Блокировка</span><span class="sxs-lookup"><span data-stu-id="418c8-177">Block</span></span> |<span data-ttu-id="418c8-178">Разрешить</span><span class="sxs-lookup"><span data-stu-id="418c8-178">Allow</span></span> |<span data-ttu-id="418c8-179">Блокировка</span><span class="sxs-lookup"><span data-stu-id="418c8-179">Block</span></span>
|<span data-ttu-id="418c8-180">Исключение антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="418c8-180">Microsoft Defender Antivirus exclusion</span></span> |<span data-ttu-id="418c8-181">Разрешить</span><span class="sxs-lookup"><span data-stu-id="418c8-181">Allow</span></span> |<span data-ttu-id="418c8-182">Блокировка</span><span class="sxs-lookup"><span data-stu-id="418c8-182">Block</span></span> |<span data-ttu-id="418c8-183">Разрешить</span><span class="sxs-lookup"><span data-stu-id="418c8-183">Allow</span></span>

## <a name="see-also"></a><span data-ttu-id="418c8-184">См. также</span><span class="sxs-lookup"><span data-stu-id="418c8-184">See also</span></span>

- [<span data-ttu-id="418c8-185">Создание индикаторов</span><span class="sxs-lookup"><span data-stu-id="418c8-185">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="418c8-186">Создание индикаторов для протоколов IP и URL-адресов или доменов</span><span class="sxs-lookup"><span data-stu-id="418c8-186">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="418c8-187">Создание индикаторов на основе сертификатов</span><span class="sxs-lookup"><span data-stu-id="418c8-187">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="418c8-188">Управление индикаторами</span><span class="sxs-lookup"><span data-stu-id="418c8-188">Manage indicators</span></span>](indicator-manage.md)
