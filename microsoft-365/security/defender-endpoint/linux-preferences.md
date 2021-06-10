---
title: Настройка предпочтений для Microsoft Defender для конечной точки в Linux
ms.reviewer: ''
description: Описывает, как настроить Microsoft Defender для конечной точки на Linux на предприятиях.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, Linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 29505a6e975fdfa2283efe3391c615e40e678164
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346382"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="ee391-104">Настройка предпочтений для Microsoft Defender для конечной точки в Linux</span><span class="sxs-lookup"><span data-stu-id="ee391-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ee391-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ee391-105">**Applies to:**</span></span>
- [<span data-ttu-id="ee391-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ee391-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ee391-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ee391-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ee391-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ee391-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ee391-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ee391-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="ee391-110">В этом разделе содержатся инструкции по выбору предпочтений для Defender для конечной точки в Linux в корпоративных средах.</span><span class="sxs-lookup"><span data-stu-id="ee391-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="ee391-111">Если вы заинтересованы в настройке продукта на устройстве из командной строки, см. [в этой строке Ресурсы.](linux-resources.md#configure-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="ee391-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="ee391-112">В корпоративных средах управление Защитником для конечной точки на Linux можно с помощью профиля конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ee391-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="ee391-113">Этот профиль развернут из средства управления по вашему выбору.</span><span class="sxs-lookup"><span data-stu-id="ee391-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="ee391-114">Предпочтения, управляемые предприятием, имеют приоритет над предпочтениями, установленными локально на устройстве.</span><span class="sxs-lookup"><span data-stu-id="ee391-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="ee391-115">Другими словами, пользователи в вашем предприятии не могут изменять предпочтения, задав этот профиль конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ee391-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="ee391-116">В этой статье описывается структура этого профиля (включая рекомендуемый профиль, который можно использовать для начала работы) и инструкции по развертыванию профиля.</span><span class="sxs-lookup"><span data-stu-id="ee391-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="ee391-117">Структура профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="ee391-117">Configuration profile structure</span></span>

<span data-ttu-id="ee391-118">Профиль конфигурации — это файл .json, состоящий из записей, идентифицированных ключом (который обозначает имя предпочтения), за которым следует значение, которое зависит от характера предпочтения.</span><span class="sxs-lookup"><span data-stu-id="ee391-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="ee391-119">Значения могут быть простыми, такими как численное значение или сложные, например вложенный список предпочтений.</span><span class="sxs-lookup"><span data-stu-id="ee391-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="ee391-120">Обычно для нажима файла с именем в расположении используется средство управления ```mdatp_managed.json``` ```/etc/opt/microsoft/mdatp/managed/``` конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="ee391-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="ee391-121">Верхний уровень профиля конфигурации включает в себя все продукты и записи для subareas продукта, которые подробно объясняются в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="ee391-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="ee391-122">Параметры антивирусного двигателя</span><span class="sxs-lookup"><span data-stu-id="ee391-122">Antivirus engine preferences</span></span>

<span data-ttu-id="ee391-123">Раздел *antivirusEngine* профиля конфигурации используется для управления предпочтениями антивирусного компонента продукта.</span><span class="sxs-lookup"><span data-stu-id="ee391-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-124">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-124">**Key**</span></span> | <span data-ttu-id="ee391-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="ee391-125">antivirusEngine</span></span> |
| <span data-ttu-id="ee391-126">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-126">**Data type**</span></span> | <span data-ttu-id="ee391-127">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="ee391-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ee391-128">**Comments**</span><span class="sxs-lookup"><span data-stu-id="ee391-128">**Comments**</span></span> | <span data-ttu-id="ee391-129">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="ee391-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="ee391-130">Включить и отключить защиту в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="ee391-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="ee391-131">Определяет, включена ли защита в режиме реального времени (сканировать файлы по мере их доступа).</span><span class="sxs-lookup"><span data-stu-id="ee391-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-132">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-132">**Key**</span></span> | <span data-ttu-id="ee391-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="ee391-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="ee391-134">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-134">**Data type**</span></span> | <span data-ttu-id="ee391-135">Логический</span><span class="sxs-lookup"><span data-stu-id="ee391-135">Boolean</span></span> |
| <span data-ttu-id="ee391-136">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-136">**Possible values**</span></span> | <span data-ttu-id="ee391-137">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ee391-137">true (default)</span></span> <br/> <span data-ttu-id="ee391-138">false</span><span class="sxs-lookup"><span data-stu-id="ee391-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="ee391-139">Включить и отключить пассивный режим</span><span class="sxs-lookup"><span data-stu-id="ee391-139">Enable / disable passive mode</span></span>

<span data-ttu-id="ee391-140">Определяет, работает ли антивирусный двигатель в пассивном режиме или нет.</span><span class="sxs-lookup"><span data-stu-id="ee391-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="ee391-141">В пассивном режиме:</span><span class="sxs-lookup"><span data-stu-id="ee391-141">In passive mode:</span></span>
- <span data-ttu-id="ee391-142">Защита в режиме реального времени отключена.</span><span class="sxs-lookup"><span data-stu-id="ee391-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="ee391-143">Сканирование по запросу включено.</span><span class="sxs-lookup"><span data-stu-id="ee391-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="ee391-144">Автоматическое устранение угрозы отключено.</span><span class="sxs-lookup"><span data-stu-id="ee391-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="ee391-145">Включаем обновления разведки безопасности.</span><span class="sxs-lookup"><span data-stu-id="ee391-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="ee391-146">Значок меню состояния скрыт.</span><span class="sxs-lookup"><span data-stu-id="ee391-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-147">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-147">**Key**</span></span> | <span data-ttu-id="ee391-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="ee391-148">passiveMode</span></span> |
| <span data-ttu-id="ee391-149">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-149">**Data type**</span></span> | <span data-ttu-id="ee391-150">Логический</span><span class="sxs-lookup"><span data-stu-id="ee391-150">Boolean</span></span> |
| <span data-ttu-id="ee391-151">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-151">**Possible values**</span></span> | <span data-ttu-id="ee391-152">false (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ee391-152">false (default)</span></span> <br/> <span data-ttu-id="ee391-153">true</span><span class="sxs-lookup"><span data-stu-id="ee391-153">true</span></span> |
| <span data-ttu-id="ee391-154">**Comments**</span><span class="sxs-lookup"><span data-stu-id="ee391-154">**Comments**</span></span> | <span data-ttu-id="ee391-155">Доступно в Защитнике для конечной точки версии 100.67.60 или выше.</span><span class="sxs-lookup"><span data-stu-id="ee391-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="ee391-156">Политика слияния исключений</span><span class="sxs-lookup"><span data-stu-id="ee391-156">Exclusion merge policy</span></span>

<span data-ttu-id="ee391-157">Указывает политику слияния исключений.</span><span class="sxs-lookup"><span data-stu-id="ee391-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="ee391-158">Это может быть сочетание исключений, определенных администратором и пользователей , или только исключений, определенных `merge` администратором ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="ee391-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="ee391-159">Этот параметр можно использовать, чтобы ограничить местным пользователям определение собственных исключений.</span><span class="sxs-lookup"><span data-stu-id="ee391-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-160">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-160">**Key**</span></span> | <span data-ttu-id="ee391-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="ee391-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="ee391-162">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-162">**Data type**</span></span> | <span data-ttu-id="ee391-163">String</span><span class="sxs-lookup"><span data-stu-id="ee391-163">String</span></span> |
| <span data-ttu-id="ee391-164">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-164">**Possible values**</span></span> | <span data-ttu-id="ee391-165">слияние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ee391-165">merge (default)</span></span> <br/> <span data-ttu-id="ee391-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="ee391-166">admin_only</span></span> |
| <span data-ttu-id="ee391-167">**Comments**</span><span class="sxs-lookup"><span data-stu-id="ee391-167">**Comments**</span></span> | <span data-ttu-id="ee391-168">Доступно в Защитнике для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="ee391-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="ee391-169">Исключения сканирования</span><span class="sxs-lookup"><span data-stu-id="ee391-169">Scan exclusions</span></span>

<span data-ttu-id="ee391-170">Объекты, которые были исключены из проверки.</span><span class="sxs-lookup"><span data-stu-id="ee391-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="ee391-171">Исключения могут быть указаны полными путями, расширениями или именами файлов.</span><span class="sxs-lookup"><span data-stu-id="ee391-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="ee391-172">(Исключения заданы в качестве массива элементов, администратор может указать столько элементов, сколько необходимо, в любом порядке.)</span><span class="sxs-lookup"><span data-stu-id="ee391-172">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-173">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-173">**Key**</span></span> | <span data-ttu-id="ee391-174">исключения</span><span class="sxs-lookup"><span data-stu-id="ee391-174">exclusions</span></span> |
| <span data-ttu-id="ee391-175">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-175">**Data type**</span></span> | <span data-ttu-id="ee391-176">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="ee391-176">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ee391-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="ee391-177">**Comments**</span></span> | <span data-ttu-id="ee391-178">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="ee391-178">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="ee391-179">**Тип исключения**</span><span class="sxs-lookup"><span data-stu-id="ee391-179">**Type of exclusion**</span></span>

<span data-ttu-id="ee391-180">Указывает тип контента, исключенного из проверки.</span><span class="sxs-lookup"><span data-stu-id="ee391-180">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-181">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-181">**Key**</span></span> | <span data-ttu-id="ee391-182">$type</span><span class="sxs-lookup"><span data-stu-id="ee391-182">$type</span></span> |
| <span data-ttu-id="ee391-183">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-183">**Data type**</span></span> | <span data-ttu-id="ee391-184">String</span><span class="sxs-lookup"><span data-stu-id="ee391-184">String</span></span> |
| <span data-ttu-id="ee391-185">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-185">**Possible values**</span></span> | <span data-ttu-id="ee391-186">excludedPath</span><span class="sxs-lookup"><span data-stu-id="ee391-186">excludedPath</span></span> <br/> <span data-ttu-id="ee391-187">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="ee391-187">excludedFileExtension</span></span> <br/> <span data-ttu-id="ee391-188">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="ee391-188">excludedFileName</span></span> |
|||

<span data-ttu-id="ee391-189">**Путь к исключению контента**</span><span class="sxs-lookup"><span data-stu-id="ee391-189">**Path to excluded content**</span></span>

<span data-ttu-id="ee391-190">Используется для исключения контента из сканирования путем полного файла.</span><span class="sxs-lookup"><span data-stu-id="ee391-190">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-191">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-191">**Key**</span></span> | <span data-ttu-id="ee391-192">path</span><span class="sxs-lookup"><span data-stu-id="ee391-192">path</span></span> |
| <span data-ttu-id="ee391-193">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-193">**Data type**</span></span> | <span data-ttu-id="ee391-194">String</span><span class="sxs-lookup"><span data-stu-id="ee391-194">String</span></span> |
| <span data-ttu-id="ee391-195">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-195">**Possible values**</span></span> | <span data-ttu-id="ee391-196">допустимые пути</span><span class="sxs-lookup"><span data-stu-id="ee391-196">valid paths</span></span> |
| <span data-ttu-id="ee391-197">**Comments**</span><span class="sxs-lookup"><span data-stu-id="ee391-197">**Comments**</span></span> | <span data-ttu-id="ee391-198">Применимо только если *$type* *исключенPath*</span><span class="sxs-lookup"><span data-stu-id="ee391-198">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="ee391-199">**Тип пути (файл / каталог)**</span><span class="sxs-lookup"><span data-stu-id="ee391-199">**Path type (file / directory)**</span></span>

<span data-ttu-id="ee391-200">Указывает, *относится ли* свойство пути к файлу или каталогу.</span><span class="sxs-lookup"><span data-stu-id="ee391-200">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="ee391-201">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-201">**Key**</span></span> | <span data-ttu-id="ee391-202">isDirectory</span><span class="sxs-lookup"><span data-stu-id="ee391-202">isDirectory</span></span> |
| <span data-ttu-id="ee391-203">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-203">**Data type**</span></span> | <span data-ttu-id="ee391-204">Логический</span><span class="sxs-lookup"><span data-stu-id="ee391-204">Boolean</span></span> |
| <span data-ttu-id="ee391-205">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-205">**Possible values**</span></span> | <span data-ttu-id="ee391-206">false (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ee391-206">false (default)</span></span> <br/> <span data-ttu-id="ee391-207">true</span><span class="sxs-lookup"><span data-stu-id="ee391-207">true</span></span> |
| <span data-ttu-id="ee391-208">**Comments**</span><span class="sxs-lookup"><span data-stu-id="ee391-208">**Comments**</span></span> | <span data-ttu-id="ee391-209">Применимо только если *$type* *исключенPath*</span><span class="sxs-lookup"><span data-stu-id="ee391-209">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="ee391-210">**Расширение файла, исключено из сканирования**</span><span class="sxs-lookup"><span data-stu-id="ee391-210">**File extension excluded from the scan**</span></span>

<span data-ttu-id="ee391-211">Используется для исключения контента из сканирования с помощью расширения файла.</span><span class="sxs-lookup"><span data-stu-id="ee391-211">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-212">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-212">**Key**</span></span> | <span data-ttu-id="ee391-213">расширение</span><span class="sxs-lookup"><span data-stu-id="ee391-213">extension</span></span> |
| <span data-ttu-id="ee391-214">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-214">**Data type**</span></span> | <span data-ttu-id="ee391-215">String</span><span class="sxs-lookup"><span data-stu-id="ee391-215">String</span></span> |
| <span data-ttu-id="ee391-216">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-216">**Possible values**</span></span> | <span data-ttu-id="ee391-217">допустимые расширения файлов</span><span class="sxs-lookup"><span data-stu-id="ee391-217">valid file extensions</span></span> |
| <span data-ttu-id="ee391-218">**Comments**</span><span class="sxs-lookup"><span data-stu-id="ee391-218">**Comments**</span></span> | <span data-ttu-id="ee391-219">Применимо только если *$type* *исключеноFileExtension*</span><span class="sxs-lookup"><span data-stu-id="ee391-219">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="ee391-220">**Процесс, исключенный из сканирования**</span><span class="sxs-lookup"><span data-stu-id="ee391-220">**Process excluded from the scan**</span></span>

<span data-ttu-id="ee391-221">Указывает процесс, для которого все действия файла исключены из сканирования.</span><span class="sxs-lookup"><span data-stu-id="ee391-221">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="ee391-222">Процесс может быть указан либо по имени (например, ) или `cat` по полному пути (например, `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="ee391-222">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-223">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-223">**Key**</span></span> | <span data-ttu-id="ee391-224">name</span><span class="sxs-lookup"><span data-stu-id="ee391-224">name</span></span> |
| <span data-ttu-id="ee391-225">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-225">**Data type**</span></span> | <span data-ttu-id="ee391-226">String</span><span class="sxs-lookup"><span data-stu-id="ee391-226">String</span></span> |
| <span data-ttu-id="ee391-227">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-227">**Possible values**</span></span> | <span data-ttu-id="ee391-228">любая строка</span><span class="sxs-lookup"><span data-stu-id="ee391-228">any string</span></span> |
| <span data-ttu-id="ee391-229">**Comments**</span><span class="sxs-lookup"><span data-stu-id="ee391-229">**Comments**</span></span> | <span data-ttu-id="ee391-230">Применимо только *если $type* *исключеноFileName*</span><span class="sxs-lookup"><span data-stu-id="ee391-230">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="ee391-231">Разрешенные угрозы</span><span class="sxs-lookup"><span data-stu-id="ee391-231">Allowed threats</span></span>

<span data-ttu-id="ee391-232">Список угроз (идентифицированных по их имени), которые не заблокированы продуктом и разрешены к запуску.</span><span class="sxs-lookup"><span data-stu-id="ee391-232">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-233">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-233">**Key**</span></span> | <span data-ttu-id="ee391-234">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="ee391-234">allowedThreats</span></span> |
| <span data-ttu-id="ee391-235">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-235">**Data type**</span></span> | <span data-ttu-id="ee391-236">Массив строк</span><span class="sxs-lookup"><span data-stu-id="ee391-236">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="ee391-237">Действия с неустановляемой угрозой</span><span class="sxs-lookup"><span data-stu-id="ee391-237">Disallowed threat actions</span></span>

<span data-ttu-id="ee391-238">Ограничивает действия, которые может принимать локальный пользователь устройства при обнаружении угроз.</span><span class="sxs-lookup"><span data-stu-id="ee391-238">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="ee391-239">Действия, включенные в этот список, не отображаются в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="ee391-239">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-240">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-240">**Key**</span></span> | <span data-ttu-id="ee391-241">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="ee391-241">disallowedThreatActions</span></span> |
| <span data-ttu-id="ee391-242">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-242">**Data type**</span></span> | <span data-ttu-id="ee391-243">Массив строк</span><span class="sxs-lookup"><span data-stu-id="ee391-243">Array of strings</span></span> |
| <span data-ttu-id="ee391-244">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-244">**Possible values**</span></span> | <span data-ttu-id="ee391-245">разрешить (ограничивает пользователей от допуска угроз)</span><span class="sxs-lookup"><span data-stu-id="ee391-245">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="ee391-246">восстановление (ограничивает пользователей от восстановления угроз из карантина)</span><span class="sxs-lookup"><span data-stu-id="ee391-246">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="ee391-247">**Comments**</span><span class="sxs-lookup"><span data-stu-id="ee391-247">**Comments**</span></span> | <span data-ttu-id="ee391-248">Доступно в Защитнике для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="ee391-248">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="ee391-249">Параметры типа угроз</span><span class="sxs-lookup"><span data-stu-id="ee391-249">Threat type settings</span></span>

<span data-ttu-id="ee391-250">Предпочтение *threatTypeSettings* в антивирусном движке используется для управления обработкой определенных типов угроз продуктом.</span><span class="sxs-lookup"><span data-stu-id="ee391-250">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-251">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-251">**Key**</span></span> | <span data-ttu-id="ee391-252">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="ee391-252">threatTypeSettings</span></span> |
| <span data-ttu-id="ee391-253">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-253">**Data type**</span></span> | <span data-ttu-id="ee391-254">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="ee391-254">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ee391-255">**Comments**</span><span class="sxs-lookup"><span data-stu-id="ee391-255">**Comments**</span></span> | <span data-ttu-id="ee391-256">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="ee391-256">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="ee391-257">**Тип угрозы**</span><span class="sxs-lookup"><span data-stu-id="ee391-257">**Threat type**</span></span>

<span data-ttu-id="ee391-258">Тип угрозы, для которой настроено поведение.</span><span class="sxs-lookup"><span data-stu-id="ee391-258">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-259">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-259">**Key**</span></span> | <span data-ttu-id="ee391-260">ключа</span><span class="sxs-lookup"><span data-stu-id="ee391-260">key</span></span> |
| <span data-ttu-id="ee391-261">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-261">**Data type**</span></span> | <span data-ttu-id="ee391-262">String</span><span class="sxs-lookup"><span data-stu-id="ee391-262">String</span></span> |
| <span data-ttu-id="ee391-263">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-263">**Possible values**</span></span> | <span data-ttu-id="ee391-264">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="ee391-264">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="ee391-265">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="ee391-265">archive_bomb</span></span> |
|||

<span data-ttu-id="ee391-266">**Действие**</span><span class="sxs-lookup"><span data-stu-id="ee391-266">**Action to take**</span></span>

<span data-ttu-id="ee391-267">Действия, которые необходимо принять при наступивших угрозах типа, указанного в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="ee391-267">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="ee391-268">Может быть:</span><span class="sxs-lookup"><span data-stu-id="ee391-268">Can be:</span></span>

- <span data-ttu-id="ee391-269">**Аудит.** Устройство не защищено от этого типа угрозы, но запись об угрозе регистрируется.</span><span class="sxs-lookup"><span data-stu-id="ee391-269">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="ee391-270">**Блок.** Устройство защищено от этого типа угрозы, и вы уведомлены в консоли безопасности.</span><span class="sxs-lookup"><span data-stu-id="ee391-270">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="ee391-271">**Отключено.** Устройство не защищено от этого типа угрозы и ничего не регистрируется.</span><span class="sxs-lookup"><span data-stu-id="ee391-271">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-272">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-272">**Key**</span></span> | <span data-ttu-id="ee391-273">значение</span><span class="sxs-lookup"><span data-stu-id="ee391-273">value</span></span> |
| <span data-ttu-id="ee391-274">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-274">**Data type**</span></span> | <span data-ttu-id="ee391-275">String</span><span class="sxs-lookup"><span data-stu-id="ee391-275">String</span></span> |
| <span data-ttu-id="ee391-276">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-276">**Possible values**</span></span> | <span data-ttu-id="ee391-277">аудит (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ee391-277">audit (default)</span></span> <br/> <span data-ttu-id="ee391-278">block</span><span class="sxs-lookup"><span data-stu-id="ee391-278">block</span></span> <br/> <span data-ttu-id="ee391-279">Off</span><span class="sxs-lookup"><span data-stu-id="ee391-279">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="ee391-280">Параметры типа угрозы объединяют политику слияния</span><span class="sxs-lookup"><span data-stu-id="ee391-280">Threat type settings merge policy</span></span>

<span data-ttu-id="ee391-281">Указывает политику слияния для параметров типа угроз.</span><span class="sxs-lookup"><span data-stu-id="ee391-281">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="ee391-282">Это может быть сочетание параметров, определенных администратором и определенных пользователем , или только параметров, определенных `merge` администратором ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="ee391-282">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="ee391-283">Этот параметр можно использовать, чтобы ограничить местным пользователям определение собственных параметров для различных типов угроз.</span><span class="sxs-lookup"><span data-stu-id="ee391-283">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-284">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-284">**Key**</span></span> | <span data-ttu-id="ee391-285">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="ee391-285">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="ee391-286">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-286">**Data type**</span></span> | <span data-ttu-id="ee391-287">String</span><span class="sxs-lookup"><span data-stu-id="ee391-287">String</span></span> |
| <span data-ttu-id="ee391-288">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-288">**Possible values**</span></span> | <span data-ttu-id="ee391-289">слияние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ee391-289">merge (default)</span></span> <br/> <span data-ttu-id="ee391-290">admin_only</span><span class="sxs-lookup"><span data-stu-id="ee391-290">admin_only</span></span> |
| <span data-ttu-id="ee391-291">**Comments**</span><span class="sxs-lookup"><span data-stu-id="ee391-291">**Comments**</span></span> | <span data-ttu-id="ee391-292">Доступно в Защитнике для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="ee391-292">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="ee391-293">Хранение истории антивирусного сканирования (в днях)</span><span class="sxs-lookup"><span data-stu-id="ee391-293">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="ee391-294">Укажите количество дней, которые сохраняются в истории сканирования на устройстве.</span><span class="sxs-lookup"><span data-stu-id="ee391-294">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="ee391-295">Старые результаты сканирования удаляются из истории.</span><span class="sxs-lookup"><span data-stu-id="ee391-295">Old scan results are removed from the history.</span></span> <span data-ttu-id="ee391-296">Старые карантинные файлы, которые также удаляются с диска.</span><span class="sxs-lookup"><span data-stu-id="ee391-296">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-297">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-297">**Key**</span></span> | <span data-ttu-id="ee391-298">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="ee391-298">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="ee391-299">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-299">**Data type**</span></span> | <span data-ttu-id="ee391-300">String</span><span class="sxs-lookup"><span data-stu-id="ee391-300">String</span></span> |
| <span data-ttu-id="ee391-301">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-301">**Possible values**</span></span> | <span data-ttu-id="ee391-302">90 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ee391-302">90 (default).</span></span> <span data-ttu-id="ee391-303">Допустимые значения от 1 дня до 180 дней.</span><span class="sxs-lookup"><span data-stu-id="ee391-303">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="ee391-304">**Comments**</span><span class="sxs-lookup"><span data-stu-id="ee391-304">**Comments**</span></span> | <span data-ttu-id="ee391-305">Доступно в Защитнике для конечной точки версии 101.04.76 или выше.</span><span class="sxs-lookup"><span data-stu-id="ee391-305">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="ee391-306">Максимальное количество элементов в истории антивирусного сканирования</span><span class="sxs-lookup"><span data-stu-id="ee391-306">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="ee391-307">Укажите максимальное количество записей, которые необходимо сохранить в истории сканирования.</span><span class="sxs-lookup"><span data-stu-id="ee391-307">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="ee391-308">Записи включают все проверки по запросу, выполняемые в прошлом, и все обнаружения антивирусов.</span><span class="sxs-lookup"><span data-stu-id="ee391-308">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-309">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-309">**Key**</span></span> | <span data-ttu-id="ee391-310">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="ee391-310">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="ee391-311">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-311">**Data type**</span></span> | <span data-ttu-id="ee391-312">String</span><span class="sxs-lookup"><span data-stu-id="ee391-312">String</span></span> |
| <span data-ttu-id="ee391-313">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-313">**Possible values**</span></span> | <span data-ttu-id="ee391-314">10000 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ee391-314">10000 (default).</span></span> <span data-ttu-id="ee391-315">Допустимые значения : от 5000 элементов до 15000 элементов.</span><span class="sxs-lookup"><span data-stu-id="ee391-315">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="ee391-316">**Comments**</span><span class="sxs-lookup"><span data-stu-id="ee391-316">**Comments**</span></span> | <span data-ttu-id="ee391-317">Доступно в Защитнике для конечной точки версии 101.04.76 или выше.</span><span class="sxs-lookup"><span data-stu-id="ee391-317">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="ee391-318">Параметры защиты с облачной доставкой</span><span class="sxs-lookup"><span data-stu-id="ee391-318">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="ee391-319">Запись *cloudService* в профиле конфигурации используется для настройки облачной функции защиты продукта.</span><span class="sxs-lookup"><span data-stu-id="ee391-319">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-320">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-320">**Key**</span></span> | <span data-ttu-id="ee391-321">cloudService</span><span class="sxs-lookup"><span data-stu-id="ee391-321">cloudService</span></span> |
| <span data-ttu-id="ee391-322">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-322">**Data type**</span></span> | <span data-ttu-id="ee391-323">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="ee391-323">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ee391-324">**Comments**</span><span class="sxs-lookup"><span data-stu-id="ee391-324">**Comments**</span></span> | <span data-ttu-id="ee391-325">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="ee391-325">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="ee391-326">Включить и отключить защиту от облачной доставки</span><span class="sxs-lookup"><span data-stu-id="ee391-326">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="ee391-327">Определяет, включена ли облачная защита на устройстве или нет.</span><span class="sxs-lookup"><span data-stu-id="ee391-327">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="ee391-328">Чтобы повысить безопасность ваших служб, рекомендуется сохранить эту функцию включенной.</span><span class="sxs-lookup"><span data-stu-id="ee391-328">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-329">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-329">**Key**</span></span> | <span data-ttu-id="ee391-330">включено</span><span class="sxs-lookup"><span data-stu-id="ee391-330">enabled</span></span> |
| <span data-ttu-id="ee391-331">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-331">**Data type**</span></span> | <span data-ttu-id="ee391-332">Логический</span><span class="sxs-lookup"><span data-stu-id="ee391-332">Boolean</span></span> |
| <span data-ttu-id="ee391-333">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-333">**Possible values**</span></span> | <span data-ttu-id="ee391-334">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ee391-334">true (default)</span></span> <br/> <span data-ttu-id="ee391-335">false</span><span class="sxs-lookup"><span data-stu-id="ee391-335">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="ee391-336">Уровень диагностической коллекции</span><span class="sxs-lookup"><span data-stu-id="ee391-336">Diagnostic collection level</span></span>

<span data-ttu-id="ee391-337">Диагностические данные используются для обеспечения безопасности и повышения безопасности Defender для конечной точки, обнаружения, диагностики и устранения проблем, а также улучшения продукта.</span><span class="sxs-lookup"><span data-stu-id="ee391-337">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="ee391-338">Этот параметр определяет уровень диагностики, отправленной продуктом в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ee391-338">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-339">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-339">**Key**</span></span> | <span data-ttu-id="ee391-340">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="ee391-340">diagnosticLevel</span></span> |
| <span data-ttu-id="ee391-341">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-341">**Data type**</span></span> | <span data-ttu-id="ee391-342">String</span><span class="sxs-lookup"><span data-stu-id="ee391-342">String</span></span> |
| <span data-ttu-id="ee391-343">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-343">**Possible values**</span></span> | <span data-ttu-id="ee391-344">необязательный (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ee391-344">optional (default)</span></span> <br/> <span data-ttu-id="ee391-345">Обязательный</span><span class="sxs-lookup"><span data-stu-id="ee391-345">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="ee391-346">Включить и отключить автоматические отправки образцов</span><span class="sxs-lookup"><span data-stu-id="ee391-346">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="ee391-347">Определяет, отправляются ли подозрительные образцы (которые могут содержать угрозы) в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ee391-347">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="ee391-348">Существует три уровня для управления отправкой примера:</span><span class="sxs-lookup"><span data-stu-id="ee391-348">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="ee391-349">**Нет:** никаких подозрительных образцов не передается в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ee391-349">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="ee391-350">**Сейф:** автоматически будут отправлены только подозрительные образцы, не содержащие личных сведений (PII).</span><span class="sxs-lookup"><span data-stu-id="ee391-350">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="ee391-351">Это значение по умолчанию для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="ee391-351">This is the default value for this setting.</span></span>
- <span data-ttu-id="ee391-352">**Все:** все подозрительные образцы отправлены в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ee391-352">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-353">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-353">**Key**</span></span> | <span data-ttu-id="ee391-354">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="ee391-354">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="ee391-355">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-355">**Data type**</span></span> | <span data-ttu-id="ee391-356">String</span><span class="sxs-lookup"><span data-stu-id="ee391-356">String</span></span> |
| <span data-ttu-id="ee391-357">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-357">**Possible values**</span></span> | <span data-ttu-id="ee391-358">нет</span><span class="sxs-lookup"><span data-stu-id="ee391-358">none</span></span> <br/> <span data-ttu-id="ee391-359">безопасный (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ee391-359">safe (default)</span></span> <br/> <span data-ttu-id="ee391-360">все</span><span class="sxs-lookup"><span data-stu-id="ee391-360">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="ee391-361">Включить и отключить автоматические обновления сведении о безопасности</span><span class="sxs-lookup"><span data-stu-id="ee391-361">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="ee391-362">Определяет, устанавливаются ли обновления разведки безопасности автоматически:</span><span class="sxs-lookup"><span data-stu-id="ee391-362">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="ee391-363">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="ee391-363">**Key**</span></span> | <span data-ttu-id="ee391-364">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="ee391-364">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="ee391-365">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ee391-365">**Data type**</span></span> | <span data-ttu-id="ee391-366">Логический</span><span class="sxs-lookup"><span data-stu-id="ee391-366">Boolean</span></span> |
| <span data-ttu-id="ee391-367">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="ee391-367">**Possible values**</span></span> | <span data-ttu-id="ee391-368">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ee391-368">true (default)</span></span> <br/> <span data-ttu-id="ee391-369">false</span><span class="sxs-lookup"><span data-stu-id="ee391-369">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="ee391-370">Рекомендуемый профиль конфигурации</span><span class="sxs-lookup"><span data-stu-id="ee391-370">Recommended configuration profile</span></span>

<span data-ttu-id="ee391-371">Чтобы начать работу, рекомендуется в следующем профиле конфигурации для предприятия воспользоваться всеми функциями защиты, которые предоставляет Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="ee391-371">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="ee391-372">Следующий профиль конфигурации:</span><span class="sxs-lookup"><span data-stu-id="ee391-372">The following configuration profile will:</span></span>

- <span data-ttu-id="ee391-373">Включить защиту в режиме реального времени (RTP)</span><span class="sxs-lookup"><span data-stu-id="ee391-373">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="ee391-374">Укажите, как обрабатываются следующие типы угроз:</span><span class="sxs-lookup"><span data-stu-id="ee391-374">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="ee391-375">**Потенциально нежелательные приложения (PUA)** заблокированы</span><span class="sxs-lookup"><span data-stu-id="ee391-375">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="ee391-376">**Архивные** бомбы (файл с высокой скоростью сжатия) проверяются в журналах продуктов</span><span class="sxs-lookup"><span data-stu-id="ee391-376">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="ee391-377">Включить автоматические обновления сведении о безопасности</span><span class="sxs-lookup"><span data-stu-id="ee391-377">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="ee391-378">Включение облачной защиты</span><span class="sxs-lookup"><span data-stu-id="ee391-378">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="ee391-379">Включить автоматическую отправку образца на `safe` уровне</span><span class="sxs-lookup"><span data-stu-id="ee391-379">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="ee391-380">Пример профиля</span><span class="sxs-lookup"><span data-stu-id="ee391-380">Sample profile</span></span>

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
      "enabled":true,
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="ee391-381">Пример профиля полной конфигурации</span><span class="sxs-lookup"><span data-stu-id="ee391-381">Full configuration profile example</span></span>

<span data-ttu-id="ee391-382">Следующий профиль конфигурации содержит записи для всех параметров, описанных в этом документе, и может использоваться для более сложных сценариев, в которых требуется больше контроля над продуктом.</span><span class="sxs-lookup"><span data-stu-id="ee391-382">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="ee391-383">Полный профиль</span><span class="sxs-lookup"><span data-stu-id="ee391-383">Full profile</span></span>

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
            "path":"/run"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home/*/git"
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
      "automaticDefinitionUpdateEnabled":true,
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="ee391-384">Проверка профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="ee391-384">Configuration profile validation</span></span>

<span data-ttu-id="ee391-385">Профиль конфигурации должен быть допустимым JSON-форматированный файл.</span><span class="sxs-lookup"><span data-stu-id="ee391-385">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="ee391-386">Существует ряд средств, которые можно использовать для проверки этого.</span><span class="sxs-lookup"><span data-stu-id="ee391-386">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="ee391-387">Например, если вы установили `python` на устройстве:</span><span class="sxs-lookup"><span data-stu-id="ee391-387">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="ee391-388">Если JSON хорошо сформирован, вышеуказанная команда выводит его обратно в терминал и возвращает код выхода `0` .</span><span class="sxs-lookup"><span data-stu-id="ee391-388">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="ee391-389">В противном случае отображается ошибка, описываемая проблемой, и команда возвращает код выхода `1` .</span><span class="sxs-lookup"><span data-stu-id="ee391-389">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="ee391-390">Проверка того, mdatp_managed.jsфайл работает как ожидалось</span><span class="sxs-lookup"><span data-stu-id="ee391-390">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="ee391-391">Чтобы убедиться, что ваш /etc/opt/microsoft/mdatp/managed/mdatp_managed.jsработает должным образом, рядом с этими настройками следует увидеть "[managed]":</span><span class="sxs-lookup"><span data-stu-id="ee391-391">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>  
- <span data-ttu-id="ee391-392">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="ee391-392">cloud_enabled</span></span>
- <span data-ttu-id="ee391-393">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="ee391-393">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="ee391-394">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="ee391-394">passice_mode_enabled</span></span>
- <span data-ttu-id="ee391-395">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="ee391-395">real_time_protection_enabled</span></span>
- <span data-ttu-id="ee391-396">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="ee391-396">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="ee391-397">Чтобы mdatp_managed.jsвступил в силу, перезагрузка wdavdaemon не требуется.</span><span class="sxs-lookup"><span data-stu-id="ee391-397">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="ee391-398">Развертывание профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="ee391-398">Configuration profile deployment</span></span>

<span data-ttu-id="ee391-399">После создания профиля конфигурации для предприятия его можно развернуть с помощью средства управления, используемом вашим предприятием.</span><span class="sxs-lookup"><span data-stu-id="ee391-399">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="ee391-400">Защитник для конечной точки на Linux читает управляемой конфигурации из */etc/opt/microsoft/mdatp/managed/mdatp_managed.jsв* файле.</span><span class="sxs-lookup"><span data-stu-id="ee391-400">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
