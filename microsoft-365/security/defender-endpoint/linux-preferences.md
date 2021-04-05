---
title: Настройка предпочтений для ATP Защитника Майкрософт для Linux
ms.reviewer: ''
description: Описывает настройку ATP Microsoft Defender для Linux на предприятиях.
keywords: Microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5aedf841ddfc5a592fe4afd2f13d6470e24c438c
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587519"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="3301d-104">Настройка предпочтений для Microsoft Defender для конечной точки для Linux</span><span class="sxs-lookup"><span data-stu-id="3301d-104">Set preferences for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3301d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3301d-105">**Applies to:**</span></span>
- [<span data-ttu-id="3301d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3301d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3301d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3301d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3301d-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="3301d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3301d-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="3301d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="3301d-110">В этом разделе содержатся инструкции по набору предпочтений для Defender для конечной точки для Linux в корпоративных средах.</span><span class="sxs-lookup"><span data-stu-id="3301d-110">This topic contains instructions for how to set preferences for Defender for Endpoint for Linux in enterprise environments.</span></span> <span data-ttu-id="3301d-111">Если вы заинтересованы в настройке продукта на устройстве из командной строки, см. [в этой строке Ресурсы.](linux-resources.md#configure-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="3301d-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="3301d-112">В корпоративных средах управление защитником конечной точки для Linux можно с помощью профиля конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3301d-112">In enterprise environments, Defender for Endpoint for Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="3301d-113">Этот профиль развернут из средства управления по вашему выбору.</span><span class="sxs-lookup"><span data-stu-id="3301d-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="3301d-114">Предпочтения, управляемые предприятием, имеют приоритет над предпочтениями, установленными локально на устройстве.</span><span class="sxs-lookup"><span data-stu-id="3301d-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="3301d-115">Другими словами, пользователи в вашем предприятии не могут изменять предпочтения, задав этот профиль конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3301d-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="3301d-116">В этой статье описывается структура этого профиля (включая рекомендуемый профиль, который можно использовать для начала работы) и инструкции по развертыванию профиля.</span><span class="sxs-lookup"><span data-stu-id="3301d-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="3301d-117">Структура профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="3301d-117">Configuration profile structure</span></span>

<span data-ttu-id="3301d-118">Профиль конфигурации — это файл .json, состоящий из записей, идентифицированных ключом (который обозначает имя предпочтения), за которым следует значение, которое зависит от характера предпочтения.</span><span class="sxs-lookup"><span data-stu-id="3301d-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="3301d-119">Значения могут быть простыми, такими как численное значение или сложные, например вложенный список предпочтений.</span><span class="sxs-lookup"><span data-stu-id="3301d-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="3301d-120">Обычно для нажима файла с именем в расположении используется средство управления ```mdatp_managed.json``` ```/etc/opt/microsoft/mdatp/managed/``` конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="3301d-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="3301d-121">Верхний уровень профиля конфигурации включает в себя все продукты и записи для subareas продукта, которые подробно объясняются в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="3301d-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="3301d-122">Параметры антивирусного двигателя</span><span class="sxs-lookup"><span data-stu-id="3301d-122">Antivirus engine preferences</span></span>

<span data-ttu-id="3301d-123">Раздел *antivirusEngine* профиля конфигурации используется для управления предпочтениями антивирусного компонента продукта.</span><span class="sxs-lookup"><span data-stu-id="3301d-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-124">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-124">**Key**</span></span> | <span data-ttu-id="3301d-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="3301d-125">antivirusEngine</span></span> |
| <span data-ttu-id="3301d-126">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-126">**Data type**</span></span> | <span data-ttu-id="3301d-127">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="3301d-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3301d-128">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3301d-128">**Comments**</span></span> | <span data-ttu-id="3301d-129">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="3301d-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="3301d-130">Включить и отключить защиту в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="3301d-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="3301d-131">Определяет, включена ли защита в режиме реального времени (сканировать файлы по мере их доступа).</span><span class="sxs-lookup"><span data-stu-id="3301d-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-132">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-132">**Key**</span></span> | <span data-ttu-id="3301d-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="3301d-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="3301d-134">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-134">**Data type**</span></span> | <span data-ttu-id="3301d-135">Логический</span><span class="sxs-lookup"><span data-stu-id="3301d-135">Boolean</span></span> |
| <span data-ttu-id="3301d-136">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-136">**Possible values**</span></span> | <span data-ttu-id="3301d-137">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3301d-137">true (default)</span></span> <br/> <span data-ttu-id="3301d-138">false</span><span class="sxs-lookup"><span data-stu-id="3301d-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="3301d-139">Включить и отключить пассивный режим</span><span class="sxs-lookup"><span data-stu-id="3301d-139">Enable / disable passive mode</span></span>

<span data-ttu-id="3301d-140">Определяет, работает ли антивирусный двигатель в пассивном режиме или нет.</span><span class="sxs-lookup"><span data-stu-id="3301d-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="3301d-141">В пассивном режиме:</span><span class="sxs-lookup"><span data-stu-id="3301d-141">In passive mode:</span></span>
- <span data-ttu-id="3301d-142">Защита в режиме реального времени отключена.</span><span class="sxs-lookup"><span data-stu-id="3301d-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="3301d-143">Сканирование по запросу включено.</span><span class="sxs-lookup"><span data-stu-id="3301d-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="3301d-144">Автоматическое устранение угрозы отключено.</span><span class="sxs-lookup"><span data-stu-id="3301d-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="3301d-145">Включаем обновления разведки безопасности.</span><span class="sxs-lookup"><span data-stu-id="3301d-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="3301d-146">Значок меню состояния скрыт.</span><span class="sxs-lookup"><span data-stu-id="3301d-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-147">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-147">**Key**</span></span> | <span data-ttu-id="3301d-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="3301d-148">passiveMode</span></span> |
| <span data-ttu-id="3301d-149">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-149">**Data type**</span></span> | <span data-ttu-id="3301d-150">Логический</span><span class="sxs-lookup"><span data-stu-id="3301d-150">Boolean</span></span> |
| <span data-ttu-id="3301d-151">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-151">**Possible values**</span></span> | <span data-ttu-id="3301d-152">false (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3301d-152">false (default)</span></span> <br/> <span data-ttu-id="3301d-153">true</span><span class="sxs-lookup"><span data-stu-id="3301d-153">true</span></span> |
| <span data-ttu-id="3301d-154">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3301d-154">**Comments**</span></span> | <span data-ttu-id="3301d-155">Доступно в Защитнике для конечной точки версии 100.67.60 или выше.</span><span class="sxs-lookup"><span data-stu-id="3301d-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="3301d-156">Политика слияния исключений</span><span class="sxs-lookup"><span data-stu-id="3301d-156">Exclusion merge policy</span></span>

<span data-ttu-id="3301d-157">Указывает политику слияния исключений.</span><span class="sxs-lookup"><span data-stu-id="3301d-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="3301d-158">Это может быть сочетание исключений, определенных администратором и пользователей , или только исключений, определенных `merge` администратором ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="3301d-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="3301d-159">Этот параметр можно использовать, чтобы ограничить местным пользователям определение собственных исключений.</span><span class="sxs-lookup"><span data-stu-id="3301d-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-160">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-160">**Key**</span></span> | <span data-ttu-id="3301d-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="3301d-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="3301d-162">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-162">**Data type**</span></span> | <span data-ttu-id="3301d-163">String</span><span class="sxs-lookup"><span data-stu-id="3301d-163">String</span></span> |
| <span data-ttu-id="3301d-164">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-164">**Possible values**</span></span> | <span data-ttu-id="3301d-165">слияние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3301d-165">merge (default)</span></span> <br/> <span data-ttu-id="3301d-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="3301d-166">admin_only</span></span> |
| <span data-ttu-id="3301d-167">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3301d-167">**Comments**</span></span> | <span data-ttu-id="3301d-168">Доступно в Защитнике для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="3301d-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="3301d-169">Исключения сканирования</span><span class="sxs-lookup"><span data-stu-id="3301d-169">Scan exclusions</span></span>

<span data-ttu-id="3301d-170">Объекты, которые были исключены из проверки.</span><span class="sxs-lookup"><span data-stu-id="3301d-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="3301d-171">Исключения могут быть указаны полными путями, расширениями или именами файлов.</span><span class="sxs-lookup"><span data-stu-id="3301d-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-172">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-172">**Key**</span></span> | <span data-ttu-id="3301d-173">исключения</span><span class="sxs-lookup"><span data-stu-id="3301d-173">exclusions</span></span> |
| <span data-ttu-id="3301d-174">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-174">**Data type**</span></span> | <span data-ttu-id="3301d-175">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="3301d-175">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3301d-176">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3301d-176">**Comments**</span></span> | <span data-ttu-id="3301d-177">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="3301d-177">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="3301d-178">**Тип исключения**</span><span class="sxs-lookup"><span data-stu-id="3301d-178">**Type of exclusion**</span></span>

<span data-ttu-id="3301d-179">Указывает тип контента, исключенного из проверки.</span><span class="sxs-lookup"><span data-stu-id="3301d-179">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-180">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-180">**Key**</span></span> | <span data-ttu-id="3301d-181">$type</span><span class="sxs-lookup"><span data-stu-id="3301d-181">$type</span></span> |
| <span data-ttu-id="3301d-182">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-182">**Data type**</span></span> | <span data-ttu-id="3301d-183">String</span><span class="sxs-lookup"><span data-stu-id="3301d-183">String</span></span> |
| <span data-ttu-id="3301d-184">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-184">**Possible values**</span></span> | <span data-ttu-id="3301d-185">excludedPath</span><span class="sxs-lookup"><span data-stu-id="3301d-185">excludedPath</span></span> <br/> <span data-ttu-id="3301d-186">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="3301d-186">excludedFileExtension</span></span> <br/> <span data-ttu-id="3301d-187">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="3301d-187">excludedFileName</span></span> |
|||

<span data-ttu-id="3301d-188">**Путь к исключению контента**</span><span class="sxs-lookup"><span data-stu-id="3301d-188">**Path to excluded content**</span></span>

<span data-ttu-id="3301d-189">Используется для исключения контента из сканирования путем полного файла.</span><span class="sxs-lookup"><span data-stu-id="3301d-189">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-190">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-190">**Key**</span></span> | <span data-ttu-id="3301d-191">path</span><span class="sxs-lookup"><span data-stu-id="3301d-191">path</span></span> |
| <span data-ttu-id="3301d-192">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-192">**Data type**</span></span> | <span data-ttu-id="3301d-193">String</span><span class="sxs-lookup"><span data-stu-id="3301d-193">String</span></span> |
| <span data-ttu-id="3301d-194">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-194">**Possible values**</span></span> | <span data-ttu-id="3301d-195">допустимые пути</span><span class="sxs-lookup"><span data-stu-id="3301d-195">valid paths</span></span> |
| <span data-ttu-id="3301d-196">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3301d-196">**Comments**</span></span> | <span data-ttu-id="3301d-197">Применимо только если *$type* *исключенPath*</span><span class="sxs-lookup"><span data-stu-id="3301d-197">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="3301d-198">**Тип пути (файл / каталог)**</span><span class="sxs-lookup"><span data-stu-id="3301d-198">**Path type (file / directory)**</span></span>

<span data-ttu-id="3301d-199">Указывает, *относится ли* свойство пути к файлу или каталогу.</span><span class="sxs-lookup"><span data-stu-id="3301d-199">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="3301d-200">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-200">**Key**</span></span> | <span data-ttu-id="3301d-201">isDirectory</span><span class="sxs-lookup"><span data-stu-id="3301d-201">isDirectory</span></span> |
| <span data-ttu-id="3301d-202">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-202">**Data type**</span></span> | <span data-ttu-id="3301d-203">Логический</span><span class="sxs-lookup"><span data-stu-id="3301d-203">Boolean</span></span> |
| <span data-ttu-id="3301d-204">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-204">**Possible values**</span></span> | <span data-ttu-id="3301d-205">false (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3301d-205">false (default)</span></span> <br/> <span data-ttu-id="3301d-206">true</span><span class="sxs-lookup"><span data-stu-id="3301d-206">true</span></span> |
| <span data-ttu-id="3301d-207">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3301d-207">**Comments**</span></span> | <span data-ttu-id="3301d-208">Применимо только если *$type* *исключенPath*</span><span class="sxs-lookup"><span data-stu-id="3301d-208">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="3301d-209">**Расширение файла, исключено из сканирования**</span><span class="sxs-lookup"><span data-stu-id="3301d-209">**File extension excluded from the scan**</span></span>

<span data-ttu-id="3301d-210">Используется для исключения контента из сканирования с помощью расширения файла.</span><span class="sxs-lookup"><span data-stu-id="3301d-210">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-211">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-211">**Key**</span></span> | <span data-ttu-id="3301d-212">расширение</span><span class="sxs-lookup"><span data-stu-id="3301d-212">extension</span></span> |
| <span data-ttu-id="3301d-213">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-213">**Data type**</span></span> | <span data-ttu-id="3301d-214">String</span><span class="sxs-lookup"><span data-stu-id="3301d-214">String</span></span> |
| <span data-ttu-id="3301d-215">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-215">**Possible values**</span></span> | <span data-ttu-id="3301d-216">допустимые расширения файлов</span><span class="sxs-lookup"><span data-stu-id="3301d-216">valid file extensions</span></span> |
| <span data-ttu-id="3301d-217">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3301d-217">**Comments**</span></span> | <span data-ttu-id="3301d-218">Применимо только если *$type* *исключеноFileExtension*</span><span class="sxs-lookup"><span data-stu-id="3301d-218">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="3301d-219">**Процесс, исключенный из сканирования**</span><span class="sxs-lookup"><span data-stu-id="3301d-219">**Process excluded from the scan**</span></span>

<span data-ttu-id="3301d-220">Указывает процесс, для которого все действия файла исключены из сканирования.</span><span class="sxs-lookup"><span data-stu-id="3301d-220">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="3301d-221">Процесс может быть указан либо по имени (например, ) или `cat` по полному пути (например, `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="3301d-221">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-222">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-222">**Key**</span></span> | <span data-ttu-id="3301d-223">name</span><span class="sxs-lookup"><span data-stu-id="3301d-223">name</span></span> |
| <span data-ttu-id="3301d-224">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-224">**Data type**</span></span> | <span data-ttu-id="3301d-225">String</span><span class="sxs-lookup"><span data-stu-id="3301d-225">String</span></span> |
| <span data-ttu-id="3301d-226">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-226">**Possible values**</span></span> | <span data-ttu-id="3301d-227">любая строка</span><span class="sxs-lookup"><span data-stu-id="3301d-227">any string</span></span> |
| <span data-ttu-id="3301d-228">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3301d-228">**Comments**</span></span> | <span data-ttu-id="3301d-229">Применимо только *если $type* *исключеноFileName*</span><span class="sxs-lookup"><span data-stu-id="3301d-229">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="3301d-230">Разрешенные угрозы</span><span class="sxs-lookup"><span data-stu-id="3301d-230">Allowed threats</span></span>

<span data-ttu-id="3301d-231">Список угроз (идентифицированных по их имени), которые не заблокированы продуктом и разрешены к запуску.</span><span class="sxs-lookup"><span data-stu-id="3301d-231">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-232">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-232">**Key**</span></span> | <span data-ttu-id="3301d-233">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="3301d-233">allowedThreats</span></span> |
| <span data-ttu-id="3301d-234">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-234">**Data type**</span></span> | <span data-ttu-id="3301d-235">Массив строк</span><span class="sxs-lookup"><span data-stu-id="3301d-235">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="3301d-236">Действия с неустановляемой угрозой</span><span class="sxs-lookup"><span data-stu-id="3301d-236">Disallowed threat actions</span></span>

<span data-ttu-id="3301d-237">Ограничивает действия, которые может принимать локальный пользователь устройства при обнаружении угроз.</span><span class="sxs-lookup"><span data-stu-id="3301d-237">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="3301d-238">Действия, включенные в этот список, не отображаются в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="3301d-238">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-239">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-239">**Key**</span></span> | <span data-ttu-id="3301d-240">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="3301d-240">disallowedThreatActions</span></span> |
| <span data-ttu-id="3301d-241">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-241">**Data type**</span></span> | <span data-ttu-id="3301d-242">Массив строк</span><span class="sxs-lookup"><span data-stu-id="3301d-242">Array of strings</span></span> |
| <span data-ttu-id="3301d-243">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-243">**Possible values**</span></span> | <span data-ttu-id="3301d-244">разрешить (ограничивает пользователей от допуска угроз)</span><span class="sxs-lookup"><span data-stu-id="3301d-244">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="3301d-245">восстановление (ограничивает пользователей от восстановления угроз из карантина)</span><span class="sxs-lookup"><span data-stu-id="3301d-245">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="3301d-246">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3301d-246">**Comments**</span></span> | <span data-ttu-id="3301d-247">Доступно в Защитнике для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="3301d-247">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="3301d-248">Параметры типа угроз</span><span class="sxs-lookup"><span data-stu-id="3301d-248">Threat type settings</span></span>

<span data-ttu-id="3301d-249">Предпочтение *threatTypeSettings* в антивирусном движке используется для управления обработкой определенных типов угроз продуктом.</span><span class="sxs-lookup"><span data-stu-id="3301d-249">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-250">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-250">**Key**</span></span> | <span data-ttu-id="3301d-251">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="3301d-251">threatTypeSettings</span></span> |
| <span data-ttu-id="3301d-252">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-252">**Data type**</span></span> | <span data-ttu-id="3301d-253">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="3301d-253">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3301d-254">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3301d-254">**Comments**</span></span> | <span data-ttu-id="3301d-255">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="3301d-255">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="3301d-256">**Тип угрозы**</span><span class="sxs-lookup"><span data-stu-id="3301d-256">**Threat type**</span></span>

<span data-ttu-id="3301d-257">Тип угрозы, для которой настроено поведение.</span><span class="sxs-lookup"><span data-stu-id="3301d-257">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-258">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-258">**Key**</span></span> | <span data-ttu-id="3301d-259">ключа</span><span class="sxs-lookup"><span data-stu-id="3301d-259">key</span></span> |
| <span data-ttu-id="3301d-260">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-260">**Data type**</span></span> | <span data-ttu-id="3301d-261">String</span><span class="sxs-lookup"><span data-stu-id="3301d-261">String</span></span> |
| <span data-ttu-id="3301d-262">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-262">**Possible values**</span></span> | <span data-ttu-id="3301d-263">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="3301d-263">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="3301d-264">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="3301d-264">archive_bomb</span></span> |
|||

<span data-ttu-id="3301d-265">**Действие**</span><span class="sxs-lookup"><span data-stu-id="3301d-265">**Action to take**</span></span>

<span data-ttu-id="3301d-266">Действия, которые необходимо принять при наступивших угрозах типа, указанного в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="3301d-266">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="3301d-267">Может быть:</span><span class="sxs-lookup"><span data-stu-id="3301d-267">Can be:</span></span>

- <span data-ttu-id="3301d-268">**Аудит.** Устройство не защищено от этого типа угрозы, но запись об угрозе регистрируется.</span><span class="sxs-lookup"><span data-stu-id="3301d-268">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="3301d-269">**Блок.** Устройство защищено от этого типа угрозы, и вы уведомлены в консоли безопасности.</span><span class="sxs-lookup"><span data-stu-id="3301d-269">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="3301d-270">**Отключено.** Устройство не защищено от этого типа угрозы и ничего не регистрируется.</span><span class="sxs-lookup"><span data-stu-id="3301d-270">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-271">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-271">**Key**</span></span> | <span data-ttu-id="3301d-272">значение</span><span class="sxs-lookup"><span data-stu-id="3301d-272">value</span></span> |
| <span data-ttu-id="3301d-273">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-273">**Data type**</span></span> | <span data-ttu-id="3301d-274">String</span><span class="sxs-lookup"><span data-stu-id="3301d-274">String</span></span> |
| <span data-ttu-id="3301d-275">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-275">**Possible values**</span></span> | <span data-ttu-id="3301d-276">аудит (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3301d-276">audit (default)</span></span> <br/> <span data-ttu-id="3301d-277">block</span><span class="sxs-lookup"><span data-stu-id="3301d-277">block</span></span> <br/> <span data-ttu-id="3301d-278">Off</span><span class="sxs-lookup"><span data-stu-id="3301d-278">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="3301d-279">Параметры типа угрозы объединяют политику слияния</span><span class="sxs-lookup"><span data-stu-id="3301d-279">Threat type settings merge policy</span></span>

<span data-ttu-id="3301d-280">Указывает политику слияния для параметров типа угроз.</span><span class="sxs-lookup"><span data-stu-id="3301d-280">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="3301d-281">Это может быть сочетание параметров, определенных администратором и определенных пользователем , или только параметров, определенных `merge` администратором ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="3301d-281">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="3301d-282">Этот параметр можно использовать, чтобы ограничить местным пользователям определение собственных параметров для различных типов угроз.</span><span class="sxs-lookup"><span data-stu-id="3301d-282">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-283">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-283">**Key**</span></span> | <span data-ttu-id="3301d-284">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="3301d-284">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="3301d-285">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-285">**Data type**</span></span> | <span data-ttu-id="3301d-286">String</span><span class="sxs-lookup"><span data-stu-id="3301d-286">String</span></span> |
| <span data-ttu-id="3301d-287">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-287">**Possible values**</span></span> | <span data-ttu-id="3301d-288">слияние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3301d-288">merge (default)</span></span> <br/> <span data-ttu-id="3301d-289">admin_only</span><span class="sxs-lookup"><span data-stu-id="3301d-289">admin_only</span></span> |
| <span data-ttu-id="3301d-290">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3301d-290">**Comments**</span></span> | <span data-ttu-id="3301d-291">Доступно в Защитнике для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="3301d-291">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="3301d-292">Хранение истории антивирусного сканирования (в днях)</span><span class="sxs-lookup"><span data-stu-id="3301d-292">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="3301d-293">Укажите количество дней, которые сохраняются в истории сканирования на устройстве.</span><span class="sxs-lookup"><span data-stu-id="3301d-293">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="3301d-294">Старые результаты сканирования удаляются из истории.</span><span class="sxs-lookup"><span data-stu-id="3301d-294">Old scan results are removed from the history.</span></span> <span data-ttu-id="3301d-295">Старые карантинные файлы, которые также удаляются с диска.</span><span class="sxs-lookup"><span data-stu-id="3301d-295">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-296">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-296">**Key**</span></span> | <span data-ttu-id="3301d-297">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="3301d-297">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="3301d-298">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-298">**Data type**</span></span> | <span data-ttu-id="3301d-299">String</span><span class="sxs-lookup"><span data-stu-id="3301d-299">String</span></span> |
| <span data-ttu-id="3301d-300">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-300">**Possible values**</span></span> | <span data-ttu-id="3301d-301">90 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="3301d-301">90 (default).</span></span> <span data-ttu-id="3301d-302">Допустимые значения от 1 дня до 180 дней.</span><span class="sxs-lookup"><span data-stu-id="3301d-302">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="3301d-303">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3301d-303">**Comments**</span></span> | <span data-ttu-id="3301d-304">Доступно в Защитнике для конечной точки версии 101.04.76 или выше.</span><span class="sxs-lookup"><span data-stu-id="3301d-304">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="3301d-305">Максимальное количество элементов в истории антивирусного сканирования</span><span class="sxs-lookup"><span data-stu-id="3301d-305">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="3301d-306">Укажите максимальное количество записей, которые необходимо сохранить в истории сканирования.</span><span class="sxs-lookup"><span data-stu-id="3301d-306">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="3301d-307">Записи включают все проверки по запросу, выполняемые в прошлом, и все обнаружения антивирусов.</span><span class="sxs-lookup"><span data-stu-id="3301d-307">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-308">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-308">**Key**</span></span> | <span data-ttu-id="3301d-309">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="3301d-309">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="3301d-310">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-310">**Data type**</span></span> | <span data-ttu-id="3301d-311">String</span><span class="sxs-lookup"><span data-stu-id="3301d-311">String</span></span> |
| <span data-ttu-id="3301d-312">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-312">**Possible values**</span></span> | <span data-ttu-id="3301d-313">10000 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="3301d-313">10000 (default).</span></span> <span data-ttu-id="3301d-314">Допустимые значения : от 5000 элементов до 15000 элементов.</span><span class="sxs-lookup"><span data-stu-id="3301d-314">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="3301d-315">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3301d-315">**Comments**</span></span> | <span data-ttu-id="3301d-316">Доступно в Защитнике для конечной точки версии 101.04.76 или выше.</span><span class="sxs-lookup"><span data-stu-id="3301d-316">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="3301d-317">Параметры защиты с облачной доставкой</span><span class="sxs-lookup"><span data-stu-id="3301d-317">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="3301d-318">Запись *cloudService* в профиле конфигурации используется для настройки облачной функции защиты продукта.</span><span class="sxs-lookup"><span data-stu-id="3301d-318">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-319">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-319">**Key**</span></span> | <span data-ttu-id="3301d-320">cloudService</span><span class="sxs-lookup"><span data-stu-id="3301d-320">cloudService</span></span> |
| <span data-ttu-id="3301d-321">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-321">**Data type**</span></span> | <span data-ttu-id="3301d-322">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="3301d-322">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3301d-323">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3301d-323">**Comments**</span></span> | <span data-ttu-id="3301d-324">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="3301d-324">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="3301d-325">Включить и отключить защиту от облачной доставки</span><span class="sxs-lookup"><span data-stu-id="3301d-325">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="3301d-326">Определяет, включена ли облачная защита на устройстве или нет.</span><span class="sxs-lookup"><span data-stu-id="3301d-326">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="3301d-327">Чтобы повысить безопасность ваших служб, рекомендуется сохранить эту функцию включенной.</span><span class="sxs-lookup"><span data-stu-id="3301d-327">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-328">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-328">**Key**</span></span> | <span data-ttu-id="3301d-329">включено</span><span class="sxs-lookup"><span data-stu-id="3301d-329">enabled</span></span> |
| <span data-ttu-id="3301d-330">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-330">**Data type**</span></span> | <span data-ttu-id="3301d-331">Логический</span><span class="sxs-lookup"><span data-stu-id="3301d-331">Boolean</span></span> |
| <span data-ttu-id="3301d-332">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-332">**Possible values**</span></span> | <span data-ttu-id="3301d-333">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3301d-333">true (default)</span></span> <br/> <span data-ttu-id="3301d-334">false</span><span class="sxs-lookup"><span data-stu-id="3301d-334">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="3301d-335">Уровень диагностической коллекции</span><span class="sxs-lookup"><span data-stu-id="3301d-335">Diagnostic collection level</span></span>

<span data-ttu-id="3301d-336">Диагностические данные используются для обеспечения безопасности и повышения безопасности Defender для конечной точки, обнаружения, диагностики и устранения проблем, а также улучшения продукта.</span><span class="sxs-lookup"><span data-stu-id="3301d-336">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="3301d-337">Этот параметр определяет уровень диагностики, отправленной продуктом в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3301d-337">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-338">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-338">**Key**</span></span> | <span data-ttu-id="3301d-339">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="3301d-339">diagnosticLevel</span></span> |
| <span data-ttu-id="3301d-340">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-340">**Data type**</span></span> | <span data-ttu-id="3301d-341">String</span><span class="sxs-lookup"><span data-stu-id="3301d-341">String</span></span> |
| <span data-ttu-id="3301d-342">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-342">**Possible values**</span></span> | <span data-ttu-id="3301d-343">необязательный (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3301d-343">optional (default)</span></span> <br/> <span data-ttu-id="3301d-344">Обязательный</span><span class="sxs-lookup"><span data-stu-id="3301d-344">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="3301d-345">Включить и отключить автоматические отправки образцов</span><span class="sxs-lookup"><span data-stu-id="3301d-345">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="3301d-346">Определяет, отправляются ли подозрительные образцы (которые могут содержать угрозы) в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3301d-346">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="3301d-347">Существует три уровня для управления отправкой примера:</span><span class="sxs-lookup"><span data-stu-id="3301d-347">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="3301d-348">**Нет:** никаких подозрительных образцов не передается в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3301d-348">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="3301d-349">**Безопасные:** автоматически будут отправлены только подозрительные образцы, которые не содержат личных идентифицируемых сведений (PII).</span><span class="sxs-lookup"><span data-stu-id="3301d-349">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="3301d-350">Это значение по умолчанию для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="3301d-350">This is the default value for this setting.</span></span>
- <span data-ttu-id="3301d-351">**Все:** все подозрительные образцы отправлены в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3301d-351">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-352">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-352">**Key**</span></span> | <span data-ttu-id="3301d-353">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="3301d-353">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="3301d-354">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-354">**Data type**</span></span> | <span data-ttu-id="3301d-355">String</span><span class="sxs-lookup"><span data-stu-id="3301d-355">String</span></span> |
| <span data-ttu-id="3301d-356">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-356">**Possible values**</span></span> | <span data-ttu-id="3301d-357">нет</span><span class="sxs-lookup"><span data-stu-id="3301d-357">none</span></span> <br/> <span data-ttu-id="3301d-358">безопасный (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3301d-358">safe (default)</span></span> <br/> <span data-ttu-id="3301d-359">все</span><span class="sxs-lookup"><span data-stu-id="3301d-359">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="3301d-360">Включить и отключить автоматические обновления сведении о безопасности</span><span class="sxs-lookup"><span data-stu-id="3301d-360">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="3301d-361">Определяет, устанавливаются ли обновления разведки безопасности автоматически:</span><span class="sxs-lookup"><span data-stu-id="3301d-361">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="3301d-362">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="3301d-362">**Key**</span></span> | <span data-ttu-id="3301d-363">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="3301d-363">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="3301d-364">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3301d-364">**Data type**</span></span> | <span data-ttu-id="3301d-365">Логический</span><span class="sxs-lookup"><span data-stu-id="3301d-365">Boolean</span></span> |
| <span data-ttu-id="3301d-366">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="3301d-366">**Possible values**</span></span> | <span data-ttu-id="3301d-367">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3301d-367">true (default)</span></span> <br/> <span data-ttu-id="3301d-368">false</span><span class="sxs-lookup"><span data-stu-id="3301d-368">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="3301d-369">Рекомендуемый профиль конфигурации</span><span class="sxs-lookup"><span data-stu-id="3301d-369">Recommended configuration profile</span></span>

<span data-ttu-id="3301d-370">Чтобы начать работу, рекомендуется в следующем профиле конфигурации для предприятия воспользоваться всеми функциями защиты, которые предоставляет Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="3301d-370">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="3301d-371">Следующий профиль конфигурации:</span><span class="sxs-lookup"><span data-stu-id="3301d-371">The following configuration profile will:</span></span>

- <span data-ttu-id="3301d-372">Включить защиту в режиме реального времени (RTP)</span><span class="sxs-lookup"><span data-stu-id="3301d-372">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="3301d-373">Укажите, как обрабатываются следующие типы угроз:</span><span class="sxs-lookup"><span data-stu-id="3301d-373">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="3301d-374">**Потенциально нежелательные приложения (PUA)** заблокированы</span><span class="sxs-lookup"><span data-stu-id="3301d-374">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="3301d-375">**Архивные** бомбы (файл с высокой скоростью сжатия) проверяются в журналах продуктов</span><span class="sxs-lookup"><span data-stu-id="3301d-375">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="3301d-376">Включить автоматические обновления сведении о безопасности</span><span class="sxs-lookup"><span data-stu-id="3301d-376">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="3301d-377">Включить облачную защиту</span><span class="sxs-lookup"><span data-stu-id="3301d-377">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="3301d-378">Включить автоматическую отправку образца на `safe` уровне</span><span class="sxs-lookup"><span data-stu-id="3301d-378">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="3301d-379">Пример профиля</span><span class="sxs-lookup"><span data-stu-id="3301d-379">Sample profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="3301d-380">Пример профиля полной конфигурации</span><span class="sxs-lookup"><span data-stu-id="3301d-380">Full configuration profile example</span></span>

<span data-ttu-id="3301d-381">Следующий профиль конфигурации содержит записи для всех параметров, описанных в этом документе, и может использоваться для более сложных сценариев, в которых требуется больше контроля над продуктом.</span><span class="sxs-lookup"><span data-stu-id="3301d-381">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="3301d-382">Полный профиль</span><span class="sxs-lookup"><span data-stu-id="3301d-382">Full profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home"
         },
         {
            "$type":"excludedFileExtension",
            "extension":"pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="3301d-383">Проверка профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="3301d-383">Configuration profile validation</span></span>

<span data-ttu-id="3301d-384">Профиль конфигурации должен быть допустимым JSON-форматированный файл.</span><span class="sxs-lookup"><span data-stu-id="3301d-384">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="3301d-385">Существует ряд средств, которые можно использовать для проверки этого.</span><span class="sxs-lookup"><span data-stu-id="3301d-385">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="3301d-386">Например, если вы установили `python` на устройстве:</span><span class="sxs-lookup"><span data-stu-id="3301d-386">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="3301d-387">Если JSON хорошо сформирован, вышеуказанная команда выводит его обратно в терминал и возвращает код выхода `0` .</span><span class="sxs-lookup"><span data-stu-id="3301d-387">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="3301d-388">В противном случае отображается ошибка, описываемая проблемой, и команда возвращает код выхода `1` .</span><span class="sxs-lookup"><span data-stu-id="3301d-388">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="3301d-389">Проверка того, mdatp_managed.jsфайл работает как ожидалось</span><span class="sxs-lookup"><span data-stu-id="3301d-389">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="3301d-390">Чтобы убедиться, что ваш /etc/opt/microsoft/mdatp/managed/mdatp_managed.jsработает должным образом, рядом с этими настройками следует увидеть "[managed]":</span><span class="sxs-lookup"><span data-stu-id="3301d-390">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>  
- <span data-ttu-id="3301d-391">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="3301d-391">cloud_enabled</span></span>
- <span data-ttu-id="3301d-392">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="3301d-392">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="3301d-393">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="3301d-393">passice_mode_enabled</span></span>
- <span data-ttu-id="3301d-394">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="3301d-394">real_time_protection_enabled</span></span>
- <span data-ttu-id="3301d-395">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="3301d-395">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="3301d-396">Чтобы mdatp_managed.jsвступил в силу, перезагрузка wdavdaemon не требуется.</span><span class="sxs-lookup"><span data-stu-id="3301d-396">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="3301d-397">Развертывание профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="3301d-397">Configuration profile deployment</span></span>

<span data-ttu-id="3301d-398">После создания профиля конфигурации для предприятия его можно развернуть с помощью средства управления, используемом вашим предприятием.</span><span class="sxs-lookup"><span data-stu-id="3301d-398">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="3301d-399">Защитник для конечной точки для Linux читает управляемой конфигурации из */etc/opt/microsoft/mdatp/managed/mdatp_managed.jsв* файле.</span><span class="sxs-lookup"><span data-stu-id="3301d-399">Defender for Endpoint for Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
