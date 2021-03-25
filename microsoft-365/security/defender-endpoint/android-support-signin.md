---
title: Устранение неполадок в ATP Защитника Microsoft для Android
description: Устранение неполадок для ATP Защитника Microsoft для Android
keywords: Microsoft, defender, atp, android, cloud, connectivity, communication
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 444541c85f8f4416288dcebf4bbee2c65a33d3d2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164873"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="b3e11-104">Устранение неполадок в Microsoft Defender для конечной точки для Android</span><span class="sxs-lookup"><span data-stu-id="b3e11-104">Troubleshooting issues on Microsoft Defender for Endpoint for Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b3e11-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b3e11-105">**Applies to:**</span></span>
- [<span data-ttu-id="b3e11-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b3e11-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b3e11-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3e11-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b3e11-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b3e11-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b3e11-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b3e11-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="b3e11-110">При входе на устройство после установки приложения могут возникнуть проблемы с входом.</span><span class="sxs-lookup"><span data-stu-id="b3e11-110">When onboarding a device, you might see sign in issues after the app is installed.</span></span>

<span data-ttu-id="b3e11-111">Во время входной платы после установки приложения на вашем устройстве могут возникнуть проблемы с входом.</span><span class="sxs-lookup"><span data-stu-id="b3e11-111">During onboarding, you might encounter sign in issues after the app is installed on your device.</span></span>

<span data-ttu-id="b3e11-112">В этой статье данная статья предоставляет решения, которые помогут решить проблемы с входом.</span><span class="sxs-lookup"><span data-stu-id="b3e11-112">This article provides solutions to help address the sign-on issues.</span></span>  

## <a name="sign-in-failed---unexpected-error"></a><span data-ttu-id="b3e11-113">Вход не удалось - неожиданная ошибка</span><span class="sxs-lookup"><span data-stu-id="b3e11-113">Sign in failed - unexpected error</span></span>
<span data-ttu-id="b3e11-114">**Вход не удалось:** *непредвиденное ошибка, попробуйте позже*</span><span class="sxs-lookup"><span data-stu-id="b3e11-114">**Sign in failed:** *Unexpected error, try later*</span></span>

![Изображение знака в ошибке с ошибкой Непредвиденное ошибка](images/f9c3bad127d636c1f150d79814f35d4c.png)

<span data-ttu-id="b3e11-116">**Сообщение:**</span><span class="sxs-lookup"><span data-stu-id="b3e11-116">**Message:**</span></span>

<span data-ttu-id="b3e11-117">Неожиданная ошибка, попробуйте позже</span><span class="sxs-lookup"><span data-stu-id="b3e11-117">Unexpected error, try later</span></span>

<span data-ttu-id="b3e11-118">**Причина:**</span><span class="sxs-lookup"><span data-stu-id="b3e11-118">**Cause:**</span></span>

<span data-ttu-id="b3e11-119">На вашем устройстве установлена более старая версия приложения "Microsoft Authenticator".</span><span class="sxs-lookup"><span data-stu-id="b3e11-119">You have an older version of "Microsoft Authenticator" app installed on your device.</span></span>

<span data-ttu-id="b3e11-120">**Решение:**</span><span class="sxs-lookup"><span data-stu-id="b3e11-120">**Solution:**</span></span>

<span data-ttu-id="b3e11-121">Установите последнюю версию и [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) из магазина Google Play и попробуйте еще раз</span><span class="sxs-lookup"><span data-stu-id="b3e11-121">Install latest version and of [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) from Google Play Store and try again</span></span>

## <a name="sign-in-failed---invalid-license"></a><span data-ttu-id="b3e11-122">Вход в сбой - недействительные лицензии</span><span class="sxs-lookup"><span data-stu-id="b3e11-122">Sign in failed - invalid license</span></span>

<span data-ttu-id="b3e11-123">**Вход сбой:** *недействительные лицензии, обратитесь к администратору*</span><span class="sxs-lookup"><span data-stu-id="b3e11-123">**Sign in failed:** *Invalid license, please contact administrator*</span></span>

![Изображение знака в сбой, пожалуйста, свяжитесь с администратором](images/920e433f440fa1d3d298e6a2a43d4811.png)

<span data-ttu-id="b3e11-125">**Сообщение.** *Недействительные лицензии, обратитесь к администратору*</span><span class="sxs-lookup"><span data-stu-id="b3e11-125">**Message:** *Invalid license, please contact administrator*</span></span>

<span data-ttu-id="b3e11-126">**Причина:**</span><span class="sxs-lookup"><span data-stu-id="b3e11-126">**Cause:**</span></span>

<span data-ttu-id="b3e11-127">Вам не назначена лицензия Microsoft 365 или у организации нет лицензии на подписку microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b3e11-127">You do not have Microsoft 365 license assigned, or your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="b3e11-128">**Решение:**</span><span class="sxs-lookup"><span data-stu-id="b3e11-128">**Solution:**</span></span>

<span data-ttu-id="b3e11-129">Обратитесь к системному администратору.</span><span class="sxs-lookup"><span data-stu-id="b3e11-129">Contact your administrator for help.</span></span>

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a><span data-ttu-id="b3e11-130">Фишинговые страницы не заблокированы на некоторых устройствах OEM</span><span class="sxs-lookup"><span data-stu-id="b3e11-130">Phishing pages aren't blocked on some OEM devices</span></span>

<span data-ttu-id="b3e11-131">**Применяется к:** Только конкретные OEMs</span><span class="sxs-lookup"><span data-stu-id="b3e11-131">**Applies to:** Specific OEMs only</span></span>

-   <span data-ttu-id="b3e11-132">**Xiaomi**</span><span class="sxs-lookup"><span data-stu-id="b3e11-132">**Xiaomi**</span></span>

<span data-ttu-id="b3e11-133">Фишинговые и вредоносные веб-угрозы, обнаруженные Defender для конечной точки для Android, не блокируются на некоторых устройствах Xiaomi.</span><span class="sxs-lookup"><span data-stu-id="b3e11-133">Phishing and harmful web threats that are detected by Defender for Endpoint for Android are not blocked on some Xiaomi devices.</span></span> <span data-ttu-id="b3e11-134">Следующие функции не работают на этих устройствах.</span><span class="sxs-lookup"><span data-stu-id="b3e11-134">The following functionality doesn't work on these devices.</span></span>

![Изображение сайта, сообщаемого небезопасно](images/0c04975c74746a5cdb085e1d9386e713.png)


<span data-ttu-id="b3e11-136">**Причина:**</span><span class="sxs-lookup"><span data-stu-id="b3e11-136">**Cause:**</span></span>

<span data-ttu-id="b3e11-137">Устройства Xiaomi включают новую модель разрешений.</span><span class="sxs-lookup"><span data-stu-id="b3e11-137">Xiaomi devices include a new permission model.</span></span> <span data-ttu-id="b3e11-138">Это не позволяет Защитнику для конечной точки для Android отобразить всплывающее окно во время его работы в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="b3e11-138">This prevents Defender for Endpoint for Android from displaying pop-up windows while it runs in the background.</span></span>

<span data-ttu-id="b3e11-139">Разрешение устройств Xiaomi: "Отображение всплывающих окон во время работы в фоновом режиме".</span><span class="sxs-lookup"><span data-stu-id="b3e11-139">Xiaomi devices permission: "Display pop-up windows while running in the background."</span></span>

![Изображение всплывающее параметра](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

<span data-ttu-id="b3e11-141">**Решение:**</span><span class="sxs-lookup"><span data-stu-id="b3e11-141">**Solution:**</span></span>

<span data-ttu-id="b3e11-142">Включить необходимое разрешение на устройствах Xiaomi.</span><span class="sxs-lookup"><span data-stu-id="b3e11-142">Enable the required permission on Xiaomi devices.</span></span>

- <span data-ttu-id="b3e11-143">Отображение всплывающих окон во время работы в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="b3e11-143">Display pop-up windows while running in the background.</span></span>
