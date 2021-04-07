---
title: Обзор ATP Защитника Майкрософт для iOS
ms.reviewer: ''
description: Описание установки и использования ATP Microsoft Defender для iOS
keywords: Microsoft, defender, atp, ios, overview, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: 7d4bc095a9fbc0b9cd166d3133ed291a2c8c01da
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615427"
---
# <a name="microsoft-defender-for-endpoint-for-ios"></a><span data-ttu-id="62bdd-104">Microsoft Defender для конечной точки для iOS</span><span class="sxs-lookup"><span data-stu-id="62bdd-104">Microsoft Defender for Endpoint for iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="62bdd-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="62bdd-105">**Applies to:**</span></span>
- [<span data-ttu-id="62bdd-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="62bdd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="62bdd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62bdd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="62bdd-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="62bdd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="62bdd-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="62bdd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="62bdd-110">**Microsoft Defender для конечной точки для iOS** будет предлагать защиту от фишинга и небезопасных сетевых подключений с веб-сайтов, электронной почты и приложений.</span><span class="sxs-lookup"><span data-stu-id="62bdd-110">**Microsoft Defender for Endpoint for iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="62bdd-111">Все оповещения будут доступны с помощью единой области стекла в Центре безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="62bdd-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="62bdd-112">Портал предоставляет группам безопасности централизованное представление угроз на устройствах iOS наряду с другими платформами.</span><span class="sxs-lookup"><span data-stu-id="62bdd-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="62bdd-113">Запуск других сторонних продуктов защиты конечных точек наряду с Defender for Endpoint для iOS может привести к проблемам с производительностью и непредсказуемым системным ошибкам.</span><span class="sxs-lookup"><span data-stu-id="62bdd-113">Running other third-party endpoint protection products alongside Defender for Endpoint for iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="62bdd-114">Необходимые условия</span><span class="sxs-lookup"><span data-stu-id="62bdd-114">Pre-requisites</span></span>

<span data-ttu-id="62bdd-115">**Для конечных пользователей**</span><span class="sxs-lookup"><span data-stu-id="62bdd-115">**For End Users**</span></span>

- <span data-ttu-id="62bdd-116">Лицензия Microsoft Defender для конечной точки, назначенная конечному пользователю приложения.</span><span class="sxs-lookup"><span data-stu-id="62bdd-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="62bdd-117">См. требования к microsoft Defender для лицензирования [конечных точек.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="62bdd-117">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="62bdd-118">Device(s) [регистрироваться через](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) приложение Портал компании Intune для обеспечения соблюдения политик соответствия устройствам Intune.</span><span class="sxs-lookup"><span data-stu-id="62bdd-118">Device(s) are [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="62bdd-119">Это требует, чтобы конечному пользователю была назначена лицензия Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="62bdd-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="62bdd-120">Приложение Портал компании Intune можно скачать из [Магазина приложений Apple.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="62bdd-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="62bdd-121">Обратите внимание, что Apple не позволяет перенаправлять пользователей для скачивания других приложений из магазина приложений, и поэтому этот шаг должен быть сделан пользователем перед его загрузкой в приложение Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="62bdd-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="62bdd-122">Дополнительные сведения о назначении лицензий см. в дополнительных сведениях о назначении [лицензий пользователям.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="62bdd-122">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="62bdd-123">**Для администраторов**</span><span class="sxs-lookup"><span data-stu-id="62bdd-123">**For Administrators**</span></span>

- <span data-ttu-id="62bdd-124">Доступ к порталу Центра безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="62bdd-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="62bdd-125">Microsoft Intune является единственным поддерживаемым решением управления мобильными устройствами (MDM) для развертывания Microsoft Defender для конечной точки для iOS.</span><span class="sxs-lookup"><span data-stu-id="62bdd-125">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint for iOS.</span></span> <span data-ttu-id="62bdd-126">В настоящее время поддерживаются только зарегистрированные устройства для принудительного выполнения политик соответствия требованиям Defender для конечной точки для iOS, связанных с устройствами в Intune.</span><span class="sxs-lookup"><span data-stu-id="62bdd-126">Currently only enrolled devices are supported for enforcing Defender for Endpoint for iOS related device compliance policies in Intune.</span></span>

- <span data-ttu-id="62bdd-127">Доступ к [центру администрирования Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)чтобы развернуть приложение для зарегистрированных групп пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="62bdd-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="62bdd-128">**Требования к системе**</span><span class="sxs-lookup"><span data-stu-id="62bdd-128">**System Requirements**</span></span>

- <span data-ttu-id="62bdd-129">устройства iOS с iOS 11.0 и выше.</span><span class="sxs-lookup"><span data-stu-id="62bdd-129">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="62bdd-130">Устройства iPad официально поддерживаются с версии 1.1.15010101 и дальше.</span><span class="sxs-lookup"><span data-stu-id="62bdd-130">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="62bdd-131">Устройство регистрироваться с помощью [приложения Портал компании Intune.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="62bdd-131">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

> [!NOTE]
> <span data-ttu-id="62bdd-132">**AtP защитника Microsoft (Microsoft Defender для конечной точки) для iOS теперь доступен в [Магазине приложений Apple.](https://aka.ms/mdatpiosappstore)**</span><span class="sxs-lookup"><span data-stu-id="62bdd-132">**Microsoft Defender ATP (Microsoft Defender for Endpoint) for iOS is now available on [Apple App Store](https://aka.ms/mdatpiosappstore).**</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="62bdd-133">Инструкции по установке</span><span class="sxs-lookup"><span data-stu-id="62bdd-133">Installation instructions</span></span>

<span data-ttu-id="62bdd-134">Развертывание конечной точки Microsoft Defender для iOS осуществляется с помощью Microsoft Intune (MDM), и поддерживаются как контролируемые, так и неконтролные устройства.</span><span class="sxs-lookup"><span data-stu-id="62bdd-134">Deployment of Microsoft Defender for Endpoint for iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span>
<span data-ttu-id="62bdd-135">Дополнительные сведения см. в [веб-сайте Deploy Microsoft Defender for Endpoint for iOS.](ios-install.md)</span><span class="sxs-lookup"><span data-stu-id="62bdd-135">For more information, see [Deploy Microsoft Defender for Endpoint for iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="62bdd-136">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="62bdd-136">Resources</span></span>

- <span data-ttu-id="62bdd-137">Будьте в курсе предстоящих выпусков, посетив новые возможности [в Microsoft Defender для конечной](ios-whatsnew.md) точки для iOS или в нашем [блоге.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)</span><span class="sxs-lookup"><span data-stu-id="62bdd-137">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint for iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="62bdd-138">Предоставление обратной связи через систему обратной связи в приложении или через [портал SecOps](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="62bdd-138">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="62bdd-139">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="62bdd-139">Next steps</span></span>

- [<span data-ttu-id="62bdd-140">Развертывание Microsoft Defender для конечной точки для iOS</span><span class="sxs-lookup"><span data-stu-id="62bdd-140">Deploy Microsoft Defender for Endpoint for iOS</span></span>](ios-install.md)
- [<span data-ttu-id="62bdd-141">Настройка Microsoft Defender для конечной точки для функций iOS</span><span class="sxs-lookup"><span data-stu-id="62bdd-141">Configure Microsoft Defender for Endpoint for iOS features</span></span>](ios-configure-features.md)
