---
title: Microsoft Defender для конечной точки в iOS
ms.reviewer: ''
description: Описание установки и использования Microsoft Defender для конечной точки на iOS
keywords: Microsoft, defender, Microsoft Defender for Endpoint, ios, overview, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: 3d9dd871edba29ec6119329f98ada990abad6e8d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246420"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="241ee-104">Microsoft Defender для конечной точки в iOS</span><span class="sxs-lookup"><span data-stu-id="241ee-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="241ee-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="241ee-105">**Applies to:**</span></span>
- [<span data-ttu-id="241ee-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="241ee-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="241ee-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="241ee-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="241ee-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="241ee-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="241ee-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="241ee-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="241ee-110">**Microsoft Defender для конечной точки на iOS** будет предлагать защиту от фишинга и небезопасных сетевых подключений с веб-сайтов, электронной почты и приложений.</span><span class="sxs-lookup"><span data-stu-id="241ee-110">**Microsoft Defender for Endpoint on iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="241ee-111">Все оповещения будут доступны с помощью одной области стекла в Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="241ee-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="241ee-112">Портал предоставляет группам безопасности централизованное представление угроз на устройствах iOS наряду с другими платформами.</span><span class="sxs-lookup"><span data-stu-id="241ee-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="241ee-113">Запуск других сторонних продуктов защиты конечных точек наряду с Defender for Endpoint на iOS может привести к проблемам с производительностью и непредсказуемым системным ошибкам.</span><span class="sxs-lookup"><span data-stu-id="241ee-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="241ee-114">Необходимые условия</span><span class="sxs-lookup"><span data-stu-id="241ee-114">Pre-requisites</span></span>

<span data-ttu-id="241ee-115">**Для конечных пользователей**</span><span class="sxs-lookup"><span data-stu-id="241ee-115">**For End Users**</span></span>

- <span data-ttu-id="241ee-116">Лицензия Microsoft Defender для конечной точки, назначенная конечному пользователю приложения.</span><span class="sxs-lookup"><span data-stu-id="241ee-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="241ee-117">См. требования к microsoft Defender для лицензирования [конечных точек.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="241ee-117">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="241ee-118">Device(s) [регистрироваться](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) через приложение Корпоративный портал Intune для применения политик соответствия требованиям устройств Intune.</span><span class="sxs-lookup"><span data-stu-id="241ee-118">Device(s) are [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="241ee-119">Это требует, чтобы конечному пользователю была назначена Microsoft Intune лицензия.</span><span class="sxs-lookup"><span data-stu-id="241ee-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="241ee-120">Корпоративный портал Intune приложение можно скачать из [Магазина приложений Apple.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="241ee-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="241ee-121">Обратите внимание, что Apple не позволяет перенаправлять пользователей для скачивания других приложений из магазина приложений, и поэтому этот шаг должен быть сделан пользователем перед его загрузкой в приложение Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="241ee-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="241ee-122">Дополнительные сведения о назначении лицензий см. в дополнительных сведениях о назначении [лицензий пользователям.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="241ee-122">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="241ee-123">**Для администраторов**</span><span class="sxs-lookup"><span data-stu-id="241ee-123">**For Administrators**</span></span>

- <span data-ttu-id="241ee-124">Доступ к порталу Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="241ee-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="241ee-125">Microsoft Intune это единственное поддерживаемое решение управления мобильными устройствами (MDM) для развертывания Microsoft Defender для конечной точки на iOS.</span><span class="sxs-lookup"><span data-stu-id="241ee-125">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="241ee-126">В настоящее время поддерживаются только зарегистрированные устройства для принудительного выполнения Defender для конечной точки в политиках соответствия требованиям к устройствам iOS в Intune.</span><span class="sxs-lookup"><span data-stu-id="241ee-126">Currently only enrolled devices are supported for enforcing Defender for Endpoint on iOS related device compliance policies in Intune.</span></span>

- <span data-ttu-id="241ee-127">Доступ к [Microsoft Endpoint Manager центра администрирования,](https://go.microsoft.com/fwlink/?linkid=2109431)чтобы развернуть приложение для зарегистрированных групп пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="241ee-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="241ee-128">**Требования к сети**</span><span class="sxs-lookup"><span data-stu-id="241ee-128">**Network Requirements**</span></span>
- <span data-ttu-id="241ee-129">Чтобы Microsoft Defender для конечной точки на iOS функционировала при подстройке к сети, необходимо настроить брандмауэр/прокси, чтобы включить доступ к URL-адресам [службы Microsoft Defender для конечных точек.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="241ee-129">For Microsoft Defender for Endpoint on iOS to function when connected to a network the firewall/proxy will need to be configured to [enable access to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span></span>

<span data-ttu-id="241ee-130">**Требования к системе**</span><span class="sxs-lookup"><span data-stu-id="241ee-130">**System Requirements**</span></span>

- <span data-ttu-id="241ee-131">устройства iOS с iOS 11.0 и выше.</span><span class="sxs-lookup"><span data-stu-id="241ee-131">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="241ee-132">iPad официально поддерживается с версии 1.1.15010101.</span><span class="sxs-lookup"><span data-stu-id="241ee-132">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="241ee-133">Устройство записуется с [приложением Корпоративный портал Intune.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="241ee-133">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

> [!NOTE]
> <span data-ttu-id="241ee-134">**ATP в Защитнике Microsoft (Microsoft Defender для конечной точки) на iOS теперь доступна в [Apple App Store.](https://aka.ms/mdatpiosappstore)**</span><span class="sxs-lookup"><span data-stu-id="241ee-134">**Microsoft Defender ATP (Microsoft Defender for Endpoint) on iOS is now available on [Apple App Store](https://aka.ms/mdatpiosappstore).**</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="241ee-135">Инструкции по установке</span><span class="sxs-lookup"><span data-stu-id="241ee-135">Installation instructions</span></span>

<span data-ttu-id="241ee-136">Развертывание Microsoft Defender для конечной точки на iOS осуществляется с Microsoft Intune (MDM), и поддерживаются как контролируемые, так и неконтролные устройства.</span><span class="sxs-lookup"><span data-stu-id="241ee-136">Deployment of Microsoft Defender for Endpoint on iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span>
<span data-ttu-id="241ee-137">Дополнительные сведения см. в [сайте Deploy Microsoft Defender for Endpoint on iOS.](ios-install.md)</span><span class="sxs-lookup"><span data-stu-id="241ee-137">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="241ee-138">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="241ee-138">Resources</span></span>

- <span data-ttu-id="241ee-139">Будьте в курсе предстоящих выпусков, посетив новые возможности [в Microsoft Defender для конечной](ios-whatsnew.md) точки на iOS или в нашем [блоге.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)</span><span class="sxs-lookup"><span data-stu-id="241ee-139">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="241ee-140">Предоставление обратной связи через систему обратной связи в приложении или через [портал SecOps](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="241ee-140">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="241ee-141">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="241ee-141">Next steps</span></span>

- [<span data-ttu-id="241ee-142">Развертывание Microsoft Defender для конечной точки на iOS</span><span class="sxs-lookup"><span data-stu-id="241ee-142">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="241ee-143">Настройка Microsoft Defender для конечной точки для функций iOS</span><span class="sxs-lookup"><span data-stu-id="241ee-143">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
