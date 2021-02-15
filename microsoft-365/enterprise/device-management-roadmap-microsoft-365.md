---
title: Стратегия управления устройством в Microsoft 365
keywords: Microsoft 365, Microsoft 365 для предприятий, документация по Microsoft 365, управление мобильными устройствами, Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: План по настройкам управления устройствами для Microsoft 365.
ms.openlocfilehash: 79be47d6bc83c124f2203866986e06181a1f7f3d
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749543"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="37141-104">Стратегия управления устройством в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="37141-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="37141-105">Microsoft 365 для предприятий включает функции для управления устройствами и их приложениями в организации.</span><span class="sxs-lookup"><span data-stu-id="37141-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="37141-106">Управление мобильными устройствами помогает защитить ресурсы организации.</span><span class="sxs-lookup"><span data-stu-id="37141-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="37141-107">Существует два варианта управления устройствами:</span><span class="sxs-lookup"><span data-stu-id="37141-107">There are two options for device management:</span></span>

- [<span data-ttu-id="37141-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="37141-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="37141-109">Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="37141-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="37141-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="37141-110">Microsoft Intune</span></span>

<span data-ttu-id="37141-111">Microsoft Intune можно использовать для управления доступом к организации с помощью управления мобильными устройствами или мобильных приложений.</span><span class="sxs-lookup"><span data-stu-id="37141-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="37141-112">Управление мобильными устройствами происходит, когда пользователи "регистрировать" свои устройства в Intune.</span><span class="sxs-lookup"><span data-stu-id="37141-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="37141-113">После регистрации устройство является управляемым; таким образом, она может получать политики, правила и параметры вашей организации.</span><span class="sxs-lookup"><span data-stu-id="37141-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="37141-114">Например, вы можете установить определенные приложения, создать политику паролей, установить VPN-подключение и много другое.</span><span class="sxs-lookup"><span data-stu-id="37141-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="37141-115">Пользователи с личными устройствами могут не захоть зарегистрироваться на своих устройствах или управляться с помощью Intune и политик вашей организации.</span><span class="sxs-lookup"><span data-stu-id="37141-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="37141-116">Однако вам все равно необходимо защитить ресурсы и данные организации.</span><span class="sxs-lookup"><span data-stu-id="37141-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="37141-117">В этом сценарии вы можете защитить свои приложения с помощью управления мобильными приложениями.</span><span class="sxs-lookup"><span data-stu-id="37141-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="37141-118">Например, можно использовать политику управления мобильными приложениями, которая требует, чтобы пользователь ввести ПИН-код при доступе к SharePoint Online на устройстве.</span><span class="sxs-lookup"><span data-stu-id="37141-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing SharePoint Online on the device.</span></span>

<span data-ttu-id="37141-119">Вы также определите, как вы собираетесь управлять личными устройствами и устройствами, которые принадлежат организации.</span><span class="sxs-lookup"><span data-stu-id="37141-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="37141-120">Вам может потребоваться по-разному обрабатывать устройства в зависимости от их использования.</span><span class="sxs-lookup"><span data-stu-id="37141-120">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="37141-121">Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="37141-121">Basic Mobility and Security</span></span>

<span data-ttu-id="37141-122">Эта возможность встроена в Microsoft 365 и помогает защитить мобильные устройства пользователей, такие как iPhone, iPad, Android и телефоны с Windows, а также управлять ими.</span><span class="sxs-lookup"><span data-stu-id="37141-122">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="37141-123">Вы можете создавать политики безопасности устройств и управлять ими, удаленно очищать устройства и просматривать подробные отчеты об устройствах.</span><span class="sxs-lookup"><span data-stu-id="37141-123">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

## <a name="choose-between-the-two-options"></a><span data-ttu-id="37141-124">Выбор между двумя вариантами</span><span class="sxs-lookup"><span data-stu-id="37141-124">Choose between the two options</span></span>

<span data-ttu-id="37141-125">Чтобы лучше оценить оптимальный вариант управления устройствами, см. "Выбор [между Basic Mobility Security и Intune".](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune)</span><span class="sxs-lookup"><span data-stu-id="37141-125">To help you better assess which device management option is best for you, see [Choose between Basic Mobility Security and Intune](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune).</span></span>

<span data-ttu-id="37141-126">В зависимости от оценки управляющего устройствами вы можете начать с:</span><span class="sxs-lookup"><span data-stu-id="37141-126">Based on your assessment, get started managing your devices with:</span></span>

- [<span data-ttu-id="37141-127">Intune</span><span class="sxs-lookup"><span data-stu-id="37141-127">Intune</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)
- [<span data-ttu-id="37141-128">Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="37141-128">Basic Mobility and Security</span></span>](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="37141-129">Рекомендации по доступу для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="37141-129">Identity and device access recommendations</span></span>

<span data-ttu-id="37141-130">Корпорация Майкрософт предоставляет набор рекомендаций для [удостоверений и доступа к устройству](../security/office-365-security/microsoft-365-policies-configurations.md) с целью обеспечения безопасности и эффективности работы сотрудников.</span><span class="sxs-lookup"><span data-stu-id="37141-130">Microsoft provides a set of recommendations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="37141-131">Для доступа к устройствам используйте рекомендации и параметры, указанные в этих статьях:</span><span class="sxs-lookup"><span data-stu-id="37141-131">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="37141-132">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="37141-132">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="37141-133">Основные политики доступа для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="37141-133">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="37141-134">Управление устройствами в Contoso для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="37141-134">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="37141-135">Сведения о развертывании инфраструктуры управления мобильными устройствами с помощью облачных служб Microsoft 365 вымышленным, но представительным представителем нескольких национальных предприятий см. в руководстве по управлению мобильными устройствами [для Contoso.](contoso-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="37141-135">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>
