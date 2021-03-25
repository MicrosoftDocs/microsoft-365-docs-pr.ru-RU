---
title: Устранение неполадок с расширением ядра в ATP Microsoft Defender для Mac
description: Устранение неполадок, связанных с расширением ядра в MICROSOFT Defender ATP для Mac.
keywords: Microsoft, defender, atp, mac, kernel, extension
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
ms.openlocfilehash: bdd5c6309a19863339b00e846c1c2670fc4f261b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187605"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="9e54e-104">Устранение неполадок с расширением ядра в Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="9e54e-104">Troubleshoot kernel extension issues in Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9e54e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9e54e-105">**Applies to:**</span></span>

- [<span data-ttu-id="9e54e-106">Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="9e54e-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="9e54e-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9e54e-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9e54e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e54e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9e54e-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="9e54e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9e54e-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="9e54e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="9e54e-111">В этой статье данная статья содержит сведения о том, как устранить проблемы с расширением ядра, которое установлено в рамках Microsoft Defender для конечной точки для Mac.</span><span class="sxs-lookup"><span data-stu-id="9e54e-111">This article provides information on how to troubleshoot issues with the kernel extension that is installed as part of Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="9e54e-112">Начиная с macOS High Sierra (10.13), macOS требует явного утверждения всех расширений ядра, прежде чем они будут разрешены для запуска на устройстве.</span><span class="sxs-lookup"><span data-stu-id="9e54e-112">Starting with macOS High Sierra (10.13), macOS requires all kernel extensions to be explicitly approved before they are allowed to run on the device.</span></span>

<span data-ttu-id="9e54e-113">Если вы не одобрили расширение ядра во время развертывания и установки Microsoft Defender для конечной точки для Mac, приложение отображает баннер, в результате чего вы сможете включить его:</span><span class="sxs-lookup"><span data-stu-id="9e54e-113">If you did not approve the kernel extension during the deployment/installation of Microsoft Defender for Endpoint for Mac, the application displays a banner prompting you to enable it:</span></span>

   ![Снимок экрана отключенного RTP](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-32-main-app-fix)

<span data-ttu-id="9e54e-115">Вы также можете запустить ```mdatp health``` .</span><span class="sxs-lookup"><span data-stu-id="9e54e-115">You can also run ```mdatp health```.</span></span> <span data-ttu-id="9e54e-116">Он сообщает, включена ли защита в режиме реального времени, но недоступна.</span><span class="sxs-lookup"><span data-stu-id="9e54e-116">It reports if real-time protection is enabled but not available.</span></span> <span data-ttu-id="9e54e-117">Это означает, что расширение ядра не утверждено для запуска на устройстве.</span><span class="sxs-lookup"><span data-stu-id="9e54e-117">This indicates that the kernel extension is not approved to run on your device.</span></span>

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : false
real_time_protection_available              : true
...
```

<span data-ttu-id="9e54e-118">В следующих разделах указаны инструкции по решению этой проблемы в зависимости от метода, используемого для развертывания Microsoft Defender для конечной точки для Mac.</span><span class="sxs-lookup"><span data-stu-id="9e54e-118">The following sections provide guidance on how to address this issue, depending on the method that you used to deploy Microsoft Defender for Endpoint for Mac.</span></span>

## <a name="managed-deployment"></a><span data-ttu-id="9e54e-119">Управляемое развертывание</span><span class="sxs-lookup"><span data-stu-id="9e54e-119">Managed deployment</span></span>

<span data-ttu-id="9e54e-120">См. инструкции, соответствующие средству управления, который использовался для развертывания продукта:</span><span class="sxs-lookup"><span data-stu-id="9e54e-120">See the instructions corresponding to the management tool that you used to deploy the product:</span></span>

- [<span data-ttu-id="9e54e-121">Развертывание на основе JAMF</span><span class="sxs-lookup"><span data-stu-id="9e54e-121">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
- [<span data-ttu-id="9e54e-122">Развертывание на основе Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9e54e-122">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a><span data-ttu-id="9e54e-123">Ручное развертывание</span><span class="sxs-lookup"><span data-stu-id="9e54e-123">Manual deployment</span></span>

<span data-ttu-id="9e54e-124">Если с момента установки продукта прошло менее 30 минут, перейдите к system **Preferences** Security & Privacy, где необходимо разрешить системное программное обеспечение от разработчиков  >  "Корпорация  Майкрософт".</span><span class="sxs-lookup"><span data-stu-id="9e54e-124">If less than 30 minutes have passed since the product was installed, navigate to **System Preferences** > **Security & Privacy**, where you have to **Allow** system software from developers "Microsoft Corporation".</span></span>

<span data-ttu-id="9e54e-125">Если вы не видите эту подсказку, это означает, что прошло 30 или более минут, и расширение ядра еще не было утверждено для запуска на устройстве:</span><span class="sxs-lookup"><span data-stu-id="9e54e-125">If you don't see this prompt, it means that 30 or more minutes have passed, and the kernel extension still not been approved to run on your device:</span></span>

![Окно безопасности и конфиденциальности после оперативного экрана с истекшим сроком действия](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-33-securityprivacysettings-noprompt)

<span data-ttu-id="9e54e-127">В этом случае необходимо выполнить следующие действия, чтобы снова вызвать поток утверждения.</span><span class="sxs-lookup"><span data-stu-id="9e54e-127">In this case, you need to perform the following steps to trigger the approval flow again.</span></span>

1. <span data-ttu-id="9e54e-128">В терминале попытайтесь установить драйвер.</span><span class="sxs-lookup"><span data-stu-id="9e54e-128">In Terminal, attempt to install the driver.</span></span> <span data-ttu-id="9e54e-129">Следующая операция будет неудачной, так как расширение ядра не было утверждено для запуска на устройстве.</span><span class="sxs-lookup"><span data-stu-id="9e54e-129">The following operation will fail, because the kernel extension was not approved to run on the device.</span></span> <span data-ttu-id="9e54e-130">Тем не менее, он будет запускать поток утверждения снова.</span><span class="sxs-lookup"><span data-stu-id="9e54e-130">However, it will trigger the approval flow again.</span></span>

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```
    
    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. <span data-ttu-id="9e54e-131">Open **System Preferences**  >  **Security & конфиденциальности** из меню.</span><span class="sxs-lookup"><span data-stu-id="9e54e-131">Open **System Preferences** > **Security & Privacy** from the menu.</span></span> <span data-ttu-id="9e54e-132">(Сначала закрой его, если он открыт.)</span><span class="sxs-lookup"><span data-stu-id="9e54e-132">(Close it first, if it's opened.)</span></span>

3. <span data-ttu-id="9e54e-133">**Разрешить** системное программное обеспечение от разработчиков "Корпорация Майкрософт"</span><span class="sxs-lookup"><span data-stu-id="9e54e-133">**Allow** system software from developers "Microsoft Corporation"</span></span>

4. <span data-ttu-id="9e54e-134">В терминале установите драйвер снова.</span><span class="sxs-lookup"><span data-stu-id="9e54e-134">In Terminal, install the driver again.</span></span> <span data-ttu-id="9e54e-135">На этот раз операция будет успешной:</span><span class="sxs-lookup"><span data-stu-id="9e54e-135">This time the operation will succeed:</span></span>

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    <span data-ttu-id="9e54e-136">Баннер должен исчезнуть из приложения Defender и теперь должен сообщить, что защита в режиме реального времени включена и ```mdatp health``` доступна:</span><span class="sxs-lookup"><span data-stu-id="9e54e-136">The banner should disappear from the Defender application, and ```mdatp health``` should now report that real-time protection is both enabled and available:</span></span>

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
