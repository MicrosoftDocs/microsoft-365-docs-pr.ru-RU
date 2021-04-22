---
title: Управление устройствами для macOS
description: Узнайте, как настроить Microsoft Defender для конечной точки на Mac, чтобы уменьшить угрозы со съемного хранилища, например USB-устройств.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mac, device, control, usb, removable, media
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
ms.openlocfilehash: 39f8367c34e98c5e9dd11e9716f08e6c9e7fd9c0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935129"
---
# <a name="device-control-for-macos"></a><span data-ttu-id="1789d-104">Управление устройствами для macOS</span><span class="sxs-lookup"><span data-stu-id="1789d-104">Device control for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1789d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1789d-105">**Applies to:**</span></span>
- [<span data-ttu-id="1789d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1789d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1789d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1789d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1789d-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="1789d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1789d-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="1789d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="requirements"></a><span data-ttu-id="1789d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1789d-110">Requirements</span></span>

<span data-ttu-id="1789d-111">Управление устройствами для macOS имеет следующие условия:</span><span class="sxs-lookup"><span data-stu-id="1789d-111">Device control for macOS has the following prerequisites:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="1789d-112">Право Microsoft Defender для конечной точки (может быть пробным)</span><span class="sxs-lookup"><span data-stu-id="1789d-112">Microsoft Defender for Endpoint entitlement (can be trial)</span></span>
> - <span data-ttu-id="1789d-113">Минимальная версия ОС: macOS 10.15.4 или более</span><span class="sxs-lookup"><span data-stu-id="1789d-113">Minimum OS version: macOS 10.15.4 or higher</span></span>
> - <span data-ttu-id="1789d-114">Минимальная версия продукта: 101.24.59</span><span class="sxs-lookup"><span data-stu-id="1789d-114">Minimum product version: 101.24.59</span></span>
> - <span data-ttu-id="1789d-115">Устройство должно работать с расширениями системы (это по умолчанию для macOS 11 Big Sur).</span><span class="sxs-lookup"><span data-stu-id="1789d-115">Your device must be running with system extensions (this is the default on macOS 11 Big Sur).</span></span> 
> 
>   <span data-ttu-id="1789d-116">Вы можете проверить, работает ли ваше устройство на системных расширениях, подав следующую команду, и убедиться, что оно печатает `endpoint_security_extension` на консоли:</span><span class="sxs-lookup"><span data-stu-id="1789d-116">You can check if your device is running on system extensions by running the following command and verify that it is printing `endpoint_security_extension` to the console:</span></span> 
> 
>   ```bash
>   mdatp health --field real_time_protection_subsystem 
>   ```
> - <span data-ttu-id="1789d-117">Ваше устройство должно быть в `Beta` (ранее `InsiderFast` называемом) канале обновления Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="1789d-117">Your device must be in `Beta` (previously called `InsiderFast`) Microsoft AutoUpdate update channel.</span></span> <span data-ttu-id="1789d-118">Дополнительные сведения см. в [сайте Deploy updates for Microsoft Defender for Endpoint on Mac.](mac-updates.md)</span><span class="sxs-lookup"><span data-stu-id="1789d-118">For more information, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span>
> 
>   <span data-ttu-id="1789d-119">Вы можете проверить канал обновления с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="1789d-119">You can check the update channel using the following command:</span></span> 
> 
>    ```bash
>    mdatp health --field release_ring 
>    ```
>
>    <span data-ttu-id="1789d-120">Если вышеуказанная команда не распечатает или `Beta` `InsiderFast` не выполнит следующую команду из терминала.</span><span class="sxs-lookup"><span data-stu-id="1789d-120">If the above command does not print either `Beta` or `InsiderFast`, execute the following command from the Terminal.</span></span> <span data-ttu-id="1789d-121">Обновление канала вступает в силу в следующий раз, когда продукт запускается (при следующем обновлении продукта или при перезагрузке устройства).</span><span class="sxs-lookup"><span data-stu-id="1789d-121">The channel update takes effect next time the product starts (when the next product update is installed or when the device is rebooted).</span></span> 
> 
>    ```bash
>    defaults write com.microsoft.autoupdate2 ChannelName -string Beta
>    ```
>
>    <span data-ttu-id="1789d-122">Кроме того, если вы находитесь в управляемой среде (JAMF или Intune), вы можете настроить канал обновления удаленно.</span><span class="sxs-lookup"><span data-stu-id="1789d-122">Alternatively, if you are in a managed environment (JAMF or Intune), you can configure the update channel remotely.</span></span> <span data-ttu-id="1789d-123">Дополнительные сведения см. в [сайте Deploy updates for Microsoft Defender for Endpoint on Mac.](mac-updates.md)</span><span class="sxs-lookup"><span data-stu-id="1789d-123">For more information, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span> 

## <a name="device-control-policy"></a><span data-ttu-id="1789d-124">Политика управления устройствами</span><span class="sxs-lookup"><span data-stu-id="1789d-124">Device control policy</span></span>

<span data-ttu-id="1789d-125">Чтобы настроить управление устройствами для macOS, необходимо создать политику, описываемую ограничения, которые необходимо ввести в организации.</span><span class="sxs-lookup"><span data-stu-id="1789d-125">To configure device control for macOS, you must create a policy that describes the restrictions you want to put in place within your organization.</span></span>

<span data-ttu-id="1789d-126">Политика управления устройством включена в профиль конфигурации, используемый для настройки всех остальных параметров продукта.</span><span class="sxs-lookup"><span data-stu-id="1789d-126">The device control policy is included in the configuration profile used to configure all other product settings.</span></span> <span data-ttu-id="1789d-127">Дополнительные сведения см. в [странице Конфигурация структуры профилей.](mac-preferences.md#configuration-profile-structure)</span><span class="sxs-lookup"><span data-stu-id="1789d-127">For more information, see [Configuration profile structure](mac-preferences.md#configuration-profile-structure).</span></span>

<span data-ttu-id="1789d-128">В профиле конфигурации политика управления устройствами определяется в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="1789d-128">Within the configuration profile, the device control policy is defined in the following section:</span></span>

|<span data-ttu-id="1789d-129">Section</span><span class="sxs-lookup"><span data-stu-id="1789d-129">Section</span></span>|<span data-ttu-id="1789d-130">Значение</span><span class="sxs-lookup"><span data-stu-id="1789d-130">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1789d-131">**Домен**</span><span class="sxs-lookup"><span data-stu-id="1789d-131">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1789d-132">**Key**</span><span class="sxs-lookup"><span data-stu-id="1789d-132">**Key**</span></span> | <span data-ttu-id="1789d-133">deviceControl</span><span class="sxs-lookup"><span data-stu-id="1789d-133">deviceControl</span></span> |
| <span data-ttu-id="1789d-134">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1789d-134">**Data type**</span></span> | <span data-ttu-id="1789d-135">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="1789d-135">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1789d-136">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="1789d-136">**Comments**</span></span> | <span data-ttu-id="1789d-137">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="1789d-137">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="1789d-138">Политика управления устройствами может использоваться для:</span><span class="sxs-lookup"><span data-stu-id="1789d-138">The device control policy can be used to:</span></span>

- [<span data-ttu-id="1789d-139">Настройка целевого URL-адреса для уведомлений, поднятых с помощью управления устройствами</span><span class="sxs-lookup"><span data-stu-id="1789d-139">Customize the URL target for notifications raised by device control</span></span>](#customize-url-target-for-notifications-raised-by-device-control)
- [<span data-ttu-id="1789d-140">Разрешить или заблокировать съемные устройства</span><span class="sxs-lookup"><span data-stu-id="1789d-140">Allow or block removable devices</span></span>](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a><span data-ttu-id="1789d-141">Настройка URL-адреса для уведомлений, поднятых с помощью управления устройствами</span><span class="sxs-lookup"><span data-stu-id="1789d-141">Customize URL target for notifications raised by device control</span></span>

<span data-ttu-id="1789d-142">Если на устройстве применена политика управления устройствами (например, доступ к съемным носитему устройству ограничен), пользователю отображается уведомление.</span><span class="sxs-lookup"><span data-stu-id="1789d-142">When the device control policy that you have put in place is enforced on a device (for example, access to a removable media device is restricted), a notification is displayed to the user.</span></span>

![Уведомление об устройстве управления](images/mac-device-control-notification.png)

<span data-ttu-id="1789d-144">Когда конечные пользователи щелкают это уведомление, веб-страница открывается в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1789d-144">When end users click this notification, a web page is opened in the default browser.</span></span> <span data-ttu-id="1789d-145">Вы можете настроить URL-адрес, открываемый при нажатии уведомления конечными пользователями.</span><span class="sxs-lookup"><span data-stu-id="1789d-145">You can configure the URL that is opened when end users click the notification.</span></span>

|<span data-ttu-id="1789d-146">Section</span><span class="sxs-lookup"><span data-stu-id="1789d-146">Section</span></span>|<span data-ttu-id="1789d-147">Значение</span><span class="sxs-lookup"><span data-stu-id="1789d-147">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1789d-148">**Домен**</span><span class="sxs-lookup"><span data-stu-id="1789d-148">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1789d-149">**Key**</span><span class="sxs-lookup"><span data-stu-id="1789d-149">**Key**</span></span> | <span data-ttu-id="1789d-150">navigationTarget</span><span class="sxs-lookup"><span data-stu-id="1789d-150">navigationTarget</span></span> |
| <span data-ttu-id="1789d-151">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1789d-151">**Data type**</span></span> | <span data-ttu-id="1789d-152">String</span><span class="sxs-lookup"><span data-stu-id="1789d-152">String</span></span> |
| <span data-ttu-id="1789d-153">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="1789d-153">**Comments**</span></span> | <span data-ttu-id="1789d-154">Если не определено, продукт использует URL-адрес по умолчанию, указывающий на общую страницу с объяснением действий, принятых продуктом.</span><span class="sxs-lookup"><span data-stu-id="1789d-154">If not defined, the product uses a default URL pointing to a generic page explaining the action taken by the product.</span></span> |

### <a name="allow-or-block-removable-devices"></a><span data-ttu-id="1789d-155">Разрешить или заблокировать съемные устройства</span><span class="sxs-lookup"><span data-stu-id="1789d-155">Allow or block removable devices</span></span>

<span data-ttu-id="1789d-156">Съемный раздел мультимедиа политики управления устройствами используется для ограничения доступа к съемным носителям.</span><span class="sxs-lookup"><span data-stu-id="1789d-156">The removable media section of the device control policy is used to restrict access to removable media.</span></span> 

> [!NOTE]
> <span data-ttu-id="1789d-157">В настоящее время поддерживаются следующие типы съемных мультимедиа, которые могут быть включены в политику: устройства хранения USB.</span><span class="sxs-lookup"><span data-stu-id="1789d-157">The following types of removable media are currently supported and can be included in the policy: USB storage devices.</span></span>

|<span data-ttu-id="1789d-158">Section</span><span class="sxs-lookup"><span data-stu-id="1789d-158">Section</span></span>|<span data-ttu-id="1789d-159">Значение</span><span class="sxs-lookup"><span data-stu-id="1789d-159">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1789d-160">**Домен**</span><span class="sxs-lookup"><span data-stu-id="1789d-160">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1789d-161">**Key**</span><span class="sxs-lookup"><span data-stu-id="1789d-161">**Key**</span></span> | <span data-ttu-id="1789d-162">removableMediaPolicy</span><span class="sxs-lookup"><span data-stu-id="1789d-162">removableMediaPolicy</span></span> |
| <span data-ttu-id="1789d-163">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1789d-163">**Data type**</span></span> | <span data-ttu-id="1789d-164">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="1789d-164">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1789d-165">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="1789d-165">**Comments**</span></span> | <span data-ttu-id="1789d-166">В следующих разделах описано содержимое словаря.</span><span class="sxs-lookup"><span data-stu-id="1789d-166">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="1789d-167">Этот раздел политики иерархичен, что обеспечивает максимальную гибкость и охватывает широкий диапазон случаев использования.</span><span class="sxs-lookup"><span data-stu-id="1789d-167">This section of the policy is hierarchical, allowing for maximum flexibility and covering a wide range of use cases.</span></span> <span data-ttu-id="1789d-168">На верхнем уровне находятся поставщики, идентифицированные по ID поставщика.</span><span class="sxs-lookup"><span data-stu-id="1789d-168">At the top level are vendors, identified by a vendor ID.</span></span> <span data-ttu-id="1789d-169">Для каждого поставщика существуют продукты, идентифицированные по ID продукта.</span><span class="sxs-lookup"><span data-stu-id="1789d-169">For each vendor, there are products, identified by a product ID.</span></span> <span data-ttu-id="1789d-170">Наконец, для каждого продукта существуют серийные номера, обозначающие конкретные устройства.</span><span class="sxs-lookup"><span data-stu-id="1789d-170">Finally, for each product there are serial numbers denoting specific devices.</span></span>

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

<span data-ttu-id="1789d-171">Сведения о поиске идентификаторов устройств см. в документе [Look up device identifiers.](#look-up-device-identifiers)</span><span class="sxs-lookup"><span data-stu-id="1789d-171">For information on how to find the device identifiers, see [Look up device identifiers](#look-up-device-identifiers).</span></span>

<span data-ttu-id="1789d-172">Политика оценивается от самой конкретной записи до самой общей.</span><span class="sxs-lookup"><span data-stu-id="1789d-172">The policy is evaluated from the most specific entry to the most general one.</span></span> <span data-ttu-id="1789d-173">То есть, когда устройство подключено, продукт пытается найти наиболее конкретное совпадение в политике для каждого съемного устройства мультимедиа и применить разрешения на этом уровне.</span><span class="sxs-lookup"><span data-stu-id="1789d-173">Meaning, when a device is plugged in, the product tries to find the most specific match in the policy for each removable media device and apply the permissions at that level.</span></span> <span data-ttu-id="1789d-174">Если нет совпадения, применяется следующий оптимальный совпадение, в том числе разрешение, указанное на верхнем уровне, которое является по умолчанию, если устройство не соответствует какой-либо другой записи в политике.</span><span class="sxs-lookup"><span data-stu-id="1789d-174">If there is no match, then the next best match is applied, all the way to the permission specified at the top level, which is the default when a device does not match any other entry in the policy.</span></span>

#### <a name="policy-enforcement-level"></a><span data-ttu-id="1789d-175">Уровень правоприменения политики</span><span class="sxs-lookup"><span data-stu-id="1789d-175">Policy enforcement level</span></span>

<span data-ttu-id="1789d-176">В разделе съемное мультимедиа можно установить уровень правоприменения, который может принять одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="1789d-176">Under the removable media section, there is an option to set the enforcement level, which can take one of the following values:</span></span>

- <span data-ttu-id="1789d-177">`audit` - В соответствии с этим уровнем правоприменения, если доступ к устройству ограничен, пользователю отображается уведомление, однако устройство все еще можно использовать.</span><span class="sxs-lookup"><span data-stu-id="1789d-177">`audit` - Under this enforcement level, if access to a device is restricted, a notification is displayed to the user, however the device can still be used.</span></span> <span data-ttu-id="1789d-178">Этот уровень применения может быть полезен для оценки эффективности политики.</span><span class="sxs-lookup"><span data-stu-id="1789d-178">This enforcement level can be useful to evaluate the effectiveness of a policy.</span></span>
- <span data-ttu-id="1789d-179">`block` — В соответствии с этим уровнем обеспечения выполнения операций, которые пользователь может выполнять на устройстве, ограничивается тем, что определено в политике.</span><span class="sxs-lookup"><span data-stu-id="1789d-179">`block` - Under this enforcement level, the operations that the user can perform on the device are limited to what is defined in the policy.</span></span> <span data-ttu-id="1789d-180">Кроме того, пользователь получает уведомление.</span><span class="sxs-lookup"><span data-stu-id="1789d-180">Furthermore, a notification is raised to the user.</span></span> 

|<span data-ttu-id="1789d-181">Section</span><span class="sxs-lookup"><span data-stu-id="1789d-181">Section</span></span>|<span data-ttu-id="1789d-182">Значение</span><span class="sxs-lookup"><span data-stu-id="1789d-182">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1789d-183">**Домен**</span><span class="sxs-lookup"><span data-stu-id="1789d-183">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1789d-184">**Key**</span><span class="sxs-lookup"><span data-stu-id="1789d-184">**Key**</span></span> | <span data-ttu-id="1789d-185">enforcementLevel</span><span class="sxs-lookup"><span data-stu-id="1789d-185">enforcementLevel</span></span> |
| <span data-ttu-id="1789d-186">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1789d-186">**Data type**</span></span> | <span data-ttu-id="1789d-187">String</span><span class="sxs-lookup"><span data-stu-id="1789d-187">String</span></span> |
| <span data-ttu-id="1789d-188">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="1789d-188">**Possible values**</span></span> | <span data-ttu-id="1789d-189">аудит (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1789d-189">audit (default)</span></span> <br/> <span data-ttu-id="1789d-190">block</span><span class="sxs-lookup"><span data-stu-id="1789d-190">block</span></span> |

#### <a name="default-permission-level"></a><span data-ttu-id="1789d-191">Уровень разрешений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1789d-191">Default permission level</span></span>

<span data-ttu-id="1789d-192">На верхнем уровне съемного раздела мультимедиа можно настроить уровень разрешений по умолчанию для устройств, которые не соответствуют ни к чему другому в политике.</span><span class="sxs-lookup"><span data-stu-id="1789d-192">At the top level of the removable media section, you can configure the default permission level for devices that do not match anything else in the policy.</span></span>

<span data-ttu-id="1789d-193">Этот параметр может быть заданной для:</span><span class="sxs-lookup"><span data-stu-id="1789d-193">This setting can be set to:</span></span>

- <span data-ttu-id="1789d-194">`none` - Операции на устройстве не выполняются</span><span class="sxs-lookup"><span data-stu-id="1789d-194">`none` - No operations can be performed on the device</span></span>
- <span data-ttu-id="1789d-195">Сочетание следующих значений:</span><span class="sxs-lookup"><span data-stu-id="1789d-195">A combination of the following values:</span></span>
    - <span data-ttu-id="1789d-196">`read` - Операции чтения разрешены на устройстве</span><span class="sxs-lookup"><span data-stu-id="1789d-196">`read` - Read operations are permitted on the device</span></span>
    - <span data-ttu-id="1789d-197">`write` - Операции записи разрешены на устройстве</span><span class="sxs-lookup"><span data-stu-id="1789d-197">`write` - Write operations are permitted on the device</span></span>
    - <span data-ttu-id="1789d-198">`execute` - Выполнение операций разрешено на устройстве</span><span class="sxs-lookup"><span data-stu-id="1789d-198">`execute` - Execute operations are permitted on the device</span></span>

> [!NOTE]
> <span data-ttu-id="1789d-199">Если они присутствуют на уровне разрешений, любые другие разрешения `none` `read` `write` (или) будут `execute` игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="1789d-199">If `none` is present in the permission level, any other permissions (`read`, `write`, or `execute`) will be ignored.</span></span>

> [!NOTE]
> <span data-ttu-id="1789d-200">Разрешение `execute` относится только к выполнению бинарей Mach-O.</span><span class="sxs-lookup"><span data-stu-id="1789d-200">The `execute` permission only refers to execution of Mach-O binaries.</span></span> <span data-ttu-id="1789d-201">Он не включает выполнение скриптов или других типов полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="1789d-201">It does not include execution of scripts or other types of payloads.</span></span>

|<span data-ttu-id="1789d-202">Section</span><span class="sxs-lookup"><span data-stu-id="1789d-202">Section</span></span>|<span data-ttu-id="1789d-203">Значение</span><span class="sxs-lookup"><span data-stu-id="1789d-203">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1789d-204">**Домен**</span><span class="sxs-lookup"><span data-stu-id="1789d-204">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1789d-205">**Key**</span><span class="sxs-lookup"><span data-stu-id="1789d-205">**Key**</span></span> | <span data-ttu-id="1789d-206">разрешение</span><span class="sxs-lookup"><span data-stu-id="1789d-206">permission</span></span> |
| <span data-ttu-id="1789d-207">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1789d-207">**Data type**</span></span> | <span data-ttu-id="1789d-208">Массив строк</span><span class="sxs-lookup"><span data-stu-id="1789d-208">Array of strings</span></span> |
| <span data-ttu-id="1789d-209">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="1789d-209">**Possible values**</span></span> | <span data-ttu-id="1789d-210">нет</span><span class="sxs-lookup"><span data-stu-id="1789d-210">none</span></span> <br/> <span data-ttu-id="1789d-211">read</span><span class="sxs-lookup"><span data-stu-id="1789d-211">read</span></span> <br/> <span data-ttu-id="1789d-212">write</span><span class="sxs-lookup"><span data-stu-id="1789d-212">write</span></span> <br/> <span data-ttu-id="1789d-213">выполнение</span><span class="sxs-lookup"><span data-stu-id="1789d-213">execute</span></span> |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a><span data-ttu-id="1789d-214">Ограничение съемных мультимедиа поставщиком, продуктом и серийным номером</span><span class="sxs-lookup"><span data-stu-id="1789d-214">Restrict removable media by vendor, product, and serial number</span></span>

<span data-ttu-id="1789d-215">Как описано в [описании Разрешить](#allow-or-block-removable-devices)или блокировать съемные устройства, съемные носитли, такие как USB-устройства, могут быть идентифицированы по ID поставщика, ID продукта и серийному номеру.</span><span class="sxs-lookup"><span data-stu-id="1789d-215">As described in [Allow or block removable devices](#allow-or-block-removable-devices), removable media such as USB devices can be identified by the vendor ID, product ID, and serial number.</span></span>

<span data-ttu-id="1789d-216">На верхнем уровне политики съемных мультимедиа можно дополнительно определить более подробное ограничение на уровне поставщика.</span><span class="sxs-lookup"><span data-stu-id="1789d-216">At the top level of the removable media policy, you can optionally define more granular restrictions at the vendor level.</span></span> 

<span data-ttu-id="1789d-217">Словарь содержит одну или несколько записей, каждая запись `vendors` которых идентифицирована по ID поставщика.</span><span class="sxs-lookup"><span data-stu-id="1789d-217">The `vendors` dictionary contains one or more entries, with each entry being identified by the vendor ID.</span></span>

|<span data-ttu-id="1789d-218">Section</span><span class="sxs-lookup"><span data-stu-id="1789d-218">Section</span></span>|<span data-ttu-id="1789d-219">Значение</span><span class="sxs-lookup"><span data-stu-id="1789d-219">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1789d-220">**Домен**</span><span class="sxs-lookup"><span data-stu-id="1789d-220">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1789d-221">**Key**</span><span class="sxs-lookup"><span data-stu-id="1789d-221">**Key**</span></span> | <span data-ttu-id="1789d-222">поставщики</span><span class="sxs-lookup"><span data-stu-id="1789d-222">vendors</span></span> |
| <span data-ttu-id="1789d-223">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1789d-223">**Data type**</span></span> | <span data-ttu-id="1789d-224">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="1789d-224">Dictionary (nested preference)</span></span> |

<span data-ttu-id="1789d-225">Для каждого поставщика можно указать желаемый уровень разрешений для устройств этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="1789d-225">For each vendor, you can specify the desired permission level for devices from that vendor.</span></span>

|<span data-ttu-id="1789d-226">Section</span><span class="sxs-lookup"><span data-stu-id="1789d-226">Section</span></span>|<span data-ttu-id="1789d-227">Значение</span><span class="sxs-lookup"><span data-stu-id="1789d-227">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1789d-228">**Домен**</span><span class="sxs-lookup"><span data-stu-id="1789d-228">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1789d-229">**Key**</span><span class="sxs-lookup"><span data-stu-id="1789d-229">**Key**</span></span> | <span data-ttu-id="1789d-230">разрешение</span><span class="sxs-lookup"><span data-stu-id="1789d-230">permission</span></span> |
| <span data-ttu-id="1789d-231">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1789d-231">**Data type**</span></span> | <span data-ttu-id="1789d-232">Массив строк</span><span class="sxs-lookup"><span data-stu-id="1789d-232">Array of strings</span></span> |
| <span data-ttu-id="1789d-233">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="1789d-233">**Possible values**</span></span> | <span data-ttu-id="1789d-234">Такой же, [как уровень разрешений по умолчанию](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="1789d-234">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="1789d-235">Кроме того, можно дополнительно указать набор продуктов, принадлежащих этому поставщику, для которого определяются более гранулярные разрешения.</span><span class="sxs-lookup"><span data-stu-id="1789d-235">Furthermore, you can optionally specify the set of products belonging to that vendor for which more granular permissions are defined.</span></span> <span data-ttu-id="1789d-236">Словарь содержит одну или несколько записей, каждая запись `products` которых идентифицирована по ID продукта.</span><span class="sxs-lookup"><span data-stu-id="1789d-236">The `products` dictionary contains one or more entries, with each entry being identified by the product ID.</span></span> 

|<span data-ttu-id="1789d-237">Section</span><span class="sxs-lookup"><span data-stu-id="1789d-237">Section</span></span>|<span data-ttu-id="1789d-238">Значение</span><span class="sxs-lookup"><span data-stu-id="1789d-238">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1789d-239">**Домен**</span><span class="sxs-lookup"><span data-stu-id="1789d-239">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1789d-240">**Key**</span><span class="sxs-lookup"><span data-stu-id="1789d-240">**Key**</span></span> | <span data-ttu-id="1789d-241">продукты</span><span class="sxs-lookup"><span data-stu-id="1789d-241">products</span></span> |
| <span data-ttu-id="1789d-242">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1789d-242">**Data type**</span></span> | <span data-ttu-id="1789d-243">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="1789d-243">Dictionary (nested preference)</span></span> |

<span data-ttu-id="1789d-244">Для каждого продукта можно указать нужный уровень разрешений для этого продукта.</span><span class="sxs-lookup"><span data-stu-id="1789d-244">For each product, you can specify the desired permission level for that product.</span></span>

|<span data-ttu-id="1789d-245">Section</span><span class="sxs-lookup"><span data-stu-id="1789d-245">Section</span></span>|<span data-ttu-id="1789d-246">Значение</span><span class="sxs-lookup"><span data-stu-id="1789d-246">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1789d-247">**Домен**</span><span class="sxs-lookup"><span data-stu-id="1789d-247">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1789d-248">**Key**</span><span class="sxs-lookup"><span data-stu-id="1789d-248">**Key**</span></span> | <span data-ttu-id="1789d-249">разрешение</span><span class="sxs-lookup"><span data-stu-id="1789d-249">permission</span></span> |
| <span data-ttu-id="1789d-250">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1789d-250">**Data type**</span></span> | <span data-ttu-id="1789d-251">Массив строк</span><span class="sxs-lookup"><span data-stu-id="1789d-251">Array of strings</span></span> |
| <span data-ttu-id="1789d-252">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="1789d-252">**Possible values**</span></span> | <span data-ttu-id="1789d-253">Такой же, [как уровень разрешений по умолчанию](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="1789d-253">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="1789d-254">Кроме того, можно указать необязательный набор серийных номеров, для которых определены более детализативные разрешения.</span><span class="sxs-lookup"><span data-stu-id="1789d-254">Furthermore, you can specify an optional set of serial numbers for which more granular permissions are defined.</span></span>

<span data-ttu-id="1789d-255">Словарь `serialNumbers` содержит одну или несколько записей, каждая запись которых идентифицирована серийным номером.</span><span class="sxs-lookup"><span data-stu-id="1789d-255">The `serialNumbers` dictionary contains one or more entries, with each entry being identified by the serial number.</span></span>

|<span data-ttu-id="1789d-256">Section</span><span class="sxs-lookup"><span data-stu-id="1789d-256">Section</span></span>|<span data-ttu-id="1789d-257">Значение</span><span class="sxs-lookup"><span data-stu-id="1789d-257">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1789d-258">**Домен**</span><span class="sxs-lookup"><span data-stu-id="1789d-258">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1789d-259">**Key**</span><span class="sxs-lookup"><span data-stu-id="1789d-259">**Key**</span></span> | <span data-ttu-id="1789d-260">serialNumbers</span><span class="sxs-lookup"><span data-stu-id="1789d-260">serialNumbers</span></span> |
| <span data-ttu-id="1789d-261">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1789d-261">**Data type**</span></span> | <span data-ttu-id="1789d-262">Словарь (вложенные предпочтения)</span><span class="sxs-lookup"><span data-stu-id="1789d-262">Dictionary (nested preference)</span></span> |

<span data-ttu-id="1789d-263">Для каждого серийного номера можно указать нужный уровень разрешений.</span><span class="sxs-lookup"><span data-stu-id="1789d-263">For each serial number, you can specify the desired permission level.</span></span>

|<span data-ttu-id="1789d-264">Section</span><span class="sxs-lookup"><span data-stu-id="1789d-264">Section</span></span>|<span data-ttu-id="1789d-265">Значение</span><span class="sxs-lookup"><span data-stu-id="1789d-265">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1789d-266">**Домен**</span><span class="sxs-lookup"><span data-stu-id="1789d-266">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1789d-267">**Key**</span><span class="sxs-lookup"><span data-stu-id="1789d-267">**Key**</span></span> | <span data-ttu-id="1789d-268">разрешение</span><span class="sxs-lookup"><span data-stu-id="1789d-268">permission</span></span> |
| <span data-ttu-id="1789d-269">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1789d-269">**Data type**</span></span> | <span data-ttu-id="1789d-270">Массив строк</span><span class="sxs-lookup"><span data-stu-id="1789d-270">Array of strings</span></span> |
| <span data-ttu-id="1789d-271">**Возможные значения**</span><span class="sxs-lookup"><span data-stu-id="1789d-271">**Possible values**</span></span> | <span data-ttu-id="1789d-272">Такой же, [как уровень разрешений по умолчанию](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="1789d-272">Same as [Default permission level](#default-permission-level)</span></span> |

#### <a name="example-device-control-policy"></a><span data-ttu-id="1789d-273">Пример политики управления устройствами</span><span class="sxs-lookup"><span data-stu-id="1789d-273">Example device control policy</span></span>

<span data-ttu-id="1789d-274">В следующем примере показано, как все вышеперечисленные понятия можно объединить в политику управления устройствами.</span><span class="sxs-lookup"><span data-stu-id="1789d-274">The following example shows how all of the above concepts can be combined into a device control policy.</span></span> <span data-ttu-id="1789d-275">В следующем примере обратите внимание на иерархический характер съемной политики мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="1789d-275">In the following example, note the hierarchical nature of the removable media policy.</span></span>

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

<span data-ttu-id="1789d-276">В следующих документах мы включили дополнительные примеры политик управления устройствами:</span><span class="sxs-lookup"><span data-stu-id="1789d-276">We have included more examples of device control policies in the following documents:</span></span>

- [<span data-ttu-id="1789d-277">Примеры политик управления устройствами для Intune</span><span class="sxs-lookup"><span data-stu-id="1789d-277">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="1789d-278">Примеры политик управления устройствами для JAMF</span><span class="sxs-lookup"><span data-stu-id="1789d-278">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a><span data-ttu-id="1789d-279">Искать идентификаторы устройств</span><span class="sxs-lookup"><span data-stu-id="1789d-279">Look up device identifiers</span></span>

<span data-ttu-id="1789d-280">Чтобы найти ID поставщика, ID продукта и серийный номер USB-устройства:</span><span class="sxs-lookup"><span data-stu-id="1789d-280">To find the vendor ID, product ID, and serial number of a USB device:</span></span>

1. <span data-ttu-id="1789d-281">Войдите в устройство Mac.</span><span class="sxs-lookup"><span data-stu-id="1789d-281">Log into a Mac device.</span></span>
1. <span data-ttu-id="1789d-282">Подключите usb-устройство, для которого необходимо искать идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="1789d-282">Plug in the USB device for which you want to look up the identifiers.</span></span>
1. <span data-ttu-id="1789d-283">В меню macOS верхнего уровня выберите **About This Mac**.</span><span class="sxs-lookup"><span data-stu-id="1789d-283">In the top-level menu of macOS, select **About This Mac**.</span></span>

    ![Об этом Mac](images/mac-device-control-lookup-1.png)

1. <span data-ttu-id="1789d-285">Выберите **системный отчет**.</span><span class="sxs-lookup"><span data-stu-id="1789d-285">Select **System Report**.</span></span>

    ![Отчет о системе](images/mac-device-control-lookup-2.png)

1. <span data-ttu-id="1789d-287">В левом столбце выберите **USB.**</span><span class="sxs-lookup"><span data-stu-id="1789d-287">From the left column, select **USB**.</span></span>

    ![Просмотр всех USB-устройств](images/mac-device-control-lookup-3.png)

1. <span data-ttu-id="1789d-289">В **usb Device Tree** перейдите на подключенное устройство USB.</span><span class="sxs-lookup"><span data-stu-id="1789d-289">Under **USB Device Tree**, navigate to the USB device that you plugged in.</span></span>

    ![Сведения о USB-устройстве](images/mac-device-control-lookup-4.png)

1. <span data-ttu-id="1789d-291">Отображаются ИД поставщика, ИД продукта и серийный номер.</span><span class="sxs-lookup"><span data-stu-id="1789d-291">The vendor ID, product ID, and serial number are displayed.</span></span> <span data-ttu-id="1789d-292">При добавлении id поставщика и ИД продукта в съемную политику мультимедиа необходимо добавить только часть после `0x` .</span><span class="sxs-lookup"><span data-stu-id="1789d-292">When adding the vendor ID and product ID to the removable media policy, you must only add the part after `0x`.</span></span> <span data-ttu-id="1789d-293">Например, на приведенной ниже картинке имеется ИД поставщика и `1000` ID продукта `090c` .</span><span class="sxs-lookup"><span data-stu-id="1789d-293">For example, in the below image, vendor ID is `1000` and product ID is `090c`.</span></span>

#### <a name="discover-usb-devices-in-your-organization"></a><span data-ttu-id="1789d-294">Обнаружение USB-устройств в организации</span><span class="sxs-lookup"><span data-stu-id="1789d-294">Discover USB devices in your organization</span></span>

<span data-ttu-id="1789d-295">Вы можете просматривать события изменения крепления, перенагрузки и изменения громкости, происходящие с USB-устройств в Microsoft Defender для продвинутой охоты endpoint.</span><span class="sxs-lookup"><span data-stu-id="1789d-295">You can view mount, unmount, and volume change events originating from USB devices in Microsoft Defender for Endpoint advanced hunting.</span></span> <span data-ttu-id="1789d-296">Эти события могут быть полезны для выявления подозрительных действий по использованию или проведения внутренних расследований.</span><span class="sxs-lookup"><span data-stu-id="1789d-296">These events can be helpful to identify suspicious usage activity or perform internal investigations.</span></span>

```
DeviceEvents 
    | where ActionType == "UsbDriveMount" or ActionType == "UsbDriveUnmount" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a><span data-ttu-id="1789d-297">Развертывание политики управления устройствами</span><span class="sxs-lookup"><span data-stu-id="1789d-297">Device control policy deployment</span></span>

<span data-ttu-id="1789d-298">Политика управления устройствами должна быть включена рядом с другими настройками продукта, как описано в параметрах [Set preferences for Microsoft Defender for Endpoint на macOS.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="1789d-298">The device control policy must be included next to the other product settings, as described in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="1789d-299">Этот профиль можно развернуть с помощью инструкций, перечисленных в [развертывании профиля Конфигурация.](mac-preferences.md#configuration-profile-deployment)</span><span class="sxs-lookup"><span data-stu-id="1789d-299">This profile can be deployed using the instructions listed in [Configuration profile deployment](mac-preferences.md#configuration-profile-deployment).</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="1789d-300">Советы по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="1789d-300">Troubleshooting tips</span></span>

<span data-ttu-id="1789d-301">После нажатия профиля конфигурации через Intune или JAMF вы можете проверить, был ли он успешно подхвален продуктом, подав следующую команду из терминала:</span><span class="sxs-lookup"><span data-stu-id="1789d-301">After pushing the configuration profile through Intune or JAMF, you can check if it was successfully picked up by the product by running the following command from the Terminal:</span></span>

```bash
mdatp device-control removable-media policy list
```

<span data-ttu-id="1789d-302">Эта команда напечатает для стандартного вывода политику управления устройствами, используемую продуктом.</span><span class="sxs-lookup"><span data-stu-id="1789d-302">This command will print to standard output the device control policy that the product is using.</span></span> <span data-ttu-id="1789d-303">В случае принтов убедитесь, что a) профиль конфигурации действительно был оттеснен на ваше устройство из консоли управления, и b) это допустимая политика управления устройствами, как описано в этом `Policy is empty` документе.</span><span class="sxs-lookup"><span data-stu-id="1789d-303">In case this prints `Policy is empty`, make sure that (a) the configuration profile has indeed been pushed to your device from the management console, and (b) it is a valid device control policy, as described in this document.</span></span>

<span data-ttu-id="1789d-304">На устройстве, где политика была успешно доставлена и где подключено одно или несколько устройств, можно выполнить следующую команду, чтобы перечислить все устройства и эффективные разрешения, применяемые к ним.</span><span class="sxs-lookup"><span data-stu-id="1789d-304">On a device where the policy has been delivered successfully and where there are one or more devices plugged in, you can run the following command to list all devices and the effective permissions applied to them.</span></span>

```bash
mdatp device-control removable-media devices list
```

<span data-ttu-id="1789d-305">Пример вывода.</span><span class="sxs-lookup"><span data-stu-id="1789d-305">Example of output:</span></span>

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

<span data-ttu-id="1789d-306">В этом примере подключено только одно съемное мультимедиа-устройство, которое имеет и разрешения, в соответствии с политикой управления устройством, доставленной `read` `execute` на устройство.</span><span class="sxs-lookup"><span data-stu-id="1789d-306">In the above example, there is only one removable media device plugged in and it has `read` and `execute` permissions, according to the device control policy that was delivered to the device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1789d-307">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="1789d-307">Related topics</span></span>

- [<span data-ttu-id="1789d-308">Примеры политик управления устройствами для Intune</span><span class="sxs-lookup"><span data-stu-id="1789d-308">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="1789d-309">Примеры политик управления устройствами для JAMF</span><span class="sxs-lookup"><span data-stu-id="1789d-309">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)
