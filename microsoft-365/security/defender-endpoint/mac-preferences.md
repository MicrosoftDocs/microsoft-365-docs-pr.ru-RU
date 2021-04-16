---
title: Настройка предпочтений для Microsoft Defender для конечной точки для Mac
description: Настройка Microsoft Defender для конечной точки для Mac в корпоративных организациях.
keywords: Microsoft, defender, atp, mac, management, preferences, enterprise, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: d2bea469031e2c5932e859fbad7d442ebe4d34ed
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860927"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="d8be4-104">Настройка предпочтений для Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="d8be4-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d8be4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d8be4-105">**Applies to:**</span></span>

- [<span data-ttu-id="d8be4-106">Microsoft Defender для конечной точки в macOS</span><span class="sxs-lookup"><span data-stu-id="d8be4-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="d8be4-107">В этой статье содержатся инструкции по выбору предпочтений для Microsoft Defender для конечной точки на macOS в корпоративных организациях.</span><span class="sxs-lookup"><span data-stu-id="d8be4-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="d8be4-108">Чтобы настроить Microsoft Defender для конечной точки на macOS с помощью интерфейса командной строки, см. [в пункте Ресурсы.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="d8be4-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="d8be4-109">Аннотация</span><span class="sxs-lookup"><span data-stu-id="d8be4-109">Summary</span></span>

<span data-ttu-id="d8be4-110">В корпоративных организациях управление Microsoft Defender для конечной точки на macOS можно с помощью профиля конфигурации, развернутого с помощью одного из нескольких средств управления.</span><span class="sxs-lookup"><span data-stu-id="d8be4-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="d8be4-111">Предпочтения, управляемые командой операций безопасности, имеют приоритет над предпочтениями, задав локализованные параметры на устройстве.</span><span class="sxs-lookup"><span data-stu-id="d8be4-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="d8be4-112">Изменение предпочтений, задающихся в профиле конфигурации, требует дополнительных привилегий и недоступна пользователям без административных разрешений.</span><span class="sxs-lookup"><span data-stu-id="d8be4-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="d8be4-113">В этой статье описывается структура профиля конфигурации, содержится рекомендуемый профиль, который можно использовать для начала работы, и содержатся инструкции по развертыванию профиля.</span><span class="sxs-lookup"><span data-stu-id="d8be4-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="d8be4-114">Структура профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="d8be4-114">Configuration profile structure</span></span>

<span data-ttu-id="d8be4-115">Профиль конфигурации — это *файл .plist,* состоящий из записей, идентифицированных ключом (который обозначает имя предпочтения), за которым следует значение, которое зависит от характера предпочтения.</span><span class="sxs-lookup"><span data-stu-id="d8be4-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="d8be4-116">Значения могут быть простыми (например, численное значение) или сложными, например вложенным списком предпочтений.</span><span class="sxs-lookup"><span data-stu-id="d8be4-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="d8be4-117">Макет профиля конфигурации зависит от используемой консоли управления.</span><span class="sxs-lookup"><span data-stu-id="d8be4-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="d8be4-118">В следующих разделах содержатся примеры профилей конфигурации для JAMF и Intune.</span><span class="sxs-lookup"><span data-stu-id="d8be4-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="d8be4-119">Верхний уровень профиля конфигурации включает в себя все продукты и записи для subareas Microsoft Defender для конечной точки, которые подробно объясняются в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="d8be4-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="d8be4-120">Параметры антивирусного двигателя</span><span class="sxs-lookup"><span data-stu-id="d8be4-120">Antivirus engine preferences</span></span>

<span data-ttu-id="d8be4-121">Раздел *antivirusEngine* профиля конфигурации используется для управления предпочтениями антивирусного компонента Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d8be4-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="d8be4-122">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-122">Section</span></span>|<span data-ttu-id="d8be4-123">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-124">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-125">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-125">**Key**</span></span> | <span data-ttu-id="d8be4-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="d8be4-126">antivirusEngine</span></span> |
| <span data-ttu-id="d8be4-127">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-127">**Data type**</span></span> | <span data-ttu-id="d8be4-128">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="d8be4-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d8be4-129">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-129">**Comments**</span></span> | <span data-ttu-id="d8be4-130">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="d8be4-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="d8be4-131">Включить и отключить защиту в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="d8be4-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="d8be4-132">Укажите, следует ли включить защиту в режиме реального времени, которая сканирует файлы по мере их доступа.</span><span class="sxs-lookup"><span data-stu-id="d8be4-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="d8be4-133">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-133">Section</span></span>|<span data-ttu-id="d8be4-134">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-135">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-136">**Key**</span></span> | <span data-ttu-id="d8be4-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="d8be4-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="d8be4-138">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-138">**Data type**</span></span> | <span data-ttu-id="d8be4-139">Логический</span><span class="sxs-lookup"><span data-stu-id="d8be4-139">Boolean</span></span> |
| <span data-ttu-id="d8be4-140">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-140">**Possible values**</span></span> | <span data-ttu-id="d8be4-141">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d8be4-141">true (default)</span></span> <br/> <span data-ttu-id="d8be4-142">false</span><span class="sxs-lookup"><span data-stu-id="d8be4-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="d8be4-143">Включить и отключить пассивный режим</span><span class="sxs-lookup"><span data-stu-id="d8be4-143">Enable / disable passive mode</span></span>

<span data-ttu-id="d8be4-144">Укажите, работает ли антивирусный двигатель в пассивном режиме.</span><span class="sxs-lookup"><span data-stu-id="d8be4-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="d8be4-145">Пассивный режим имеет следующие последствия:</span><span class="sxs-lookup"><span data-stu-id="d8be4-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="d8be4-146">Защита в режиме реального времени отключена</span><span class="sxs-lookup"><span data-stu-id="d8be4-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="d8be4-147">Включено сканирование по запросу</span><span class="sxs-lookup"><span data-stu-id="d8be4-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="d8be4-148">Автоматическое устранение угрозы отключено</span><span class="sxs-lookup"><span data-stu-id="d8be4-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="d8be4-149">Включаем обновления разведки безопасности</span><span class="sxs-lookup"><span data-stu-id="d8be4-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="d8be4-150">Значок меню состояния скрыт</span><span class="sxs-lookup"><span data-stu-id="d8be4-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="d8be4-151">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-151">Section</span></span>|<span data-ttu-id="d8be4-152">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-153">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-154">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-154">**Key**</span></span> | <span data-ttu-id="d8be4-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="d8be4-155">passiveMode</span></span> |
| <span data-ttu-id="d8be4-156">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-156">**Data type**</span></span> | <span data-ttu-id="d8be4-157">Логический</span><span class="sxs-lookup"><span data-stu-id="d8be4-157">Boolean</span></span> |
| <span data-ttu-id="d8be4-158">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-158">**Possible values**</span></span> | <span data-ttu-id="d8be4-159">false (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d8be4-159">false (default)</span></span> <br/> <span data-ttu-id="d8be4-160">true</span><span class="sxs-lookup"><span data-stu-id="d8be4-160">true</span></span> |
| <span data-ttu-id="d8be4-161">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-161">**Comments**</span></span> | <span data-ttu-id="d8be4-162">Доступно в Microsoft Defender для конечной точки версии 100.67.60 или выше.</span><span class="sxs-lookup"><span data-stu-id="d8be4-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="d8be4-163">Политика слияния исключений</span><span class="sxs-lookup"><span data-stu-id="d8be4-163">Exclusion merge policy</span></span>

<span data-ttu-id="d8be4-164">Укажите политику слияния исключений.</span><span class="sxs-lookup"><span data-stu-id="d8be4-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="d8be4-165">Это может быть сочетание исключений, определенных администратором и пользователей , или только исключений, определенных `merge` администратором ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="d8be4-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="d8be4-166">Этот параметр можно использовать, чтобы ограничить местным пользователям определение собственных исключений.</span><span class="sxs-lookup"><span data-stu-id="d8be4-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="d8be4-167">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-167">Section</span></span>|<span data-ttu-id="d8be4-168">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-169">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-170">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-170">**Key**</span></span> | <span data-ttu-id="d8be4-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="d8be4-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="d8be4-172">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-172">**Data type**</span></span> | <span data-ttu-id="d8be4-173">String</span><span class="sxs-lookup"><span data-stu-id="d8be4-173">String</span></span> |
| <span data-ttu-id="d8be4-174">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-174">**Possible values**</span></span> | <span data-ttu-id="d8be4-175">слияние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d8be4-175">merge (default)</span></span> <br/> <span data-ttu-id="d8be4-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="d8be4-176">admin_only</span></span> |
| <span data-ttu-id="d8be4-177">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-177">**Comments**</span></span> | <span data-ttu-id="d8be4-178">Доступно в Microsoft Defender для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="d8be4-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="d8be4-179">Исключения сканирования</span><span class="sxs-lookup"><span data-stu-id="d8be4-179">Scan exclusions</span></span>

<span data-ttu-id="d8be4-180">Укажите объекты, исключенные из проверки.</span><span class="sxs-lookup"><span data-stu-id="d8be4-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="d8be4-181">Исключения могут быть указаны полными путями, расширениями или именами файлов.</span><span class="sxs-lookup"><span data-stu-id="d8be4-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|<span data-ttu-id="d8be4-182">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-182">Section</span></span>|<span data-ttu-id="d8be4-183">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-183">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-184">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-184">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-185">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-185">**Key**</span></span> | <span data-ttu-id="d8be4-186">исключения</span><span class="sxs-lookup"><span data-stu-id="d8be4-186">exclusions</span></span> |
| <span data-ttu-id="d8be4-187">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-187">**Data type**</span></span> | <span data-ttu-id="d8be4-188">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="d8be4-188">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d8be4-189">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-189">**Comments**</span></span> | <span data-ttu-id="d8be4-190">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="d8be4-190">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="d8be4-191">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="d8be4-191">Type of exclusion</span></span>

<span data-ttu-id="d8be4-192">Укажите содержимое, исключенное из проверки по типу.</span><span class="sxs-lookup"><span data-stu-id="d8be4-192">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="d8be4-193">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-193">Section</span></span>|<span data-ttu-id="d8be4-194">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-194">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-195">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-195">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-196">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-196">**Key**</span></span> | <span data-ttu-id="d8be4-197">$type</span><span class="sxs-lookup"><span data-stu-id="d8be4-197">$type</span></span> |
| <span data-ttu-id="d8be4-198">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-198">**Data type**</span></span> | <span data-ttu-id="d8be4-199">String</span><span class="sxs-lookup"><span data-stu-id="d8be4-199">String</span></span> |
| <span data-ttu-id="d8be4-200">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-200">**Possible values**</span></span> | <span data-ttu-id="d8be4-201">excludedPath</span><span class="sxs-lookup"><span data-stu-id="d8be4-201">excludedPath</span></span> <br/> <span data-ttu-id="d8be4-202">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="d8be4-202">excludedFileExtension</span></span> <br/> <span data-ttu-id="d8be4-203">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="d8be4-203">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="d8be4-204">Путь к исключению контента</span><span class="sxs-lookup"><span data-stu-id="d8be4-204">Path to excluded content</span></span>

<span data-ttu-id="d8be4-205">Укажите содержимое, исключенное из проверки полным путем файла.</span><span class="sxs-lookup"><span data-stu-id="d8be4-205">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="d8be4-206">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-206">Section</span></span>|<span data-ttu-id="d8be4-207">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-207">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-208">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-208">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-209">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-209">**Key**</span></span> | <span data-ttu-id="d8be4-210">path</span><span class="sxs-lookup"><span data-stu-id="d8be4-210">path</span></span> |
| <span data-ttu-id="d8be4-211">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-211">**Data type**</span></span> | <span data-ttu-id="d8be4-212">String</span><span class="sxs-lookup"><span data-stu-id="d8be4-212">String</span></span> |
| <span data-ttu-id="d8be4-213">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-213">**Possible values**</span></span> | <span data-ttu-id="d8be4-214">допустимые пути</span><span class="sxs-lookup"><span data-stu-id="d8be4-214">valid paths</span></span> |
| <span data-ttu-id="d8be4-215">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-215">**Comments**</span></span> | <span data-ttu-id="d8be4-216">Применимо только если *$type* *исключенPath*</span><span class="sxs-lookup"><span data-stu-id="d8be4-216">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="d8be4-217">Тип пути (файл / каталог)</span><span class="sxs-lookup"><span data-stu-id="d8be4-217">Path type (file / directory)</span></span>

<span data-ttu-id="d8be4-218">Указать, *относится ли* свойство пути к файлу или каталогу.</span><span class="sxs-lookup"><span data-stu-id="d8be4-218">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="d8be4-219">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-219">Section</span></span>|<span data-ttu-id="d8be4-220">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-220">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-221">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-221">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-222">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-222">**Key**</span></span> | <span data-ttu-id="d8be4-223">isDirectory</span><span class="sxs-lookup"><span data-stu-id="d8be4-223">isDirectory</span></span> |
| <span data-ttu-id="d8be4-224">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-224">**Data type**</span></span> | <span data-ttu-id="d8be4-225">Логический</span><span class="sxs-lookup"><span data-stu-id="d8be4-225">Boolean</span></span> |
| <span data-ttu-id="d8be4-226">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-226">**Possible values**</span></span> | <span data-ttu-id="d8be4-227">false (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d8be4-227">false (default)</span></span> <br/> <span data-ttu-id="d8be4-228">true</span><span class="sxs-lookup"><span data-stu-id="d8be4-228">true</span></span> |
| <span data-ttu-id="d8be4-229">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-229">**Comments**</span></span> | <span data-ttu-id="d8be4-230">Применимо только если *$type* *исключенPath*</span><span class="sxs-lookup"><span data-stu-id="d8be4-230">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="d8be4-231">Расширение файла, исключено из сканирования</span><span class="sxs-lookup"><span data-stu-id="d8be4-231">File extension excluded from the scan</span></span>

<span data-ttu-id="d8be4-232">Укажите содержимое, исключенное из проверки расширением файла.</span><span class="sxs-lookup"><span data-stu-id="d8be4-232">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="d8be4-233">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-233">Section</span></span>|<span data-ttu-id="d8be4-234">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-234">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-235">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-235">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-236">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-236">**Key**</span></span> | <span data-ttu-id="d8be4-237">расширение</span><span class="sxs-lookup"><span data-stu-id="d8be4-237">extension</span></span> |
| <span data-ttu-id="d8be4-238">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-238">**Data type**</span></span> | <span data-ttu-id="d8be4-239">String</span><span class="sxs-lookup"><span data-stu-id="d8be4-239">String</span></span> |
| <span data-ttu-id="d8be4-240">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-240">**Possible values**</span></span> | <span data-ttu-id="d8be4-241">допустимые расширения файлов</span><span class="sxs-lookup"><span data-stu-id="d8be4-241">valid file extensions</span></span> |
| <span data-ttu-id="d8be4-242">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-242">**Comments**</span></span> | <span data-ttu-id="d8be4-243">Применимо только если *$type* *исключеноFileExtension*</span><span class="sxs-lookup"><span data-stu-id="d8be4-243">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="d8be4-244">Процесс, исключенный из сканирования</span><span class="sxs-lookup"><span data-stu-id="d8be4-244">Process excluded from the scan</span></span>

<span data-ttu-id="d8be4-245">Укажите процесс, для которого все действия файла исключены из сканирования.</span><span class="sxs-lookup"><span data-stu-id="d8be4-245">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="d8be4-246">Процесс можно укаварить как по имени (например, так и по полному `cat` пути( `/bin/cat` например).</span><span class="sxs-lookup"><span data-stu-id="d8be4-246">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="d8be4-247">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-247">Section</span></span>|<span data-ttu-id="d8be4-248">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-248">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-249">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-250">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-250">**Key**</span></span> | <span data-ttu-id="d8be4-251">name</span><span class="sxs-lookup"><span data-stu-id="d8be4-251">name</span></span> |
| <span data-ttu-id="d8be4-252">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-252">**Data type**</span></span> | <span data-ttu-id="d8be4-253">String</span><span class="sxs-lookup"><span data-stu-id="d8be4-253">String</span></span> |
| <span data-ttu-id="d8be4-254">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-254">**Possible values**</span></span> | <span data-ttu-id="d8be4-255">любая строка</span><span class="sxs-lookup"><span data-stu-id="d8be4-255">any string</span></span> |
| <span data-ttu-id="d8be4-256">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-256">**Comments**</span></span> | <span data-ttu-id="d8be4-257">Применимо только *если $type* *исключеноFileName*</span><span class="sxs-lookup"><span data-stu-id="d8be4-257">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="d8be4-258">Разрешенные угрозы</span><span class="sxs-lookup"><span data-stu-id="d8be4-258">Allowed threats</span></span>

<span data-ttu-id="d8be4-259">Укажите угрозы по имени, которые не заблокированы Защитником для конечной точки для Mac.</span><span class="sxs-lookup"><span data-stu-id="d8be4-259">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="d8be4-260">Эти угрозы будут разрешены для запуска.</span><span class="sxs-lookup"><span data-stu-id="d8be4-260">These threats will be allowed to run.</span></span>

|<span data-ttu-id="d8be4-261">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-261">Section</span></span>|<span data-ttu-id="d8be4-262">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-262">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-263">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-263">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-264">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-264">**Key**</span></span> | <span data-ttu-id="d8be4-265">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="d8be4-265">allowedThreats</span></span> |
| <span data-ttu-id="d8be4-266">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-266">**Data type**</span></span> | <span data-ttu-id="d8be4-267">Массив строк</span><span class="sxs-lookup"><span data-stu-id="d8be4-267">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="d8be4-268">Действия с неустановляемой угрозой</span><span class="sxs-lookup"><span data-stu-id="d8be4-268">Disallowed threat actions</span></span>

<span data-ttu-id="d8be4-269">Ограничивает действия, которые может принимать локальный пользователь устройства при обнаружении угроз.</span><span class="sxs-lookup"><span data-stu-id="d8be4-269">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="d8be4-270">Действия, включенные в этот список, не отображаются в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="d8be4-270">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="d8be4-271">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-271">Section</span></span>|<span data-ttu-id="d8be4-272">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-272">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-273">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-273">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-274">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-274">**Key**</span></span> | <span data-ttu-id="d8be4-275">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="d8be4-275">disallowedThreatActions</span></span> |
| <span data-ttu-id="d8be4-276">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-276">**Data type**</span></span> | <span data-ttu-id="d8be4-277">Массив строк</span><span class="sxs-lookup"><span data-stu-id="d8be4-277">Array of strings</span></span> |
| <span data-ttu-id="d8be4-278">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-278">**Possible values**</span></span> | <span data-ttu-id="d8be4-279">разрешить (ограничивает пользователей от допуска угроз)</span><span class="sxs-lookup"><span data-stu-id="d8be4-279">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="d8be4-280">восстановление (ограничивает пользователей от восстановления угроз из карантина)</span><span class="sxs-lookup"><span data-stu-id="d8be4-280">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="d8be4-281">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-281">**Comments**</span></span> | <span data-ttu-id="d8be4-282">Доступно в Microsoft Defender для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="d8be4-282">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="d8be4-283">Параметры типа угроз</span><span class="sxs-lookup"><span data-stu-id="d8be4-283">Threat type settings</span></span>

<span data-ttu-id="d8be4-284">Укажите, как определенные типы угроз обрабатываются Microsoft Defender для конечной точки на macOS.</span><span class="sxs-lookup"><span data-stu-id="d8be4-284">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="d8be4-285">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-285">Section</span></span>|<span data-ttu-id="d8be4-286">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-286">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-287">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-287">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-288">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-288">**Key**</span></span> | <span data-ttu-id="d8be4-289">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="d8be4-289">threatTypeSettings</span></span> |
| <span data-ttu-id="d8be4-290">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-290">**Data type**</span></span> | <span data-ttu-id="d8be4-291">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="d8be4-291">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d8be4-292">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-292">**Comments**</span></span> | <span data-ttu-id="d8be4-293">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="d8be4-293">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="d8be4-294">Тип угрозы</span><span class="sxs-lookup"><span data-stu-id="d8be4-294">Threat type</span></span>

<span data-ttu-id="d8be4-295">Укажите типы угроз.</span><span class="sxs-lookup"><span data-stu-id="d8be4-295">Specify threat types.</span></span>

|<span data-ttu-id="d8be4-296">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-296">Section</span></span>|<span data-ttu-id="d8be4-297">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-298">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-299">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-299">**Key**</span></span> | <span data-ttu-id="d8be4-300">ключа</span><span class="sxs-lookup"><span data-stu-id="d8be4-300">key</span></span> |
| <span data-ttu-id="d8be4-301">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-301">**Data type**</span></span> | <span data-ttu-id="d8be4-302">String</span><span class="sxs-lookup"><span data-stu-id="d8be4-302">String</span></span> |
| <span data-ttu-id="d8be4-303">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-303">**Possible values**</span></span> | <span data-ttu-id="d8be4-304">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="d8be4-304">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="d8be4-305">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="d8be4-305">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="d8be4-306">Действие</span><span class="sxs-lookup"><span data-stu-id="d8be4-306">Action to take</span></span>

<span data-ttu-id="d8be4-307">Укажите, какие действия необходимо принять при обнаружении угрозы типа, указанного в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="d8be4-307">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="d8be4-308">Выберите из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="d8be4-308">Choose from the following options:</span></span>

- <span data-ttu-id="d8be4-309">**Аудит:** устройство не защищено от этого типа угрозы, но запись об угрозе регистрируется.</span><span class="sxs-lookup"><span data-stu-id="d8be4-309">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="d8be4-310">**Блок:** ваше устройство защищено от этого типа угрозы, и вы будете уведомлены в пользовательском интерфейсе и консоли безопасности.</span><span class="sxs-lookup"><span data-stu-id="d8be4-310">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="d8be4-311">**Отключено:** устройство не защищено от этого типа угрозы и ничего не регистрируется.</span><span class="sxs-lookup"><span data-stu-id="d8be4-311">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="d8be4-312">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-312">Section</span></span>|<span data-ttu-id="d8be4-313">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-313">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-314">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-314">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-315">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-315">**Key**</span></span> | <span data-ttu-id="d8be4-316">значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-316">value</span></span> |
| <span data-ttu-id="d8be4-317">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-317">**Data type**</span></span> | <span data-ttu-id="d8be4-318">String</span><span class="sxs-lookup"><span data-stu-id="d8be4-318">String</span></span> |
| <span data-ttu-id="d8be4-319">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-319">**Possible values**</span></span> | <span data-ttu-id="d8be4-320">аудит (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d8be4-320">audit (default)</span></span> <br/> <span data-ttu-id="d8be4-321">block</span><span class="sxs-lookup"><span data-stu-id="d8be4-321">block</span></span> <br/> <span data-ttu-id="d8be4-322">Off</span><span class="sxs-lookup"><span data-stu-id="d8be4-322">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="d8be4-323">Параметры типа угрозы объединяют политику слияния</span><span class="sxs-lookup"><span data-stu-id="d8be4-323">Threat type settings merge policy</span></span>

<span data-ttu-id="d8be4-324">Укажите политику слияния для параметров типа угроз.</span><span class="sxs-lookup"><span data-stu-id="d8be4-324">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="d8be4-325">Это может быть сочетание параметров, определенных администратором и определенных пользователем , или только параметров, определенных `merge` администратором ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="d8be4-325">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="d8be4-326">Этот параметр можно использовать, чтобы ограничить местным пользователям определение собственных параметров для различных типов угроз.</span><span class="sxs-lookup"><span data-stu-id="d8be4-326">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="d8be4-327">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-327">Section</span></span>|<span data-ttu-id="d8be4-328">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-328">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-329">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-329">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-330">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-330">**Key**</span></span> | <span data-ttu-id="d8be4-331">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="d8be4-331">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="d8be4-332">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-332">**Data type**</span></span> | <span data-ttu-id="d8be4-333">String</span><span class="sxs-lookup"><span data-stu-id="d8be4-333">String</span></span> |
| <span data-ttu-id="d8be4-334">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-334">**Possible values**</span></span> | <span data-ttu-id="d8be4-335">слияние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d8be4-335">merge (default)</span></span> <br/> <span data-ttu-id="d8be4-336">admin_only</span><span class="sxs-lookup"><span data-stu-id="d8be4-336">admin_only</span></span> |
| <span data-ttu-id="d8be4-337">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-337">**Comments**</span></span> | <span data-ttu-id="d8be4-338">Доступно в Microsoft Defender для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="d8be4-338">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="d8be4-339">Хранение истории антивирусного сканирования (в днях)</span><span class="sxs-lookup"><span data-stu-id="d8be4-339">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="d8be4-340">Укажите количество дней, которые сохраняются в истории сканирования на устройстве.</span><span class="sxs-lookup"><span data-stu-id="d8be4-340">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="d8be4-341">Старые результаты сканирования удаляются из истории.</span><span class="sxs-lookup"><span data-stu-id="d8be4-341">Old scan results are removed from the history.</span></span> <span data-ttu-id="d8be4-342">Старые карантинные файлы, которые также удаляются с диска.</span><span class="sxs-lookup"><span data-stu-id="d8be4-342">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="d8be4-343">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-343">Section</span></span>|<span data-ttu-id="d8be4-344">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-344">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-345">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-345">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-346">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-346">**Key**</span></span> | <span data-ttu-id="d8be4-347">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="d8be4-347">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="d8be4-348">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-348">**Data type**</span></span> | <span data-ttu-id="d8be4-349">String</span><span class="sxs-lookup"><span data-stu-id="d8be4-349">String</span></span> |
| <span data-ttu-id="d8be4-350">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-350">**Possible values**</span></span> | <span data-ttu-id="d8be4-351">90 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d8be4-351">90 (default).</span></span> <span data-ttu-id="d8be4-352">Допустимые значения от 1 дня до 180 дней.</span><span class="sxs-lookup"><span data-stu-id="d8be4-352">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="d8be4-353">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-353">**Comments**</span></span> | <span data-ttu-id="d8be4-354">Доступно в Microsoft Defender для конечной точки версии 101.07.23 или выше.</span><span class="sxs-lookup"><span data-stu-id="d8be4-354">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="d8be4-355">Максимальное количество элементов в истории антивирусного сканирования</span><span class="sxs-lookup"><span data-stu-id="d8be4-355">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="d8be4-356">Укажите максимальное количество записей, которые необходимо сохранить в истории сканирования.</span><span class="sxs-lookup"><span data-stu-id="d8be4-356">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="d8be4-357">Записи включают все проверки по запросу, выполняемые в прошлом, и все обнаружения антивирусов.</span><span class="sxs-lookup"><span data-stu-id="d8be4-357">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="d8be4-358">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-358">Section</span></span>|<span data-ttu-id="d8be4-359">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-359">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-360">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-360">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-361">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-361">**Key**</span></span> | <span data-ttu-id="d8be4-362">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="d8be4-362">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="d8be4-363">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-363">**Data type**</span></span> | <span data-ttu-id="d8be4-364">String</span><span class="sxs-lookup"><span data-stu-id="d8be4-364">String</span></span> |
| <span data-ttu-id="d8be4-365">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-365">**Possible values**</span></span> | <span data-ttu-id="d8be4-366">10000 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d8be4-366">10000 (default).</span></span> <span data-ttu-id="d8be4-367">Допустимые значения : от 5000 элементов до 15000 элементов.</span><span class="sxs-lookup"><span data-stu-id="d8be4-367">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="d8be4-368">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-368">**Comments**</span></span> | <span data-ttu-id="d8be4-369">Доступно в Microsoft Defender для конечной точки версии 101.07.23 или выше.</span><span class="sxs-lookup"><span data-stu-id="d8be4-369">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="d8be4-370">Параметры защиты с облачной доставкой</span><span class="sxs-lookup"><span data-stu-id="d8be4-370">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="d8be4-371">Настройка облачных функций защиты Microsoft Defender для конечной точки на macOS.</span><span class="sxs-lookup"><span data-stu-id="d8be4-371">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="d8be4-372">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-372">Section</span></span>|<span data-ttu-id="d8be4-373">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-373">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-374">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-374">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-375">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-375">**Key**</span></span> | <span data-ttu-id="d8be4-376">cloudService</span><span class="sxs-lookup"><span data-stu-id="d8be4-376">cloudService</span></span> |
| <span data-ttu-id="d8be4-377">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-377">**Data type**</span></span> | <span data-ttu-id="d8be4-378">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="d8be4-378">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d8be4-379">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-379">**Comments**</span></span> | <span data-ttu-id="d8be4-380">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="d8be4-380">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="d8be4-381">Включить и отключить облачную защиту</span><span class="sxs-lookup"><span data-stu-id="d8be4-381">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="d8be4-382">Укажите, включить ли облачную защиту устройства или нет.</span><span class="sxs-lookup"><span data-stu-id="d8be4-382">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="d8be4-383">Чтобы повысить безопасность ваших служб, рекомендуется сохранить эту функцию включенной.</span><span class="sxs-lookup"><span data-stu-id="d8be4-383">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="d8be4-384">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-384">Section</span></span>|<span data-ttu-id="d8be4-385">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-385">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-386">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-386">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-387">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-387">**Key**</span></span> | <span data-ttu-id="d8be4-388">включено</span><span class="sxs-lookup"><span data-stu-id="d8be4-388">enabled</span></span> |
| <span data-ttu-id="d8be4-389">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-389">**Data type**</span></span> | <span data-ttu-id="d8be4-390">Логический</span><span class="sxs-lookup"><span data-stu-id="d8be4-390">Boolean</span></span> |
| <span data-ttu-id="d8be4-391">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-391">**Possible values**</span></span> | <span data-ttu-id="d8be4-392">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d8be4-392">true (default)</span></span> <br/> <span data-ttu-id="d8be4-393">false</span><span class="sxs-lookup"><span data-stu-id="d8be4-393">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="d8be4-394">Уровень диагностической коллекции</span><span class="sxs-lookup"><span data-stu-id="d8be4-394">Diagnostic collection level</span></span>

<span data-ttu-id="d8be4-395">Диагностические данные используются для обеспечения безопасности и повышения безопасности Microsoft Defender для конечной точки, обнаружения, диагностики и устранения проблем, а также улучшения продукта.</span><span class="sxs-lookup"><span data-stu-id="d8be4-395">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="d8be4-396">Этот параметр определяет уровень диагностики, отправленной Microsoft Defender для конечной точки в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d8be4-396">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="d8be4-397">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-397">Section</span></span>|<span data-ttu-id="d8be4-398">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-399">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-400">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-400">**Key**</span></span> | <span data-ttu-id="d8be4-401">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="d8be4-401">diagnosticLevel</span></span> |
| <span data-ttu-id="d8be4-402">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-402">**Data type**</span></span> | <span data-ttu-id="d8be4-403">String</span><span class="sxs-lookup"><span data-stu-id="d8be4-403">String</span></span> |
| <span data-ttu-id="d8be4-404">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-404">**Possible values**</span></span> | <span data-ttu-id="d8be4-405">необязательный (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d8be4-405">optional (default)</span></span> <br/> <span data-ttu-id="d8be4-406">Обязательный</span><span class="sxs-lookup"><span data-stu-id="d8be4-406">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="d8be4-407">Включить и отключить автоматические отправки образцов</span><span class="sxs-lookup"><span data-stu-id="d8be4-407">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="d8be4-408">Определяет, отправляются ли подозрительные образцы (которые могут содержать угрозы) в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d8be4-408">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="d8be4-409">Вам будет предложено, если в отправленных файлах могут содержаться персональные данные.</span><span class="sxs-lookup"><span data-stu-id="d8be4-409">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="d8be4-410">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-410">Section</span></span>|<span data-ttu-id="d8be4-411">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-411">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-412">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-412">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-413">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-413">**Key**</span></span> | <span data-ttu-id="d8be4-414">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="d8be4-414">automaticSampleSubmission</span></span> |
| <span data-ttu-id="d8be4-415">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-415">**Data type**</span></span> | <span data-ttu-id="d8be4-416">Логический</span><span class="sxs-lookup"><span data-stu-id="d8be4-416">Boolean</span></span> |
| <span data-ttu-id="d8be4-417">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-417">**Possible values**</span></span> | <span data-ttu-id="d8be4-418">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d8be4-418">true (default)</span></span> <br/> <span data-ttu-id="d8be4-419">false</span><span class="sxs-lookup"><span data-stu-id="d8be4-419">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="d8be4-420">Включить и отключить автоматические обновления сведении о безопасности</span><span class="sxs-lookup"><span data-stu-id="d8be4-420">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="d8be4-421">Определяет, устанавливаются ли обновления разведки безопасности автоматически:</span><span class="sxs-lookup"><span data-stu-id="d8be4-421">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="d8be4-422">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-422">Section</span></span>|<span data-ttu-id="d8be4-423">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-424">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-424">**Key**</span></span> | <span data-ttu-id="d8be4-425">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="d8be4-425">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="d8be4-426">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-426">**Data type**</span></span> | <span data-ttu-id="d8be4-427">Логический</span><span class="sxs-lookup"><span data-stu-id="d8be4-427">Boolean</span></span> |
| <span data-ttu-id="d8be4-428">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-428">**Possible values**</span></span> | <span data-ttu-id="d8be4-429">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d8be4-429">true (default)</span></span> <br/> <span data-ttu-id="d8be4-430">false</span><span class="sxs-lookup"><span data-stu-id="d8be4-430">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="d8be4-431">Предпочтения пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="d8be4-431">User interface preferences</span></span>

<span data-ttu-id="d8be4-432">Управление предпочтениями пользовательского интерфейса Microsoft Defender для конечной точки на macOS.</span><span class="sxs-lookup"><span data-stu-id="d8be4-432">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="d8be4-433">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-433">Section</span></span>|<span data-ttu-id="d8be4-434">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-434">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-435">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-435">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-436">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-436">**Key**</span></span> | <span data-ttu-id="d8be4-437">userInterface</span><span class="sxs-lookup"><span data-stu-id="d8be4-437">userInterface</span></span> |
| <span data-ttu-id="d8be4-438">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-438">**Data type**</span></span> | <span data-ttu-id="d8be4-439">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="d8be4-439">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d8be4-440">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-440">**Comments**</span></span> | <span data-ttu-id="d8be4-441">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="d8be4-441">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="d8be4-442">Значок меню "Показать/ скрыть состояние"</span><span class="sxs-lookup"><span data-stu-id="d8be4-442">Show / hide status menu icon</span></span>

<span data-ttu-id="d8be4-443">Укажите, показывать или скрывать значок меню состояния в правом верхнем углу экрана.</span><span class="sxs-lookup"><span data-stu-id="d8be4-443">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="d8be4-444">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-444">Section</span></span>|<span data-ttu-id="d8be4-445">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-445">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-446">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-447">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-447">**Key**</span></span> | <span data-ttu-id="d8be4-448">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="d8be4-448">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="d8be4-449">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-449">**Data type**</span></span> | <span data-ttu-id="d8be4-450">Логический</span><span class="sxs-lookup"><span data-stu-id="d8be4-450">Boolean</span></span> |
| <span data-ttu-id="d8be4-451">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-451">**Possible values**</span></span> | <span data-ttu-id="d8be4-452">false (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d8be4-452">false (default)</span></span> <br/> <span data-ttu-id="d8be4-453">true</span><span class="sxs-lookup"><span data-stu-id="d8be4-453">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="d8be4-454">Параметр Show/hide для отправки отзывов</span><span class="sxs-lookup"><span data-stu-id="d8be4-454">Show / hide option to send feedback</span></span>

<span data-ttu-id="d8be4-455">Укажите, могут ли пользователи отправлять отзывы в Корпорацию Майкрософт, переехав `Help`  >  `Send Feedback` в .</span><span class="sxs-lookup"><span data-stu-id="d8be4-455">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="d8be4-456">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-456">Section</span></span>|<span data-ttu-id="d8be4-457">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-457">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-458">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-458">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-459">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-459">**Key**</span></span> | <span data-ttu-id="d8be4-460">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="d8be4-460">userInitiatedFeedback</span></span> |
| <span data-ttu-id="d8be4-461">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-461">**Data type**</span></span> | <span data-ttu-id="d8be4-462">String</span><span class="sxs-lookup"><span data-stu-id="d8be4-462">String</span></span> |
| <span data-ttu-id="d8be4-463">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-463">**Possible values**</span></span> | <span data-ttu-id="d8be4-464">включено (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d8be4-464">enabled (default)</span></span> <br/> <span data-ttu-id="d8be4-465">отключено</span><span class="sxs-lookup"><span data-stu-id="d8be4-465">disabled</span></span> |
| <span data-ttu-id="d8be4-466">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-466">**Comments**</span></span> | <span data-ttu-id="d8be4-467">Доступно в Microsoft Defender для конечной точки версии 101.19.61 или выше.</span><span class="sxs-lookup"><span data-stu-id="d8be4-467">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="d8be4-468">Параметры обнаружения конечных точек и ответов</span><span class="sxs-lookup"><span data-stu-id="d8be4-468">Endpoint detection and response preferences</span></span>

<span data-ttu-id="d8be4-469">Управление предпочтениями компонента обнаружения конечной точки и ответа (EDR) Microsoft Defender для конечной точки на macOS.</span><span class="sxs-lookup"><span data-stu-id="d8be4-469">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="d8be4-470">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-470">Section</span></span>|<span data-ttu-id="d8be4-471">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-471">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-472">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-472">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-473">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-473">**Key**</span></span> | <span data-ttu-id="d8be4-474">edr</span><span class="sxs-lookup"><span data-stu-id="d8be4-474">edr</span></span> |
| <span data-ttu-id="d8be4-475">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-475">**Data type**</span></span> | <span data-ttu-id="d8be4-476">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="d8be4-476">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d8be4-477">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-477">**Comments**</span></span> | <span data-ttu-id="d8be4-478">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="d8be4-478">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="d8be4-479">Теги устройств</span><span class="sxs-lookup"><span data-stu-id="d8be4-479">Device tags</span></span>

<span data-ttu-id="d8be4-480">Укажите имя тега и его значение.</span><span class="sxs-lookup"><span data-stu-id="d8be4-480">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="d8be4-481">Тег GROUP указывает устройство с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="d8be4-481">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="d8be4-482">Тег отражается на портале на странице устройства и может использоваться для фильтрации и группировки устройств.</span><span class="sxs-lookup"><span data-stu-id="d8be4-482">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="d8be4-483">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-483">Section</span></span>|<span data-ttu-id="d8be4-484">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-484">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-485">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-485">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-486">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-486">**Key**</span></span> | <span data-ttu-id="d8be4-487">tags</span><span class="sxs-lookup"><span data-stu-id="d8be4-487">tags</span></span> |
| <span data-ttu-id="d8be4-488">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-488">**Data type**</span></span> | <span data-ttu-id="d8be4-489">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="d8be4-489">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d8be4-490">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="d8be4-490">**Comments**</span></span> | <span data-ttu-id="d8be4-491">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="d8be4-491">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="d8be4-492">Тип тега</span><span class="sxs-lookup"><span data-stu-id="d8be4-492">Type of tag</span></span>

<span data-ttu-id="d8be4-493">Указывает тип тега</span><span class="sxs-lookup"><span data-stu-id="d8be4-493">Specifies the type of tag</span></span>

|<span data-ttu-id="d8be4-494">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-494">Section</span></span>|<span data-ttu-id="d8be4-495">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-495">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-496">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-496">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-497">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-497">**Key**</span></span> | <span data-ttu-id="d8be4-498">ключа</span><span class="sxs-lookup"><span data-stu-id="d8be4-498">key</span></span> |
| <span data-ttu-id="d8be4-499">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-499">**Data type**</span></span> | <span data-ttu-id="d8be4-500">String</span><span class="sxs-lookup"><span data-stu-id="d8be4-500">String</span></span> |
| <span data-ttu-id="d8be4-501">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-501">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="d8be4-502">Значение тега</span><span class="sxs-lookup"><span data-stu-id="d8be4-502">Value of tag</span></span>

<span data-ttu-id="d8be4-503">Указывает значение тега</span><span class="sxs-lookup"><span data-stu-id="d8be4-503">Specifies the value of tag</span></span>

|<span data-ttu-id="d8be4-504">Section</span><span class="sxs-lookup"><span data-stu-id="d8be4-504">Section</span></span>|<span data-ttu-id="d8be4-505">Значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-505">Value</span></span>|
|:---|:---|
| <span data-ttu-id="d8be4-506">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8be4-506">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d8be4-507">**Key**</span><span class="sxs-lookup"><span data-stu-id="d8be4-507">**Key**</span></span> | <span data-ttu-id="d8be4-508">значение</span><span class="sxs-lookup"><span data-stu-id="d8be4-508">value</span></span> |
| <span data-ttu-id="d8be4-509">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d8be4-509">**Data type**</span></span> | <span data-ttu-id="d8be4-510">String</span><span class="sxs-lookup"><span data-stu-id="d8be4-510">String</span></span> |
| <span data-ttu-id="d8be4-511">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="d8be4-511">**Possible values**</span></span> | <span data-ttu-id="d8be4-512">любая строка</span><span class="sxs-lookup"><span data-stu-id="d8be4-512">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="d8be4-513">Можно установить только одно значение для каждого типа тегов.</span><span class="sxs-lookup"><span data-stu-id="d8be4-513">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="d8be4-514">Тип тегов уникален и не должен повторяться в одном профиле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d8be4-514">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="d8be4-515">Рекомендуемый профиль конфигурации</span><span class="sxs-lookup"><span data-stu-id="d8be4-515">Recommended configuration profile</span></span>

<span data-ttu-id="d8be4-516">Чтобы начать работу, рекомендуется в следующей конфигурации для предприятия воспользоваться всеми функциями защиты, которые предоставляет Microsoft Defender для Endpoint.</span><span class="sxs-lookup"><span data-stu-id="d8be4-516">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="d8be4-517">Следующий профиль конфигурации (или, в случае JAMF, список свойств, которые можно было бы загрузить в настраиваемый профиль конфигурации параметров) будет:</span><span class="sxs-lookup"><span data-stu-id="d8be4-517">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="d8be4-518">Включить защиту в режиме реального времени (RTP)</span><span class="sxs-lookup"><span data-stu-id="d8be4-518">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="d8be4-519">Укажите, как обрабатываются следующие типы угроз:</span><span class="sxs-lookup"><span data-stu-id="d8be4-519">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="d8be4-520">**Потенциально нежелательные приложения (PUA)** заблокированы</span><span class="sxs-lookup"><span data-stu-id="d8be4-520">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="d8be4-521">**Архивные бомбы** (файл с высокой скоростью сжатия) проверяются в журналах Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="d8be4-521">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="d8be4-522">Включить автоматические обновления сведении о безопасности</span><span class="sxs-lookup"><span data-stu-id="d8be4-522">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="d8be4-523">Включить облачную защиту</span><span class="sxs-lookup"><span data-stu-id="d8be4-523">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="d8be4-524">Включить автоматическую отправку образца</span><span class="sxs-lookup"><span data-stu-id="d8be4-524">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="d8be4-525">Список свойств для профиля конфигурации JAMF</span><span class="sxs-lookup"><span data-stu-id="d8be4-525">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="d8be4-526">Профиль Intune</span><span class="sxs-lookup"><span data-stu-id="d8be4-526">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="d8be4-527">Пример профиля полной конфигурации</span><span class="sxs-lookup"><span data-stu-id="d8be4-527">Full configuration profile example</span></span>

<span data-ttu-id="d8be4-528">В следующих шаблонах содержатся записи для всех параметров, описанных в этом документе, и их можно использовать для более сложных сценариев, в которых требуется больше контроля над Microsoft Defender для конечной точки на macOS.</span><span class="sxs-lookup"><span data-stu-id="d8be4-528">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="d8be4-529">Список свойств для профиля конфигурации JAMF</span><span class="sxs-lookup"><span data-stu-id="d8be4-529">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="d8be4-530">Профиль Intune</span><span class="sxs-lookup"><span data-stu-id="d8be4-530">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="d8be4-531">Проверка списка свойств</span><span class="sxs-lookup"><span data-stu-id="d8be4-531">Property list validation</span></span>

<span data-ttu-id="d8be4-532">Список свойств должен быть допустимым *файлом .plist.*</span><span class="sxs-lookup"><span data-stu-id="d8be4-532">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="d8be4-533">Это можно проверить, исполнив:</span><span class="sxs-lookup"><span data-stu-id="d8be4-533">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="d8be4-534">Если файл хорошо сформирован, вышеуказанная команда выводит и возвращает `OK` код выхода `0` .</span><span class="sxs-lookup"><span data-stu-id="d8be4-534">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="d8be4-535">В противном случае отображается ошибка, описываемая проблемой, и команда возвращает код выхода `1` .</span><span class="sxs-lookup"><span data-stu-id="d8be4-535">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="d8be4-536">Развертывание профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="d8be4-536">Configuration profile deployment</span></span>

<span data-ttu-id="d8be4-537">После того как вы создали профиль конфигурации для предприятия, вы можете развернуть его через консоль управления, которую использует ваше предприятие.</span><span class="sxs-lookup"><span data-stu-id="d8be4-537">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="d8be4-538">В следующих разделах указаны инструкции по развертыванию этого профиля с помощью JAMF и Intune.</span><span class="sxs-lookup"><span data-stu-id="d8be4-538">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="d8be4-539">Развертывание JAMF</span><span class="sxs-lookup"><span data-stu-id="d8be4-539">JAMF deployment</span></span>

<span data-ttu-id="d8be4-540">На консоли JAMF откройте **профили** конфигурации компьютеров , перейдите в профиль конфигурации, который вы хотите использовать, а затем выберите  >   **настраиваемые параметры.**</span><span class="sxs-lookup"><span data-stu-id="d8be4-540">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="d8be4-541">Создайте запись в качестве домена предпочтений и загрузите ранее произведенный `com.microsoft.wdav` *список .plist.*</span><span class="sxs-lookup"><span data-stu-id="d8be4-541">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="d8be4-542">Необходимо ввести правильный домен предпочтений (); в противном случае параметры не будут `com.microsoft.wdav` распознаны Защитником Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d8be4-542">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="d8be4-543">Развертывание Intune</span><span class="sxs-lookup"><span data-stu-id="d8be4-543">Intune deployment</span></span>

1. <span data-ttu-id="d8be4-544">Откройте   >  **конфигурацию управления устройством.**</span><span class="sxs-lookup"><span data-stu-id="d8be4-544">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="d8be4-545">Выберите **Управление**  >  **профилями**  >  **Создание профиля**.</span><span class="sxs-lookup"><span data-stu-id="d8be4-545">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="d8be4-546">Выберите имя для профиля.</span><span class="sxs-lookup"><span data-stu-id="d8be4-546">Choose a name for the profile.</span></span> <span data-ttu-id="d8be4-547">Изменение **platform=macOS на** **тип profile=Custom.**</span><span class="sxs-lookup"><span data-stu-id="d8be4-547">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="d8be4-548">Выберите Настройка.</span><span class="sxs-lookup"><span data-stu-id="d8be4-548">Select Configure.</span></span>

3. <span data-ttu-id="d8be4-549">Сохранение списка .plist, выпущенного ранее как `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="d8be4-549">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="d8be4-550">Введите `com.microsoft.wdav` в **качестве настраиваемой конфигурации имя профиля**.</span><span class="sxs-lookup"><span data-stu-id="d8be4-550">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="d8be4-551">Откройте профиль конфигурации и загрузите `com.microsoft.wdav.xml` файл.</span><span class="sxs-lookup"><span data-stu-id="d8be4-551">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="d8be4-552">(Этот файл был создан в шаге 3.)</span><span class="sxs-lookup"><span data-stu-id="d8be4-552">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="d8be4-553">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d8be4-553">Select **OK**.</span></span>

7. <span data-ttu-id="d8be4-554">Выберите **управление**  >  **назначениями.**</span><span class="sxs-lookup"><span data-stu-id="d8be4-554">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="d8be4-555">На **вкладке Включить** выберите Назначение всем пользователям & **всех устройств.**</span><span class="sxs-lookup"><span data-stu-id="d8be4-555">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="d8be4-556">Необходимо ввести правильное имя профиля настраиваемой конфигурации; в противном случае эти параметры не будут распознаться Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d8be4-556">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="d8be4-557">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="d8be4-557">Resources</span></span>

- [<span data-ttu-id="d8be4-558">Справочник по профилям конфигурации (документация для разработчиков Apple)</span><span class="sxs-lookup"><span data-stu-id="d8be4-558">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
