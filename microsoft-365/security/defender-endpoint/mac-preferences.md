---
title: Настройка предпочтений для ATP Защитника Майкрософт для Mac
description: Настройка ATP Microsoft Defender для Mac в корпоративных организациях.
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
ms.openlocfilehash: 578830d44a9a69c3ccafd78ceaf59ddfe100e43f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076933"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="8de5c-104">Настройка предпочтений для Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="8de5c-104">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8de5c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8de5c-105">**Applies to:**</span></span>

- [<span data-ttu-id="8de5c-106">Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="8de5c-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="8de5c-107">В этой статье содержатся инструкции по набору предпочтений для Microsoft Defender для конечной точки для Mac в корпоративных организациях.</span><span class="sxs-lookup"><span data-stu-id="8de5c-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint for Mac in enterprise organizations.</span></span> <span data-ttu-id="8de5c-108">Чтобы настроить Microsoft Defender для конечной точки для Mac с помощью интерфейса командной строки, см. [в пункте Ресурсы.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="8de5c-108">To configure Microsoft Defender for Endpoint for Mac using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="8de5c-109">Краткое содержание</span><span class="sxs-lookup"><span data-stu-id="8de5c-109">Summary</span></span>

<span data-ttu-id="8de5c-110">В корпоративных организациях управление Microsoft Defender для конечной точки для Mac можно с помощью профиля конфигурации, развернутого с помощью одного из нескольких средств управления.</span><span class="sxs-lookup"><span data-stu-id="8de5c-110">In enterprise organizations, Microsoft Defender for Endpoint for Mac can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="8de5c-111">Предпочтения, управляемые командой операций безопасности, имеют приоритет над предпочтениями, задав локализованные параметры на устройстве.</span><span class="sxs-lookup"><span data-stu-id="8de5c-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="8de5c-112">Изменение предпочтений, задающихся в профиле конфигурации, требует дополнительных привилегий и недоступна пользователям без административных разрешений.</span><span class="sxs-lookup"><span data-stu-id="8de5c-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="8de5c-113">В этой статье описывается структура профиля конфигурации, содержится рекомендуемый профиль, который можно использовать для начала работы, и содержатся инструкции по развертыванию профиля.</span><span class="sxs-lookup"><span data-stu-id="8de5c-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="8de5c-114">Структура профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="8de5c-114">Configuration profile structure</span></span>

<span data-ttu-id="8de5c-115">Профиль конфигурации — это *файл .plist,* состоящий из записей, идентифицированных ключом (который обозначает имя предпочтения), за которым следует значение, которое зависит от характера предпочтения.</span><span class="sxs-lookup"><span data-stu-id="8de5c-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="8de5c-116">Значения могут быть простыми (например, численное значение) или сложными, например вложенным списком предпочтений.</span><span class="sxs-lookup"><span data-stu-id="8de5c-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="8de5c-117">Макет профиля конфигурации зависит от используемой консоли управления.</span><span class="sxs-lookup"><span data-stu-id="8de5c-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="8de5c-118">В следующих разделах содержатся примеры профилей конфигурации для JAMF и Intune.</span><span class="sxs-lookup"><span data-stu-id="8de5c-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="8de5c-119">Верхний уровень профиля конфигурации включает в себя все продукты и записи для subareas Microsoft Defender для конечной точки, которые подробно объясняются в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="8de5c-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="8de5c-120">Параметры антивирусного двигателя</span><span class="sxs-lookup"><span data-stu-id="8de5c-120">Antivirus engine preferences</span></span>

<span data-ttu-id="8de5c-121">Раздел *antivirusEngine* профиля конфигурации используется для управления предпочтениями антивирусного компонента Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8de5c-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-122">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-122">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-123">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-123">**Key**</span></span> | <span data-ttu-id="8de5c-124">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="8de5c-124">antivirusEngine</span></span> |
| <span data-ttu-id="8de5c-125">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-125">**Data type**</span></span> | <span data-ttu-id="8de5c-126">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="8de5c-126">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8de5c-127">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-127">**Comments**</span></span> | <span data-ttu-id="8de5c-128">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="8de5c-128">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="8de5c-129">Включить и отключить защиту в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="8de5c-129">Enable / disable real-time protection</span></span>

<span data-ttu-id="8de5c-130">Укажите, следует ли включить защиту в режиме реального времени, которая сканирует файлы по мере их доступа.</span><span class="sxs-lookup"><span data-stu-id="8de5c-130">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-131">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-131">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-132">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-132">**Key**</span></span> | <span data-ttu-id="8de5c-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="8de5c-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="8de5c-134">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-134">**Data type**</span></span> | <span data-ttu-id="8de5c-135">Логический</span><span class="sxs-lookup"><span data-stu-id="8de5c-135">Boolean</span></span> |
| <span data-ttu-id="8de5c-136">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-136">**Possible values**</span></span> | <span data-ttu-id="8de5c-137">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8de5c-137">true (default)</span></span> <br/> <span data-ttu-id="8de5c-138">false</span><span class="sxs-lookup"><span data-stu-id="8de5c-138">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="8de5c-139">Включить и отключить пассивный режим</span><span class="sxs-lookup"><span data-stu-id="8de5c-139">Enable / disable passive mode</span></span>

<span data-ttu-id="8de5c-140">Укажите, работает ли антивирусный двигатель в пассивном режиме.</span><span class="sxs-lookup"><span data-stu-id="8de5c-140">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="8de5c-141">Пассивный режим имеет следующие последствия:</span><span class="sxs-lookup"><span data-stu-id="8de5c-141">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="8de5c-142">Защита в режиме реального времени отключена</span><span class="sxs-lookup"><span data-stu-id="8de5c-142">Real-time protection is turned off</span></span>
- <span data-ttu-id="8de5c-143">Включено сканирование по запросу</span><span class="sxs-lookup"><span data-stu-id="8de5c-143">On-demand scanning is turned on</span></span>
- <span data-ttu-id="8de5c-144">Автоматическое устранение угрозы отключено</span><span class="sxs-lookup"><span data-stu-id="8de5c-144">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="8de5c-145">Включаем обновления разведки безопасности</span><span class="sxs-lookup"><span data-stu-id="8de5c-145">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="8de5c-146">Значок меню состояния скрыт</span><span class="sxs-lookup"><span data-stu-id="8de5c-146">Status menu icon is hidden</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-147">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-147">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-148">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-148">**Key**</span></span> | <span data-ttu-id="8de5c-149">passiveMode</span><span class="sxs-lookup"><span data-stu-id="8de5c-149">passiveMode</span></span> |
| <span data-ttu-id="8de5c-150">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-150">**Data type**</span></span> | <span data-ttu-id="8de5c-151">Логический</span><span class="sxs-lookup"><span data-stu-id="8de5c-151">Boolean</span></span> |
| <span data-ttu-id="8de5c-152">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-152">**Possible values**</span></span> | <span data-ttu-id="8de5c-153">false (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8de5c-153">false (default)</span></span> <br/> <span data-ttu-id="8de5c-154">true</span><span class="sxs-lookup"><span data-stu-id="8de5c-154">true</span></span> |
| <span data-ttu-id="8de5c-155">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-155">**Comments**</span></span> | <span data-ttu-id="8de5c-156">Доступно в Microsoft Defender для конечной точки версии 100.67.60 или выше.</span><span class="sxs-lookup"><span data-stu-id="8de5c-156">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="8de5c-157">Политика слияния исключений</span><span class="sxs-lookup"><span data-stu-id="8de5c-157">Exclusion merge policy</span></span>

<span data-ttu-id="8de5c-158">Укажите политику слияния исключений.</span><span class="sxs-lookup"><span data-stu-id="8de5c-158">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="8de5c-159">Это может быть сочетание исключений, определенных администратором и пользователей , или только исключений, определенных `merge` администратором ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="8de5c-159">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="8de5c-160">Этот параметр можно использовать, чтобы ограничить местным пользователям определение собственных исключений.</span><span class="sxs-lookup"><span data-stu-id="8de5c-160">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-161">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-161">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-162">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-162">**Key**</span></span> | <span data-ttu-id="8de5c-163">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="8de5c-163">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="8de5c-164">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-164">**Data type**</span></span> | <span data-ttu-id="8de5c-165">String</span><span class="sxs-lookup"><span data-stu-id="8de5c-165">String</span></span> |
| <span data-ttu-id="8de5c-166">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-166">**Possible values**</span></span> | <span data-ttu-id="8de5c-167">слияние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8de5c-167">merge (default)</span></span> <br/> <span data-ttu-id="8de5c-168">admin_only</span><span class="sxs-lookup"><span data-stu-id="8de5c-168">admin_only</span></span> |
| <span data-ttu-id="8de5c-169">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-169">**Comments**</span></span> | <span data-ttu-id="8de5c-170">Доступно в Microsoft Defender для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="8de5c-170">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="8de5c-171">Исключения сканирования</span><span class="sxs-lookup"><span data-stu-id="8de5c-171">Scan exclusions</span></span>

<span data-ttu-id="8de5c-172">Укажите объекты, исключенные из проверки.</span><span class="sxs-lookup"><span data-stu-id="8de5c-172">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="8de5c-173">Исключения могут быть указаны полными путями, расширениями или именами файлов.</span><span class="sxs-lookup"><span data-stu-id="8de5c-173">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-174">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-174">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-175">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-175">**Key**</span></span> | <span data-ttu-id="8de5c-176">исключения</span><span class="sxs-lookup"><span data-stu-id="8de5c-176">exclusions</span></span> |
| <span data-ttu-id="8de5c-177">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-177">**Data type**</span></span> | <span data-ttu-id="8de5c-178">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="8de5c-178">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8de5c-179">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-179">**Comments**</span></span> | <span data-ttu-id="8de5c-180">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="8de5c-180">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="8de5c-181">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="8de5c-181">Type of exclusion</span></span>

<span data-ttu-id="8de5c-182">Укажите содержимое, исключенное из проверки по типу.</span><span class="sxs-lookup"><span data-stu-id="8de5c-182">Specify content excluded from being scanned by type.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-183">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-183">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-184">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-184">**Key**</span></span> | <span data-ttu-id="8de5c-185">$type</span><span class="sxs-lookup"><span data-stu-id="8de5c-185">$type</span></span> |
| <span data-ttu-id="8de5c-186">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-186">**Data type**</span></span> | <span data-ttu-id="8de5c-187">String</span><span class="sxs-lookup"><span data-stu-id="8de5c-187">String</span></span> |
| <span data-ttu-id="8de5c-188">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-188">**Possible values**</span></span> | <span data-ttu-id="8de5c-189">excludedPath</span><span class="sxs-lookup"><span data-stu-id="8de5c-189">excludedPath</span></span> <br/> <span data-ttu-id="8de5c-190">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="8de5c-190">excludedFileExtension</span></span> <br/> <span data-ttu-id="8de5c-191">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="8de5c-191">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="8de5c-192">Путь к исключению контента</span><span class="sxs-lookup"><span data-stu-id="8de5c-192">Path to excluded content</span></span>

<span data-ttu-id="8de5c-193">Укажите содержимое, исключенное из проверки полным путем файла.</span><span class="sxs-lookup"><span data-stu-id="8de5c-193">Specify content excluded from being scanned by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-194">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-194">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-195">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-195">**Key**</span></span> | <span data-ttu-id="8de5c-196">path</span><span class="sxs-lookup"><span data-stu-id="8de5c-196">path</span></span> |
| <span data-ttu-id="8de5c-197">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-197">**Data type**</span></span> | <span data-ttu-id="8de5c-198">String</span><span class="sxs-lookup"><span data-stu-id="8de5c-198">String</span></span> |
| <span data-ttu-id="8de5c-199">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-199">**Possible values**</span></span> | <span data-ttu-id="8de5c-200">допустимые пути</span><span class="sxs-lookup"><span data-stu-id="8de5c-200">valid paths</span></span> |
| <span data-ttu-id="8de5c-201">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-201">**Comments**</span></span> | <span data-ttu-id="8de5c-202">Применимо только если *$type* *исключенPath*</span><span class="sxs-lookup"><span data-stu-id="8de5c-202">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="8de5c-203">Тип пути (файл / каталог)</span><span class="sxs-lookup"><span data-stu-id="8de5c-203">Path type (file / directory)</span></span>

<span data-ttu-id="8de5c-204">Указать, *относится ли* свойство пути к файлу или каталогу.</span><span class="sxs-lookup"><span data-stu-id="8de5c-204">Indicate if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="8de5c-205">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-205">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-206">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-206">**Key**</span></span> | <span data-ttu-id="8de5c-207">isDirectory</span><span class="sxs-lookup"><span data-stu-id="8de5c-207">isDirectory</span></span> |
| <span data-ttu-id="8de5c-208">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-208">**Data type**</span></span> | <span data-ttu-id="8de5c-209">Логический</span><span class="sxs-lookup"><span data-stu-id="8de5c-209">Boolean</span></span> |
| <span data-ttu-id="8de5c-210">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-210">**Possible values**</span></span> | <span data-ttu-id="8de5c-211">false (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8de5c-211">false (default)</span></span> <br/> <span data-ttu-id="8de5c-212">true</span><span class="sxs-lookup"><span data-stu-id="8de5c-212">true</span></span> |
| <span data-ttu-id="8de5c-213">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-213">**Comments**</span></span> | <span data-ttu-id="8de5c-214">Применимо только если *$type* *исключенPath*</span><span class="sxs-lookup"><span data-stu-id="8de5c-214">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="8de5c-215">Расширение файла, исключено из сканирования</span><span class="sxs-lookup"><span data-stu-id="8de5c-215">File extension excluded from the scan</span></span>

<span data-ttu-id="8de5c-216">Укажите содержимое, исключенное из проверки расширением файла.</span><span class="sxs-lookup"><span data-stu-id="8de5c-216">Specify content excluded from being scanned by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-217">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-217">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-218">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-218">**Key**</span></span> | <span data-ttu-id="8de5c-219">расширение</span><span class="sxs-lookup"><span data-stu-id="8de5c-219">extension</span></span> |
| <span data-ttu-id="8de5c-220">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-220">**Data type**</span></span> | <span data-ttu-id="8de5c-221">String</span><span class="sxs-lookup"><span data-stu-id="8de5c-221">String</span></span> |
| <span data-ttu-id="8de5c-222">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-222">**Possible values**</span></span> | <span data-ttu-id="8de5c-223">допустимые расширения файлов</span><span class="sxs-lookup"><span data-stu-id="8de5c-223">valid file extensions</span></span> |
| <span data-ttu-id="8de5c-224">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-224">**Comments**</span></span> | <span data-ttu-id="8de5c-225">Применимо только если *$type* *исключеноFileExtension*</span><span class="sxs-lookup"><span data-stu-id="8de5c-225">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="8de5c-226">Процесс, исключенный из сканирования</span><span class="sxs-lookup"><span data-stu-id="8de5c-226">Process excluded from the scan</span></span>

<span data-ttu-id="8de5c-227">Укажите процесс, для которого все действия файла исключены из сканирования.</span><span class="sxs-lookup"><span data-stu-id="8de5c-227">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="8de5c-228">Процесс можно укаварить как по имени (например, так и по полному `cat` пути( `/bin/cat` например).</span><span class="sxs-lookup"><span data-stu-id="8de5c-228">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-229">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-229">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-230">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-230">**Key**</span></span> | <span data-ttu-id="8de5c-231">name</span><span class="sxs-lookup"><span data-stu-id="8de5c-231">name</span></span> |
| <span data-ttu-id="8de5c-232">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-232">**Data type**</span></span> | <span data-ttu-id="8de5c-233">String</span><span class="sxs-lookup"><span data-stu-id="8de5c-233">String</span></span> |
| <span data-ttu-id="8de5c-234">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-234">**Possible values**</span></span> | <span data-ttu-id="8de5c-235">любая строка</span><span class="sxs-lookup"><span data-stu-id="8de5c-235">any string</span></span> |
| <span data-ttu-id="8de5c-236">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-236">**Comments**</span></span> | <span data-ttu-id="8de5c-237">Применимо только *если $type* *исключеноFileName*</span><span class="sxs-lookup"><span data-stu-id="8de5c-237">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="8de5c-238">Разрешенные угрозы</span><span class="sxs-lookup"><span data-stu-id="8de5c-238">Allowed threats</span></span>

<span data-ttu-id="8de5c-239">Укажите угрозы по имени, которые не заблокированы Защитником для конечной точки для Mac.</span><span class="sxs-lookup"><span data-stu-id="8de5c-239">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="8de5c-240">Эти угрозы будут разрешены для запуска.</span><span class="sxs-lookup"><span data-stu-id="8de5c-240">These threats will be allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-241">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-241">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-242">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-242">**Key**</span></span> | <span data-ttu-id="8de5c-243">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="8de5c-243">allowedThreats</span></span> |
| <span data-ttu-id="8de5c-244">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-244">**Data type**</span></span> | <span data-ttu-id="8de5c-245">Массив строк</span><span class="sxs-lookup"><span data-stu-id="8de5c-245">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="8de5c-246">Действия с неустановляемой угрозой</span><span class="sxs-lookup"><span data-stu-id="8de5c-246">Disallowed threat actions</span></span>

<span data-ttu-id="8de5c-247">Ограничивает действия, которые может принимать локальный пользователь устройства при обнаружении угроз.</span><span class="sxs-lookup"><span data-stu-id="8de5c-247">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="8de5c-248">Действия, включенные в этот список, не отображаются в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="8de5c-248">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-249">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-250">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-250">**Key**</span></span> | <span data-ttu-id="8de5c-251">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="8de5c-251">disallowedThreatActions</span></span> |
| <span data-ttu-id="8de5c-252">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-252">**Data type**</span></span> | <span data-ttu-id="8de5c-253">Массив строк</span><span class="sxs-lookup"><span data-stu-id="8de5c-253">Array of strings</span></span> |
| <span data-ttu-id="8de5c-254">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-254">**Possible values**</span></span> | <span data-ttu-id="8de5c-255">разрешить (ограничивает пользователей от допуска угроз)</span><span class="sxs-lookup"><span data-stu-id="8de5c-255">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="8de5c-256">восстановление (ограничивает пользователей от восстановления угроз из карантина)</span><span class="sxs-lookup"><span data-stu-id="8de5c-256">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="8de5c-257">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-257">**Comments**</span></span> | <span data-ttu-id="8de5c-258">Доступно в Microsoft Defender для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="8de5c-258">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="8de5c-259">Параметры типа угроз</span><span class="sxs-lookup"><span data-stu-id="8de5c-259">Threat type settings</span></span>

<span data-ttu-id="8de5c-260">Укажите, как определенные типы угроз обрабатываются Microsoft Defender для конечной точки для Mac.</span><span class="sxs-lookup"><span data-stu-id="8de5c-260">Specify how certain threat types are handled by Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-261">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-261">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-262">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-262">**Key**</span></span> | <span data-ttu-id="8de5c-263">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="8de5c-263">threatTypeSettings</span></span> |
| <span data-ttu-id="8de5c-264">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-264">**Data type**</span></span> | <span data-ttu-id="8de5c-265">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="8de5c-265">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8de5c-266">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-266">**Comments**</span></span> | <span data-ttu-id="8de5c-267">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="8de5c-267">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="8de5c-268">Тип угрозы</span><span class="sxs-lookup"><span data-stu-id="8de5c-268">Threat type</span></span>

<span data-ttu-id="8de5c-269">Укажите типы угроз.</span><span class="sxs-lookup"><span data-stu-id="8de5c-269">Specify threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-270">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-270">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-271">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-271">**Key**</span></span> | <span data-ttu-id="8de5c-272">ключа</span><span class="sxs-lookup"><span data-stu-id="8de5c-272">key</span></span> |
| <span data-ttu-id="8de5c-273">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-273">**Data type**</span></span> | <span data-ttu-id="8de5c-274">String</span><span class="sxs-lookup"><span data-stu-id="8de5c-274">String</span></span> |
| <span data-ttu-id="8de5c-275">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-275">**Possible values**</span></span> | <span data-ttu-id="8de5c-276">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="8de5c-276">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="8de5c-277">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="8de5c-277">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="8de5c-278">Действие</span><span class="sxs-lookup"><span data-stu-id="8de5c-278">Action to take</span></span>

<span data-ttu-id="8de5c-279">Укажите, какие действия необходимо принять при обнаружении угрозы типа, указанного в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="8de5c-279">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="8de5c-280">Выберите из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="8de5c-280">Choose from the following options:</span></span>

- <span data-ttu-id="8de5c-281">**Аудит:** устройство не защищено от этого типа угрозы, но запись об угрозе регистрируется.</span><span class="sxs-lookup"><span data-stu-id="8de5c-281">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="8de5c-282">**Блок:** ваше устройство защищено от этого типа угрозы, и вы будете уведомлены в пользовательском интерфейсе и консоли безопасности.</span><span class="sxs-lookup"><span data-stu-id="8de5c-282">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="8de5c-283">**Отключено:** устройство не защищено от этого типа угрозы и ничего не регистрируется.</span><span class="sxs-lookup"><span data-stu-id="8de5c-283">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-284">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-284">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-285">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-285">**Key**</span></span> | <span data-ttu-id="8de5c-286">значение</span><span class="sxs-lookup"><span data-stu-id="8de5c-286">value</span></span> |
| <span data-ttu-id="8de5c-287">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-287">**Data type**</span></span> | <span data-ttu-id="8de5c-288">String</span><span class="sxs-lookup"><span data-stu-id="8de5c-288">String</span></span> |
| <span data-ttu-id="8de5c-289">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-289">**Possible values**</span></span> | <span data-ttu-id="8de5c-290">аудит (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8de5c-290">audit (default)</span></span> <br/> <span data-ttu-id="8de5c-291">block</span><span class="sxs-lookup"><span data-stu-id="8de5c-291">block</span></span> <br/> <span data-ttu-id="8de5c-292">Off</span><span class="sxs-lookup"><span data-stu-id="8de5c-292">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="8de5c-293">Параметры типа угрозы объединяют политику слияния</span><span class="sxs-lookup"><span data-stu-id="8de5c-293">Threat type settings merge policy</span></span>

<span data-ttu-id="8de5c-294">Укажите политику слияния для параметров типа угроз.</span><span class="sxs-lookup"><span data-stu-id="8de5c-294">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="8de5c-295">Это может быть сочетание параметров, определенных администратором и определенных пользователем , или только параметров, определенных `merge` администратором ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="8de5c-295">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="8de5c-296">Этот параметр можно использовать, чтобы ограничить местным пользователям определение собственных параметров для различных типов угроз.</span><span class="sxs-lookup"><span data-stu-id="8de5c-296">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-297">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-297">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-298">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-298">**Key**</span></span> | <span data-ttu-id="8de5c-299">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="8de5c-299">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="8de5c-300">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-300">**Data type**</span></span> | <span data-ttu-id="8de5c-301">String</span><span class="sxs-lookup"><span data-stu-id="8de5c-301">String</span></span> |
| <span data-ttu-id="8de5c-302">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-302">**Possible values**</span></span> | <span data-ttu-id="8de5c-303">слияние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8de5c-303">merge (default)</span></span> <br/> <span data-ttu-id="8de5c-304">admin_only</span><span class="sxs-lookup"><span data-stu-id="8de5c-304">admin_only</span></span> |
| <span data-ttu-id="8de5c-305">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-305">**Comments**</span></span> | <span data-ttu-id="8de5c-306">Доступно в Microsoft Defender для конечной точки версии 100.83.73 или выше.</span><span class="sxs-lookup"><span data-stu-id="8de5c-306">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="8de5c-307">Хранение истории антивирусного сканирования (в днях)</span><span class="sxs-lookup"><span data-stu-id="8de5c-307">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="8de5c-308">Укажите количество дней, которые сохраняются в истории сканирования на устройстве.</span><span class="sxs-lookup"><span data-stu-id="8de5c-308">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="8de5c-309">Старые результаты сканирования удаляются из истории.</span><span class="sxs-lookup"><span data-stu-id="8de5c-309">Old scan results are removed from the history.</span></span> <span data-ttu-id="8de5c-310">Старые карантинные файлы, которые также удаляются с диска.</span><span class="sxs-lookup"><span data-stu-id="8de5c-310">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-311">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-311">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-312">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-312">**Key**</span></span> | <span data-ttu-id="8de5c-313">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="8de5c-313">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="8de5c-314">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-314">**Data type**</span></span> | <span data-ttu-id="8de5c-315">String</span><span class="sxs-lookup"><span data-stu-id="8de5c-315">String</span></span> |
| <span data-ttu-id="8de5c-316">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-316">**Possible values**</span></span> | <span data-ttu-id="8de5c-317">90 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="8de5c-317">90 (default).</span></span> <span data-ttu-id="8de5c-318">Допустимые значения от 1 дня до 180 дней.</span><span class="sxs-lookup"><span data-stu-id="8de5c-318">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="8de5c-319">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-319">**Comments**</span></span> | <span data-ttu-id="8de5c-320">Доступно в Microsoft Defender для конечной точки версии 101.07.23 или выше.</span><span class="sxs-lookup"><span data-stu-id="8de5c-320">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="8de5c-321">Максимальное количество элементов в истории антивирусного сканирования</span><span class="sxs-lookup"><span data-stu-id="8de5c-321">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="8de5c-322">Укажите максимальное количество записей, которые необходимо сохранить в истории сканирования.</span><span class="sxs-lookup"><span data-stu-id="8de5c-322">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="8de5c-323">Записи включают все проверки по запросу, выполняемые в прошлом, и все обнаружения антивирусов.</span><span class="sxs-lookup"><span data-stu-id="8de5c-323">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-324">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-324">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-325">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-325">**Key**</span></span> | <span data-ttu-id="8de5c-326">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="8de5c-326">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="8de5c-327">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-327">**Data type**</span></span> | <span data-ttu-id="8de5c-328">String</span><span class="sxs-lookup"><span data-stu-id="8de5c-328">String</span></span> |
| <span data-ttu-id="8de5c-329">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-329">**Possible values**</span></span> | <span data-ttu-id="8de5c-330">10000 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="8de5c-330">10000 (default).</span></span> <span data-ttu-id="8de5c-331">Допустимые значения : от 5000 элементов до 15000 элементов.</span><span class="sxs-lookup"><span data-stu-id="8de5c-331">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="8de5c-332">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-332">**Comments**</span></span> | <span data-ttu-id="8de5c-333">Доступно в Microsoft Defender для конечной точки версии 101.07.23 или выше.</span><span class="sxs-lookup"><span data-stu-id="8de5c-333">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="8de5c-334">Параметры защиты с облачной доставкой</span><span class="sxs-lookup"><span data-stu-id="8de5c-334">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="8de5c-335">Настройте облачные функции защиты Microsoft Defender для конечной точки для Mac.</span><span class="sxs-lookup"><span data-stu-id="8de5c-335">Configure the cloud-driven protection features of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-336">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-336">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-337">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-337">**Key**</span></span> | <span data-ttu-id="8de5c-338">cloudService</span><span class="sxs-lookup"><span data-stu-id="8de5c-338">cloudService</span></span> |
| <span data-ttu-id="8de5c-339">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-339">**Data type**</span></span> | <span data-ttu-id="8de5c-340">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="8de5c-340">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8de5c-341">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-341">**Comments**</span></span> | <span data-ttu-id="8de5c-342">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="8de5c-342">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="8de5c-343">Включить и отключить облачную защиту</span><span class="sxs-lookup"><span data-stu-id="8de5c-343">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="8de5c-344">Укажите, включить ли облачную защиту устройства или нет.</span><span class="sxs-lookup"><span data-stu-id="8de5c-344">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="8de5c-345">Чтобы повысить безопасность ваших служб, рекомендуется сохранить эту функцию включенной.</span><span class="sxs-lookup"><span data-stu-id="8de5c-345">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-346">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-346">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-347">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-347">**Key**</span></span> | <span data-ttu-id="8de5c-348">включено</span><span class="sxs-lookup"><span data-stu-id="8de5c-348">enabled</span></span> |
| <span data-ttu-id="8de5c-349">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-349">**Data type**</span></span> | <span data-ttu-id="8de5c-350">Логический</span><span class="sxs-lookup"><span data-stu-id="8de5c-350">Boolean</span></span> |
| <span data-ttu-id="8de5c-351">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-351">**Possible values**</span></span> | <span data-ttu-id="8de5c-352">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8de5c-352">true (default)</span></span> <br/> <span data-ttu-id="8de5c-353">false</span><span class="sxs-lookup"><span data-stu-id="8de5c-353">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="8de5c-354">Уровень диагностической коллекции</span><span class="sxs-lookup"><span data-stu-id="8de5c-354">Diagnostic collection level</span></span>

<span data-ttu-id="8de5c-355">Диагностические данные используются для обеспечения безопасности и повышения безопасности Microsoft Defender для конечной точки, обнаружения, диагностики и устранения проблем, а также улучшения продукта.</span><span class="sxs-lookup"><span data-stu-id="8de5c-355">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="8de5c-356">Этот параметр определяет уровень диагностики, отправленной Microsoft Defender для конечной точки в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8de5c-356">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-357">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-357">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-358">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-358">**Key**</span></span> | <span data-ttu-id="8de5c-359">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="8de5c-359">diagnosticLevel</span></span> |
| <span data-ttu-id="8de5c-360">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-360">**Data type**</span></span> | <span data-ttu-id="8de5c-361">String</span><span class="sxs-lookup"><span data-stu-id="8de5c-361">String</span></span> |
| <span data-ttu-id="8de5c-362">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-362">**Possible values**</span></span> | <span data-ttu-id="8de5c-363">необязательный (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8de5c-363">optional (default)</span></span> <br/> <span data-ttu-id="8de5c-364">Обязательный</span><span class="sxs-lookup"><span data-stu-id="8de5c-364">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="8de5c-365">Включить и отключить автоматические отправки образцов</span><span class="sxs-lookup"><span data-stu-id="8de5c-365">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="8de5c-366">Определяет, отправляются ли подозрительные образцы (которые могут содержать угрозы) в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8de5c-366">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="8de5c-367">Вам будет предложено, если в отправленных файлах могут содержаться персональные данные.</span><span class="sxs-lookup"><span data-stu-id="8de5c-367">You are prompted if the submitted file is likely to contain personal information.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-368">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-368">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-369">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-369">**Key**</span></span> | <span data-ttu-id="8de5c-370">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="8de5c-370">automaticSampleSubmission</span></span> |
| <span data-ttu-id="8de5c-371">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-371">**Data type**</span></span> | <span data-ttu-id="8de5c-372">Логический</span><span class="sxs-lookup"><span data-stu-id="8de5c-372">Boolean</span></span> |
| <span data-ttu-id="8de5c-373">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-373">**Possible values**</span></span> | <span data-ttu-id="8de5c-374">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8de5c-374">true (default)</span></span> <br/> <span data-ttu-id="8de5c-375">false</span><span class="sxs-lookup"><span data-stu-id="8de5c-375">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="8de5c-376">Включить и отключить автоматические обновления сведении о безопасности</span><span class="sxs-lookup"><span data-stu-id="8de5c-376">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="8de5c-377">Определяет, устанавливаются ли обновления разведки безопасности автоматически:</span><span class="sxs-lookup"><span data-stu-id="8de5c-377">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-378">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-378">**Key**</span></span> | <span data-ttu-id="8de5c-379">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="8de5c-379">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="8de5c-380">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-380">**Data type**</span></span> | <span data-ttu-id="8de5c-381">Логический</span><span class="sxs-lookup"><span data-stu-id="8de5c-381">Boolean</span></span> |
| <span data-ttu-id="8de5c-382">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-382">**Possible values**</span></span> | <span data-ttu-id="8de5c-383">true (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8de5c-383">true (default)</span></span> <br/> <span data-ttu-id="8de5c-384">false</span><span class="sxs-lookup"><span data-stu-id="8de5c-384">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="8de5c-385">Предпочтения пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="8de5c-385">User interface preferences</span></span>

<span data-ttu-id="8de5c-386">Управление предпочтениями пользовательского интерфейса Microsoft Defender для конечной точки для Mac.</span><span class="sxs-lookup"><span data-stu-id="8de5c-386">Manage the preferences for the user interface of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-387">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-387">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-388">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-388">**Key**</span></span> | <span data-ttu-id="8de5c-389">userInterface</span><span class="sxs-lookup"><span data-stu-id="8de5c-389">userInterface</span></span> |
| <span data-ttu-id="8de5c-390">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-390">**Data type**</span></span> | <span data-ttu-id="8de5c-391">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="8de5c-391">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8de5c-392">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-392">**Comments**</span></span> | <span data-ttu-id="8de5c-393">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="8de5c-393">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="8de5c-394">Значок меню "Показать/ скрыть состояние"</span><span class="sxs-lookup"><span data-stu-id="8de5c-394">Show / hide status menu icon</span></span>

<span data-ttu-id="8de5c-395">Укажите, показывать или скрывать значок меню состояния в правом верхнем углу экрана.</span><span class="sxs-lookup"><span data-stu-id="8de5c-395">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-396">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-396">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-397">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-397">**Key**</span></span> | <span data-ttu-id="8de5c-398">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="8de5c-398">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="8de5c-399">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-399">**Data type**</span></span> | <span data-ttu-id="8de5c-400">Логический</span><span class="sxs-lookup"><span data-stu-id="8de5c-400">Boolean</span></span> |
| <span data-ttu-id="8de5c-401">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-401">**Possible values**</span></span> | <span data-ttu-id="8de5c-402">false (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8de5c-402">false (default)</span></span> <br/> <span data-ttu-id="8de5c-403">true</span><span class="sxs-lookup"><span data-stu-id="8de5c-403">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="8de5c-404">Параметр Show/hide для отправки отзывов</span><span class="sxs-lookup"><span data-stu-id="8de5c-404">Show / hide option to send feedback</span></span>

<span data-ttu-id="8de5c-405">Укажите, могут ли пользователи отправлять отзывы в Корпорацию Майкрософт, переехав `Help`  >  `Send Feedback` в .</span><span class="sxs-lookup"><span data-stu-id="8de5c-405">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-406">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-406">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-407">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-407">**Key**</span></span> | <span data-ttu-id="8de5c-408">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="8de5c-408">userInitiatedFeedback</span></span> |
| <span data-ttu-id="8de5c-409">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-409">**Data type**</span></span> | <span data-ttu-id="8de5c-410">String</span><span class="sxs-lookup"><span data-stu-id="8de5c-410">String</span></span> |
| <span data-ttu-id="8de5c-411">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-411">**Possible values**</span></span> | <span data-ttu-id="8de5c-412">включено (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8de5c-412">enabled (default)</span></span> <br/> <span data-ttu-id="8de5c-413">отключено</span><span class="sxs-lookup"><span data-stu-id="8de5c-413">disabled</span></span> |
| <span data-ttu-id="8de5c-414">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-414">**Comments**</span></span> | <span data-ttu-id="8de5c-415">Доступно в Microsoft Defender для конечной точки версии 101.19.61 или выше.</span><span class="sxs-lookup"><span data-stu-id="8de5c-415">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="8de5c-416">Параметры обнаружения конечных точек и ответов</span><span class="sxs-lookup"><span data-stu-id="8de5c-416">Endpoint detection and response preferences</span></span>

<span data-ttu-id="8de5c-417">Управление предпочтениями компонента обнаружения и ответа конечной точки (EDR) Microsoft Defender для конечной точки для Mac.</span><span class="sxs-lookup"><span data-stu-id="8de5c-417">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-418">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-418">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-419">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-419">**Key**</span></span> | <span data-ttu-id="8de5c-420">edr</span><span class="sxs-lookup"><span data-stu-id="8de5c-420">edr</span></span> |
| <span data-ttu-id="8de5c-421">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-421">**Data type**</span></span> | <span data-ttu-id="8de5c-422">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="8de5c-422">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8de5c-423">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-423">**Comments**</span></span> | <span data-ttu-id="8de5c-424">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="8de5c-424">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="8de5c-425">Теги устройств</span><span class="sxs-lookup"><span data-stu-id="8de5c-425">Device tags</span></span>

<span data-ttu-id="8de5c-426">Укажите имя тега и его значение.</span><span class="sxs-lookup"><span data-stu-id="8de5c-426">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="8de5c-427">Тег GROUP указывает устройство с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="8de5c-427">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="8de5c-428">Тег отражается на портале на странице устройства и может использоваться для фильтрации и группировки устройств.</span><span class="sxs-lookup"><span data-stu-id="8de5c-428">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-429">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-429">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-430">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-430">**Key**</span></span> | <span data-ttu-id="8de5c-431">tags</span><span class="sxs-lookup"><span data-stu-id="8de5c-431">tags</span></span> |
| <span data-ttu-id="8de5c-432">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-432">**Data type**</span></span> | <span data-ttu-id="8de5c-433">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="8de5c-433">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8de5c-434">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8de5c-434">**Comments**</span></span> | <span data-ttu-id="8de5c-435">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="8de5c-435">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="8de5c-436">Тип тега</span><span class="sxs-lookup"><span data-stu-id="8de5c-436">Type of tag</span></span>

<span data-ttu-id="8de5c-437">Указывает тип тега</span><span class="sxs-lookup"><span data-stu-id="8de5c-437">Specifies the type of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-438">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-438">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-439">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-439">**Key**</span></span> | <span data-ttu-id="8de5c-440">ключа</span><span class="sxs-lookup"><span data-stu-id="8de5c-440">key</span></span> |
| <span data-ttu-id="8de5c-441">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-441">**Data type**</span></span> | <span data-ttu-id="8de5c-442">String</span><span class="sxs-lookup"><span data-stu-id="8de5c-442">String</span></span> |
| <span data-ttu-id="8de5c-443">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-443">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="8de5c-444">Значение тега</span><span class="sxs-lookup"><span data-stu-id="8de5c-444">Value of tag</span></span>

<span data-ttu-id="8de5c-445">Указывает значение тега</span><span class="sxs-lookup"><span data-stu-id="8de5c-445">Specifies the value of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="8de5c-446">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8de5c-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8de5c-447">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="8de5c-447">**Key**</span></span> | <span data-ttu-id="8de5c-448">значение</span><span class="sxs-lookup"><span data-stu-id="8de5c-448">value</span></span> |
| <span data-ttu-id="8de5c-449">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8de5c-449">**Data type**</span></span> | <span data-ttu-id="8de5c-450">String</span><span class="sxs-lookup"><span data-stu-id="8de5c-450">String</span></span> |
| <span data-ttu-id="8de5c-451">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="8de5c-451">**Possible values**</span></span> | <span data-ttu-id="8de5c-452">любая строка</span><span class="sxs-lookup"><span data-stu-id="8de5c-452">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="8de5c-453">Можно установить только одно значение для каждого типа тегов.</span><span class="sxs-lookup"><span data-stu-id="8de5c-453">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="8de5c-454">Тип тегов уникален и не должен повторяться в одном профиле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8de5c-454">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="8de5c-455">Рекомендуемый профиль конфигурации</span><span class="sxs-lookup"><span data-stu-id="8de5c-455">Recommended configuration profile</span></span>

<span data-ttu-id="8de5c-456">Чтобы начать работу, рекомендуется в следующей конфигурации для предприятия воспользоваться всеми функциями защиты, которые предоставляет Microsoft Defender для Endpoint.</span><span class="sxs-lookup"><span data-stu-id="8de5c-456">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="8de5c-457">Следующий профиль конфигурации (или, в случае JAMF, список свойств, которые можно было бы загрузить в настраиваемый профиль конфигурации параметров) будет:</span><span class="sxs-lookup"><span data-stu-id="8de5c-457">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="8de5c-458">Включить защиту в режиме реального времени (RTP)</span><span class="sxs-lookup"><span data-stu-id="8de5c-458">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="8de5c-459">Укажите, как обрабатываются следующие типы угроз:</span><span class="sxs-lookup"><span data-stu-id="8de5c-459">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="8de5c-460">**Потенциально нежелательные приложения (PUA)** заблокированы</span><span class="sxs-lookup"><span data-stu-id="8de5c-460">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="8de5c-461">**Архивные бомбы** (файл с высокой скоростью сжатия) проверяются в журналах Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="8de5c-461">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="8de5c-462">Включить автоматические обновления сведении о безопасности</span><span class="sxs-lookup"><span data-stu-id="8de5c-462">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="8de5c-463">Включить облачную защиту</span><span class="sxs-lookup"><span data-stu-id="8de5c-463">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="8de5c-464">Включить автоматическую отправку образца</span><span class="sxs-lookup"><span data-stu-id="8de5c-464">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="8de5c-465">Список свойств для профиля конфигурации JAMF</span><span class="sxs-lookup"><span data-stu-id="8de5c-465">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="8de5c-466">Профиль Intune</span><span class="sxs-lookup"><span data-stu-id="8de5c-466">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="8de5c-467">Пример профиля полной конфигурации</span><span class="sxs-lookup"><span data-stu-id="8de5c-467">Full configuration profile example</span></span>

<span data-ttu-id="8de5c-468">В следующих шаблонах содержатся записи для всех параметров, описанных в этом документе, и они могут использоваться для более сложных сценариев, в которых требуется больше контроля над Microsoft Defender для конечной точки для Mac.</span><span class="sxs-lookup"><span data-stu-id="8de5c-468">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint for Mac.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="8de5c-469">Список свойств для профиля конфигурации JAMF</span><span class="sxs-lookup"><span data-stu-id="8de5c-469">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="8de5c-470">Профиль Intune</span><span class="sxs-lookup"><span data-stu-id="8de5c-470">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="8de5c-471">Проверка списка свойств</span><span class="sxs-lookup"><span data-stu-id="8de5c-471">Property list validation</span></span>

<span data-ttu-id="8de5c-472">Список свойств должен быть допустимым *файлом .plist.*</span><span class="sxs-lookup"><span data-stu-id="8de5c-472">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="8de5c-473">Это можно проверить, исполнив:</span><span class="sxs-lookup"><span data-stu-id="8de5c-473">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="8de5c-474">Если файл хорошо сформирован, вышеуказанная команда выводит и возвращает `OK` код выхода `0` .</span><span class="sxs-lookup"><span data-stu-id="8de5c-474">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="8de5c-475">В противном случае отображается ошибка, описываемая проблемой, и команда возвращает код выхода `1` .</span><span class="sxs-lookup"><span data-stu-id="8de5c-475">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="8de5c-476">Развертывание профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="8de5c-476">Configuration profile deployment</span></span>

<span data-ttu-id="8de5c-477">После того как вы создали профиль конфигурации для предприятия, вы можете развернуть его через консоль управления, которую использует ваше предприятие.</span><span class="sxs-lookup"><span data-stu-id="8de5c-477">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="8de5c-478">В следующих разделах указаны инструкции по развертыванию этого профиля с помощью JAMF и Intune.</span><span class="sxs-lookup"><span data-stu-id="8de5c-478">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="8de5c-479">Развертывание JAMF</span><span class="sxs-lookup"><span data-stu-id="8de5c-479">JAMF deployment</span></span>

<span data-ttu-id="8de5c-480">На консоли JAMF откройте **профили** конфигурации компьютеров , перейдите в профиль конфигурации, который вы хотите использовать, а затем выберите  >   **настраиваемые параметры.**</span><span class="sxs-lookup"><span data-stu-id="8de5c-480">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="8de5c-481">Создайте запись в качестве домена предпочтений и загрузите ранее произведенный `com.microsoft.wdav` *список .plist.*</span><span class="sxs-lookup"><span data-stu-id="8de5c-481">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="8de5c-482">Необходимо ввести правильный домен предпочтений (); в противном случае параметры не будут `com.microsoft.wdav` распознаны Защитником Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8de5c-482">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="8de5c-483">Развертывание Intune</span><span class="sxs-lookup"><span data-stu-id="8de5c-483">Intune deployment</span></span>

1. <span data-ttu-id="8de5c-484">Откройте   >  **конфигурацию управления устройством.**</span><span class="sxs-lookup"><span data-stu-id="8de5c-484">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="8de5c-485">Выберите **Управление**  >  **профилями**  >  **Создание профиля**.</span><span class="sxs-lookup"><span data-stu-id="8de5c-485">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="8de5c-486">Выберите имя для профиля.</span><span class="sxs-lookup"><span data-stu-id="8de5c-486">Choose a name for the profile.</span></span> <span data-ttu-id="8de5c-487">Изменение **platform=macOS на** **тип profile=Custom.**</span><span class="sxs-lookup"><span data-stu-id="8de5c-487">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="8de5c-488">Выберите Настройка.</span><span class="sxs-lookup"><span data-stu-id="8de5c-488">Select Configure.</span></span>

3. <span data-ttu-id="8de5c-489">Сохранение списка .plist, выпущенного ранее как `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="8de5c-489">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="8de5c-490">Введите `com.microsoft.wdav` в **качестве настраиваемой конфигурации имя профиля**.</span><span class="sxs-lookup"><span data-stu-id="8de5c-490">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="8de5c-491">Откройте профиль конфигурации и загрузите `com.microsoft.wdav.xml` файл.</span><span class="sxs-lookup"><span data-stu-id="8de5c-491">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="8de5c-492">(Этот файл был создан в шаге 3.)</span><span class="sxs-lookup"><span data-stu-id="8de5c-492">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="8de5c-493">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8de5c-493">Select **OK**.</span></span>

7. <span data-ttu-id="8de5c-494">Выберите **управление**  >  **назначениями.**</span><span class="sxs-lookup"><span data-stu-id="8de5c-494">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="8de5c-495">На **вкладке Включить** выберите Назначение всем пользователям & **всех устройств.**</span><span class="sxs-lookup"><span data-stu-id="8de5c-495">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="8de5c-496">Необходимо ввести правильное имя профиля настраиваемой конфигурации; в противном случае эти параметры не будут распознаться Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8de5c-496">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="8de5c-497">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="8de5c-497">Resources</span></span>

- [<span data-ttu-id="8de5c-498">Справочник по профилям конфигурации (документация для разработчиков Apple)</span><span class="sxs-lookup"><span data-stu-id="8de5c-498">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
