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
ms.openlocfilehash: 7998e878ad03fdfb64c314dc8b7234ece46164ce
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289497"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="06e43-104">Настройка предпочтений для Microsoft Defender для конечной точки в Linux</span><span class="sxs-lookup"><span data-stu-id="06e43-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="06e43-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="06e43-105">**Applies to:**</span></span>
- [<span data-ttu-id="06e43-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="06e43-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="06e43-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="06e43-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="06e43-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="06e43-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="06e43-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="06e43-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="06e43-110">В этом разделе содержатся инструкции по выбору предпочтений для Defender для конечной точки в Linux в корпоративных средах.</span><span class="sxs-lookup"><span data-stu-id="06e43-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="06e43-111">Если вы заинтересованы в настройке продукта на устройстве из командной строки, см. [в этой строке Ресурсы.](linux-resources.md#configure-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="06e43-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="06e43-112">В корпоративных средах управление Защитником для конечной точки на Linux можно с помощью профиля конфигурации.</span><span class="sxs-lookup"><span data-stu-id="06e43-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="06e43-113">Этот профиль развернут из средства управления по вашему выбору.</span><span class="sxs-lookup"><span data-stu-id="06e43-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="06e43-114">Предпочтения, управляемые предприятием, имеют приоритет над предпочтениями, установленными локально на устройстве.</span><span class="sxs-lookup"><span data-stu-id="06e43-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="06e43-115">Другими словами, пользователи в вашем предприятии не могут изменять предпочтения, задав этот профиль конфигурации.</span><span class="sxs-lookup"><span data-stu-id="06e43-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="06e43-116">В этой статье описывается структура этого профиля (включая рекомендуемый профиль, который можно использовать для начала работы) и инструкции по развертыванию профиля.</span><span class="sxs-lookup"><span data-stu-id="06e43-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="06e43-117">Структура профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="06e43-117">Configuration profile structure</span></span>

<span data-ttu-id="06e43-118">Профиль конфигурации — это файл .json, состоящий из записей, идентифицированных ключом (который обозначает имя предпочтения), за которым следует значение, которое зависит от характера предпочтения.</span><span class="sxs-lookup"><span data-stu-id="06e43-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="06e43-119">Значения могут быть простыми, такими как численное значение или сложные, например вложенный список предпочтений.</span><span class="sxs-lookup"><span data-stu-id="06e43-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="06e43-120">Обычно для нажима файла с именем в расположении используется средство управления ```mdatp_managed.json``` ```/etc/opt/microsoft/mdatp/managed/``` конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="06e43-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="06e43-121">Верхний уровень профиля конфигурации включает в себя все продукты и записи для subareas продукта, которые подробно объясняются в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="06e43-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="06e43-122">Параметры антивирусного двигателя</span><span class="sxs-lookup"><span data-stu-id="06e43-122">Antivirus engine preferences</span></span>

<span data-ttu-id="06e43-123">Раздел *antivirusEngine* профиля конфигурации используется для управления предпочтениями антивирусного компонента продукта.</span><span class="sxs-lookup"><span data-stu-id="06e43-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

<br>

****

|<span data-ttu-id="06e43-124">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-124">Description</span></span>|<span data-ttu-id="06e43-125">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-125">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-126">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-126">**Key**</span></span>|<span data-ttu-id="06e43-127">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="06e43-127">antivirusEngine</span></span>|
|<span data-ttu-id="06e43-128">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-128">**Data type**</span></span>|<span data-ttu-id="06e43-129">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="06e43-129">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="06e43-130">**Comments**</span><span class="sxs-lookup"><span data-stu-id="06e43-130">**Comments**</span></span>|<span data-ttu-id="06e43-131">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="06e43-131">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="06e43-132">Включить и отключить защиту в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="06e43-132">Enable / disable real-time protection</span></span>

<span data-ttu-id="06e43-133">Определяет, включена ли защита в режиме реального времени (сканировать файлы по мере их доступа).</span><span class="sxs-lookup"><span data-stu-id="06e43-133">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

<br>

****

|<span data-ttu-id="06e43-134">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-134">Description</span></span>|<span data-ttu-id="06e43-135">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-135">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-136">**Key**</span></span>|<span data-ttu-id="06e43-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="06e43-137">enableRealTimeProtection</span></span>|
|<span data-ttu-id="06e43-138">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-138">**Data type**</span></span>|<span data-ttu-id="06e43-139">Логический</span><span class="sxs-lookup"><span data-stu-id="06e43-139">Boolean</span></span>|
|<span data-ttu-id="06e43-140">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-140">**Possible values**</span></span>|<span data-ttu-id="06e43-141">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="06e43-141">true (default)</span></span> <p> <span data-ttu-id="06e43-142">false</span><span class="sxs-lookup"><span data-stu-id="06e43-142">false</span></span>|
|

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="06e43-143">Включить и отключить пассивный режим</span><span class="sxs-lookup"><span data-stu-id="06e43-143">Enable / disable passive mode</span></span>

<span data-ttu-id="06e43-144">Определяет, работает ли антивирусный двигатель в пассивном режиме или нет.</span><span class="sxs-lookup"><span data-stu-id="06e43-144">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="06e43-145">В пассивном режиме:</span><span class="sxs-lookup"><span data-stu-id="06e43-145">In passive mode:</span></span>

- <span data-ttu-id="06e43-146">Защита в режиме реального времени отключена.</span><span class="sxs-lookup"><span data-stu-id="06e43-146">Real-time protection is turned off.</span></span>
- <span data-ttu-id="06e43-147">Сканирование по запросу включено.</span><span class="sxs-lookup"><span data-stu-id="06e43-147">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="06e43-148">Автоматическое устранение угрозы отключено.</span><span class="sxs-lookup"><span data-stu-id="06e43-148">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="06e43-149">Включаем обновления разведки безопасности.</span><span class="sxs-lookup"><span data-stu-id="06e43-149">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="06e43-150">Значок меню состояния скрыт.</span><span class="sxs-lookup"><span data-stu-id="06e43-150">Status menu icon is hidden.</span></span>

<br>

****

|<span data-ttu-id="06e43-151">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-151">Description</span></span>|<span data-ttu-id="06e43-152">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-152">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-153">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-153">**Key**</span></span>|<span data-ttu-id="06e43-154">passiveMode</span><span class="sxs-lookup"><span data-stu-id="06e43-154">passiveMode</span></span>|
|<span data-ttu-id="06e43-155">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-155">**Data type**</span></span>|<span data-ttu-id="06e43-156">Логический</span><span class="sxs-lookup"><span data-stu-id="06e43-156">Boolean</span></span>|
|<span data-ttu-id="06e43-157">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-157">**Possible values**</span></span>|<span data-ttu-id="06e43-158">false (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="06e43-158">false (default)</span></span> <p> <span data-ttu-id="06e43-159">true</span><span class="sxs-lookup"><span data-stu-id="06e43-159">true</span></span>|
|<span data-ttu-id="06e43-160">**Comments**</span><span class="sxs-lookup"><span data-stu-id="06e43-160">**Comments**</span></span>|<span data-ttu-id="06e43-161">Доступно в Защитнике для конечной точки версии 100.67.60 или выше.</span><span class="sxs-lookup"><span data-stu-id="06e43-161">Available in Defender for Endpoint version 100.67.60 or higher.</span></span>|
|

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="06e43-162">Политика слияния исключений</span><span class="sxs-lookup"><span data-stu-id="06e43-162">Exclusion merge policy</span></span>

<span data-ttu-id="06e43-163">Указывает политику слияния исключений.</span><span class="sxs-lookup"><span data-stu-id="06e43-163">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="06e43-164">Это может быть сочетание исключений, определенных администратором и пользователей , или только исключений, определенных `merge` администратором ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="06e43-164">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="06e43-165">Этот параметр можно использовать, чтобы ограничить местным пользователям определение собственных исключений.</span><span class="sxs-lookup"><span data-stu-id="06e43-165">This setting can be used to restrict local users from defining their own exclusions.</span></span>

<br>

****

|<span data-ttu-id="06e43-166">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-166">Description</span></span>|<span data-ttu-id="06e43-167">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-167">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-168">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-168">**Key**</span></span>|<span data-ttu-id="06e43-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="06e43-169">exclusionsMergePolicy</span></span>|
|<span data-ttu-id="06e43-170">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-170">**Data type**</span></span>|<span data-ttu-id="06e43-171">String</span><span class="sxs-lookup"><span data-stu-id="06e43-171">String</span></span>|
|<span data-ttu-id="06e43-172">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-172">**Possible values**</span></span>|<span data-ttu-id="06e43-173">слияние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="06e43-173">merge (default)</span></span> <p> <span data-ttu-id="06e43-174">admin_only</span><span class="sxs-lookup"><span data-stu-id="06e43-174">admin_only</span></span>|
|<span data-ttu-id="06e43-175">**Comments**</span><span class="sxs-lookup"><span data-stu-id="06e43-175">**Comments**</span></span>|<span data-ttu-id="06e43-176">Доступно в Защитнике для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="06e43-176">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="scan-exclusions"></a><span data-ttu-id="06e43-177">Исключения сканирования</span><span class="sxs-lookup"><span data-stu-id="06e43-177">Scan exclusions</span></span>

<span data-ttu-id="06e43-178">Объекты, которые были исключены из проверки.</span><span class="sxs-lookup"><span data-stu-id="06e43-178">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="06e43-179">Исключения могут быть указаны полными путями, расширениями или именами файлов.</span><span class="sxs-lookup"><span data-stu-id="06e43-179">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="06e43-180">(Исключения заданы в качестве массива элементов, администратор может указать столько элементов, сколько необходимо, в любом порядке.)</span><span class="sxs-lookup"><span data-stu-id="06e43-180">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

<br>

****

|<span data-ttu-id="06e43-181">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-181">Description</span></span>|<span data-ttu-id="06e43-182">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-182">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-183">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-183">**Key**</span></span>|<span data-ttu-id="06e43-184">исключения</span><span class="sxs-lookup"><span data-stu-id="06e43-184">exclusions</span></span>|
|<span data-ttu-id="06e43-185">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-185">**Data type**</span></span>|<span data-ttu-id="06e43-186">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="06e43-186">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="06e43-187">**Comments**</span><span class="sxs-lookup"><span data-stu-id="06e43-187">**Comments**</span></span>|<span data-ttu-id="06e43-188">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="06e43-188">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="type-of-exclusion"></a><span data-ttu-id="06e43-189">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="06e43-189">Type of exclusion</span></span>

<span data-ttu-id="06e43-190">Указывает тип контента, исключенного из проверки.</span><span class="sxs-lookup"><span data-stu-id="06e43-190">Specifies the type of content excluded from the scan.</span></span>

<br>

****

|<span data-ttu-id="06e43-191">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-191">Description</span></span>|<span data-ttu-id="06e43-192">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-192">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-193">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-193">**Key**</span></span>|<span data-ttu-id="06e43-194">$type</span><span class="sxs-lookup"><span data-stu-id="06e43-194">$type</span></span>|
|<span data-ttu-id="06e43-195">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-195">**Data type**</span></span>|<span data-ttu-id="06e43-196">String</span><span class="sxs-lookup"><span data-stu-id="06e43-196">String</span></span>|
|<span data-ttu-id="06e43-197">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-197">**Possible values**</span></span>|<span data-ttu-id="06e43-198">excludedPath</span><span class="sxs-lookup"><span data-stu-id="06e43-198">excludedPath</span></span> <p> <span data-ttu-id="06e43-199">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="06e43-199">excludedFileExtension</span></span> <p> <span data-ttu-id="06e43-200">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="06e43-200">excludedFileName</span></span>|
|

##### <a name="path-to-excluded-content"></a><span data-ttu-id="06e43-201">Путь к исключению контента</span><span class="sxs-lookup"><span data-stu-id="06e43-201">Path to excluded content</span></span>

<span data-ttu-id="06e43-202">Используется для исключения контента из сканирования путем полного файла.</span><span class="sxs-lookup"><span data-stu-id="06e43-202">Used to exclude content from the scan by full file path.</span></span>

<br>

****

|<span data-ttu-id="06e43-203">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-203">Description</span></span>|<span data-ttu-id="06e43-204">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-204">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-205">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-205">**Key**</span></span>|<span data-ttu-id="06e43-206">path</span><span class="sxs-lookup"><span data-stu-id="06e43-206">path</span></span>|
|<span data-ttu-id="06e43-207">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-207">**Data type**</span></span>|<span data-ttu-id="06e43-208">String</span><span class="sxs-lookup"><span data-stu-id="06e43-208">String</span></span>|
|<span data-ttu-id="06e43-209">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-209">**Possible values**</span></span>|<span data-ttu-id="06e43-210">допустимые пути</span><span class="sxs-lookup"><span data-stu-id="06e43-210">valid paths</span></span>|
|<span data-ttu-id="06e43-211">**Comments**</span><span class="sxs-lookup"><span data-stu-id="06e43-211">**Comments**</span></span>|<span data-ttu-id="06e43-212">Применимо только если *$type* *исключенPath*</span><span class="sxs-lookup"><span data-stu-id="06e43-212">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="path-type-file--directory"></a><span data-ttu-id="06e43-213">Тип пути (файл / каталог)</span><span class="sxs-lookup"><span data-stu-id="06e43-213">Path type (file / directory)</span></span>

<span data-ttu-id="06e43-214">Указывает, *относится ли* свойство пути к файлу или каталогу.</span><span class="sxs-lookup"><span data-stu-id="06e43-214">Indicates if the *path* property refers to a file or directory.</span></span>

<br>

****

|<span data-ttu-id="06e43-215">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-215">Description</span></span>|<span data-ttu-id="06e43-216">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-216">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-217">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-217">**Key**</span></span>|<span data-ttu-id="06e43-218">isDirectory</span><span class="sxs-lookup"><span data-stu-id="06e43-218">isDirectory</span></span>|
|<span data-ttu-id="06e43-219">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-219">**Data type**</span></span>|<span data-ttu-id="06e43-220">Логический</span><span class="sxs-lookup"><span data-stu-id="06e43-220">Boolean</span></span>|
|<span data-ttu-id="06e43-221">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-221">**Possible values**</span></span>|<span data-ttu-id="06e43-222">false (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="06e43-222">false (default)</span></span> <p> <span data-ttu-id="06e43-223">true</span><span class="sxs-lookup"><span data-stu-id="06e43-223">true</span></span>|
|<span data-ttu-id="06e43-224">**Comments**</span><span class="sxs-lookup"><span data-stu-id="06e43-224">**Comments**</span></span>|<span data-ttu-id="06e43-225">Применимо только если *$type* *исключенPath*</span><span class="sxs-lookup"><span data-stu-id="06e43-225">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="06e43-226">Расширение файла, исключено из сканирования</span><span class="sxs-lookup"><span data-stu-id="06e43-226">File extension excluded from the scan</span></span>

<span data-ttu-id="06e43-227">Используется для исключения контента из сканирования с помощью расширения файла.</span><span class="sxs-lookup"><span data-stu-id="06e43-227">Used to exclude content from the scan by file extension.</span></span>

<br>

****

|<span data-ttu-id="06e43-228">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-228">Description</span></span>|<span data-ttu-id="06e43-229">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-229">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-230">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-230">**Key**</span></span>|<span data-ttu-id="06e43-231">расширение</span><span class="sxs-lookup"><span data-stu-id="06e43-231">extension</span></span>|
|<span data-ttu-id="06e43-232">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-232">**Data type**</span></span>|<span data-ttu-id="06e43-233">String</span><span class="sxs-lookup"><span data-stu-id="06e43-233">String</span></span>|
|<span data-ttu-id="06e43-234">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-234">**Possible values**</span></span>|<span data-ttu-id="06e43-235">допустимые расширения файлов</span><span class="sxs-lookup"><span data-stu-id="06e43-235">valid file extensions</span></span>|
|<span data-ttu-id="06e43-236">**Comments**</span><span class="sxs-lookup"><span data-stu-id="06e43-236">**Comments**</span></span>|<span data-ttu-id="06e43-237">Применимо только если *$type* *исключеноFileExtension*</span><span class="sxs-lookup"><span data-stu-id="06e43-237">Applicable only if *$type* is *excludedFileExtension*</span></span>|
|

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="06e43-238">Процесс, исключенный из сканирования\*</span><span class="sxs-lookup"><span data-stu-id="06e43-238">Process excluded from the scan\*</span></span>

<span data-ttu-id="06e43-239">Указывает процесс, для которого все действия файла исключены из сканирования.</span><span class="sxs-lookup"><span data-stu-id="06e43-239">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="06e43-240">Процесс может быть указан либо по имени (например, ) или `cat` по полному пути (например, `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="06e43-240">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

<br>

****

|<span data-ttu-id="06e43-241">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-241">Description</span></span>|<span data-ttu-id="06e43-242">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-242">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-243">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-243">**Key**</span></span>|<span data-ttu-id="06e43-244">name</span><span class="sxs-lookup"><span data-stu-id="06e43-244">name</span></span>|
|<span data-ttu-id="06e43-245">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-245">**Data type**</span></span>|<span data-ttu-id="06e43-246">String</span><span class="sxs-lookup"><span data-stu-id="06e43-246">String</span></span>|
|<span data-ttu-id="06e43-247">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-247">**Possible values**</span></span>|<span data-ttu-id="06e43-248">любая строка</span><span class="sxs-lookup"><span data-stu-id="06e43-248">any string</span></span>|
|<span data-ttu-id="06e43-249">**Comments**</span><span class="sxs-lookup"><span data-stu-id="06e43-249">**Comments**</span></span>|<span data-ttu-id="06e43-250">Применимо только *если $type* *исключеноFileName*</span><span class="sxs-lookup"><span data-stu-id="06e43-250">Applicable only if *$type* is *excludedFileName*</span></span>|
|

#### <a name="allowed-threats"></a><span data-ttu-id="06e43-251">Разрешенные угрозы</span><span class="sxs-lookup"><span data-stu-id="06e43-251">Allowed threats</span></span>

<span data-ttu-id="06e43-252">Список угроз (идентифицированных по их имени), которые не заблокированы продуктом и разрешены к запуску.</span><span class="sxs-lookup"><span data-stu-id="06e43-252">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

<br>

****

|<span data-ttu-id="06e43-253">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-253">Description</span></span>|<span data-ttu-id="06e43-254">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-254">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-255">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-255">**Key**</span></span>|<span data-ttu-id="06e43-256">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="06e43-256">allowedThreats</span></span>|
|<span data-ttu-id="06e43-257">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-257">**Data type**</span></span>|<span data-ttu-id="06e43-258">Массив строк</span><span class="sxs-lookup"><span data-stu-id="06e43-258">Array of strings</span></span>|
|

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="06e43-259">Действия с неустановляемой угрозой</span><span class="sxs-lookup"><span data-stu-id="06e43-259">Disallowed threat actions</span></span>

<span data-ttu-id="06e43-260">Ограничивает действия, которые может принимать локальный пользователь устройства при обнаружении угроз.</span><span class="sxs-lookup"><span data-stu-id="06e43-260">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="06e43-261">Действия, включенные в этот список, не отображаются в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="06e43-261">The actions included in this list are not displayed in the user interface.</span></span>

<br>

****

|<span data-ttu-id="06e43-262">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-262">Description</span></span>|<span data-ttu-id="06e43-263">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-263">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-264">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-264">**Key**</span></span>|<span data-ttu-id="06e43-265">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="06e43-265">disallowedThreatActions</span></span>|
|<span data-ttu-id="06e43-266">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-266">**Data type**</span></span>|<span data-ttu-id="06e43-267">Массив строк</span><span class="sxs-lookup"><span data-stu-id="06e43-267">Array of strings</span></span>|
|<span data-ttu-id="06e43-268">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-268">**Possible values**</span></span>|<span data-ttu-id="06e43-269">разрешить (ограничивает пользователей от допуска угроз)</span><span class="sxs-lookup"><span data-stu-id="06e43-269">allow (restricts users from allowing threats)</span></span> <p> <span data-ttu-id="06e43-270">восстановление (ограничивает пользователей от восстановления угроз из карантина)</span><span class="sxs-lookup"><span data-stu-id="06e43-270">restore (restricts users from restoring threats from the quarantine)</span></span>|
|<span data-ttu-id="06e43-271">**Comments**</span><span class="sxs-lookup"><span data-stu-id="06e43-271">**Comments**</span></span>|<span data-ttu-id="06e43-272">Доступно в Защитнике для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="06e43-272">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="threat-type-settings"></a><span data-ttu-id="06e43-273">Параметры типа угроз</span><span class="sxs-lookup"><span data-stu-id="06e43-273">Threat type settings</span></span>

<span data-ttu-id="06e43-274">Предпочтение *threatTypeSettings* в антивирусном движке используется для управления обработкой определенных типов угроз продуктом.</span><span class="sxs-lookup"><span data-stu-id="06e43-274">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

<br>

****

|<span data-ttu-id="06e43-275">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-275">Description</span></span>|<span data-ttu-id="06e43-276">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-276">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-277">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-277">**Key**</span></span>|<span data-ttu-id="06e43-278">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="06e43-278">threatTypeSettings</span></span>|
|<span data-ttu-id="06e43-279">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-279">**Data type**</span></span>|<span data-ttu-id="06e43-280">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="06e43-280">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="06e43-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="06e43-281">**Comments**</span></span>|<span data-ttu-id="06e43-282">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="06e43-282">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="threat-type"></a><span data-ttu-id="06e43-283">Тип угрозы</span><span class="sxs-lookup"><span data-stu-id="06e43-283">Threat type</span></span>

<span data-ttu-id="06e43-284">Тип угрозы, для которой настроено поведение.</span><span class="sxs-lookup"><span data-stu-id="06e43-284">Type of threat for which the behavior is configured.</span></span>

<br>

****

|<span data-ttu-id="06e43-285">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-285">Description</span></span>|<span data-ttu-id="06e43-286">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-286">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-287">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-287">**Key**</span></span>|<span data-ttu-id="06e43-288">ключа</span><span class="sxs-lookup"><span data-stu-id="06e43-288">key</span></span>|
|<span data-ttu-id="06e43-289">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-289">**Data type**</span></span>|<span data-ttu-id="06e43-290">String</span><span class="sxs-lookup"><span data-stu-id="06e43-290">String</span></span>|
|<span data-ttu-id="06e43-291">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-291">**Possible values**</span></span>|<span data-ttu-id="06e43-292">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="06e43-292">potentially_unwanted_application</span></span> <p> <span data-ttu-id="06e43-293">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="06e43-293">archive_bomb</span></span>|
|

##### <a name="action-to-take"></a><span data-ttu-id="06e43-294">Действие</span><span class="sxs-lookup"><span data-stu-id="06e43-294">Action to take</span></span>

<span data-ttu-id="06e43-295">Действия, которые необходимо принять при наступивших угрозах типа, указанного в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="06e43-295">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="06e43-296">Может быть:</span><span class="sxs-lookup"><span data-stu-id="06e43-296">Can be:</span></span>

- <span data-ttu-id="06e43-297">**Аудит.** Устройство не защищено от этого типа угрозы, но запись об угрозе регистрируется.</span><span class="sxs-lookup"><span data-stu-id="06e43-297">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="06e43-298">**Блок.** Устройство защищено от этого типа угрозы, и вы уведомлены в консоли безопасности.</span><span class="sxs-lookup"><span data-stu-id="06e43-298">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="06e43-299">**Отключено.** Устройство не защищено от этого типа угрозы и ничего не регистрируется.</span><span class="sxs-lookup"><span data-stu-id="06e43-299">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

<br>

****

|<span data-ttu-id="06e43-300">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-300">Description</span></span>|<span data-ttu-id="06e43-301">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-301">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-302">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-302">**Key**</span></span>|<span data-ttu-id="06e43-303">значение</span><span class="sxs-lookup"><span data-stu-id="06e43-303">value</span></span>|
|<span data-ttu-id="06e43-304">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-304">**Data type**</span></span>|<span data-ttu-id="06e43-305">String</span><span class="sxs-lookup"><span data-stu-id="06e43-305">String</span></span>|
|<span data-ttu-id="06e43-306">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-306">**Possible values**</span></span>|<span data-ttu-id="06e43-307">аудит (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="06e43-307">audit (default)</span></span> <p> <span data-ttu-id="06e43-308">block</span><span class="sxs-lookup"><span data-stu-id="06e43-308">block</span></span> <p> <span data-ttu-id="06e43-309">Off</span><span class="sxs-lookup"><span data-stu-id="06e43-309">off</span></span>|
|

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="06e43-310">Параметры типа угрозы объединяют политику слияния</span><span class="sxs-lookup"><span data-stu-id="06e43-310">Threat type settings merge policy</span></span>

<span data-ttu-id="06e43-311">Указывает политику слияния для параметров типа угроз.</span><span class="sxs-lookup"><span data-stu-id="06e43-311">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="06e43-312">Это может быть сочетание параметров, определенных администратором и определенных пользователем , или только параметров, определенных `merge` администратором ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="06e43-312">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="06e43-313">Этот параметр можно использовать, чтобы ограничить местным пользователям определение собственных параметров для различных типов угроз.</span><span class="sxs-lookup"><span data-stu-id="06e43-313">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

<br>

****

|<span data-ttu-id="06e43-314">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-314">Description</span></span>|<span data-ttu-id="06e43-315">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-315">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-316">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-316">**Key**</span></span>|<span data-ttu-id="06e43-317">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="06e43-317">threatTypeSettingsMergePolicy</span></span>|
|<span data-ttu-id="06e43-318">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-318">**Data type**</span></span>|<span data-ttu-id="06e43-319">String</span><span class="sxs-lookup"><span data-stu-id="06e43-319">String</span></span>|
|<span data-ttu-id="06e43-320">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-320">**Possible values**</span></span>|<span data-ttu-id="06e43-321">слияние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="06e43-321">merge (default)</span></span> <p> <span data-ttu-id="06e43-322">admin_only</span><span class="sxs-lookup"><span data-stu-id="06e43-322">admin_only</span></span>|
|<span data-ttu-id="06e43-323">**Comments**</span><span class="sxs-lookup"><span data-stu-id="06e43-323">**Comments**</span></span>|<span data-ttu-id="06e43-324">Доступно в Защитнике для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="06e43-324">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="06e43-325">Хранение истории антивирусного сканирования (в днях)</span><span class="sxs-lookup"><span data-stu-id="06e43-325">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="06e43-326">Укажите количество дней, которые сохраняются в истории сканирования на устройстве.</span><span class="sxs-lookup"><span data-stu-id="06e43-326">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="06e43-327">Старые результаты сканирования удаляются из истории.</span><span class="sxs-lookup"><span data-stu-id="06e43-327">Old scan results are removed from the history.</span></span> <span data-ttu-id="06e43-328">Старые карантинные файлы, которые также удаляются с диска.</span><span class="sxs-lookup"><span data-stu-id="06e43-328">Old quarantined files that are also removed from the disk.</span></span>

<br>

****

|<span data-ttu-id="06e43-329">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-329">Description</span></span>|<span data-ttu-id="06e43-330">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-330">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-331">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-331">**Key**</span></span>|<span data-ttu-id="06e43-332">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="06e43-332">scanResultsRetentionDays</span></span>|
|<span data-ttu-id="06e43-333">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-333">**Data type**</span></span>|<span data-ttu-id="06e43-334">String</span><span class="sxs-lookup"><span data-stu-id="06e43-334">String</span></span>|
|<span data-ttu-id="06e43-335">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-335">**Possible values**</span></span>|<span data-ttu-id="06e43-336">90 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="06e43-336">90 (default).</span></span> <span data-ttu-id="06e43-337">Допустимые значения от 1 дня до 180 дней.</span><span class="sxs-lookup"><span data-stu-id="06e43-337">Allowed values are from 1 day to 180 days.</span></span>|
|<span data-ttu-id="06e43-338">**Comments**</span><span class="sxs-lookup"><span data-stu-id="06e43-338">**Comments**</span></span>|<span data-ttu-id="06e43-339">Доступно в Защитнике для конечной точки версии 101.04.76 или выше.</span><span class="sxs-lookup"><span data-stu-id="06e43-339">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="06e43-340">Максимальное количество элементов в истории антивирусного сканирования</span><span class="sxs-lookup"><span data-stu-id="06e43-340">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="06e43-341">Укажите максимальное количество записей, которые необходимо сохранить в истории сканирования.</span><span class="sxs-lookup"><span data-stu-id="06e43-341">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="06e43-342">Записи включают все проверки по запросу, выполняемые в прошлом, и все обнаружения антивирусов.</span><span class="sxs-lookup"><span data-stu-id="06e43-342">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

<br>

****

|<span data-ttu-id="06e43-343">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-343">Description</span></span>|<span data-ttu-id="06e43-344">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-344">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-345">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-345">**Key**</span></span>|<span data-ttu-id="06e43-346">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="06e43-346">scanHistoryMaximumItems</span></span>|
|<span data-ttu-id="06e43-347">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-347">**Data type**</span></span>|<span data-ttu-id="06e43-348">String</span><span class="sxs-lookup"><span data-stu-id="06e43-348">String</span></span>|
|<span data-ttu-id="06e43-349">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-349">**Possible values**</span></span>|<span data-ttu-id="06e43-350">10000 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="06e43-350">10000 (default).</span></span> <span data-ttu-id="06e43-351">Допустимые значения : от 5000 элементов до 15000 элементов.</span><span class="sxs-lookup"><span data-stu-id="06e43-351">Allowed values are from 5000 items to 15000 items.</span></span>|
|<span data-ttu-id="06e43-352">**Comments**</span><span class="sxs-lookup"><span data-stu-id="06e43-352">**Comments**</span></span>|<span data-ttu-id="06e43-353">Доступно в Защитнике для конечной точки версии 101.04.76 или выше.</span><span class="sxs-lookup"><span data-stu-id="06e43-353">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="06e43-354">Параметры защиты с облачной доставкой</span><span class="sxs-lookup"><span data-stu-id="06e43-354">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="06e43-355">Запись *cloudService* в профиле конфигурации используется для настройки облачной функции защиты продукта.</span><span class="sxs-lookup"><span data-stu-id="06e43-355">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

<br>

****

|<span data-ttu-id="06e43-356">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-356">Description</span></span>|<span data-ttu-id="06e43-357">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-357">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-358">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-358">**Key**</span></span>|<span data-ttu-id="06e43-359">cloudService</span><span class="sxs-lookup"><span data-stu-id="06e43-359">cloudService</span></span>|
|<span data-ttu-id="06e43-360">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-360">**Data type**</span></span>|<span data-ttu-id="06e43-361">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="06e43-361">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="06e43-362">**Comments**</span><span class="sxs-lookup"><span data-stu-id="06e43-362">**Comments**</span></span>|<span data-ttu-id="06e43-363">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="06e43-363">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="06e43-364">Включить и отключить защиту от облачной доставки</span><span class="sxs-lookup"><span data-stu-id="06e43-364">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="06e43-365">Определяет, включена ли облачная защита на устройстве или нет.</span><span class="sxs-lookup"><span data-stu-id="06e43-365">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="06e43-366">Чтобы повысить безопасность ваших служб, рекомендуется сохранить эту функцию включенной.</span><span class="sxs-lookup"><span data-stu-id="06e43-366">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

<br>

****

|<span data-ttu-id="06e43-367">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-367">Description</span></span>|<span data-ttu-id="06e43-368">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-368">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-369">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-369">**Key**</span></span>|<span data-ttu-id="06e43-370">включено</span><span class="sxs-lookup"><span data-stu-id="06e43-370">enabled</span></span>|
|<span data-ttu-id="06e43-371">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-371">**Data type**</span></span>|<span data-ttu-id="06e43-372">Логический</span><span class="sxs-lookup"><span data-stu-id="06e43-372">Boolean</span></span>|
|<span data-ttu-id="06e43-373">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-373">**Possible values**</span></span>|<span data-ttu-id="06e43-374">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="06e43-374">true (default)</span></span> <p> <span data-ttu-id="06e43-375">false</span><span class="sxs-lookup"><span data-stu-id="06e43-375">false</span></span>|
|

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="06e43-376">Уровень диагностической коллекции</span><span class="sxs-lookup"><span data-stu-id="06e43-376">Diagnostic collection level</span></span>

<span data-ttu-id="06e43-377">Диагностические данные используются для обеспечения безопасности и повышения безопасности Defender для конечной точки, обнаружения, диагностики и устранения проблем, а также улучшения продукта.</span><span class="sxs-lookup"><span data-stu-id="06e43-377">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="06e43-378">Этот параметр определяет уровень диагностики, отправленной продуктом в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="06e43-378">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="06e43-379">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-379">Description</span></span>|<span data-ttu-id="06e43-380">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-380">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-381">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-381">**Key**</span></span>|<span data-ttu-id="06e43-382">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="06e43-382">diagnosticLevel</span></span>|
|<span data-ttu-id="06e43-383">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-383">**Data type**</span></span>|<span data-ttu-id="06e43-384">String</span><span class="sxs-lookup"><span data-stu-id="06e43-384">String</span></span>|
|<span data-ttu-id="06e43-385">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-385">**Possible values**</span></span>|<span data-ttu-id="06e43-386">необязательный (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="06e43-386">optional (default)</span></span> <p> <span data-ttu-id="06e43-387">Обязательный</span><span class="sxs-lookup"><span data-stu-id="06e43-387">required</span></span>|
|

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="06e43-388">Включить и отключить автоматические отправки образцов</span><span class="sxs-lookup"><span data-stu-id="06e43-388">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="06e43-389">Определяет, отправляются ли подозрительные образцы (которые могут содержать угрозы) в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="06e43-389">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="06e43-390">Существует три уровня для управления отправкой примера:</span><span class="sxs-lookup"><span data-stu-id="06e43-390">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="06e43-391">**Нет:** никаких подозрительных образцов не передается в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="06e43-391">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="06e43-392">**Сейф:** автоматически будут отправлены только подозрительные образцы, не содержащие личных сведений (PII).</span><span class="sxs-lookup"><span data-stu-id="06e43-392">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="06e43-393">Это значение по умолчанию для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="06e43-393">This is the default value for this setting.</span></span>
- <span data-ttu-id="06e43-394">**Все:** все подозрительные образцы отправлены в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="06e43-394">**All**: all suspicious samples are submitted to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="06e43-395">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-395">Description</span></span>|<span data-ttu-id="06e43-396">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-396">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-397">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-397">**Key**</span></span>|<span data-ttu-id="06e43-398">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="06e43-398">automaticSampleSubmissionConsent</span></span>|
|<span data-ttu-id="06e43-399">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-399">**Data type**</span></span>|<span data-ttu-id="06e43-400">String</span><span class="sxs-lookup"><span data-stu-id="06e43-400">String</span></span>|
|<span data-ttu-id="06e43-401">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-401">**Possible values**</span></span>|<span data-ttu-id="06e43-402">нет</span><span class="sxs-lookup"><span data-stu-id="06e43-402">none</span></span> <p> <span data-ttu-id="06e43-403">безопасный (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="06e43-403">safe (default)</span></span> <p> <span data-ttu-id="06e43-404">все</span><span class="sxs-lookup"><span data-stu-id="06e43-404">all</span></span>|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="06e43-405">Включить и отключить автоматические обновления сведении о безопасности</span><span class="sxs-lookup"><span data-stu-id="06e43-405">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="06e43-406">Определяет, устанавливаются ли обновления разведки безопасности автоматически:</span><span class="sxs-lookup"><span data-stu-id="06e43-406">Determines whether security intelligence updates are installed automatically:</span></span>

<br>

****

|<span data-ttu-id="06e43-407">Описание</span><span class="sxs-lookup"><span data-stu-id="06e43-407">Description</span></span>|<span data-ttu-id="06e43-408">Значение</span><span class="sxs-lookup"><span data-stu-id="06e43-408">Value</span></span>|
|---|---|
|<span data-ttu-id="06e43-409">**Key**</span><span class="sxs-lookup"><span data-stu-id="06e43-409">**Key**</span></span>|<span data-ttu-id="06e43-410">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="06e43-410">automaticDefinitionUpdateEnabled</span></span>|
|<span data-ttu-id="06e43-411">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="06e43-411">**Data type**</span></span>|<span data-ttu-id="06e43-412">Логический</span><span class="sxs-lookup"><span data-stu-id="06e43-412">Boolean</span></span>|
|<span data-ttu-id="06e43-413">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="06e43-413">**Possible values**</span></span>|<span data-ttu-id="06e43-414">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="06e43-414">true (default)</span></span> <p> <span data-ttu-id="06e43-415">false</span><span class="sxs-lookup"><span data-stu-id="06e43-415">false</span></span>|
|

## <a name="recommended-configuration-profile"></a><span data-ttu-id="06e43-416">Рекомендуемый профиль конфигурации</span><span class="sxs-lookup"><span data-stu-id="06e43-416">Recommended configuration profile</span></span>

<span data-ttu-id="06e43-417">Чтобы начать работу, рекомендуется в следующем профиле конфигурации для предприятия воспользоваться всеми функциями защиты, которые предоставляет Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="06e43-417">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="06e43-418">Следующий профиль конфигурации:</span><span class="sxs-lookup"><span data-stu-id="06e43-418">The following configuration profile will:</span></span>

- <span data-ttu-id="06e43-419">Включить защиту в режиме реального времени (RTP)</span><span class="sxs-lookup"><span data-stu-id="06e43-419">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="06e43-420">Укажите, как обрабатываются следующие типы угроз:</span><span class="sxs-lookup"><span data-stu-id="06e43-420">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="06e43-421">**Потенциально нежелательные приложения (PUA)** заблокированы</span><span class="sxs-lookup"><span data-stu-id="06e43-421">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="06e43-422">**Архивные** бомбы (файл с высокой скоростью сжатия) проверяются в журналах продуктов</span><span class="sxs-lookup"><span data-stu-id="06e43-422">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="06e43-423">Включить автоматические обновления сведении о безопасности</span><span class="sxs-lookup"><span data-stu-id="06e43-423">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="06e43-424">Включение облачной защиты</span><span class="sxs-lookup"><span data-stu-id="06e43-424">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="06e43-425">Включить автоматическую отправку образца на `safe` уровне</span><span class="sxs-lookup"><span data-stu-id="06e43-425">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="06e43-426">Пример профиля</span><span class="sxs-lookup"><span data-stu-id="06e43-426">Sample profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="06e43-427">Пример профиля полной конфигурации</span><span class="sxs-lookup"><span data-stu-id="06e43-427">Full configuration profile example</span></span>

<span data-ttu-id="06e43-428">Следующий профиль конфигурации содержит записи для всех параметров, описанных в этом документе, и может использоваться для более сложных сценариев, в которых требуется больше контроля над продуктом.</span><span class="sxs-lookup"><span data-stu-id="06e43-428">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="06e43-429">Полный профиль</span><span class="sxs-lookup"><span data-stu-id="06e43-429">Full profile</span></span>

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
            "extension":".pdf"
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

## <a name="configuration-profile-validation"></a><span data-ttu-id="06e43-430">Проверка профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="06e43-430">Configuration profile validation</span></span>

<span data-ttu-id="06e43-431">Профиль конфигурации должен быть допустимым JSON-форматированный файл.</span><span class="sxs-lookup"><span data-stu-id="06e43-431">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="06e43-432">Существует ряд средств, которые можно использовать для проверки этого.</span><span class="sxs-lookup"><span data-stu-id="06e43-432">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="06e43-433">Например, если вы установили `python` на устройстве:</span><span class="sxs-lookup"><span data-stu-id="06e43-433">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="06e43-434">Если JSON хорошо сформирован, вышеуказанная команда выводит его обратно в терминал и возвращает код выхода `0` .</span><span class="sxs-lookup"><span data-stu-id="06e43-434">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="06e43-435">В противном случае отображается ошибка, описываемая проблемой, и команда возвращает код выхода `1` .</span><span class="sxs-lookup"><span data-stu-id="06e43-435">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="06e43-436">Проверка того, mdatp_managed.jsфайл работает как ожидалось</span><span class="sxs-lookup"><span data-stu-id="06e43-436">Verifying that the mdatp_managed.json file is working as expected</span></span>

<span data-ttu-id="06e43-437">Чтобы убедиться, что ваш /etc/opt/microsoft/mdatp/managed/mdatp_managed.jsработает должным образом, рядом с этими настройками следует увидеть "[managed]":</span><span class="sxs-lookup"><span data-stu-id="06e43-437">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>

- <span data-ttu-id="06e43-438">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="06e43-438">cloud_enabled</span></span>
- <span data-ttu-id="06e43-439">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="06e43-439">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="06e43-440">passive_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="06e43-440">passive_mode_enabled</span></span>
- <span data-ttu-id="06e43-441">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="06e43-441">real_time_protection_enabled</span></span>
- <span data-ttu-id="06e43-442">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="06e43-442">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="06e43-443">Чтобы mdatp_managed.jsвступил в силу, перезагрузка wdavdaemon не требуется.</span><span class="sxs-lookup"><span data-stu-id="06e43-443">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="06e43-444">Развертывание профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="06e43-444">Configuration profile deployment</span></span>

<span data-ttu-id="06e43-445">После создания профиля конфигурации для предприятия его можно развернуть с помощью средства управления, используемом вашим предприятием.</span><span class="sxs-lookup"><span data-stu-id="06e43-445">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="06e43-446">Защитник для конечной точки на Linux читает управляемой конфигурации из */etc/opt/microsoft/mdatp/managed/mdatp_managed.jsв* файле.</span><span class="sxs-lookup"><span data-stu-id="06e43-446">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
