---
title: Устранение неполадок в Microsoft Defender для конечной точки на Android
description: Устранение неполадок для Microsoft Defender для конечной точки на Android
keywords: Microsoft, defender, atp, mde, android, cloud, connectivity, communication
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
ms.openlocfilehash: 1a19582073565a958aab444541381f5772b6f4f1
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687607"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="76798-104">Устранение неполадок в Microsoft Defender для конечной точки на Android</span><span class="sxs-lookup"><span data-stu-id="76798-104">Troubleshooting issues on Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="76798-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="76798-105">**Applies to:**</span></span>
- [<span data-ttu-id="76798-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="76798-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="76798-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76798-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="76798-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="76798-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="76798-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="76798-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="76798-110">При входе на устройство после установки приложения могут возникнуть проблемы с входом.</span><span class="sxs-lookup"><span data-stu-id="76798-110">When onboarding a device, you might see sign in issues after the app is installed.</span></span>

<span data-ttu-id="76798-111">Во время входной платы после установки приложения на вашем устройстве могут возникнуть проблемы с входом.</span><span class="sxs-lookup"><span data-stu-id="76798-111">During onboarding, you might encounter sign in issues after the app is installed on your device.</span></span>

<span data-ttu-id="76798-112">В этой статье данная статья предоставляет решения, которые помогут решить проблемы с входом.</span><span class="sxs-lookup"><span data-stu-id="76798-112">This article provides solutions to help address the sign-on issues.</span></span>  

## <a name="sign-in-failed---unexpected-error"></a><span data-ttu-id="76798-113">Вход не удалось - неожиданная ошибка</span><span class="sxs-lookup"><span data-stu-id="76798-113">Sign in failed - unexpected error</span></span>
<span data-ttu-id="76798-114">**Вход не удалось:** *непредвиденное ошибка, попробуйте позже*</span><span class="sxs-lookup"><span data-stu-id="76798-114">**Sign in failed:** *Unexpected error, try later*</span></span>

![Изображение знака в ошибке с ошибкой Непредвиденное ошибка](images/f9c3bad127d636c1f150d79814f35d4c.png)

<span data-ttu-id="76798-116">**Сообщение:**</span><span class="sxs-lookup"><span data-stu-id="76798-116">**Message:**</span></span>

<span data-ttu-id="76798-117">Неожиданная ошибка, попробуйте позже</span><span class="sxs-lookup"><span data-stu-id="76798-117">Unexpected error, try later</span></span>

<span data-ttu-id="76798-118">**Причина:**</span><span class="sxs-lookup"><span data-stu-id="76798-118">**Cause:**</span></span>

<span data-ttu-id="76798-119">На вашем устройстве установлена более старая версия приложения "Microsoft Authenticator".</span><span class="sxs-lookup"><span data-stu-id="76798-119">You have an older version of "Microsoft Authenticator" app installed on your device.</span></span>

<span data-ttu-id="76798-120">**Решение:**</span><span class="sxs-lookup"><span data-stu-id="76798-120">**Solution:**</span></span>

<span data-ttu-id="76798-121">Установите последнюю версию и [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) из магазина Google Play и попробуйте еще раз</span><span class="sxs-lookup"><span data-stu-id="76798-121">Install latest version and of [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) from Google Play Store and try again</span></span>

## <a name="sign-in-failed---invalid-license"></a><span data-ttu-id="76798-122">Вход в сбой - недействительные лицензии</span><span class="sxs-lookup"><span data-stu-id="76798-122">Sign in failed - invalid license</span></span>

<span data-ttu-id="76798-123">**Вход сбой:** *недействительные лицензии, обратитесь к администратору*</span><span class="sxs-lookup"><span data-stu-id="76798-123">**Sign in failed:** *Invalid license, please contact administrator*</span></span>

![Изображение знака в сбой, пожалуйста, свяжитесь с администратором](images/920e433f440fa1d3d298e6a2a43d4811.png)

<span data-ttu-id="76798-125">**Сообщение.** *Недействительные лицензии, обратитесь к администратору*</span><span class="sxs-lookup"><span data-stu-id="76798-125">**Message:** *Invalid license, please contact administrator*</span></span>

<span data-ttu-id="76798-126">**Причина:**</span><span class="sxs-lookup"><span data-stu-id="76798-126">**Cause:**</span></span>

<span data-ttu-id="76798-127">Вам не назначена лицензия Microsoft 365 или у организации нет лицензии на подписку microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="76798-127">You do not have Microsoft 365 license assigned, or your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="76798-128">**Решение:**</span><span class="sxs-lookup"><span data-stu-id="76798-128">**Solution:**</span></span>

<span data-ttu-id="76798-129">Обратитесь к системному администратору.</span><span class="sxs-lookup"><span data-stu-id="76798-129">Contact your administrator for help.</span></span>

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a><span data-ttu-id="76798-130">Фишинговые страницы не заблокированы на некоторых устройствах OEM</span><span class="sxs-lookup"><span data-stu-id="76798-130">Phishing pages aren't blocked on some OEM devices</span></span>

<span data-ttu-id="76798-131">**Применяется к:** Только конкретные OEMs</span><span class="sxs-lookup"><span data-stu-id="76798-131">**Applies to:** Specific OEMs only</span></span>

-   <span data-ttu-id="76798-132">**Xiaomi**</span><span class="sxs-lookup"><span data-stu-id="76798-132">**Xiaomi**</span></span>

<span data-ttu-id="76798-133">Фишинговые и вредоносные веб-угрозы, обнаруженные Defender для конечной точки для Android, не блокируются на некоторых устройствах Xiaomi.</span><span class="sxs-lookup"><span data-stu-id="76798-133">Phishing and harmful web threats that are detected by Defender for Endpoint for Android are not blocked on some Xiaomi devices.</span></span> <span data-ttu-id="76798-134">Следующие функции не работают на этих устройствах.</span><span class="sxs-lookup"><span data-stu-id="76798-134">The following functionality doesn't work on these devices.</span></span>

![Изображение сайта, сообщаемого небезопасно](images/0c04975c74746a5cdb085e1d9386e713.png)


<span data-ttu-id="76798-136">**Причина:**</span><span class="sxs-lookup"><span data-stu-id="76798-136">**Cause:**</span></span>

<span data-ttu-id="76798-137">Устройства Xiaomi включают новую модель разрешений.</span><span class="sxs-lookup"><span data-stu-id="76798-137">Xiaomi devices include a new permission model.</span></span> <span data-ttu-id="76798-138">Это не позволяет Защитнику для конечной точки для Android отобразить всплывающее окно во время его работы в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="76798-138">This prevents Defender for Endpoint for Android from displaying pop-up windows while it runs in the background.</span></span>

<span data-ttu-id="76798-139">Разрешение устройств Xiaomi: "Отображение всплывающих окон во время работы в фоновом режиме".</span><span class="sxs-lookup"><span data-stu-id="76798-139">Xiaomi devices permission: "Display pop-up windows while running in the background."</span></span>

![Изображение всплывающее параметра](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

<span data-ttu-id="76798-141">**Решение:**</span><span class="sxs-lookup"><span data-stu-id="76798-141">**Solution:**</span></span>

<span data-ttu-id="76798-142">Включить необходимое разрешение на устройствах Xiaomi.</span><span class="sxs-lookup"><span data-stu-id="76798-142">Enable the required permission on Xiaomi devices.</span></span>

- <span data-ttu-id="76798-143">Отображение всплывающих окон во время работы в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="76798-143">Display pop-up windows while running in the background.</span></span>
