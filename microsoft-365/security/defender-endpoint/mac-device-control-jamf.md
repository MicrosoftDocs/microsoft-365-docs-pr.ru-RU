---
title: Примеры политик управления устройствами для JAMF
description: Узнайте, как использовать политики управления устройствами с помощью примеров, которые можно использовать в JAMF.
keywords: Microsoft, defender, endpoint, Microsoft Defender for Endpoint, mac, device, control, usb, removable, media, jamf
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
ms.openlocfilehash: b9ce161a472366d11b267824c9bd08ceccf285aa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933461"
---
# <a name="examples-of-device-control-policies-for-jamf"></a><span data-ttu-id="d3cd4-104">Примеры политик управления устройствами для JAMF</span><span class="sxs-lookup"><span data-stu-id="d3cd4-104">Examples of device control policies for JAMF</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d3cd4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d3cd4-105">**Applies to:**</span></span>
- [<span data-ttu-id="d3cd4-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d3cd4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d3cd4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3cd4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d3cd4-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="d3cd4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d3cd4-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="d3cd4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="d3cd4-110">В этом документе представлены примеры политик управления устройствами, которые можно настроить для своей организации.</span><span class="sxs-lookup"><span data-stu-id="d3cd4-110">This document contains examples of device control policies that you can customize for your own organization.</span></span> <span data-ttu-id="d3cd4-111">Эти примеры применимы, если вы используете JAMF для управления устройствами на предприятии.</span><span class="sxs-lookup"><span data-stu-id="d3cd4-111">These examples are applicable if you are using JAMF to manage devices in your enterprise.</span></span>

## <a name="restrict-access-to-all-removable-media"></a><span data-ttu-id="d3cd4-112">Ограничение доступа ко всем съемным носитему</span><span class="sxs-lookup"><span data-stu-id="d3cd4-112">Restrict access to all removable media</span></span>

<span data-ttu-id="d3cd4-113">В следующем примере ограничивается доступ ко всем съемным носитему.</span><span class="sxs-lookup"><span data-stu-id="d3cd4-113">The following example restricts access to all removable media.</span></span> <span data-ttu-id="d3cd4-114">Обратите внимание на разрешение, которое применяется на верхнем уровне политики, что означает, что все операции файлов будут `none` запрещены.</span><span class="sxs-lookup"><span data-stu-id="d3cd4-114">Note the `none` permission that is applied at the top level of the policy, meaning that all file operations will be prohibited.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>none</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="set-all-removable-media-to-be-read-only"></a><span data-ttu-id="d3cd4-115">Установите все съемные носитли только для чтения</span><span class="sxs-lookup"><span data-stu-id="d3cd4-115">Set all removable media to be read-only</span></span>

<span data-ttu-id="d3cd4-116">В следующем примере все съемные носитли настраиваются только для чтения.</span><span class="sxs-lookup"><span data-stu-id="d3cd4-116">The following example configures all removable media to be read-only.</span></span> <span data-ttu-id="d3cd4-117">Обратите внимание на разрешение, которое применяется на верхнем уровне политики, что означает, что все операции записи и выполнения будут `read` отсеяно.</span><span class="sxs-lookup"><span data-stu-id="d3cd4-117">Note the `read` permission that is applied at the top level of the policy, meaning that all write and execute operations will be disallowed.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="disallow-program-execution-from-removable-media"></a><span data-ttu-id="d3cd4-118">Disallow program execution from removable media</span><span class="sxs-lookup"><span data-stu-id="d3cd4-118">Disallow program execution from removable media</span></span>

<span data-ttu-id="d3cd4-119">В следующем примере показано, как можно отостановить выполнение программы из съемного носитля.</span><span class="sxs-lookup"><span data-stu-id="d3cd4-119">The following example shows how program execution from removable media can be disallowed.</span></span> <span data-ttu-id="d3cd4-120">Обратите внимание на разрешения и разрешения, применяемые на верхнем `read` `write` уровне политики.</span><span class="sxs-lookup"><span data-stu-id="d3cd4-120">Note the `read` and `write` permissions that are applied at the top level of the policy.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="restrict-all-devices-from-specific-vendors"></a><span data-ttu-id="d3cd4-121">Ограничение всех устройств у определенных поставщиков</span><span class="sxs-lookup"><span data-stu-id="d3cd4-121">Restrict all devices from specific vendors</span></span>

<span data-ttu-id="d3cd4-122">В следующем примере все устройства ограничиваются конкретными поставщиками (в данном случае определены `fff0` и `4525` ).</span><span class="sxs-lookup"><span data-stu-id="d3cd4-122">The following example restricts all devices from specific vendors (in this case identified by `fff0` and `4525`).</span></span> <span data-ttu-id="d3cd4-123">Все остальные устройства будут неограниченными, так как разрешение, определенное на верхнем уровне политики, перечисляет все возможные разрешения (чтение, написание и выполнение).</span><span class="sxs-lookup"><span data-stu-id="d3cd4-123">All other devices will be unrestricted, since the permission defined at the top level of the policy lists all possible permissions (read, write, and execute).</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string>
                <string>execute</string> 
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>fff0</key> 
                <dict> 
                    <key>permission</key> 
                    <array> 
                        <string>none</string> 
                    </array> 
                </dict> 
                <key>4525</key> 
                <dict> 
                    <key>permission</key> 
                    <array>                         
                        <string>none</string> 
                    </array> 
                </dict> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a><span data-ttu-id="d3cd4-124">Ограничение определенных устройств, определенных по ID поставщика, ID продукта и серийному номеру</span><span class="sxs-lookup"><span data-stu-id="d3cd4-124">Restrict specific devices identified by vendor ID, product ID, and serial number</span></span>

<span data-ttu-id="d3cd4-125">В следующем примере ограничивается два конкретных устройства, определенных по ID `fff0` поставщика, ID продукта `1000` и серийные номера `04ZSSMHI2O7WBVOA` и `04ZSSMHI2O7WBVOB` .</span><span class="sxs-lookup"><span data-stu-id="d3cd4-125">The following example restricts two specific devices, identified by vendor ID `fff0`, product ID `1000`, and serial numbers `04ZSSMHI2O7WBVOA` and `04ZSSMHI2O7WBVOB`.</span></span> <span data-ttu-id="d3cd4-126">На всех других уровнях политики разрешения включают все возможные значения (чтение, написание и выполнение), что означает, что все другие устройства будут неограниченными.</span><span class="sxs-lookup"><span data-stu-id="d3cd4-126">At all other levels of the policy the permissions include all possible values (read, write, and execute), meaning that all other devices will be unrestricted.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string>
                <string>execute</string>
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>fff0</key> 
                <dict> 
                    <key>permission</key> 
                    <array> 
                        <string>read</string> 
                        <string>write</string>
                        <string>execute</string> 
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>1000</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>read</string> 
                                <string>write</string>
                                <string>execute</string>
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>04ZSSMHI2O7WBVOA</key> 
                                <array> 
                                  <string>none</string> 
                                </array> 
                                <key>04ZSSMHI2O7WBVOB</key>
                                <array> 
                                  <string>none</string> 
                                </array> 
                            </dict> 
                        </dict> 
                    </dict> 
                </dict>
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

## <a name="related-topics"></a><span data-ttu-id="d3cd4-127">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d3cd4-127">Related topics</span></span>

- [<span data-ttu-id="d3cd4-128">Обзор управления устройствами для macOS</span><span class="sxs-lookup"><span data-stu-id="d3cd4-128">Overview of device control for macOS</span></span>](mac-device-control-overview.md)
