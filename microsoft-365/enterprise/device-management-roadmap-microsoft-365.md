---
title: Стратегия управления устройством в Microsoft 365
keywords: Microsoft 365, Microsoft 365 корпоративной, Microsoft 365 документации, управления мобильными устройствами, Intune
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
description: Дорожная карта для организации управления устройствами для Microsoft 365.
ms.openlocfilehash: ec284a96fc8e7285f89e8a909b76c782b4469ce1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051464"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="76251-104">Стратегия управления устройством в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="76251-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="76251-105">Microsoft 365 для предприятия включает функции, которые помогают управлять устройствами и их приложениями в организации.</span><span class="sxs-lookup"><span data-stu-id="76251-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="76251-106">Управление мобильными устройствами помогает обеспечить безопасность и защиту ресурсов организации.</span><span class="sxs-lookup"><span data-stu-id="76251-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="76251-107">Существует два варианта управления устройствами:</span><span class="sxs-lookup"><span data-stu-id="76251-107">There are two options for device management:</span></span>

- [<span data-ttu-id="76251-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="76251-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="76251-109">Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="76251-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="76251-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="76251-110">Microsoft Intune</span></span>

<span data-ttu-id="76251-111">Вы можете использовать Microsoft Intune для управления доступом к организации с помощью управления мобильными устройствами или управления мобильными приложениями.</span><span class="sxs-lookup"><span data-stu-id="76251-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="76251-112">Управление мобильными устройствами — это когда пользователи "регистрировать" свои устройства в Intune.</span><span class="sxs-lookup"><span data-stu-id="76251-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="76251-113">После регистрации устройства это управляемое устройство; поэтому он может получать политики, правила и параметры вашей организации.</span><span class="sxs-lookup"><span data-stu-id="76251-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="76251-114">Например, можно установить определенные приложения, создать политику паролей, установить VPN-подключение и другие.</span><span class="sxs-lookup"><span data-stu-id="76251-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="76251-115">Пользователи со своими личными устройствами могут не захоть зарегистрироваться на своих устройствах или управляться политиками Intune и вашей организации.</span><span class="sxs-lookup"><span data-stu-id="76251-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="76251-116">Но все равно необходимо защитить ресурсы и данные организации.</span><span class="sxs-lookup"><span data-stu-id="76251-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="76251-117">В этом сценарии можно защитить приложения с помощью управления мобильными приложениями.</span><span class="sxs-lookup"><span data-stu-id="76251-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="76251-118">Например, можно использовать политику управления мобильными приложениями, которая требует от пользователя ввести ПИН-код при доступе SharePoint в Интернете на устройстве.</span><span class="sxs-lookup"><span data-stu-id="76251-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing SharePoint Online on the device.</span></span>

<span data-ttu-id="76251-119">Вы также определите, как управлять личными устройствами и устройствами, которые принадлежат организации.</span><span class="sxs-lookup"><span data-stu-id="76251-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="76251-120">Может потребоваться по-разному относиться к устройствам в зависимости от их использования.</span><span class="sxs-lookup"><span data-stu-id="76251-120">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="76251-121">Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="76251-121">Basic Mobility and Security</span></span>

<span data-ttu-id="76251-122">Это встроено в Microsoft 365 и помогает обеспечить безопасность мобильных устройств пользователей, таких как iPhone, iPad, Android и Windows телефонов.</span><span class="sxs-lookup"><span data-stu-id="76251-122">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="76251-123">Вы можете создавать политики безопасности устройств и управлять ими, удаленно очищать устройства и просматривать подробные отчеты об устройствах.</span><span class="sxs-lookup"><span data-stu-id="76251-123">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

## <a name="choose-between-the-two-options"></a><span data-ttu-id="76251-124">Выбор между двумя вариантами</span><span class="sxs-lookup"><span data-stu-id="76251-124">Choose between the two options</span></span>

<span data-ttu-id="76251-125">Чтобы лучше оценить, какой вариант управления устройствами лучше всего для вас, см. в справке Выберите между [Basic Mobility Security и Intune.](/office365/securitycompliance/choose-between-mdm-and-intune)</span><span class="sxs-lookup"><span data-stu-id="76251-125">To help you better assess which device management option is best for you, see [Choose between Basic Mobility Security and Intune](/office365/securitycompliance/choose-between-mdm-and-intune).</span></span>

<span data-ttu-id="76251-126">На основе вашей оценки начинайте управлять устройствами с помощью:</span><span class="sxs-lookup"><span data-stu-id="76251-126">Based on your assessment, get started managing your devices with:</span></span>

- [<span data-ttu-id="76251-127">Intune</span><span class="sxs-lookup"><span data-stu-id="76251-127">Intune</span></span>](/mem/intune/fundamentals/planning-guide)
- [<span data-ttu-id="76251-128">Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="76251-128">Basic Mobility and Security</span></span>](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="76251-129">Рекомендации по доступу для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="76251-129">Identity and device access recommendations</span></span>

<span data-ttu-id="76251-130">Корпорация Майкрософт предоставляет набор рекомендаций для [удостоверений и доступа к устройству](../security/defender-365-security/microsoft-365-policies-configurations.md) с целью обеспечения безопасности и эффективности работы сотрудников.</span><span class="sxs-lookup"><span data-stu-id="76251-130">Microsoft provides a set of recommendations for [identity and device access](../security/defender-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="76251-131">Для доступа к устройству используйте рекомендации и параметры в этих статьях:</span><span class="sxs-lookup"><span data-stu-id="76251-131">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="76251-132">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="76251-132">Prerequisites</span></span>](../security/defender-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="76251-133">Основные политики доступа для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="76251-133">Common identity and device access policies</span></span>](../security/defender-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="76251-134">Как Contoso сделал управление устройствами для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="76251-134">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="76251-135">Сведения о том, как вымышленный, но представительный многонациональный бизнес развернул инфраструктуру управления мобильными устройствами Microsoft 365 облачными службами, см. в книге Управление мобильными устройствами [для Contoso.](contoso-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="76251-135">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>