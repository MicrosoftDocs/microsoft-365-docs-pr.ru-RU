---
title: Устранение неполадок с расширением ядра в Microsoft Defender для конечной точки на macOS
description: Устранение неполадок, связанных с расширением ядра в Microsoft Defender для конечной точки на macOS.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mac, kernel, extension
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
ms.openlocfilehash: 9dc3ee17d79972b5d36c5fff58fbe4cc486027bd
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934277"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="d1de4-104">Устранение неполадок с расширением ядра в Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="d1de4-104">Troubleshoot kernel extension issues in Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d1de4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d1de4-105">**Applies to:**</span></span>

- [<span data-ttu-id="d1de4-106">Microsoft Defender для конечной точки в macOS</span><span class="sxs-lookup"><span data-stu-id="d1de4-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="d1de4-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d1de4-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d1de4-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d1de4-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d1de4-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="d1de4-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d1de4-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="d1de4-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="d1de4-111">В этой статье приводится информация о том, как устранить проблемы с расширением ядра, которое установлено в рамках Microsoft Defender для конечной точки на macOS.</span><span class="sxs-lookup"><span data-stu-id="d1de4-111">This article provides information on how to troubleshoot issues with the kernel extension that is installed as part of Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="d1de4-112">Начиная с macOS High Sierra (10.13), macOS требует явного утверждения всех расширений ядра до того, как они будут разрешены для запуска на устройстве.</span><span class="sxs-lookup"><span data-stu-id="d1de4-112">Starting with macOS High Sierra (10.13), macOS requires all kernel extensions to be explicitly approved before they're allowed to run on the device.</span></span>

<span data-ttu-id="d1de4-113">Если вы не одобрили расширение ядра во время развертывания и установки Microsoft Defender для конечной точки на macOS, приложение отображает баннер, который будет предложено включить его:</span><span class="sxs-lookup"><span data-stu-id="d1de4-113">If you didn't approve the kernel extension during the deployment/installation of Microsoft Defender for Endpoint on macOS, the application displays a banner prompting you to enable it:</span></span>

   ![Снимок экрана отключенного RTP](images/mdatp-32-main-app-fix.png)

<span data-ttu-id="d1de4-115">Вы также можете запустить ```mdatp health``` .</span><span class="sxs-lookup"><span data-stu-id="d1de4-115">You can also run ```mdatp health```.</span></span> <span data-ttu-id="d1de4-116">Он сообщает, включена ли защита в режиме реального времени, но недоступна.</span><span class="sxs-lookup"><span data-stu-id="d1de4-116">It reports if real-time protection is enabled but not available.</span></span> <span data-ttu-id="d1de4-117">Это означает, что расширение ядра не утверждено для запуска на устройстве.</span><span class="sxs-lookup"><span data-stu-id="d1de4-117">This indicates that the kernel extension isn't approved to run on your device.</span></span>

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : false
real_time_protection_available              : true
...
```

<span data-ttu-id="d1de4-118">В следующих разделах указаны инструкции по решению этой проблемы в зависимости от метода, используемого для развертывания Microsoft Defender для конечной точки на macOS.</span><span class="sxs-lookup"><span data-stu-id="d1de4-118">The following sections provide guidance on how to address this issue, depending on the method that you used to deploy Microsoft Defender for Endpoint on macOS.</span></span>

## <a name="managed-deployment"></a><span data-ttu-id="d1de4-119">Управляемое развертывание</span><span class="sxs-lookup"><span data-stu-id="d1de4-119">Managed deployment</span></span>

<span data-ttu-id="d1de4-120">См. инструкции, соответствующие средству управления, который использовался для развертывания продукта:</span><span class="sxs-lookup"><span data-stu-id="d1de4-120">See the instructions corresponding to the management tool that you used to deploy the product:</span></span>

- [<span data-ttu-id="d1de4-121">Развертывание на основе JAMF</span><span class="sxs-lookup"><span data-stu-id="d1de4-121">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
- [<span data-ttu-id="d1de4-122">Развертывание на основе Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d1de4-122">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a><span data-ttu-id="d1de4-123">Ручное развертывание</span><span class="sxs-lookup"><span data-stu-id="d1de4-123">Manual deployment</span></span>

<span data-ttu-id="d1de4-124">Если с момента установки продукта прошло менее 30 минут, перейдите к system **Preferences** Security & Privacy, где необходимо разрешить системное программное обеспечение от разработчиков  >  "Корпорация  Майкрософт".</span><span class="sxs-lookup"><span data-stu-id="d1de4-124">If less than 30 minutes have passed since the product was installed, navigate to **System Preferences** > **Security & Privacy**, where you have to **Allow** system software from developers "Microsoft Corporation".</span></span>

<span data-ttu-id="d1de4-125">Если вы не видите эту подсказку, это означает, что прошло 30 или более минут, и расширение ядра еще не было утверждено для запуска на устройстве:</span><span class="sxs-lookup"><span data-stu-id="d1de4-125">If you don't see this prompt, it means that 30 or more minutes have passed, and the kernel extension still not been approved to run on your device:</span></span>

![Окно безопасности и конфиденциальности после оперативного экрана с истекшим сроком действия](images/mdatp-33-securityprivacysettings-noprompt.png)

<span data-ttu-id="d1de4-127">В этом случае необходимо выполнить следующие действия, чтобы снова вызвать поток утверждения.</span><span class="sxs-lookup"><span data-stu-id="d1de4-127">In this case, you need to perform the following steps to trigger the approval flow again.</span></span>

1. <span data-ttu-id="d1de4-128">В терминале попытайтесь установить драйвер.</span><span class="sxs-lookup"><span data-stu-id="d1de4-128">In Terminal, attempt to install the driver.</span></span> <span data-ttu-id="d1de4-129">Следующая операция будет неудачной, так как расширение ядра не было утверждено для запуска на устройстве.</span><span class="sxs-lookup"><span data-stu-id="d1de4-129">The following operation will fail, because the kernel extension wasn't approved to run on the device.</span></span> <span data-ttu-id="d1de4-130">Тем не менее, он будет запускать поток утверждения снова.</span><span class="sxs-lookup"><span data-stu-id="d1de4-130">However, it will trigger the approval flow again.</span></span>

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```
    
    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. <span data-ttu-id="d1de4-131">Open **System Preferences**  >  **Security & конфиденциальности** из меню.</span><span class="sxs-lookup"><span data-stu-id="d1de4-131">Open **System Preferences** > **Security & Privacy** from the menu.</span></span> <span data-ttu-id="d1de4-132">(Сначала закрой его, если он открыт.)</span><span class="sxs-lookup"><span data-stu-id="d1de4-132">(Close it first, if it's opened.)</span></span>

3. <span data-ttu-id="d1de4-133">**Разрешить** системное программное обеспечение от разработчиков "Корпорация Майкрософт"</span><span class="sxs-lookup"><span data-stu-id="d1de4-133">**Allow** system software from developers "Microsoft Corporation"</span></span>

4. <span data-ttu-id="d1de4-134">В терминале установите драйвер снова.</span><span class="sxs-lookup"><span data-stu-id="d1de4-134">In Terminal, install the driver again.</span></span> <span data-ttu-id="d1de4-135">На этот раз операция будет успешной:</span><span class="sxs-lookup"><span data-stu-id="d1de4-135">This time the operation will succeed:</span></span>

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    <span data-ttu-id="d1de4-136">Баннер должен исчезнуть из приложения Defender и теперь должен сообщить, что защита в режиме реального времени включена и ```mdatp health``` доступна:</span><span class="sxs-lookup"><span data-stu-id="d1de4-136">The banner should disappear from the Defender application, and ```mdatp health``` should now report that real-time protection is both enabled and available:</span></span>

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
