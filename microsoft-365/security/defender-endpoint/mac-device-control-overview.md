---
title: Управление устройствами для macOS
description: Узнайте, как настроить Microsoft Defender для конечной точки для Mac, чтобы уменьшить угрозы из съемного хранилища, например USB-устройств.
keywords: Microsoft, defender, atp, mac, device, control, usb, removable, media
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: 098eb30764870e69c5b1b6c2cec3cf8e5cb11691
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186573"
---
# <a name="device-control-for-macos"></a><span data-ttu-id="12bf4-104">Управление устройствами для macOS</span><span class="sxs-lookup"><span data-stu-id="12bf4-104">Device control for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="12bf4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="12bf4-105">**Applies to:**</span></span>
- [<span data-ttu-id="12bf4-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="12bf4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="12bf4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="12bf4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="12bf4-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="12bf4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="12bf4-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="12bf4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="requirements"></a><span data-ttu-id="12bf4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="12bf4-110">Requirements</span></span>

<span data-ttu-id="12bf4-111">Управление устройствами для macOS имеет следующие условия:</span><span class="sxs-lookup"><span data-stu-id="12bf4-111">Device control for macOS has the following prerequisites:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="12bf4-112">Право Microsoft Defender для конечной точки (может быть пробным)</span><span class="sxs-lookup"><span data-stu-id="12bf4-112">Microsoft Defender for Endpoint entitlement (can be trial)</span></span>
> - <span data-ttu-id="12bf4-113">Минимальная версия ОС: macOS 10.15.4 или более</span><span class="sxs-lookup"><span data-stu-id="12bf4-113">Minimum OS version: macOS 10.15.4 or higher</span></span>
> - <span data-ttu-id="12bf4-114">Минимальная версия продукта: 101.24.59</span><span class="sxs-lookup"><span data-stu-id="12bf4-114">Minimum product version: 101.24.59</span></span>
> - <span data-ttu-id="12bf4-115">Устройство должно работать с расширениями системы (это по умолчанию для macOS 11 Big Sur).</span><span class="sxs-lookup"><span data-stu-id="12bf4-115">Your device must be running with system extensions (this is the default on macOS 11 Big Sur).</span></span> 
> 
>   <span data-ttu-id="12bf4-116">Вы можете проверить, работает ли ваше устройство на системных расширениях, подав следующую команду, и убедиться, что оно печатает `endpoint_security_extension` на консоли:</span><span class="sxs-lookup"><span data-stu-id="12bf4-116">You can check if your device is running on system extensions by running the following command and verify that it is printing `endpoint_security_extension` to the console:</span></span> 
> 
>   ```bash
>   mdatp health --field real_time_protection_subsystem 
>   ```
> - <span data-ttu-id="12bf4-117">Ваше устройство должно быть в `Beta` (ранее `InsiderFast` называемом) канале обновления Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="12bf4-117">Your device must be in `Beta` (previously called `InsiderFast`) Microsoft AutoUpdate update channel.</span></span> <span data-ttu-id="12bf4-118">Дополнительные сведения см. в [сайте Deploy updates for Microsoft Defender for Endpoint for Mac.](mac-updates.md)</span><span class="sxs-lookup"><span data-stu-id="12bf4-118">For more information, see [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md).</span></span>
> 
>   <span data-ttu-id="12bf4-119">Вы можете проверить канал обновления с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="12bf4-119">You can check the update channel using the following command:</span></span> 
> 
>    ```bash
>    mdatp health --field release_ring 
>    ```
>
>    <span data-ttu-id="12bf4-120">Если вышеуказанная команда не распечатает или `Beta` `InsiderFast` не выполнит следующую команду из терминала.</span><span class="sxs-lookup"><span data-stu-id="12bf4-120">If the above command does not print either `Beta` or `InsiderFast`, execute the following command from the Terminal.</span></span> <span data-ttu-id="12bf4-121">Обновление канала вступает в силу в следующий раз, когда продукт запускается (при следующем обновлении продукта или при перезагрузке устройства).</span><span class="sxs-lookup"><span data-stu-id="12bf4-121">The channel update takes effect next time the product starts (when the next product update is installed or when the device is rebooted).</span></span> 
> 
>    ```bash
>    defaults write com.microsoft.autoupdate2 ChannelName -string Beta
>    ```
>
>    <span data-ttu-id="12bf4-122">Кроме того, если вы находитесь в управляемой среде (JAMF или Intune), вы можете настроить канал обновления удаленно.</span><span class="sxs-lookup"><span data-stu-id="12bf4-122">Alternatively, if you are in a managed environment (JAMF or Intune), you can configure the update channel remotely.</span></span> <span data-ttu-id="12bf4-123">Дополнительные сведения см. в [сайте Deploy updates for Microsoft Defender for Endpoint for Mac.](mac-updates.md)</span><span class="sxs-lookup"><span data-stu-id="12bf4-123">For more information, see [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md).</span></span> 

## <a name="device-control-policy"></a><span data-ttu-id="12bf4-124">Политика управления устройствами</span><span class="sxs-lookup"><span data-stu-id="12bf4-124">Device control policy</span></span>

<span data-ttu-id="12bf4-125">Чтобы настроить управление устройствами для macOS, необходимо создать политику, описываемую ограничения, которые необходимо ввести в организации.</span><span class="sxs-lookup"><span data-stu-id="12bf4-125">To configure device control for macOS, you must create a policy that describes the restrictions you want to put in place within your organization.</span></span>

<span data-ttu-id="12bf4-126">Политика управления устройством включена в профиль конфигурации, используемый для настройки всех остальных параметров продукта.</span><span class="sxs-lookup"><span data-stu-id="12bf4-126">The device control policy is included in the configuration profile used to configure all other product settings.</span></span> <span data-ttu-id="12bf4-127">Дополнительные сведения см. в [странице Конфигурация структуры профилей.](mac-preferences.md#configuration-profile-structure)</span><span class="sxs-lookup"><span data-stu-id="12bf4-127">For more information, see [Configuration profile structure](mac-preferences.md#configuration-profile-structure).</span></span>

<span data-ttu-id="12bf4-128">В профиле конфигурации политика управления устройствами определяется в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="12bf4-128">Within the configuration profile, the device control policy is defined in the following section:</span></span>

|||
|:---|:---|
| <span data-ttu-id="12bf4-129">**Домен**</span><span class="sxs-lookup"><span data-stu-id="12bf4-129">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="12bf4-130">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="12bf4-130">**Key**</span></span> | <span data-ttu-id="12bf4-131">deviceControl</span><span class="sxs-lookup"><span data-stu-id="12bf4-131">deviceControl</span></span> |
| <span data-ttu-id="12bf4-132">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="12bf4-132">**Data type**</span></span> | <span data-ttu-id="12bf4-133">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="12bf4-133">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="12bf4-134">**Comments**</span><span class="sxs-lookup"><span data-stu-id="12bf4-134">**Comments**</span></span> | <span data-ttu-id="12bf4-135">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="12bf4-135">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="12bf4-136">Политика управления устройствами может использоваться для:</span><span class="sxs-lookup"><span data-stu-id="12bf4-136">The device control policy can be used to:</span></span>

- [<span data-ttu-id="12bf4-137">Настройка целевого URL-адреса для уведомлений, поднятых с помощью управления устройствами</span><span class="sxs-lookup"><span data-stu-id="12bf4-137">Customize the URL target for notifications raised by device control</span></span>](#customize-url-target-for-notifications-raised-by-device-control)
- [<span data-ttu-id="12bf4-138">Разрешить или заблокировать съемные устройства</span><span class="sxs-lookup"><span data-stu-id="12bf4-138">Allow or block removable devices</span></span>](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a><span data-ttu-id="12bf4-139">Настройка URL-адреса для уведомлений, поднятых с помощью управления устройствами</span><span class="sxs-lookup"><span data-stu-id="12bf4-139">Customize URL target for notifications raised by device control</span></span>

<span data-ttu-id="12bf4-140">Если на устройстве применена политика управления устройствами (например, доступ к съемным носитему устройству ограничен), пользователю отображается уведомление.</span><span class="sxs-lookup"><span data-stu-id="12bf4-140">When the device control policy that you have put in place is enforced on a device (for example, access to a removable media device is restricted), a notification is displayed to the user.</span></span>

![Уведомление об устройстве управления](images/mac-device-control-notification.png)

<span data-ttu-id="12bf4-142">Когда конечные пользователи щелкают это уведомление, веб-страница открывается в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="12bf4-142">When end users click this notification, a web page is opened in the default browser.</span></span> <span data-ttu-id="12bf4-143">Вы можете настроить URL-адрес, открываемый при нажатии уведомления конечными пользователями.</span><span class="sxs-lookup"><span data-stu-id="12bf4-143">You can configure the URL that is opened when end users click the notification.</span></span>

|||
|:---|:---|
| <span data-ttu-id="12bf4-144">**Домен**</span><span class="sxs-lookup"><span data-stu-id="12bf4-144">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="12bf4-145">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="12bf4-145">**Key**</span></span> | <span data-ttu-id="12bf4-146">navigationTarget</span><span class="sxs-lookup"><span data-stu-id="12bf4-146">navigationTarget</span></span> |
| <span data-ttu-id="12bf4-147">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="12bf4-147">**Data type**</span></span> | <span data-ttu-id="12bf4-148">Строка</span><span class="sxs-lookup"><span data-stu-id="12bf4-148">String</span></span> |
| <span data-ttu-id="12bf4-149">**Comments**</span><span class="sxs-lookup"><span data-stu-id="12bf4-149">**Comments**</span></span> | <span data-ttu-id="12bf4-150">Если не определено, продукт использует URL-адрес по умолчанию, указывающий на общую страницу с объяснением действий, принятых продуктом.</span><span class="sxs-lookup"><span data-stu-id="12bf4-150">If not defined, the product uses a default URL pointing to a generic page explaining the action taken by the product.</span></span> |

### <a name="allow-or-block-removable-devices"></a><span data-ttu-id="12bf4-151">Разрешить или заблокировать съемные устройства</span><span class="sxs-lookup"><span data-stu-id="12bf4-151">Allow or block removable devices</span></span>

<span data-ttu-id="12bf4-152">Съемный раздел мультимедиа политики управления устройствами используется для ограничения доступа к съемным носителям.</span><span class="sxs-lookup"><span data-stu-id="12bf4-152">The removable media section of the device control policy is used to restrict access to removable media.</span></span> 

> [!NOTE]
> <span data-ttu-id="12bf4-153">В настоящее время поддерживаются следующие типы съемных мультимедиа, которые могут быть включены в политику: устройства хранения USB.</span><span class="sxs-lookup"><span data-stu-id="12bf4-153">The following types of removable media are currently supported and can be included in the policy: USB storage devices.</span></span>

|||
|:---|:---|
| <span data-ttu-id="12bf4-154">**Домен**</span><span class="sxs-lookup"><span data-stu-id="12bf4-154">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="12bf4-155">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="12bf4-155">**Key**</span></span> | <span data-ttu-id="12bf4-156">removableMediaPolicy</span><span class="sxs-lookup"><span data-stu-id="12bf4-156">removableMediaPolicy</span></span> |
| <span data-ttu-id="12bf4-157">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="12bf4-157">**Data type**</span></span> | <span data-ttu-id="12bf4-158">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="12bf4-158">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="12bf4-159">**Comments**</span><span class="sxs-lookup"><span data-stu-id="12bf4-159">**Comments**</span></span> | <span data-ttu-id="12bf4-160">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="12bf4-160">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="12bf4-161">Этот раздел политики иерархичен, что обеспечивает максимальную гибкость и охватывает широкий диапазон случаев использования.</span><span class="sxs-lookup"><span data-stu-id="12bf4-161">This section of the policy is hierarchical, allowing for maximum flexibility and covering a wide range of use cases.</span></span> <span data-ttu-id="12bf4-162">На верхнем уровне находятся поставщики, идентифицированные по ID поставщика.</span><span class="sxs-lookup"><span data-stu-id="12bf4-162">At the top level are vendors, identified by a vendor ID.</span></span> <span data-ttu-id="12bf4-163">Для каждого поставщика существуют продукты, идентифицированные по ID продукта.</span><span class="sxs-lookup"><span data-stu-id="12bf4-163">For each vendor, there are products, identified by a product ID.</span></span> <span data-ttu-id="12bf4-164">Наконец, для каждого продукта существуют серийные номера, обозначающие конкретные устройства.</span><span class="sxs-lookup"><span data-stu-id="12bf4-164">Finally, for each product there are serial numbers denoting specific devices.</span></span>

```
|-- policy top level 
    |-- vendor 1 
        |-- product 1 
            |-- serial number 1 
            ...
            |-- serial number N 
        ...
        |-- product N 
    ...
    |-- vendor N
```

<span data-ttu-id="12bf4-165">Сведения о поиске идентификаторов устройств см. в документе [Look up device identifiers.](#look-up-device-identifiers)</span><span class="sxs-lookup"><span data-stu-id="12bf4-165">For information on how to find the device identifiers, see [Look up device identifiers](#look-up-device-identifiers).</span></span>

<span data-ttu-id="12bf4-166">Политика оценивается от самой конкретной записи до самой общей.</span><span class="sxs-lookup"><span data-stu-id="12bf4-166">The policy is evaluated from the most specific entry to the most general one.</span></span> <span data-ttu-id="12bf4-167">То есть, когда устройство подключено, продукт пытается найти наиболее конкретное совпадение в политике для каждого съемного устройства мультимедиа и применить разрешения на этом уровне.</span><span class="sxs-lookup"><span data-stu-id="12bf4-167">Meaning, when a device is plugged in, the product tries to find the most specific match in the policy for each removable media device and apply the permissions at that level.</span></span> <span data-ttu-id="12bf4-168">Если нет совпадения, применяется следующий оптимальный совпадение, в том числе разрешение, указанное на верхнем уровне, которое является по умолчанию, если устройство не соответствует какой-либо другой записи в политике.</span><span class="sxs-lookup"><span data-stu-id="12bf4-168">If there is no match, then the next best match is applied, all the way to the permission specified at the top level, which is the default when a device does not match any other entry in the policy.</span></span>

#### <a name="policy-enforcement-level"></a><span data-ttu-id="12bf4-169">Уровень правоприменения политики</span><span class="sxs-lookup"><span data-stu-id="12bf4-169">Policy enforcement level</span></span>

<span data-ttu-id="12bf4-170">В разделе съемное мультимедиа можно установить уровень правоприменения, который может принять одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="12bf4-170">Under the removable media section, there is an option to set the enforcement level, which can take one of the following values:</span></span>

- <span data-ttu-id="12bf4-171">`audit` - В соответствии с этим уровнем правоприменения, если доступ к устройству ограничен, пользователю отображается уведомление, однако устройство все еще можно использовать.</span><span class="sxs-lookup"><span data-stu-id="12bf4-171">`audit` - Under this enforcement level, if access to a device is restricted, a notification is displayed to the user, however the device can still be used.</span></span> <span data-ttu-id="12bf4-172">Этот уровень применения может быть полезен для оценки эффективности политики.</span><span class="sxs-lookup"><span data-stu-id="12bf4-172">This enforcement level can be useful to evaluate the effectiveness of a policy.</span></span>
- <span data-ttu-id="12bf4-173">`block` — В соответствии с этим уровнем обеспечения выполнения операций, которые пользователь может выполнять на устройстве, ограничивается тем, что определено в политике.</span><span class="sxs-lookup"><span data-stu-id="12bf4-173">`block` - Under this enforcement level, the operations that the user can perform on the device are limited to what is defined in the policy.</span></span> <span data-ttu-id="12bf4-174">Кроме того, пользователь получает уведомление.</span><span class="sxs-lookup"><span data-stu-id="12bf4-174">Furthermore, a notification is raised to the user.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="12bf4-175">**Домен**</span><span class="sxs-lookup"><span data-stu-id="12bf4-175">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="12bf4-176">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="12bf4-176">**Key**</span></span> | <span data-ttu-id="12bf4-177">enforcementLevel</span><span class="sxs-lookup"><span data-stu-id="12bf4-177">enforcementLevel</span></span> |
| <span data-ttu-id="12bf4-178">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="12bf4-178">**Data type**</span></span> | <span data-ttu-id="12bf4-179">String</span><span class="sxs-lookup"><span data-stu-id="12bf4-179">String</span></span> |
| <span data-ttu-id="12bf4-180">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="12bf4-180">**Possible values**</span></span> | <span data-ttu-id="12bf4-181">аудит (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="12bf4-181">audit (default)</span></span> <br/> <span data-ttu-id="12bf4-182">block</span><span class="sxs-lookup"><span data-stu-id="12bf4-182">block</span></span> |

#### <a name="default-permission-level"></a><span data-ttu-id="12bf4-183">Уровень разрешений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="12bf4-183">Default permission level</span></span>

<span data-ttu-id="12bf4-184">На верхнем уровне съемного раздела мультимедиа можно настроить уровень разрешений по умолчанию для устройств, которые не соответствуют ни к чему другому в политике.</span><span class="sxs-lookup"><span data-stu-id="12bf4-184">At the top level of the removable media section, you can configure the default permission level for devices that do not match anything else in the policy.</span></span>

<span data-ttu-id="12bf4-185">Этот параметр может быть заданной для:</span><span class="sxs-lookup"><span data-stu-id="12bf4-185">This setting can be set to:</span></span>

- <span data-ttu-id="12bf4-186">`none` - Операции на устройстве не выполняются</span><span class="sxs-lookup"><span data-stu-id="12bf4-186">`none` - No operations can be performed on the device</span></span>
- <span data-ttu-id="12bf4-187">Сочетание следующих значений:</span><span class="sxs-lookup"><span data-stu-id="12bf4-187">A combination of the following values:</span></span>
    - <span data-ttu-id="12bf4-188">`read` - Операции чтения разрешены на устройстве</span><span class="sxs-lookup"><span data-stu-id="12bf4-188">`read` - Read operations are permitted on the device</span></span>
    - <span data-ttu-id="12bf4-189">`write` - Операции записи разрешены на устройстве</span><span class="sxs-lookup"><span data-stu-id="12bf4-189">`write` - Write operations are permitted on the device</span></span>
    - <span data-ttu-id="12bf4-190">`execute` - Выполнение операций разрешено на устройстве</span><span class="sxs-lookup"><span data-stu-id="12bf4-190">`execute` - Execute operations are permitted on the device</span></span>

> [!NOTE]
> <span data-ttu-id="12bf4-191">Если они присутствуют на уровне разрешений, любые другие разрешения `none` `read` `write` (или) будут `execute` игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="12bf4-191">If `none` is present in the permission level, any other permissions (`read`, `write`, or `execute`) will be ignored.</span></span>

> [!NOTE]
> <span data-ttu-id="12bf4-192">Разрешение `execute` относится только к выполнению бинарей Mach-O.</span><span class="sxs-lookup"><span data-stu-id="12bf4-192">The `execute` permission only refers to execution of Mach-O binaries.</span></span> <span data-ttu-id="12bf4-193">Он не включает выполнение скриптов или других типов полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="12bf4-193">It does not include execution of scripts or other types of payloads.</span></span>

|||
|:---|:---|
| <span data-ttu-id="12bf4-194">**Домен**</span><span class="sxs-lookup"><span data-stu-id="12bf4-194">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="12bf4-195">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="12bf4-195">**Key**</span></span> | <span data-ttu-id="12bf4-196">разрешение</span><span class="sxs-lookup"><span data-stu-id="12bf4-196">permission</span></span> |
| <span data-ttu-id="12bf4-197">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="12bf4-197">**Data type**</span></span> | <span data-ttu-id="12bf4-198">Массив строк</span><span class="sxs-lookup"><span data-stu-id="12bf4-198">Array of strings</span></span> |
| <span data-ttu-id="12bf4-199">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="12bf4-199">**Possible values**</span></span> | <span data-ttu-id="12bf4-200">нет</span><span class="sxs-lookup"><span data-stu-id="12bf4-200">none</span></span> <br/> <span data-ttu-id="12bf4-201">read</span><span class="sxs-lookup"><span data-stu-id="12bf4-201">read</span></span> <br/> <span data-ttu-id="12bf4-202">write</span><span class="sxs-lookup"><span data-stu-id="12bf4-202">write</span></span> <br/> <span data-ttu-id="12bf4-203">выполнение</span><span class="sxs-lookup"><span data-stu-id="12bf4-203">execute</span></span> |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a><span data-ttu-id="12bf4-204">Ограничение съемных мультимедиа поставщиком, продуктом и серийным номером</span><span class="sxs-lookup"><span data-stu-id="12bf4-204">Restrict removable media by vendor, product, and serial number</span></span>

<span data-ttu-id="12bf4-205">Как описано в [описании Разрешить](#allow-or-block-removable-devices)или блокировать съемные устройства, съемные носитли, такие как USB-устройства, могут быть идентифицированы по ID поставщика, ID продукта и серийному номеру.</span><span class="sxs-lookup"><span data-stu-id="12bf4-205">As described in [Allow or block removable devices](#allow-or-block-removable-devices), removable media such as USB devices can be identified by the vendor ID, product ID, and serial number.</span></span>

<span data-ttu-id="12bf4-206">На верхнем уровне политики съемных мультимедиа можно дополнительно определить более подробное ограничение на уровне поставщика.</span><span class="sxs-lookup"><span data-stu-id="12bf4-206">At the top level of the removable media policy, you can optionally define more granular restrictions at the vendor level.</span></span> 

<span data-ttu-id="12bf4-207">Словарь содержит одну или несколько записей, каждая запись `vendors` которых идентифицирована по ID поставщика.</span><span class="sxs-lookup"><span data-stu-id="12bf4-207">The `vendors` dictionary contains one or more entries, with each entry being identified by the vendor ID.</span></span>

|||
|:---|:---|
| <span data-ttu-id="12bf4-208">**Домен**</span><span class="sxs-lookup"><span data-stu-id="12bf4-208">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="12bf4-209">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="12bf4-209">**Key**</span></span> | <span data-ttu-id="12bf4-210">поставщики</span><span class="sxs-lookup"><span data-stu-id="12bf4-210">vendors</span></span> |
| <span data-ttu-id="12bf4-211">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="12bf4-211">**Data type**</span></span> | <span data-ttu-id="12bf4-212">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="12bf4-212">Dictionary (nested preference)</span></span> |

<span data-ttu-id="12bf4-213">Для каждого поставщика можно указать желаемый уровень разрешений для устройств этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="12bf4-213">For each vendor, you can specify the desired permission level for devices from that vendor.</span></span>

|||
|:---|:---|
| <span data-ttu-id="12bf4-214">**Домен**</span><span class="sxs-lookup"><span data-stu-id="12bf4-214">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="12bf4-215">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="12bf4-215">**Key**</span></span> | <span data-ttu-id="12bf4-216">разрешение</span><span class="sxs-lookup"><span data-stu-id="12bf4-216">permission</span></span> |
| <span data-ttu-id="12bf4-217">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="12bf4-217">**Data type**</span></span> | <span data-ttu-id="12bf4-218">Массив строк</span><span class="sxs-lookup"><span data-stu-id="12bf4-218">Array of strings</span></span> |
| <span data-ttu-id="12bf4-219">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="12bf4-219">**Possible values**</span></span> | <span data-ttu-id="12bf4-220">Такой же, [как уровень разрешений по умолчанию](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="12bf4-220">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="12bf4-221">Кроме того, можно дополнительно указать набор продуктов, принадлежащих этому поставщику, для которого определяются более гранулярные разрешения.</span><span class="sxs-lookup"><span data-stu-id="12bf4-221">Furthermore, you can optionally specify the set of products belonging to that vendor for which more granular permissions are defined.</span></span> <span data-ttu-id="12bf4-222">Словарь содержит одну или несколько записей, каждая запись `products` которых идентифицирована по ID продукта.</span><span class="sxs-lookup"><span data-stu-id="12bf4-222">The `products` dictionary contains one or more entries, with each entry being identified by the product ID.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="12bf4-223">**Домен**</span><span class="sxs-lookup"><span data-stu-id="12bf4-223">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="12bf4-224">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="12bf4-224">**Key**</span></span> | <span data-ttu-id="12bf4-225">продукты</span><span class="sxs-lookup"><span data-stu-id="12bf4-225">products</span></span> |
| <span data-ttu-id="12bf4-226">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="12bf4-226">**Data type**</span></span> | <span data-ttu-id="12bf4-227">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="12bf4-227">Dictionary (nested preference)</span></span> |

<span data-ttu-id="12bf4-228">Для каждого продукта можно указать нужный уровень разрешений для этого продукта.</span><span class="sxs-lookup"><span data-stu-id="12bf4-228">For each product, you can specify the desired permission level for that product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="12bf4-229">**Домен**</span><span class="sxs-lookup"><span data-stu-id="12bf4-229">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="12bf4-230">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="12bf4-230">**Key**</span></span> | <span data-ttu-id="12bf4-231">разрешение</span><span class="sxs-lookup"><span data-stu-id="12bf4-231">permission</span></span> |
| <span data-ttu-id="12bf4-232">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="12bf4-232">**Data type**</span></span> | <span data-ttu-id="12bf4-233">Массив строк</span><span class="sxs-lookup"><span data-stu-id="12bf4-233">Array of strings</span></span> |
| <span data-ttu-id="12bf4-234">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="12bf4-234">**Possible values**</span></span> | <span data-ttu-id="12bf4-235">Такой же, [как уровень разрешений по умолчанию](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="12bf4-235">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="12bf4-236">Кроме того, можно указать необязательный набор серийных номеров, для которых определены более детализативные разрешения.</span><span class="sxs-lookup"><span data-stu-id="12bf4-236">Furthermore, you can specify an optional set of serial numbers for which more granular permissions are defined.</span></span>

<span data-ttu-id="12bf4-237">Словарь `serialNumbers` содержит одну или несколько записей, каждая запись которых идентифицирована серийным номером.</span><span class="sxs-lookup"><span data-stu-id="12bf4-237">The `serialNumbers` dictionary contains one or more entries, with each entry being identified by the serial number.</span></span>

|||
|:---|:---|
| <span data-ttu-id="12bf4-238">**Домен**</span><span class="sxs-lookup"><span data-stu-id="12bf4-238">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="12bf4-239">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="12bf4-239">**Key**</span></span> | <span data-ttu-id="12bf4-240">serialNumbers</span><span class="sxs-lookup"><span data-stu-id="12bf4-240">serialNumbers</span></span> |
| <span data-ttu-id="12bf4-241">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="12bf4-241">**Data type**</span></span> | <span data-ttu-id="12bf4-242">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="12bf4-242">Dictionary (nested preference)</span></span> |

<span data-ttu-id="12bf4-243">Для каждого серийного номера можно указать нужный уровень разрешений.</span><span class="sxs-lookup"><span data-stu-id="12bf4-243">For each serial number, you can specify the desired permission level.</span></span>

|||
|:---|:---|
| <span data-ttu-id="12bf4-244">**Домен**</span><span class="sxs-lookup"><span data-stu-id="12bf4-244">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="12bf4-245">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="12bf4-245">**Key**</span></span> | <span data-ttu-id="12bf4-246">разрешение</span><span class="sxs-lookup"><span data-stu-id="12bf4-246">permission</span></span> |
| <span data-ttu-id="12bf4-247">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="12bf4-247">**Data type**</span></span> | <span data-ttu-id="12bf4-248">Массив строк</span><span class="sxs-lookup"><span data-stu-id="12bf4-248">Array of strings</span></span> |
| <span data-ttu-id="12bf4-249">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="12bf4-249">**Possible values**</span></span> | <span data-ttu-id="12bf4-250">Такой же, [как уровень разрешений по умолчанию](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="12bf4-250">Same as [Default permission level](#default-permission-level)</span></span> |

#### <a name="example-device-control-policy"></a><span data-ttu-id="12bf4-251">Пример политики управления устройствами</span><span class="sxs-lookup"><span data-stu-id="12bf4-251">Example device control policy</span></span>

<span data-ttu-id="12bf4-252">В следующем примере показано, как все вышеперечисленные понятия можно объединить в политику управления устройствами.</span><span class="sxs-lookup"><span data-stu-id="12bf4-252">The following example shows how all of the above concepts can be combined into a device control policy.</span></span> <span data-ttu-id="12bf4-253">В следующем примере обратите внимание на иерархический характер съемной политики мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="12bf4-253">In the following example, note the hierarchical nature of the removable media policy.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>navigationTarget</key> 
        <string>[custom URL for notifications]</string> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>[enforcement level]</string> <!-- audit / block --> 
            <key>permission</key> 
            <array> 
                <string>[permission]</string> <!-- none / read / write / execute --> 
                <!-- other permissions -->
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>[vendor id]</key> 
                <dict>
                    <key>permission</key> 
                    <array> 
                        <string>[permission]</string> <!-- none / read / write / execute --> 
                        <!-- other permissions -->
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>[product id]</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>[permission]</string> <!-- none / read / write / execute --> 
                                <!-- other permissions -->
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>[serial-number]</key> 
                                <array> 
                                    <string>[permission]</string> <!-- none / read / write / execute --> 
                                    <!-- other permissions -->
                                </array> 
                                <!-- other serial numbers --> 
                            </dict> 
                        </dict> 
                        <!-- other products --> 
                    </dict> 
                </dict> 
                <!-- other vendors --> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

<span data-ttu-id="12bf4-254">В следующих документах мы включили дополнительные примеры политик управления устройствами:</span><span class="sxs-lookup"><span data-stu-id="12bf4-254">We have included more examples of device control policies in the following documents:</span></span>

- [<span data-ttu-id="12bf4-255">Примеры политик управления устройствами для Intune</span><span class="sxs-lookup"><span data-stu-id="12bf4-255">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="12bf4-256">Примеры политик управления устройствами для JAMF</span><span class="sxs-lookup"><span data-stu-id="12bf4-256">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a><span data-ttu-id="12bf4-257">Искать идентификаторы устройств</span><span class="sxs-lookup"><span data-stu-id="12bf4-257">Look up device identifiers</span></span>

<span data-ttu-id="12bf4-258">Чтобы найти ID поставщика, ID продукта и серийный номер USB-устройства:</span><span class="sxs-lookup"><span data-stu-id="12bf4-258">To find the vendor ID, product ID, and serial number of a USB device:</span></span>

1. <span data-ttu-id="12bf4-259">Войдите в устройство Mac.</span><span class="sxs-lookup"><span data-stu-id="12bf4-259">Log into a Mac device.</span></span>
1. <span data-ttu-id="12bf4-260">Подключите usb-устройство, для которого необходимо искать идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="12bf4-260">Plug in the USB device for which you want to look up the identifiers.</span></span>
1. <span data-ttu-id="12bf4-261">В меню macOS верхнего уровня выберите **About This Mac**.</span><span class="sxs-lookup"><span data-stu-id="12bf4-261">In the top-level menu of macOS, select **About This Mac**.</span></span>

    ![Об этом Mac](images/mac-device-control-lookup-1.png)

1. <span data-ttu-id="12bf4-263">Выберите **системный отчет**.</span><span class="sxs-lookup"><span data-stu-id="12bf4-263">Select **System Report**.</span></span>

    ![Отчет о системе](images/mac-device-control-lookup-2.png)

1. <span data-ttu-id="12bf4-265">В левом столбце выберите **USB.**</span><span class="sxs-lookup"><span data-stu-id="12bf4-265">From the left column, select **USB**.</span></span>

    ![Просмотр всех USB-устройств](images/mac-device-control-lookup-3.png)

1. <span data-ttu-id="12bf4-267">В **usb Device Tree** перейдите на подключенное устройство USB.</span><span class="sxs-lookup"><span data-stu-id="12bf4-267">Under **USB Device Tree**, navigate to the USB device that you plugged in.</span></span>

    ![Сведения о USB-устройстве](images/mac-device-control-lookup-4.png)

1. <span data-ttu-id="12bf4-269">Отображаются ИД поставщика, ИД продукта и серийный номер.</span><span class="sxs-lookup"><span data-stu-id="12bf4-269">The vendor ID, product ID, and serial number are displayed.</span></span> <span data-ttu-id="12bf4-270">При добавлении id поставщика и ИД продукта в съемную политику мультимедиа необходимо добавить только часть после `0x` .</span><span class="sxs-lookup"><span data-stu-id="12bf4-270">When adding the vendor ID and product ID to the removable media policy, you must only add the part after `0x`.</span></span> <span data-ttu-id="12bf4-271">Например, на приведенной ниже картинке имеется ИД поставщика и `1000` ID продукта `090c` .</span><span class="sxs-lookup"><span data-stu-id="12bf4-271">For example, in the below image, vendor ID is `1000` and product ID is `090c`.</span></span>

#### <a name="discover-usb-devices-in-your-organization"></a><span data-ttu-id="12bf4-272">Обнаружение USB-устройств в организации</span><span class="sxs-lookup"><span data-stu-id="12bf4-272">Discover USB devices in your organization</span></span>

<span data-ttu-id="12bf4-273">Вы можете просматривать события изменения крепления, перенагрузки и изменения громкости, происходящие с USB-устройств в Microsoft Defender для продвинутой охоты endpoint.</span><span class="sxs-lookup"><span data-stu-id="12bf4-273">You can view mount, unmount, and volume change events originating from USB devices in Microsoft Defender for Endpoint advanced hunting.</span></span> <span data-ttu-id="12bf4-274">Эти события могут быть полезны для выявления подозрительных действий по использованию или проведения внутренних расследований.</span><span class="sxs-lookup"><span data-stu-id="12bf4-274">These events can be helpful to identify suspicious usage activity or perform internal investigations.</span></span>

```
DeviceEvents 
    | where ActionType == "UsbDriveMount" or ActionType == "UsbDriveUnmount" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a><span data-ttu-id="12bf4-275">Развертывание политики управления устройствами</span><span class="sxs-lookup"><span data-stu-id="12bf4-275">Device control policy deployment</span></span>

<span data-ttu-id="12bf4-276">Политика управления устройствами должна быть включена рядом с другими настройками продукта, как описано в параметрах [Set preferences for Microsoft Defender for Endpoint для Mac.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="12bf4-276">The device control policy must be included next to the other product settings, as described in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

<span data-ttu-id="12bf4-277">Этот профиль можно развернуть с помощью инструкций, перечисленных в [развертывании профиля Конфигурация.](mac-preferences.md#configuration-profile-deployment)</span><span class="sxs-lookup"><span data-stu-id="12bf4-277">This profile can be deployed using the instructions listed in [Configuration profile deployment](mac-preferences.md#configuration-profile-deployment).</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="12bf4-278">Советы по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="12bf4-278">Troubleshooting tips</span></span>

<span data-ttu-id="12bf4-279">После нажатия профиля конфигурации через Intune или JAMF вы можете проверить, был ли он успешно подхвален продуктом, подав следующую команду из терминала:</span><span class="sxs-lookup"><span data-stu-id="12bf4-279">After pushing the configuration profile through Intune or JAMF, you can check if it was successfully picked up by the product by running the following command from the Terminal:</span></span>

```bash
mdatp device-control removable-media policy list
```

<span data-ttu-id="12bf4-280">Эта команда напечатает для стандартного вывода политику управления устройствами, используемую продуктом.</span><span class="sxs-lookup"><span data-stu-id="12bf4-280">This command will print to standard output the device control policy that the product is using.</span></span> <span data-ttu-id="12bf4-281">В случае принтов убедитесь, что a) профиль конфигурации действительно был оттеснен на ваше устройство из консоли управления, и b) это допустимая политика управления устройствами, как описано в этом `Policy is empty` документе.</span><span class="sxs-lookup"><span data-stu-id="12bf4-281">In case this prints `Policy is empty`, make sure that (a) the configuration profile has indeed been pushed to your device from the management console, and (b) it is a valid device control policy, as described in this document.</span></span>

<span data-ttu-id="12bf4-282">На устройстве, где политика была успешно доставлена и где подключено одно или несколько устройств, можно выполнить следующую команду, чтобы перечислить все устройства и эффективные разрешения, применяемые к ним.</span><span class="sxs-lookup"><span data-stu-id="12bf4-282">On a device where the policy has been delivered successfully and where there are one or more devices plugged in, you can run the following command to list all devices and the effective permissions applied to them.</span></span>

```bash
mdatp device-control removable-media devices list
```

<span data-ttu-id="12bf4-283">Пример вывода.</span><span class="sxs-lookup"><span data-stu-id="12bf4-283">Example of output:</span></span>

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

<span data-ttu-id="12bf4-284">В этом примере подключено только одно съемное мультимедиа-устройство, которое имеет и разрешения, в соответствии с политикой управления устройством, доставленной `read` `execute` на устройство.</span><span class="sxs-lookup"><span data-stu-id="12bf4-284">In the above example, there is only one removable media device plugged in and it has `read` and `execute` permissions, according to the device control policy that was delivered to the device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="12bf4-285">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="12bf4-285">Related topics</span></span>

- [<span data-ttu-id="12bf4-286">Примеры политик управления устройствами для Intune</span><span class="sxs-lookup"><span data-stu-id="12bf4-286">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="12bf4-287">Примеры политик управления устройствами для JAMF</span><span class="sxs-lookup"><span data-stu-id="12bf4-287">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)