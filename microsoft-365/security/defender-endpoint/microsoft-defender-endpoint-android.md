---
title: Microsoft Defender для конечной точки на Android
ms.reviewer: ''
description: Описание установки и использования Microsoft Defender для конечной точки на Android
keywords: Microsoft, defender, Microsoft Defender for Endpoint, Android, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: 3f8a8c04f608096e5c226d6899fbbd983bd8d8c1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246432"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="c2b44-104">Microsoft Defender для конечной точки на Android</span><span class="sxs-lookup"><span data-stu-id="c2b44-104">Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c2b44-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c2b44-105">**Applies to:**</span></span>
- [<span data-ttu-id="c2b44-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c2b44-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c2b44-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2b44-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c2b44-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c2b44-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c2b44-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c2b44-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="c2b44-110">В этом разделе описывается установка, настройка, обновление и использование Defender для конечной точки на Android.</span><span class="sxs-lookup"><span data-stu-id="c2b44-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="c2b44-111">Запуск других сторонних продуктов защиты конечных точек наряду с Defender для конечной точки на Android может привести к проблемам с производительностью и непредсказуемым системным ошибкам.</span><span class="sxs-lookup"><span data-stu-id="c2b44-111">Running other third-party endpoint protection products alongside Defender for Endpoint on Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="c2b44-112">Установка Microsoft Defender для конечной точки на Android</span><span class="sxs-lookup"><span data-stu-id="c2b44-112">How to install Microsoft Defender for Endpoint on Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="c2b44-113">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c2b44-113">Prerequisites</span></span>

-   <span data-ttu-id="c2b44-114">**Для конечных пользователей**</span><span class="sxs-lookup"><span data-stu-id="c2b44-114">**For end users**</span></span>

    -   <span data-ttu-id="c2b44-115">Лицензия Microsoft Defender для конечной точки, назначенная конечному пользователю приложения.</span><span class="sxs-lookup"><span data-stu-id="c2b44-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="c2b44-116">См. [требования к microsoft Defender для лицензирования конечных точек](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="c2b44-116">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="c2b44-117">Корпоративный портал Intune приложение можно загрузить из [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) и доступно на устройстве Android.</span><span class="sxs-lookup"><span data-stu-id="c2b44-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="c2b44-118">Кроме того, устройство (s) можно записать через приложение Корпоративный портал Intune для применения политик соответствия требованиям устройств Intune. [](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal)</span><span class="sxs-lookup"><span data-stu-id="c2b44-118">Additionally, device(s) can be [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="c2b44-119">Это требует, чтобы конечному пользователю была назначена Microsoft Intune лицензия.</span><span class="sxs-lookup"><span data-stu-id="c2b44-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="c2b44-120">Дополнительные сведения о назначении лицензий см. в дополнительных сведениях о назначении [лицензий пользователям.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="c2b44-120">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="c2b44-121">**Для администраторов**</span><span class="sxs-lookup"><span data-stu-id="c2b44-121">**For Administrators**</span></span>

    -   <span data-ttu-id="c2b44-122">Доступ к порталу Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c2b44-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="c2b44-123">Microsoft Intune является единственным поддерживаемой системой управления мобильными устройствами (MDM) для развертывания Microsoft Defender для конечной точки на Android.</span><span class="sxs-lookup"><span data-stu-id="c2b44-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on Android.</span></span> <span data-ttu-id="c2b44-124">В настоящее время поддерживаются только зарегистрированные устройства для принудительного выполнения политики соответствия требованиям Defender для конечной точки для Android, связанных с устройствами в Intune.</span><span class="sxs-lookup"><span data-stu-id="c2b44-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint on Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="c2b44-125">Доступ [Microsoft Endpoint Manager центра администрирования,](https://go.microsoft.com/fwlink/?linkid=2109431)чтобы развернуть приложение для зарегистрированных групп пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c2b44-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>
        
### <a name="network-requirements"></a><span data-ttu-id="c2b44-126">Требования к сети</span><span class="sxs-lookup"><span data-stu-id="c2b44-126">Network Requirements</span></span>

- <span data-ttu-id="c2b44-127">Чтобы Microsoft Defender для конечной точки на Android функционировал при подстройке к сети, необходимо настроить брандмауэр/прокси, чтобы включить доступ к URL-адресам службы Microsoft Defender для конечных [точек.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="c2b44-127">For Microsoft Defender for Endpoint on Android to function when connected to a network the firewall/proxy will need to be configured to [enable access to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="c2b44-128">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="c2b44-128">System Requirements</span></span>

-   <span data-ttu-id="c2b44-129">Android-устройства под управлением Android 6.0 и выше.</span><span class="sxs-lookup"><span data-stu-id="c2b44-129">Android devices running Android 6.0 and above.</span></span>
-   <span data-ttu-id="c2b44-130">Корпоративный портал Intune приложение загружается из [Google Play и](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) устанавливается.</span><span class="sxs-lookup"><span data-stu-id="c2b44-130">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="c2b44-131">Регистрация устройств необходима для принудительного выполнения политик соответствия требованиям к устройствам Intune.</span><span class="sxs-lookup"><span data-stu-id="c2b44-131">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="c2b44-132">Инструкции по установке</span><span class="sxs-lookup"><span data-stu-id="c2b44-132">Installation instructions</span></span>

<span data-ttu-id="c2b44-133">Microsoft Defender для конечной точки на Android поддерживает установку на обоих режимах зарегистрированных устройств — устаревших режимах администратора устройств Enterprise Android.</span><span class="sxs-lookup"><span data-stu-id="c2b44-133">Microsoft Defender for Endpoint on Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="c2b44-134">**В настоящее время в Android-Enterprise поддерживаются собственные устройства с профилем работы и полностью управляемыми пользовательскими устройствами корпоративной Enterprise. Поддержка других режимов Enterprise Android будет объявлена при готовности.**</span><span class="sxs-lookup"><span data-stu-id="c2b44-134">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrollments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="c2b44-135">Развертывание Microsoft Defender для конечной точки на Android Microsoft Intune (MDM).</span><span class="sxs-lookup"><span data-stu-id="c2b44-135">Deployment of Microsoft Defender for Endpoint on Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="c2b44-136">Дополнительные сведения см. в [ссылке Развертывание Microsoft Defender для конечной точки на Android с Microsoft Intune](android-intune.md).</span><span class="sxs-lookup"><span data-stu-id="c2b44-136">For more information, see [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="c2b44-137">**Microsoft Defender для конечной точки на Android теперь доступен в [Google Play.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="c2b44-137">**Microsoft Defender for Endpoint on Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="c2b44-138">Вы можете подключиться к Google Play из Intune, чтобы развернуть приложение Microsoft Defender для конечных точек в режимах entrollment администратора устройств Enterprise Android.</span><span class="sxs-lookup"><span data-stu-id="c2b44-138">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="c2b44-139">Настройка Microsoft Defender для конечной точки на Android</span><span class="sxs-lookup"><span data-stu-id="c2b44-139">How to Configure Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="c2b44-140">Инструкции по настройке Microsoft Defender для конечной точки на Android доступны в [настройках Microsoft Defender для конечной](android-configure.md)точки на Android.</span><span class="sxs-lookup"><span data-stu-id="c2b44-140">Guidance on how to configure Microsoft Defender for Endpoint on Android features is available in [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="c2b44-141">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c2b44-141">Related topics</span></span>
- [<span data-ttu-id="c2b44-142">Развертывание Microsoft Defender для конечной точки на Android с помощью Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c2b44-142">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="c2b44-143">Настройка функций Microsoft Defender для конечной точки на Android</span><span class="sxs-lookup"><span data-stu-id="c2b44-143">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)

