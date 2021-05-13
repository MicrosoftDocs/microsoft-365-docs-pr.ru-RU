---
title: Настройка предпочтений для Microsoft Defender для конечной точки на Mac
description: Настройка защитника MMicrosoft для конечной точки на Mac в корпоративных организациях.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mac, management, preferences, enterprise, intune, jamf, macos, catalina, mojave, high sierra
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b706cb8dbd43d545768c1c573021b5ef401e3c09
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346406"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="fc491-104">Настройка предпочтений для Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="fc491-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fc491-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="fc491-105">**Applies to:**</span></span>

- [<span data-ttu-id="fc491-106">Microsoft Defender для конечной точки в macOS</span><span class="sxs-lookup"><span data-stu-id="fc491-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="fc491-107">В этой статье содержатся инструкции по выбору предпочтений для Microsoft Defender для конечной точки на macOS в корпоративных организациях.</span><span class="sxs-lookup"><span data-stu-id="fc491-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="fc491-108">Чтобы настроить Microsoft Defender для конечной точки на macOS с помощью интерфейса командной строки, см. [в пункте Ресурсы.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="fc491-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="fc491-109">Сводка</span><span class="sxs-lookup"><span data-stu-id="fc491-109">Summary</span></span>

<span data-ttu-id="fc491-110">В корпоративных организациях управление Microsoft Defender для конечной точки на macOS можно с помощью профиля конфигурации, развернутого с помощью одного из нескольких средств управления.</span><span class="sxs-lookup"><span data-stu-id="fc491-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="fc491-111">Предпочтения, управляемые командой операций безопасности, имеют приоритет над предпочтениями, задав локализованные параметры на устройстве.</span><span class="sxs-lookup"><span data-stu-id="fc491-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="fc491-112">Изменение предпочтений, задающихся в профиле конфигурации, требует дополнительных привилегий и недоступна пользователям без административных разрешений.</span><span class="sxs-lookup"><span data-stu-id="fc491-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="fc491-113">В этой статье описывается структура профиля конфигурации, содержится рекомендуемый профиль, который можно использовать для начала работы, и содержатся инструкции по развертыванию профиля.</span><span class="sxs-lookup"><span data-stu-id="fc491-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="fc491-114">Структура профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="fc491-114">Configuration profile structure</span></span>

<span data-ttu-id="fc491-115">Профиль конфигурации — это *файл .plist,* состоящий из записей, идентифицированных ключом (который обозначает имя предпочтения), за которым следует значение, которое зависит от характера предпочтения.</span><span class="sxs-lookup"><span data-stu-id="fc491-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="fc491-116">Значения могут быть простыми (например, численное значение) или сложными, например вложенным списком предпочтений.</span><span class="sxs-lookup"><span data-stu-id="fc491-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="fc491-117">Макет профиля конфигурации зависит от используемой консоли управления.</span><span class="sxs-lookup"><span data-stu-id="fc491-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="fc491-118">В следующих разделах содержатся примеры профилей конфигурации для JAMF и Intune.</span><span class="sxs-lookup"><span data-stu-id="fc491-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="fc491-119">Верхний уровень профиля конфигурации включает в себя все продукты и записи для subareas Microsoft Defender для конечной точки, которые подробно объясняются в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="fc491-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="fc491-120">Параметры антивирусного двигателя</span><span class="sxs-lookup"><span data-stu-id="fc491-120">Antivirus engine preferences</span></span>

<span data-ttu-id="fc491-121">Раздел *antivirusEngine* профиля конфигурации используется для управления предпочтениями антивирусного компонента Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="fc491-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="fc491-122">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-122">Section</span></span>|<span data-ttu-id="fc491-123">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-124">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-125">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-125">**Key**</span></span> | <span data-ttu-id="fc491-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="fc491-126">antivirusEngine</span></span> |
| <span data-ttu-id="fc491-127">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-127">**Data type**</span></span> | <span data-ttu-id="fc491-128">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="fc491-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="fc491-129">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-129">**Comments**</span></span> | <span data-ttu-id="fc491-130">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="fc491-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="fc491-131">Включить и отключить защиту в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="fc491-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="fc491-132">Укажите, следует ли включить защиту в режиме реального времени, которая сканирует файлы по мере их доступа.</span><span class="sxs-lookup"><span data-stu-id="fc491-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="fc491-133">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-133">Section</span></span>|<span data-ttu-id="fc491-134">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-135">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-136">**Key**</span></span> | <span data-ttu-id="fc491-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="fc491-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="fc491-138">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-138">**Data type**</span></span> | <span data-ttu-id="fc491-139">Логический</span><span class="sxs-lookup"><span data-stu-id="fc491-139">Boolean</span></span> |
| <span data-ttu-id="fc491-140">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-140">**Possible values**</span></span> | <span data-ttu-id="fc491-141">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fc491-141">true (default)</span></span> <br/> <span data-ttu-id="fc491-142">false</span><span class="sxs-lookup"><span data-stu-id="fc491-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="fc491-143">Включить и отключить пассивный режим</span><span class="sxs-lookup"><span data-stu-id="fc491-143">Enable / disable passive mode</span></span>

<span data-ttu-id="fc491-144">Укажите, работает ли антивирусный двигатель в пассивном режиме.</span><span class="sxs-lookup"><span data-stu-id="fc491-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="fc491-145">Пассивный режим имеет следующие последствия:</span><span class="sxs-lookup"><span data-stu-id="fc491-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="fc491-146">Защита в режиме реального времени отключена</span><span class="sxs-lookup"><span data-stu-id="fc491-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="fc491-147">Включено сканирование по запросу</span><span class="sxs-lookup"><span data-stu-id="fc491-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="fc491-148">Автоматическое устранение угрозы отключено</span><span class="sxs-lookup"><span data-stu-id="fc491-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="fc491-149">Включаем обновления разведки безопасности</span><span class="sxs-lookup"><span data-stu-id="fc491-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="fc491-150">Значок меню состояния скрыт</span><span class="sxs-lookup"><span data-stu-id="fc491-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="fc491-151">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-151">Section</span></span>|<span data-ttu-id="fc491-152">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-153">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-154">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-154">**Key**</span></span> | <span data-ttu-id="fc491-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="fc491-155">passiveMode</span></span> |
| <span data-ttu-id="fc491-156">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-156">**Data type**</span></span> | <span data-ttu-id="fc491-157">Логический</span><span class="sxs-lookup"><span data-stu-id="fc491-157">Boolean</span></span> |
| <span data-ttu-id="fc491-158">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-158">**Possible values**</span></span> | <span data-ttu-id="fc491-159">false (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fc491-159">false (default)</span></span> <br/> <span data-ttu-id="fc491-160">true</span><span class="sxs-lookup"><span data-stu-id="fc491-160">true</span></span> |
| <span data-ttu-id="fc491-161">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-161">**Comments**</span></span> | <span data-ttu-id="fc491-162">Доступно в Microsoft Defender для конечной точки версии 100.67.60 или выше.</span><span class="sxs-lookup"><span data-stu-id="fc491-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="fc491-163">Политика слияния исключений</span><span class="sxs-lookup"><span data-stu-id="fc491-163">Exclusion merge policy</span></span>

<span data-ttu-id="fc491-164">Укажите политику слияния исключений.</span><span class="sxs-lookup"><span data-stu-id="fc491-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="fc491-165">Это может быть сочетание исключений, определенных администратором и пользователей , или только исключений, определенных `merge` администратором ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="fc491-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="fc491-166">Этот параметр можно использовать, чтобы ограничить местным пользователям определение собственных исключений.</span><span class="sxs-lookup"><span data-stu-id="fc491-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="fc491-167">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-167">Section</span></span>|<span data-ttu-id="fc491-168">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-169">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-170">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-170">**Key**</span></span> | <span data-ttu-id="fc491-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="fc491-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="fc491-172">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-172">**Data type**</span></span> | <span data-ttu-id="fc491-173">String</span><span class="sxs-lookup"><span data-stu-id="fc491-173">String</span></span> |
| <span data-ttu-id="fc491-174">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-174">**Possible values**</span></span> | <span data-ttu-id="fc491-175">слияние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fc491-175">merge (default)</span></span> <br/> <span data-ttu-id="fc491-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="fc491-176">admin_only</span></span> |
| <span data-ttu-id="fc491-177">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-177">**Comments**</span></span> | <span data-ttu-id="fc491-178">Доступно в Microsoft Defender для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="fc491-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="fc491-179">Исключения сканирования</span><span class="sxs-lookup"><span data-stu-id="fc491-179">Scan exclusions</span></span>

<span data-ttu-id="fc491-180">Укажите объекты, исключенные из проверки.</span><span class="sxs-lookup"><span data-stu-id="fc491-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="fc491-181">Исключения могут быть указаны полными путями, расширениями или именами файлов.</span><span class="sxs-lookup"><span data-stu-id="fc491-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="fc491-182">(Исключения заданы в качестве массива элементов, администратор может указать столько элементов, сколько необходимо, в любом порядке.)</span><span class="sxs-lookup"><span data-stu-id="fc491-182">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|<span data-ttu-id="fc491-183">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-183">Section</span></span>|<span data-ttu-id="fc491-184">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-184">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-185">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-185">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-186">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-186">**Key**</span></span> | <span data-ttu-id="fc491-187">исключения</span><span class="sxs-lookup"><span data-stu-id="fc491-187">exclusions</span></span> |
| <span data-ttu-id="fc491-188">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-188">**Data type**</span></span> | <span data-ttu-id="fc491-189">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="fc491-189">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="fc491-190">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-190">**Comments**</span></span> | <span data-ttu-id="fc491-191">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="fc491-191">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="fc491-192">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="fc491-192">Type of exclusion</span></span>

<span data-ttu-id="fc491-193">Укажите содержимое, исключенное из проверки по типу.</span><span class="sxs-lookup"><span data-stu-id="fc491-193">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="fc491-194">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-194">Section</span></span>|<span data-ttu-id="fc491-195">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-196">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-197">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-197">**Key**</span></span> | <span data-ttu-id="fc491-198">$type</span><span class="sxs-lookup"><span data-stu-id="fc491-198">$type</span></span> |
| <span data-ttu-id="fc491-199">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-199">**Data type**</span></span> | <span data-ttu-id="fc491-200">String</span><span class="sxs-lookup"><span data-stu-id="fc491-200">String</span></span> |
| <span data-ttu-id="fc491-201">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-201">**Possible values**</span></span> | <span data-ttu-id="fc491-202">excludedPath</span><span class="sxs-lookup"><span data-stu-id="fc491-202">excludedPath</span></span> <br/> <span data-ttu-id="fc491-203">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="fc491-203">excludedFileExtension</span></span> <br/> <span data-ttu-id="fc491-204">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="fc491-204">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="fc491-205">Путь к исключению контента</span><span class="sxs-lookup"><span data-stu-id="fc491-205">Path to excluded content</span></span>

<span data-ttu-id="fc491-206">Укажите содержимое, исключенное из проверки полным путем файла.</span><span class="sxs-lookup"><span data-stu-id="fc491-206">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="fc491-207">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-207">Section</span></span>|<span data-ttu-id="fc491-208">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-208">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-209">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-209">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-210">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-210">**Key**</span></span> | <span data-ttu-id="fc491-211">path</span><span class="sxs-lookup"><span data-stu-id="fc491-211">path</span></span> |
| <span data-ttu-id="fc491-212">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-212">**Data type**</span></span> | <span data-ttu-id="fc491-213">String</span><span class="sxs-lookup"><span data-stu-id="fc491-213">String</span></span> |
| <span data-ttu-id="fc491-214">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-214">**Possible values**</span></span> | <span data-ttu-id="fc491-215">допустимые пути</span><span class="sxs-lookup"><span data-stu-id="fc491-215">valid paths</span></span> |
| <span data-ttu-id="fc491-216">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-216">**Comments**</span></span> | <span data-ttu-id="fc491-217">Применимо только если *$type* *исключенPath*</span><span class="sxs-lookup"><span data-stu-id="fc491-217">Applicable only if *$type* is *excludedPath*</span></span> |

## <a name="supported-exclusion-types"></a><span data-ttu-id="fc491-218">Поддерживаемые типы исключений</span><span class="sxs-lookup"><span data-stu-id="fc491-218">Supported exclusion types</span></span>

<span data-ttu-id="fc491-219">В таблице ниже показаны типы исключений, поддерживаемые Защитником для конечной точки на Mac.</span><span class="sxs-lookup"><span data-stu-id="fc491-219">The follow table shows the exclusion types supported by Defender for Endpoint on Mac.</span></span>

<span data-ttu-id="fc491-220">Исключения</span><span class="sxs-lookup"><span data-stu-id="fc491-220">Exclusion</span></span> | <span data-ttu-id="fc491-221">Определение</span><span class="sxs-lookup"><span data-stu-id="fc491-221">Definition</span></span> | <span data-ttu-id="fc491-222">Примеры</span><span class="sxs-lookup"><span data-stu-id="fc491-222">Examples</span></span>
---|---|---
<span data-ttu-id="fc491-223">Расширение файла</span><span class="sxs-lookup"><span data-stu-id="fc491-223">File extension</span></span> | <span data-ttu-id="fc491-224">Все файлы с расширением в любом месте на устройстве</span><span class="sxs-lookup"><span data-stu-id="fc491-224">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="fc491-225">File</span><span class="sxs-lookup"><span data-stu-id="fc491-225">File</span></span> | <span data-ttu-id="fc491-226">Определенный файл, определенный по полному пути</span><span class="sxs-lookup"><span data-stu-id="fc491-226">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="fc491-227">Folder</span><span class="sxs-lookup"><span data-stu-id="fc491-227">Folder</span></span> | <span data-ttu-id="fc491-228">Все файлы в указанной папке (повторно)</span><span class="sxs-lookup"><span data-stu-id="fc491-228">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="fc491-229">Процесс</span><span class="sxs-lookup"><span data-stu-id="fc491-229">Process</span></span> | <span data-ttu-id="fc491-230">Определенный процесс (указанный полным путем или именем файла) и все файлы, открытые в нем.</span><span class="sxs-lookup"><span data-stu-id="fc491-230">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="fc491-231">Для успешного исключения из нее должны быть жесткие ссылки, а не символические.</span><span class="sxs-lookup"><span data-stu-id="fc491-231">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="fc491-232">Вы можете проверить, является ли путь символической ссылкой при `file <path-name>` запуске.</span><span class="sxs-lookup"><span data-stu-id="fc491-232">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="fc491-233">Исключения файлов, папок и процессов поддерживают следующие подкарды:</span><span class="sxs-lookup"><span data-stu-id="fc491-233">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="fc491-234">Подстановочный знак</span><span class="sxs-lookup"><span data-stu-id="fc491-234">Wildcard</span></span> | <span data-ttu-id="fc491-235">Описание</span><span class="sxs-lookup"><span data-stu-id="fc491-235">Description</span></span> | <span data-ttu-id="fc491-236">Пример</span><span class="sxs-lookup"><span data-stu-id="fc491-236">Example</span></span> | <span data-ttu-id="fc491-237">Совпадения</span><span class="sxs-lookup"><span data-stu-id="fc491-237">Matches</span></span> | <span data-ttu-id="fc491-238">Не совпадает</span><span class="sxs-lookup"><span data-stu-id="fc491-238">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="fc491-239">Совпадает с любым числом символов, в том числе без них (обратите внимание, что при данной подмастерье используется внутри пути, она заменит только одну папку)</span><span class="sxs-lookup"><span data-stu-id="fc491-239">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="fc491-240">?</span><span class="sxs-lookup"><span data-stu-id="fc491-240">?</span></span> | <span data-ttu-id="fc491-241">Соответствует любому отдельному символу</span><span class="sxs-lookup"><span data-stu-id="fc491-241">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

##### <a name="path-type-file--directory"></a><span data-ttu-id="fc491-242">Тип пути (файл / каталог)</span><span class="sxs-lookup"><span data-stu-id="fc491-242">Path type (file / directory)</span></span>

<span data-ttu-id="fc491-243">Указать, *относится ли* свойство пути к файлу или каталогу.</span><span class="sxs-lookup"><span data-stu-id="fc491-243">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="fc491-244">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-244">Section</span></span>|<span data-ttu-id="fc491-245">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-245">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-246">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-246">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-247">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-247">**Key**</span></span> | <span data-ttu-id="fc491-248">isDirectory</span><span class="sxs-lookup"><span data-stu-id="fc491-248">isDirectory</span></span> |
| <span data-ttu-id="fc491-249">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-249">**Data type**</span></span> | <span data-ttu-id="fc491-250">Логический</span><span class="sxs-lookup"><span data-stu-id="fc491-250">Boolean</span></span> |
| <span data-ttu-id="fc491-251">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-251">**Possible values**</span></span> | <span data-ttu-id="fc491-252">false (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fc491-252">false (default)</span></span> <br/> <span data-ttu-id="fc491-253">true</span><span class="sxs-lookup"><span data-stu-id="fc491-253">true</span></span> |
| <span data-ttu-id="fc491-254">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-254">**Comments**</span></span> | <span data-ttu-id="fc491-255">Применимо только если *$type* *исключенPath*</span><span class="sxs-lookup"><span data-stu-id="fc491-255">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="fc491-256">Расширение файла, исключено из сканирования</span><span class="sxs-lookup"><span data-stu-id="fc491-256">File extension excluded from the scan</span></span>

<span data-ttu-id="fc491-257">Укажите содержимое, исключенное из проверки расширением файла.</span><span class="sxs-lookup"><span data-stu-id="fc491-257">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="fc491-258">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-258">Section</span></span>|<span data-ttu-id="fc491-259">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-259">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-260">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-260">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-261">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-261">**Key**</span></span> | <span data-ttu-id="fc491-262">расширение</span><span class="sxs-lookup"><span data-stu-id="fc491-262">extension</span></span> |
| <span data-ttu-id="fc491-263">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-263">**Data type**</span></span> | <span data-ttu-id="fc491-264">String</span><span class="sxs-lookup"><span data-stu-id="fc491-264">String</span></span> |
| <span data-ttu-id="fc491-265">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-265">**Possible values**</span></span> | <span data-ttu-id="fc491-266">допустимые расширения файлов</span><span class="sxs-lookup"><span data-stu-id="fc491-266">valid file extensions</span></span> |
| <span data-ttu-id="fc491-267">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-267">**Comments**</span></span> | <span data-ttu-id="fc491-268">Применимо только если *$type* *исключеноFileExtension*</span><span class="sxs-lookup"><span data-stu-id="fc491-268">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="fc491-269">Процесс, исключенный из сканирования</span><span class="sxs-lookup"><span data-stu-id="fc491-269">Process excluded from the scan</span></span>

<span data-ttu-id="fc491-270">Укажите процесс, для которого все действия файла исключены из сканирования.</span><span class="sxs-lookup"><span data-stu-id="fc491-270">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="fc491-271">Процесс можно укаварить как по имени (например, так и по полному `cat` пути( `/bin/cat` например).</span><span class="sxs-lookup"><span data-stu-id="fc491-271">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="fc491-272">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-272">Section</span></span>|<span data-ttu-id="fc491-273">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-273">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-274">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-274">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-275">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-275">**Key**</span></span> | <span data-ttu-id="fc491-276">name</span><span class="sxs-lookup"><span data-stu-id="fc491-276">name</span></span> |
| <span data-ttu-id="fc491-277">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-277">**Data type**</span></span> | <span data-ttu-id="fc491-278">String</span><span class="sxs-lookup"><span data-stu-id="fc491-278">String</span></span> |
| <span data-ttu-id="fc491-279">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-279">**Possible values**</span></span> | <span data-ttu-id="fc491-280">любая строка</span><span class="sxs-lookup"><span data-stu-id="fc491-280">any string</span></span> |
| <span data-ttu-id="fc491-281">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-281">**Comments**</span></span> | <span data-ttu-id="fc491-282">Применимо только *если $type* *исключеноFileName*</span><span class="sxs-lookup"><span data-stu-id="fc491-282">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="fc491-283">Разрешенные угрозы</span><span class="sxs-lookup"><span data-stu-id="fc491-283">Allowed threats</span></span>

<span data-ttu-id="fc491-284">Укажите угрозы по имени, которые не заблокированы Защитником для конечной точки на Mac.</span><span class="sxs-lookup"><span data-stu-id="fc491-284">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="fc491-285">Эти угрозы будут разрешены для запуска.</span><span class="sxs-lookup"><span data-stu-id="fc491-285">These threats will be allowed to run.</span></span>

|<span data-ttu-id="fc491-286">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-286">Section</span></span>|<span data-ttu-id="fc491-287">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-287">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-288">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-288">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-289">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-289">**Key**</span></span> | <span data-ttu-id="fc491-290">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="fc491-290">allowedThreats</span></span> |
| <span data-ttu-id="fc491-291">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-291">**Data type**</span></span> | <span data-ttu-id="fc491-292">Массив строк</span><span class="sxs-lookup"><span data-stu-id="fc491-292">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="fc491-293">Действия с неустановляемой угрозой</span><span class="sxs-lookup"><span data-stu-id="fc491-293">Disallowed threat actions</span></span>

<span data-ttu-id="fc491-294">Ограничивает действия, которые может принимать локальный пользователь устройства при обнаружении угроз.</span><span class="sxs-lookup"><span data-stu-id="fc491-294">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="fc491-295">Действия, включенные в этот список, не отображаются в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="fc491-295">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="fc491-296">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-296">Section</span></span>|<span data-ttu-id="fc491-297">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-298">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-299">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-299">**Key**</span></span> | <span data-ttu-id="fc491-300">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="fc491-300">disallowedThreatActions</span></span> |
| <span data-ttu-id="fc491-301">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-301">**Data type**</span></span> | <span data-ttu-id="fc491-302">Массив строк</span><span class="sxs-lookup"><span data-stu-id="fc491-302">Array of strings</span></span> |
| <span data-ttu-id="fc491-303">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-303">**Possible values**</span></span> | <span data-ttu-id="fc491-304">разрешить (ограничивает пользователей от допуска угроз)</span><span class="sxs-lookup"><span data-stu-id="fc491-304">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="fc491-305">восстановление (ограничивает пользователей от восстановления угроз из карантина)</span><span class="sxs-lookup"><span data-stu-id="fc491-305">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="fc491-306">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-306">**Comments**</span></span> | <span data-ttu-id="fc491-307">Доступно в Microsoft Defender для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="fc491-307">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="fc491-308">Параметры типа угроз</span><span class="sxs-lookup"><span data-stu-id="fc491-308">Threat type settings</span></span>

<span data-ttu-id="fc491-309">Укажите, как определенные типы угроз обрабатываются Microsoft Defender для конечной точки на macOS.</span><span class="sxs-lookup"><span data-stu-id="fc491-309">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="fc491-310">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-310">Section</span></span>|<span data-ttu-id="fc491-311">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-311">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-312">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-312">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-313">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-313">**Key**</span></span> | <span data-ttu-id="fc491-314">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="fc491-314">threatTypeSettings</span></span> |
| <span data-ttu-id="fc491-315">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-315">**Data type**</span></span> | <span data-ttu-id="fc491-316">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="fc491-316">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="fc491-317">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-317">**Comments**</span></span> | <span data-ttu-id="fc491-318">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="fc491-318">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="fc491-319">Тип угрозы</span><span class="sxs-lookup"><span data-stu-id="fc491-319">Threat type</span></span>

<span data-ttu-id="fc491-320">Укажите типы угроз.</span><span class="sxs-lookup"><span data-stu-id="fc491-320">Specify threat types.</span></span>

|<span data-ttu-id="fc491-321">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-321">Section</span></span>|<span data-ttu-id="fc491-322">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-322">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-323">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-323">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-324">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-324">**Key**</span></span> | <span data-ttu-id="fc491-325">ключа</span><span class="sxs-lookup"><span data-stu-id="fc491-325">key</span></span> |
| <span data-ttu-id="fc491-326">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-326">**Data type**</span></span> | <span data-ttu-id="fc491-327">String</span><span class="sxs-lookup"><span data-stu-id="fc491-327">String</span></span> |
| <span data-ttu-id="fc491-328">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-328">**Possible values**</span></span> | <span data-ttu-id="fc491-329">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="fc491-329">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="fc491-330">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="fc491-330">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="fc491-331">Действие</span><span class="sxs-lookup"><span data-stu-id="fc491-331">Action to take</span></span>

<span data-ttu-id="fc491-332">Укажите, какие действия необходимо принять при обнаружении угрозы типа, указанного в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="fc491-332">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="fc491-333">Выберите из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="fc491-333">Choose from the following options:</span></span>

- <span data-ttu-id="fc491-334">**Аудит:** устройство не защищено от этого типа угрозы, но запись об угрозе регистрируется.</span><span class="sxs-lookup"><span data-stu-id="fc491-334">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="fc491-335">**Блок:** ваше устройство защищено от этого типа угрозы, и вы будете уведомлены в пользовательском интерфейсе и консоли безопасности.</span><span class="sxs-lookup"><span data-stu-id="fc491-335">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="fc491-336">**Отключено:** устройство не защищено от этого типа угрозы и ничего не регистрируется.</span><span class="sxs-lookup"><span data-stu-id="fc491-336">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="fc491-337">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-337">Section</span></span>|<span data-ttu-id="fc491-338">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-338">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-339">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-339">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-340">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-340">**Key**</span></span> | <span data-ttu-id="fc491-341">значение</span><span class="sxs-lookup"><span data-stu-id="fc491-341">value</span></span> |
| <span data-ttu-id="fc491-342">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-342">**Data type**</span></span> | <span data-ttu-id="fc491-343">String</span><span class="sxs-lookup"><span data-stu-id="fc491-343">String</span></span> |
| <span data-ttu-id="fc491-344">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-344">**Possible values**</span></span> | <span data-ttu-id="fc491-345">аудит (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fc491-345">audit (default)</span></span> <br/> <span data-ttu-id="fc491-346">block</span><span class="sxs-lookup"><span data-stu-id="fc491-346">block</span></span> <br/> <span data-ttu-id="fc491-347">Off</span><span class="sxs-lookup"><span data-stu-id="fc491-347">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="fc491-348">Параметры типа угрозы объединяют политику слияния</span><span class="sxs-lookup"><span data-stu-id="fc491-348">Threat type settings merge policy</span></span>

<span data-ttu-id="fc491-349">Укажите политику слияния для параметров типа угроз.</span><span class="sxs-lookup"><span data-stu-id="fc491-349">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="fc491-350">Это может быть сочетание параметров, определенных администратором и определенных пользователем , или только параметров, определенных `merge` администратором ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="fc491-350">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="fc491-351">Этот параметр можно использовать, чтобы ограничить местным пользователям определение собственных параметров для различных типов угроз.</span><span class="sxs-lookup"><span data-stu-id="fc491-351">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="fc491-352">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-352">Section</span></span>|<span data-ttu-id="fc491-353">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-353">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-354">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-354">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-355">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-355">**Key**</span></span> | <span data-ttu-id="fc491-356">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="fc491-356">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="fc491-357">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-357">**Data type**</span></span> | <span data-ttu-id="fc491-358">String</span><span class="sxs-lookup"><span data-stu-id="fc491-358">String</span></span> |
| <span data-ttu-id="fc491-359">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-359">**Possible values**</span></span> | <span data-ttu-id="fc491-360">слияние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fc491-360">merge (default)</span></span> <br/> <span data-ttu-id="fc491-361">admin_only</span><span class="sxs-lookup"><span data-stu-id="fc491-361">admin_only</span></span> |
| <span data-ttu-id="fc491-362">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-362">**Comments**</span></span> | <span data-ttu-id="fc491-363">Доступно в Microsoft Defender для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="fc491-363">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="fc491-364">Хранение истории антивирусного сканирования (в днях)</span><span class="sxs-lookup"><span data-stu-id="fc491-364">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="fc491-365">Укажите количество дней, которые сохраняются в истории сканирования на устройстве.</span><span class="sxs-lookup"><span data-stu-id="fc491-365">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="fc491-366">Старые результаты сканирования удаляются из истории.</span><span class="sxs-lookup"><span data-stu-id="fc491-366">Old scan results are removed from the history.</span></span> <span data-ttu-id="fc491-367">Старые карантинные файлы, которые также удаляются с диска.</span><span class="sxs-lookup"><span data-stu-id="fc491-367">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="fc491-368">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-368">Section</span></span>|<span data-ttu-id="fc491-369">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-369">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-370">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-370">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-371">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-371">**Key**</span></span> | <span data-ttu-id="fc491-372">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="fc491-372">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="fc491-373">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-373">**Data type**</span></span> | <span data-ttu-id="fc491-374">String</span><span class="sxs-lookup"><span data-stu-id="fc491-374">String</span></span> |
| <span data-ttu-id="fc491-375">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-375">**Possible values**</span></span> | <span data-ttu-id="fc491-376">90 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="fc491-376">90 (default).</span></span> <span data-ttu-id="fc491-377">Допустимые значения от 1 дня до 180 дней.</span><span class="sxs-lookup"><span data-stu-id="fc491-377">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="fc491-378">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-378">**Comments**</span></span> | <span data-ttu-id="fc491-379">Доступно в Microsoft Defender для конечной точки версии 101.07.23 или выше.</span><span class="sxs-lookup"><span data-stu-id="fc491-379">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="fc491-380">Максимальное количество элементов в истории антивирусного сканирования</span><span class="sxs-lookup"><span data-stu-id="fc491-380">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="fc491-381">Укажите максимальное количество записей, которые необходимо сохранить в истории сканирования.</span><span class="sxs-lookup"><span data-stu-id="fc491-381">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="fc491-382">Записи включают все проверки по запросу, выполняемые в прошлом, и все обнаружения антивирусов.</span><span class="sxs-lookup"><span data-stu-id="fc491-382">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="fc491-383">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-383">Section</span></span>|<span data-ttu-id="fc491-384">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-384">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-385">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-385">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-386">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-386">**Key**</span></span> | <span data-ttu-id="fc491-387">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="fc491-387">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="fc491-388">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-388">**Data type**</span></span> | <span data-ttu-id="fc491-389">String</span><span class="sxs-lookup"><span data-stu-id="fc491-389">String</span></span> |
| <span data-ttu-id="fc491-390">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-390">**Possible values**</span></span> | <span data-ttu-id="fc491-391">10000 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="fc491-391">10000 (default).</span></span> <span data-ttu-id="fc491-392">Допустимые значения : от 5000 элементов до 15000 элементов.</span><span class="sxs-lookup"><span data-stu-id="fc491-392">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="fc491-393">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-393">**Comments**</span></span> | <span data-ttu-id="fc491-394">Доступно в Microsoft Defender для конечной точки версии 101.07.23 или выше.</span><span class="sxs-lookup"><span data-stu-id="fc491-394">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="fc491-395">Параметры защиты с облачной доставкой</span><span class="sxs-lookup"><span data-stu-id="fc491-395">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="fc491-396">Настройка облачных функций защиты Microsoft Defender для конечной точки на macOS.</span><span class="sxs-lookup"><span data-stu-id="fc491-396">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="fc491-397">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-397">Section</span></span>|<span data-ttu-id="fc491-398">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-399">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-400">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-400">**Key**</span></span> | <span data-ttu-id="fc491-401">cloudService</span><span class="sxs-lookup"><span data-stu-id="fc491-401">cloudService</span></span> |
| <span data-ttu-id="fc491-402">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-402">**Data type**</span></span> | <span data-ttu-id="fc491-403">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="fc491-403">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="fc491-404">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-404">**Comments**</span></span> | <span data-ttu-id="fc491-405">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="fc491-405">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="fc491-406">Включить и отключить облачную защиту</span><span class="sxs-lookup"><span data-stu-id="fc491-406">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="fc491-407">Укажите, включить ли облачную защиту устройства или нет.</span><span class="sxs-lookup"><span data-stu-id="fc491-407">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="fc491-408">Чтобы повысить безопасность ваших служб, рекомендуется сохранить эту функцию включенной.</span><span class="sxs-lookup"><span data-stu-id="fc491-408">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="fc491-409">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-409">Section</span></span>|<span data-ttu-id="fc491-410">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-410">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-411">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-411">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-412">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-412">**Key**</span></span> | <span data-ttu-id="fc491-413">включено</span><span class="sxs-lookup"><span data-stu-id="fc491-413">enabled</span></span> |
| <span data-ttu-id="fc491-414">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-414">**Data type**</span></span> | <span data-ttu-id="fc491-415">Логический</span><span class="sxs-lookup"><span data-stu-id="fc491-415">Boolean</span></span> |
| <span data-ttu-id="fc491-416">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-416">**Possible values**</span></span> | <span data-ttu-id="fc491-417">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fc491-417">true (default)</span></span> <br/> <span data-ttu-id="fc491-418">false</span><span class="sxs-lookup"><span data-stu-id="fc491-418">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="fc491-419">Уровень диагностической коллекции</span><span class="sxs-lookup"><span data-stu-id="fc491-419">Diagnostic collection level</span></span>

<span data-ttu-id="fc491-420">Диагностические данные используются для обеспечения безопасности и повышения безопасности Microsoft Defender для конечной точки, обнаружения, диагностики и устранения проблем, а также улучшения продукта.</span><span class="sxs-lookup"><span data-stu-id="fc491-420">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="fc491-421">Этот параметр определяет уровень диагностики, отправленной Microsoft Defender для конечной точки в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fc491-421">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="fc491-422">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-422">Section</span></span>|<span data-ttu-id="fc491-423">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-424">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-424">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-425">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-425">**Key**</span></span> | <span data-ttu-id="fc491-426">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="fc491-426">diagnosticLevel</span></span> |
| <span data-ttu-id="fc491-427">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-427">**Data type**</span></span> | <span data-ttu-id="fc491-428">String</span><span class="sxs-lookup"><span data-stu-id="fc491-428">String</span></span> |
| <span data-ttu-id="fc491-429">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-429">**Possible values**</span></span> | <span data-ttu-id="fc491-430">необязательный (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fc491-430">optional (default)</span></span> <br/> <span data-ttu-id="fc491-431">Обязательный</span><span class="sxs-lookup"><span data-stu-id="fc491-431">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="fc491-432">Включить и отключить автоматические отправки образцов</span><span class="sxs-lookup"><span data-stu-id="fc491-432">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="fc491-433">Определяет, отправляются ли подозрительные образцы (которые могут содержать угрозы) в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fc491-433">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="fc491-434">Вам будет предложено, если в отправленных файлах могут содержаться персональные данные.</span><span class="sxs-lookup"><span data-stu-id="fc491-434">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="fc491-435">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-435">Section</span></span>|<span data-ttu-id="fc491-436">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-436">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-437">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-437">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-438">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-438">**Key**</span></span> | <span data-ttu-id="fc491-439">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="fc491-439">automaticSampleSubmission</span></span> |
| <span data-ttu-id="fc491-440">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-440">**Data type**</span></span> | <span data-ttu-id="fc491-441">Логический</span><span class="sxs-lookup"><span data-stu-id="fc491-441">Boolean</span></span> |
| <span data-ttu-id="fc491-442">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-442">**Possible values**</span></span> | <span data-ttu-id="fc491-443">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fc491-443">true (default)</span></span> <br/> <span data-ttu-id="fc491-444">false</span><span class="sxs-lookup"><span data-stu-id="fc491-444">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="fc491-445">Включить и отключить автоматические обновления сведении о безопасности</span><span class="sxs-lookup"><span data-stu-id="fc491-445">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="fc491-446">Определяет, устанавливаются ли обновления разведки безопасности автоматически:</span><span class="sxs-lookup"><span data-stu-id="fc491-446">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="fc491-447">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-447">Section</span></span>|<span data-ttu-id="fc491-448">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-448">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-449">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-449">**Key**</span></span> | <span data-ttu-id="fc491-450">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="fc491-450">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="fc491-451">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-451">**Data type**</span></span> | <span data-ttu-id="fc491-452">Логический</span><span class="sxs-lookup"><span data-stu-id="fc491-452">Boolean</span></span> |
| <span data-ttu-id="fc491-453">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-453">**Possible values**</span></span> | <span data-ttu-id="fc491-454">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fc491-454">true (default)</span></span> <br/> <span data-ttu-id="fc491-455">false</span><span class="sxs-lookup"><span data-stu-id="fc491-455">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="fc491-456">Предпочтения пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="fc491-456">User interface preferences</span></span>

<span data-ttu-id="fc491-457">Управление предпочтениями пользовательского интерфейса Microsoft Defender для конечной точки на macOS.</span><span class="sxs-lookup"><span data-stu-id="fc491-457">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="fc491-458">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-458">Section</span></span>|<span data-ttu-id="fc491-459">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-459">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-460">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-460">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-461">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-461">**Key**</span></span> | <span data-ttu-id="fc491-462">userInterface</span><span class="sxs-lookup"><span data-stu-id="fc491-462">userInterface</span></span> |
| <span data-ttu-id="fc491-463">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-463">**Data type**</span></span> | <span data-ttu-id="fc491-464">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="fc491-464">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="fc491-465">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-465">**Comments**</span></span> | <span data-ttu-id="fc491-466">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="fc491-466">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="fc491-467">Значок меню "Показать/ скрыть состояние"</span><span class="sxs-lookup"><span data-stu-id="fc491-467">Show / hide status menu icon</span></span>

<span data-ttu-id="fc491-468">Укажите, показывать или скрывать значок меню состояния в правом верхнем углу экрана.</span><span class="sxs-lookup"><span data-stu-id="fc491-468">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="fc491-469">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-469">Section</span></span>|<span data-ttu-id="fc491-470">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-470">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-471">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-471">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-472">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-472">**Key**</span></span> | <span data-ttu-id="fc491-473">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="fc491-473">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="fc491-474">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-474">**Data type**</span></span> | <span data-ttu-id="fc491-475">Логический</span><span class="sxs-lookup"><span data-stu-id="fc491-475">Boolean</span></span> |
| <span data-ttu-id="fc491-476">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-476">**Possible values**</span></span> | <span data-ttu-id="fc491-477">false (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fc491-477">false (default)</span></span> <br/> <span data-ttu-id="fc491-478">true</span><span class="sxs-lookup"><span data-stu-id="fc491-478">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="fc491-479">Параметр Show/hide для отправки отзывов</span><span class="sxs-lookup"><span data-stu-id="fc491-479">Show / hide option to send feedback</span></span>

<span data-ttu-id="fc491-480">Укажите, могут ли пользователи отправлять отзывы в Корпорацию Майкрософт, переехав `Help`  >  `Send Feedback` в .</span><span class="sxs-lookup"><span data-stu-id="fc491-480">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="fc491-481">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-481">Section</span></span>|<span data-ttu-id="fc491-482">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-482">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-483">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-483">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-484">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-484">**Key**</span></span> | <span data-ttu-id="fc491-485">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="fc491-485">userInitiatedFeedback</span></span> |
| <span data-ttu-id="fc491-486">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-486">**Data type**</span></span> | <span data-ttu-id="fc491-487">String</span><span class="sxs-lookup"><span data-stu-id="fc491-487">String</span></span> |
| <span data-ttu-id="fc491-488">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-488">**Possible values**</span></span> | <span data-ttu-id="fc491-489">включено (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fc491-489">enabled (default)</span></span> <br/> <span data-ttu-id="fc491-490">отключено</span><span class="sxs-lookup"><span data-stu-id="fc491-490">disabled</span></span> |
| <span data-ttu-id="fc491-491">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-491">**Comments**</span></span> | <span data-ttu-id="fc491-492">Доступно в Microsoft Defender для конечной точки версии 101.19.61 или выше.</span><span class="sxs-lookup"><span data-stu-id="fc491-492">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="fc491-493">Параметры обнаружения конечных точек и ответов</span><span class="sxs-lookup"><span data-stu-id="fc491-493">Endpoint detection and response preferences</span></span>

<span data-ttu-id="fc491-494">Управление предпочтениями компонента обнаружение и нейтрализация атак на конечные точки (EDR) Microsoft Defender для конечной точки на macOS.</span><span class="sxs-lookup"><span data-stu-id="fc491-494">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="fc491-495">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-495">Section</span></span>|<span data-ttu-id="fc491-496">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-496">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-497">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-497">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-498">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-498">**Key**</span></span> | <span data-ttu-id="fc491-499">edr</span><span class="sxs-lookup"><span data-stu-id="fc491-499">edr</span></span> |
| <span data-ttu-id="fc491-500">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-500">**Data type**</span></span> | <span data-ttu-id="fc491-501">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="fc491-501">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="fc491-502">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-502">**Comments**</span></span> | <span data-ttu-id="fc491-503">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="fc491-503">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="fc491-504">Теги устройств</span><span class="sxs-lookup"><span data-stu-id="fc491-504">Device tags</span></span>

<span data-ttu-id="fc491-505">Укажите имя тега и его значение.</span><span class="sxs-lookup"><span data-stu-id="fc491-505">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="fc491-506">Тег GROUP указывает устройство с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="fc491-506">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="fc491-507">Тег отражается на портале на странице устройства и может использоваться для фильтрации и группировки устройств.</span><span class="sxs-lookup"><span data-stu-id="fc491-507">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="fc491-508">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-508">Section</span></span>|<span data-ttu-id="fc491-509">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-509">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-510">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-510">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-511">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-511">**Key**</span></span> | <span data-ttu-id="fc491-512">tags</span><span class="sxs-lookup"><span data-stu-id="fc491-512">tags</span></span> |
| <span data-ttu-id="fc491-513">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-513">**Data type**</span></span> | <span data-ttu-id="fc491-514">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="fc491-514">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="fc491-515">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="fc491-515">**Comments**</span></span> | <span data-ttu-id="fc491-516">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="fc491-516">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="fc491-517">Тип тега</span><span class="sxs-lookup"><span data-stu-id="fc491-517">Type of tag</span></span>

<span data-ttu-id="fc491-518">Указывает тип тега</span><span class="sxs-lookup"><span data-stu-id="fc491-518">Specifies the type of tag</span></span>

|<span data-ttu-id="fc491-519">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-519">Section</span></span>|<span data-ttu-id="fc491-520">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-520">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-521">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-521">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-522">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-522">**Key**</span></span> | <span data-ttu-id="fc491-523">ключа</span><span class="sxs-lookup"><span data-stu-id="fc491-523">key</span></span> |
| <span data-ttu-id="fc491-524">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-524">**Data type**</span></span> | <span data-ttu-id="fc491-525">String</span><span class="sxs-lookup"><span data-stu-id="fc491-525">String</span></span> |
| <span data-ttu-id="fc491-526">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-526">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="fc491-527">Значение тега</span><span class="sxs-lookup"><span data-stu-id="fc491-527">Value of tag</span></span>

<span data-ttu-id="fc491-528">Указывает значение тега</span><span class="sxs-lookup"><span data-stu-id="fc491-528">Specifies the value of tag</span></span>

|<span data-ttu-id="fc491-529">Section</span><span class="sxs-lookup"><span data-stu-id="fc491-529">Section</span></span>|<span data-ttu-id="fc491-530">Значение</span><span class="sxs-lookup"><span data-stu-id="fc491-530">Value</span></span>|
|:---|:---|
| <span data-ttu-id="fc491-531">**Домен**</span><span class="sxs-lookup"><span data-stu-id="fc491-531">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="fc491-532">**Key**</span><span class="sxs-lookup"><span data-stu-id="fc491-532">**Key**</span></span> | <span data-ttu-id="fc491-533">значение</span><span class="sxs-lookup"><span data-stu-id="fc491-533">value</span></span> |
| <span data-ttu-id="fc491-534">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fc491-534">**Data type**</span></span> | <span data-ttu-id="fc491-535">String</span><span class="sxs-lookup"><span data-stu-id="fc491-535">String</span></span> |
| <span data-ttu-id="fc491-536">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="fc491-536">**Possible values**</span></span> | <span data-ttu-id="fc491-537">любая строка</span><span class="sxs-lookup"><span data-stu-id="fc491-537">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="fc491-538">Можно установить только одно значение для каждого типа тегов.</span><span class="sxs-lookup"><span data-stu-id="fc491-538">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="fc491-539">Тип тегов уникален и не должен повторяться в одном профиле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fc491-539">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="fc491-540">Рекомендуемый профиль конфигурации</span><span class="sxs-lookup"><span data-stu-id="fc491-540">Recommended configuration profile</span></span>

<span data-ttu-id="fc491-541">Чтобы начать работу, рекомендуется в следующей конфигурации для предприятия воспользоваться всеми функциями защиты, которые предоставляет Microsoft Defender для Endpoint.</span><span class="sxs-lookup"><span data-stu-id="fc491-541">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="fc491-542">Следующий профиль конфигурации (или, в случае JAMF, список свойств, которые можно было бы загрузить в настраиваемый профиль конфигурации параметров) будет:</span><span class="sxs-lookup"><span data-stu-id="fc491-542">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="fc491-543">Включить защиту в режиме реального времени (RTP)</span><span class="sxs-lookup"><span data-stu-id="fc491-543">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="fc491-544">Укажите, как обрабатываются следующие типы угроз:</span><span class="sxs-lookup"><span data-stu-id="fc491-544">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="fc491-545">**Потенциально нежелательные приложения (PUA)** заблокированы</span><span class="sxs-lookup"><span data-stu-id="fc491-545">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="fc491-546">**Архивные бомбы** (файл с высокой скоростью сжатия) проверяются в журналах Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="fc491-546">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="fc491-547">Включить автоматические обновления сведении о безопасности</span><span class="sxs-lookup"><span data-stu-id="fc491-547">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="fc491-548">Включение облачной защиты</span><span class="sxs-lookup"><span data-stu-id="fc491-548">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="fc491-549">Включить автоматическую отправку образца</span><span class="sxs-lookup"><span data-stu-id="fc491-549">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="fc491-550">Список свойств для профиля конфигурации JAMF</span><span class="sxs-lookup"><span data-stu-id="fc491-550">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="fc491-551">Профиль Intune</span><span class="sxs-lookup"><span data-stu-id="fc491-551">Intune profile</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="fc491-552">Пример профиля полной конфигурации</span><span class="sxs-lookup"><span data-stu-id="fc491-552">Full configuration profile example</span></span>

<span data-ttu-id="fc491-553">В следующих шаблонах содержатся записи для всех параметров, описанных в этом документе, и их можно использовать для более сложных сценариев, в которых требуется больше контроля над Microsoft Defender для конечной точки на macOS.</span><span class="sxs-lookup"><span data-stu-id="fc491-553">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="fc491-554">Список свойств для профиля конфигурации JAMF</span><span class="sxs-lookup"><span data-stu-id="fc491-554">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/Users/*/git</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="fc491-555">Профиль Intune</span><span class="sxs-lookup"><span data-stu-id="fc491-555">Intune profile</span></span>

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/Users/*/git</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a><span data-ttu-id="fc491-556">Проверка списка свойств</span><span class="sxs-lookup"><span data-stu-id="fc491-556">Property list validation</span></span>

<span data-ttu-id="fc491-557">Список свойств должен быть допустимым *файлом .plist.*</span><span class="sxs-lookup"><span data-stu-id="fc491-557">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="fc491-558">Это можно проверить, исполнив:</span><span class="sxs-lookup"><span data-stu-id="fc491-558">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="fc491-559">Если файл хорошо сформирован, вышеуказанная команда выводит и возвращает `OK` код выхода `0` .</span><span class="sxs-lookup"><span data-stu-id="fc491-559">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="fc491-560">В противном случае отображается ошибка, описываемая проблемой, и команда возвращает код выхода `1` .</span><span class="sxs-lookup"><span data-stu-id="fc491-560">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="fc491-561">Развертывание профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="fc491-561">Configuration profile deployment</span></span>

<span data-ttu-id="fc491-562">После того как вы создали профиль конфигурации для предприятия, вы можете развернуть его через консоль управления, которую использует ваше предприятие.</span><span class="sxs-lookup"><span data-stu-id="fc491-562">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="fc491-563">В следующих разделах указаны инструкции по развертыванию этого профиля с помощью JAMF и Intune.</span><span class="sxs-lookup"><span data-stu-id="fc491-563">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="fc491-564">Развертывание JAMF</span><span class="sxs-lookup"><span data-stu-id="fc491-564">JAMF deployment</span></span>

<span data-ttu-id="fc491-565">С консоли JAMF откройте профили конфигурации компьютеров , перейдите в профиль конфигурации, который вы хотите использовать, а затем выберите  >   **настраиваемые Параметры**.</span><span class="sxs-lookup"><span data-stu-id="fc491-565">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="fc491-566">Создайте запись в качестве домена предпочтений и загрузите ранее произведенный `com.microsoft.wdav` *список .plist.*</span><span class="sxs-lookup"><span data-stu-id="fc491-566">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="fc491-567">Необходимо ввести правильный домен предпочтений (); в противном случае параметры не будут `com.microsoft.wdav` распознаны Защитником Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="fc491-567">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="fc491-568">Развертывание Intune</span><span class="sxs-lookup"><span data-stu-id="fc491-568">Intune deployment</span></span>

1. <span data-ttu-id="fc491-569">Откройте   >  **конфигурацию управления устройством.**</span><span class="sxs-lookup"><span data-stu-id="fc491-569">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="fc491-570">Выберите **Управление**  >  **профилями**  >  **Создание профиля**.</span><span class="sxs-lookup"><span data-stu-id="fc491-570">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="fc491-571">Выберите имя для профиля.</span><span class="sxs-lookup"><span data-stu-id="fc491-571">Choose a name for the profile.</span></span> <span data-ttu-id="fc491-572">Изменение **platform=macOS на** **тип profile=Custom.**</span><span class="sxs-lookup"><span data-stu-id="fc491-572">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="fc491-573">Выберите Настройка.</span><span class="sxs-lookup"><span data-stu-id="fc491-573">Select Configure.</span></span>

3. <span data-ttu-id="fc491-574">Сохранение списка .plist, выпущенного ранее как `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="fc491-574">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="fc491-575">Введите `com.microsoft.wdav` в **качестве настраиваемой конфигурации имя профиля**.</span><span class="sxs-lookup"><span data-stu-id="fc491-575">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="fc491-576">Откройте профиль конфигурации и загрузите `com.microsoft.wdav.xml` файл.</span><span class="sxs-lookup"><span data-stu-id="fc491-576">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="fc491-577">(Этот файл был создан в шаге 3.)</span><span class="sxs-lookup"><span data-stu-id="fc491-577">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="fc491-578">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fc491-578">Select **OK**.</span></span>

7. <span data-ttu-id="fc491-579">Выберите **управление**  >  **назначениями.**</span><span class="sxs-lookup"><span data-stu-id="fc491-579">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="fc491-580">На **вкладке Включить** выберите Назначение всем пользователям & **всех устройств.**</span><span class="sxs-lookup"><span data-stu-id="fc491-580">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="fc491-581">Необходимо ввести правильное имя профиля настраиваемой конфигурации; в противном случае эти параметры не будут распознаться Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="fc491-581">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="fc491-582">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="fc491-582">Resources</span></span>

- [<span data-ttu-id="fc491-583">Справочник по профилям конфигурации (документация для разработчиков Apple)</span><span class="sxs-lookup"><span data-stu-id="fc491-583">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
