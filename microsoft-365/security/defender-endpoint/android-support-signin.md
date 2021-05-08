---
title: Устранение неполадок в Microsoft Defender для конечной точки на Android
description: Устранение неполадок для Microsoft Defender для конечной точки на Android
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mde, android, cloud, connectivity, communication
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 18afd4aa160ec345839d23719d1b3fcce21654ec
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246360"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="6acba-104">Устранение неполадок в Microsoft Defender для конечной точки на Android</span><span class="sxs-lookup"><span data-stu-id="6acba-104">Troubleshooting issues on Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6acba-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6acba-105">**Applies to:**</span></span>
- [<span data-ttu-id="6acba-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="6acba-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6acba-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6acba-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6acba-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="6acba-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6acba-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="6acba-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="6acba-110">При входе на устройство после установки приложения могут возникнуть проблемы с входом.</span><span class="sxs-lookup"><span data-stu-id="6acba-110">When onboarding a device, you might see sign in issues after the app is installed.</span></span>

<span data-ttu-id="6acba-111">Во время входной платы после установки приложения на вашем устройстве могут возникнуть проблемы с входом.</span><span class="sxs-lookup"><span data-stu-id="6acba-111">During onboarding, you might encounter sign in issues after the app is installed on your device.</span></span>

<span data-ttu-id="6acba-112">В этой статье данная статья предоставляет решения, которые помогут решить проблемы с входом.</span><span class="sxs-lookup"><span data-stu-id="6acba-112">This article provides solutions to help address the sign-on issues.</span></span>  

## <a name="sign-in-failed---unexpected-error"></a><span data-ttu-id="6acba-113">Вход не удалось - неожиданная ошибка</span><span class="sxs-lookup"><span data-stu-id="6acba-113">Sign in failed - unexpected error</span></span>
<span data-ttu-id="6acba-114">**Вход не удалось:** *непредвиденное ошибка, попробуйте позже*</span><span class="sxs-lookup"><span data-stu-id="6acba-114">**Sign in failed:** *Unexpected error, try later*</span></span>

![Изображение знака в ошибке с ошибкой Непредвиденное ошибка](images/f9c3bad127d636c1f150d79814f35d4c.png)

<span data-ttu-id="6acba-116">**Сообщение:**</span><span class="sxs-lookup"><span data-stu-id="6acba-116">**Message:**</span></span>

<span data-ttu-id="6acba-117">Неожиданная ошибка, попробуйте позже</span><span class="sxs-lookup"><span data-stu-id="6acba-117">Unexpected error, try later</span></span>

<span data-ttu-id="6acba-118">**Причина:**</span><span class="sxs-lookup"><span data-stu-id="6acba-118">**Cause:**</span></span>

<span data-ttu-id="6acba-119">На вашем устройстве установлена более старая версия приложения Microsoft Authenticator "Microsoft Authenticator".</span><span class="sxs-lookup"><span data-stu-id="6acba-119">You have an older version of "Microsoft Authenticator" app installed on your device.</span></span>

<span data-ttu-id="6acba-120">**Решение:**</span><span class="sxs-lookup"><span data-stu-id="6acba-120">**Solution:**</span></span>

<span data-ttu-id="6acba-121">Установите последнюю версию и [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) в Магазине Google Play и попробуйте еще раз</span><span class="sxs-lookup"><span data-stu-id="6acba-121">Install latest version and of [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) from Google Play Store and try again</span></span>

## <a name="sign-in-failed---invalid-license"></a><span data-ttu-id="6acba-122">Вход в сбой - недействительные лицензии</span><span class="sxs-lookup"><span data-stu-id="6acba-122">Sign in failed - invalid license</span></span>

<span data-ttu-id="6acba-123">**Вход сбой:** *недействительные лицензии, обратитесь к администратору*</span><span class="sxs-lookup"><span data-stu-id="6acba-123">**Sign in failed:** *Invalid license, please contact administrator*</span></span>

![Изображение знака в сбой, пожалуйста, свяжитесь с администратором](images/920e433f440fa1d3d298e6a2a43d4811.png)

<span data-ttu-id="6acba-125">**Сообщение.** *Недействительные лицензии, обратитесь к администратору*</span><span class="sxs-lookup"><span data-stu-id="6acba-125">**Message:** *Invalid license, please contact administrator*</span></span>

<span data-ttu-id="6acba-126">**Причина:**</span><span class="sxs-lookup"><span data-stu-id="6acba-126">**Cause:**</span></span>

<span data-ttu-id="6acba-127">У вас нет Microsoft 365 лицензии или у организации нет лицензии на Microsoft 365 корпоративный подписки.</span><span class="sxs-lookup"><span data-stu-id="6acba-127">You do not have Microsoft 365 license assigned, or your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="6acba-128">**Решение:**</span><span class="sxs-lookup"><span data-stu-id="6acba-128">**Solution:**</span></span>

<span data-ttu-id="6acba-129">Обратитесь к системному администратору.</span><span class="sxs-lookup"><span data-stu-id="6acba-129">Contact your administrator for help.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="6acba-130">Сообщить о небезопасном сайте</span><span class="sxs-lookup"><span data-stu-id="6acba-130">Report unsafe site</span></span>

<span data-ttu-id="6acba-131">Фишинговые веб-сайты выдают себя за надежные веб-сайты с целью получения личной или финансовой информации.</span><span class="sxs-lookup"><span data-stu-id="6acba-131">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="6acba-132">Если вы хотите сообщить о веб-сайте, который может быть фишинг-сайтом, посетите страницу Provide feedback about [network](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) protection page.</span><span class="sxs-lookup"><span data-stu-id="6acba-132">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a><span data-ttu-id="6acba-133">Фишинговые страницы не заблокированы на некоторых устройствах OEM</span><span class="sxs-lookup"><span data-stu-id="6acba-133">Phishing pages aren't blocked on some OEM devices</span></span>

<span data-ttu-id="6acba-134">**Применяется к:** Только конкретные OEMs</span><span class="sxs-lookup"><span data-stu-id="6acba-134">**Applies to:** Specific OEMs only</span></span>

-   <span data-ttu-id="6acba-135">**Xiaomi**</span><span class="sxs-lookup"><span data-stu-id="6acba-135">**Xiaomi**</span></span>

<span data-ttu-id="6acba-136">Фишинговые и вредоносные веб-угрозы, обнаруженные Defender для конечной точки для Android, не блокируются на некоторых устройствах Xiaomi.</span><span class="sxs-lookup"><span data-stu-id="6acba-136">Phishing and harmful web threats that are detected by Defender for Endpoint for Android are not blocked on some Xiaomi devices.</span></span> <span data-ttu-id="6acba-137">Следующие функции не работают на этих устройствах.</span><span class="sxs-lookup"><span data-stu-id="6acba-137">The following functionality doesn't work on these devices.</span></span>

![Изображение сайта, сообщаемого небезопасно](images/0c04975c74746a5cdb085e1d9386e713.png)


<span data-ttu-id="6acba-139">**Причина:**</span><span class="sxs-lookup"><span data-stu-id="6acba-139">**Cause:**</span></span>

<span data-ttu-id="6acba-140">Устройства Xiaomi включают новую модель разрешений.</span><span class="sxs-lookup"><span data-stu-id="6acba-140">Xiaomi devices include a new permission model.</span></span> <span data-ttu-id="6acba-141">Это не позволяет Защитнику для конечной точки для Android отобразить всплывающее окно во время его работы в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="6acba-141">This prevents Defender for Endpoint for Android from displaying pop-up windows while it runs in the background.</span></span>

<span data-ttu-id="6acba-142">Разрешение устройств Xiaomi: "Отображение всплывающих окон во время работы в фоновом режиме".</span><span class="sxs-lookup"><span data-stu-id="6acba-142">Xiaomi devices permission: "Display pop-up windows while running in the background."</span></span>

![Изображение всплывающее параметра](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

<span data-ttu-id="6acba-144">**Решение:**</span><span class="sxs-lookup"><span data-stu-id="6acba-144">**Solution:**</span></span>

<span data-ttu-id="6acba-145">Включить необходимое разрешение на устройствах Xiaomi.</span><span class="sxs-lookup"><span data-stu-id="6acba-145">Enable the required permission on Xiaomi devices.</span></span>

- <span data-ttu-id="6acba-146">Отображение всплывающих окон во время работы в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="6acba-146">Display pop-up windows while running in the background.</span></span>
