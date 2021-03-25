---
title: ATP защитника Майкрософт для Android
ms.reviewer: ''
description: Описание установки и использования ATP Microsoft Defender для Android
keywords: Microsoft, defender, atp, android, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: e2432dc4aa2c67fadc9112512a080f24c0064df4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187617"
---
# <a name="microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="73120-104">Microsoft Defender для конечной точки для Android</span><span class="sxs-lookup"><span data-stu-id="73120-104">Microsoft Defender for Endpoint for Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="73120-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="73120-105">**Applies to:**</span></span>
- [<span data-ttu-id="73120-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="73120-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="73120-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73120-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="73120-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="73120-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="73120-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="73120-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="73120-110">В этом разделе описывается установка, настройка, обновление и использование Defender для конечной точки для Android.</span><span class="sxs-lookup"><span data-stu-id="73120-110">This topic describes how to install, configure, update, and use Defender for Endpoint for Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="73120-111">Запуск других сторонних продуктов защиты конечных точек наряду с Defender for Endpoint для Android может привести к проблемам с производительностью и непредсказуемым системным ошибкам.</span><span class="sxs-lookup"><span data-stu-id="73120-111">Running other third-party endpoint protection products alongside Defender for Endpoint for Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="73120-112">Установка Microsoft Defender для конечной точки для Android</span><span class="sxs-lookup"><span data-stu-id="73120-112">How to install Microsoft Defender for Endpoint for Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="73120-113">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="73120-113">Prerequisites</span></span>

-   <span data-ttu-id="73120-114">**Для конечных пользователей**</span><span class="sxs-lookup"><span data-stu-id="73120-114">**For end users**</span></span>

    -   <span data-ttu-id="73120-115">Лицензия Microsoft Defender для конечной точки, назначенная конечному пользователю приложения.</span><span class="sxs-lookup"><span data-stu-id="73120-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="73120-116">См. [требования к microsoft Defender для лицензирования конечных точек](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="73120-116">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="73120-117">Приложение Портала компании Intune можно скачать из [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) и доступно на устройстве Android.</span><span class="sxs-lookup"><span data-stu-id="73120-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="73120-118">Кроме того, устройства(ы) могут быть зарегистрированы через приложение Портал компании Intune для применения политик соответствия требованиям устройств Intune. [](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal)</span><span class="sxs-lookup"><span data-stu-id="73120-118">Additionally, device(s) can be [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="73120-119">Это требует, чтобы конечному пользователю была назначена лицензия Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="73120-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="73120-120">Дополнительные сведения о назначении лицензий см. в дополнительных сведениях о назначении [лицензий пользователям.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="73120-120">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="73120-121">**Для администраторов**</span><span class="sxs-lookup"><span data-stu-id="73120-121">**For Administrators**</span></span>

    -   <span data-ttu-id="73120-122">Доступ к порталу Центра безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="73120-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="73120-123">Microsoft Intune является единственным поддерживаемым решением управления мобильными устройствами (MDM) для развертывания Microsoft Defender для конечной точки для Android.</span><span class="sxs-lookup"><span data-stu-id="73120-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint for Android.</span></span> <span data-ttu-id="73120-124">В настоящее время поддерживаются только зарегистрированные устройства для принудительного выполнения политик соответствия требованиям Defender для конечной точки для Android, связанных с устройствами в Intune.</span><span class="sxs-lookup"><span data-stu-id="73120-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint for Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="73120-125">Доступ [к центру администрирования Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)чтобы развернуть приложение для зарегистрированных групп пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="73120-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

### <a name="system-requirements"></a><span data-ttu-id="73120-126">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="73120-126">System Requirements</span></span>

-   <span data-ttu-id="73120-127">Android-устройства под управлением Android 6.0 и выше.</span><span class="sxs-lookup"><span data-stu-id="73120-127">Android devices running Android 6.0 and above.</span></span>
-   <span data-ttu-id="73120-128">Приложение портала компании Intune скачивается из [Google Play и](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) устанавливается.</span><span class="sxs-lookup"><span data-stu-id="73120-128">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="73120-129">Регистрация устройств необходима для принудительного выполнения политик соответствия требованиям к устройствам Intune.</span><span class="sxs-lookup"><span data-stu-id="73120-129">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="73120-130">Инструкции по установке</span><span class="sxs-lookup"><span data-stu-id="73120-130">Installation instructions</span></span>

<span data-ttu-id="73120-131">Microsoft Defender для конечной точки для Android поддерживает установку на обоих режимах зарегистрированных устройств — устаревших режимах администратора устройств и Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="73120-131">Microsoft Defender for Endpoint for Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="73120-132">**В настоящее время в Android Enterprise поддерживаются собственные устройства с профилем работы и полностью управляемыми пользовательскими устройствами. Поддержка других режимов Android Enterprise будет объявлена при готовности.**</span><span class="sxs-lookup"><span data-stu-id="73120-132">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrolments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="73120-133">Развертывание Microsoft Defender для конечной точки для Android осуществляется с помощью Microsoft Intune (MDM).</span><span class="sxs-lookup"><span data-stu-id="73120-133">Deployment of Microsoft Defender for Endpoint for Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="73120-134">Дополнительные сведения см. в [ссылке Развертывание Microsoft Defender для конечной точки для Android с помощью Microsoft Intune.](android-intune.md)</span><span class="sxs-lookup"><span data-stu-id="73120-134">For more information, see [Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="73120-135">**Microsoft Defender для конечной точки для Android теперь доступен в [Google Play.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="73120-135">**Microsoft Defender for Endpoint for Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="73120-136">Вы можете подключиться к Google Play из Intune для развертывания приложения Microsoft Defender для конечных точек в режимах entrollment администратора устройств и Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="73120-136">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="73120-137">Настройка Microsoft Defender для конечной точки для Android</span><span class="sxs-lookup"><span data-stu-id="73120-137">How to Configure Microsoft Defender for Endpoint for Android</span></span>

<span data-ttu-id="73120-138">Инструкции по настройке функций Microsoft Defender для конечной точки для Android доступны в настройках Microsoft Defender для конечных точек [для функций Android.](android-configure.md)</span><span class="sxs-lookup"><span data-stu-id="73120-138">Guidance on how to configure Microsoft Defender for Endpoint for Android features is available in [Configure Microsoft Defender for Endpoint for Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="73120-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="73120-139">Related topics</span></span>
- [<span data-ttu-id="73120-140">Развертывание Microsoft Defender для конечной точки с помощью Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="73120-140">Deploy Microsoft Defender for Endpoint for with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="73120-141">Настройка Функций Microsoft Defender для конечной точки для Android</span><span class="sxs-lookup"><span data-stu-id="73120-141">Configure Microsoft Defender for Endpoint for Android features</span></span>](android-configure.md)
