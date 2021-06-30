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
ms.openlocfilehash: cbe2fb39221bd9907a3d690503a392edb019d61b
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194857"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="9ec77-104">Microsoft Defender для конечной точки в iOS</span><span class="sxs-lookup"><span data-stu-id="9ec77-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9ec77-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9ec77-105">**Applies to:**</span></span>
- [<span data-ttu-id="9ec77-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9ec77-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9ec77-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ec77-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9ec77-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="9ec77-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9ec77-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="9ec77-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="9ec77-110">**Microsoft Defender для конечной точки на iOS** обеспечивает защиту от фишинга и небезопасных сетевых подключений с веб-сайтов, электронных почт и приложений.</span><span class="sxs-lookup"><span data-stu-id="9ec77-110">**Microsoft Defender for Endpoint on iOS** offers protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="9ec77-111">Все оповещения будут доступны с помощью одной области стекла в Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="9ec77-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="9ec77-112">Портал предоставляет группам безопасности централизованное представление угроз на устройствах iOS наряду с другими платформами.</span><span class="sxs-lookup"><span data-stu-id="9ec77-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="9ec77-113">Запуск других сторонних продуктов защиты конечных точек наряду с Defender for Endpoint на iOS может привести к проблемам с производительностью и непредсказуемым системным ошибкам.</span><span class="sxs-lookup"><span data-stu-id="9ec77-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="9ec77-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9ec77-114">Pre-requisites</span></span>

<span data-ttu-id="9ec77-115">**Для конечных пользователей**</span><span class="sxs-lookup"><span data-stu-id="9ec77-115">**For End Users**</span></span>

- <span data-ttu-id="9ec77-116">Лицензия Microsoft Defender для конечной точки, назначенная конечному пользователю приложения.</span><span class="sxs-lookup"><span data-stu-id="9ec77-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="9ec77-117">См. требования к microsoft Defender для лицензирования [конечных точек.](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="9ec77-117">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="9ec77-118">**Для зарегистрированных устройств**: Device(s) региструются через приложение Корпоративный портал Intune для применения политик соответствия требованиям устройств Intune. [](/mem/intune/user-help/enroll-your-device-in-intune-ios)</span><span class="sxs-lookup"><span data-stu-id="9ec77-118">**For enrolled devices**: Device(s) are [enrolled](/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="9ec77-119">Это требует, чтобы конечному пользователю была назначена Microsoft Intune лицензия.</span><span class="sxs-lookup"><span data-stu-id="9ec77-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="9ec77-120">Корпоративный портал Intune приложение можно скачать из [Магазина приложений Apple.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="9ec77-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="9ec77-121">Обратите внимание, что Apple не позволяет перенаправлять пользователей для скачивания других приложений из магазина приложений, и поэтому этот шаг должен быть сделан пользователем перед его загрузкой в приложение Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9ec77-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="9ec77-122">**Для незавершенных устройств**: Device(s) регистрируются с помощью Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9ec77-122">**For unenrolled devices**: Device(s) are registered with Azure Active Directory.</span></span> <span data-ttu-id="9ec77-123">Это требует, чтобы конечный пользователь был подписан через [Microsoft Authenticator приложение](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span><span class="sxs-lookup"><span data-stu-id="9ec77-123">This requires end user to be signed in through [Microsoft Authenticator app](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

- <span data-ttu-id="9ec77-124">Дополнительные сведения о назначении лицензий см. в дополнительных сведениях о назначении [лицензий пользователям.](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="9ec77-124">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="9ec77-125">**Для администраторов**</span><span class="sxs-lookup"><span data-stu-id="9ec77-125">**For Administrators**</span></span>

- <span data-ttu-id="9ec77-126">Доступ к порталу Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="9ec77-126">Access to the Microsoft Defender Security Center portal.</span></span>

- <span data-ttu-id="9ec77-127">Доступ к [Microsoft Endpoint Manager центра администрирования,](https://go.microsoft.com/fwlink/?linkid=2109431)чтобы развернуть приложение для зарегистрированных групп пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9ec77-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9ec77-128">Microsoft Intune является единственным поддерживаемым решением единой конечной точки управления (UEM) для развертывания Microsoft Defender для конечной точки и принудительного обеспечения политики соответствия требованиям к устройствам, связанным с Endpoint, в Intune.</span><span class="sxs-lookup"><span data-stu-id="9ec77-128">Microsoft Intune is the only supported Unified Endpoint Management (UEM) solution for deploying Microsoft Defender for Endpoint and enforcing Defender for Endpoint related device compliance policies in Intune.</span></span>

<span data-ttu-id="9ec77-129">**Требования к системе**</span><span class="sxs-lookup"><span data-stu-id="9ec77-129">**System Requirements**</span></span>

- <span data-ttu-id="9ec77-130">устройство iOS с iOS 11.0 и выше.</span><span class="sxs-lookup"><span data-stu-id="9ec77-130">iOS device running iOS 11.0 and above.</span></span> <span data-ttu-id="9ec77-131">iPad официально поддерживается с версии 1.1.15010101.</span><span class="sxs-lookup"><span data-stu-id="9ec77-131">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="9ec77-132">Устройство регистрируется в приложении [Корпоративный портал Intune или](https://apps.apple.com/us/app/intune-company-portal/id719171358) регистрируется в Azure Active Directory через [Microsoft Authenticator.](https://apps.apple.com/app/microsoft-authenticator/id983156458)</span><span class="sxs-lookup"><span data-stu-id="9ec77-132">Device is either enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358) or registered with Azure Active Directory through [Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="9ec77-133">Инструкции по установке</span><span class="sxs-lookup"><span data-stu-id="9ec77-133">Installation instructions</span></span>

<span data-ttu-id="9ec77-134">Развертывание microsoft Defender для конечной точки на iOS можно сделать с помощью Microsoft Endpoint Manager (MEM), и поддерживаются как контролируемые, так и неподконтрольные устройства.</span><span class="sxs-lookup"><span data-stu-id="9ec77-134">Deployment of Microsoft Defender for Endpoint on iOS can be done via Microsoft Endpoint Manager (MEM) and both supervised and unsupervised devices are supported.</span></span> <span data-ttu-id="9ec77-135">Конечные пользователи также могут напрямую установить приложение из [магазина приложений Apple.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="9ec77-135">End-users can also directly install the app from the [Apple app store](https://aka.ms/mdatpiosappstore).</span></span>
<span data-ttu-id="9ec77-136">Дополнительные сведения см. в [сайте Deploy Microsoft Defender for Endpoint on iOS.](ios-install.md)</span><span class="sxs-lookup"><span data-stu-id="9ec77-136">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="9ec77-137">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="9ec77-137">Resources</span></span>

- <span data-ttu-id="9ec77-138">Будьте в курсе предстоящих выпусков, посетив новые возможности [в Microsoft Defender для конечной](ios-whatsnew.md) точки на iOS или в нашем [блоге.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)</span><span class="sxs-lookup"><span data-stu-id="9ec77-138">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="9ec77-139">Предоставление обратной связи через систему обратной связи в приложении или через [портал SecOps](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="9ec77-139">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="9ec77-140">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="9ec77-140">Next steps</span></span>

- [<span data-ttu-id="9ec77-141">Развертывание Microsoft Defender для конечной точки на iOS</span><span class="sxs-lookup"><span data-stu-id="9ec77-141">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="9ec77-142">Настройка Microsoft Defender для конечной точки для функций iOS</span><span class="sxs-lookup"><span data-stu-id="9ec77-142">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
