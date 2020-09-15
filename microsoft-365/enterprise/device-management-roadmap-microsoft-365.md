---
title: Схема управления устройствами для Microsoft 365
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
description: Схема настройки управления устройствами для Microsoft 365.
ms.openlocfilehash: bb19c38d5cf92cfc04ac83bc29573ea24c93ef30
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775175"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="0db82-104">Схема управления устройствами для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0db82-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="0db82-105">Microsoft 365 для предприятий включает функции, помогающие управлять устройствами и их приложениями в Организации.</span><span class="sxs-lookup"><span data-stu-id="0db82-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="0db82-106">Управление мобильными устройствами помогает защитить и защитить ресурсы Организации.</span><span class="sxs-lookup"><span data-stu-id="0db82-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="0db82-107">Существует два способа управления устройствами:</span><span class="sxs-lookup"><span data-stu-id="0db82-107">There are two options for device management:</span></span>

- [<span data-ttu-id="0db82-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="0db82-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="0db82-109">Базовые мобильность и безопасность</span><span class="sxs-lookup"><span data-stu-id="0db82-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="0db82-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="0db82-110">Microsoft Intune</span></span>

<span data-ttu-id="0db82-111">С помощью Microsoft Intune можно управлять доступом к Организации с помощью управления мобильными устройствами и управления мобильными приложениями.</span><span class="sxs-lookup"><span data-stu-id="0db82-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="0db82-112">Управление мобильными устройствами — это то, что пользователи регистрируют свои устройства в Intune.</span><span class="sxs-lookup"><span data-stu-id="0db82-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="0db82-113">После регистрации устройства это управляемое устройство; Таким образом, она может принимать политики, правила и параметры вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0db82-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="0db82-114">Например, вы можете установить определенные приложения, создать политику паролей, установить VPN-подключение и т. д.</span><span class="sxs-lookup"><span data-stu-id="0db82-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="0db82-115">Пользователи с собственными личными устройствами могут не заносить свои устройства или управляться Intune и политиками вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0db82-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="0db82-116">Но по-прежнему необходимо защищать ресурсы и данные Организации.</span><span class="sxs-lookup"><span data-stu-id="0db82-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="0db82-117">В этом сценарии можно защитить приложения с помощью управления мобильными приложениями.</span><span class="sxs-lookup"><span data-stu-id="0db82-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="0db82-118">Например, вы можете использовать политику управления мобильными приложениями, требующую от пользователя ввода ПИН-кода при доступе к Microsoft SharePoint на устройстве.</span><span class="sxs-lookup"><span data-stu-id="0db82-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing Microsoft SharePoint on the device.</span></span>

<span data-ttu-id="0db82-119">Кроме того, вы узнаете, как вы будете управлять личными устройствами и устройствами, принадлежащими Организации.</span><span class="sxs-lookup"><span data-stu-id="0db82-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="0db82-120">Вы можете по-разному обрабатывать устройства в зависимости от их использования.</span><span class="sxs-lookup"><span data-stu-id="0db82-120">You might want to treat devices differently, depending on their uses.</span></span>

<span data-ttu-id="0db82-121">Чтобы управлять устройствами с помощью Intune, начните [отсюда](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span><span class="sxs-lookup"><span data-stu-id="0db82-121">To manage devices using Intune, start [here](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="0db82-122">Базовые мобильность и безопасность</span><span class="sxs-lookup"><span data-stu-id="0db82-122">Basic Mobility and Security</span></span>

<span data-ttu-id="0db82-123">Эта возможность встроена в Microsoft 365 и помогает защищать мобильные устройства пользователей, такие как iPhone, iPad, Андроидс и Windows phones, и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="0db82-123">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="0db82-124">Вы можете создавать политики безопасности устройств и управлять ими, удаленно очищать устройства и просматривать подробные отчеты об устройствах.</span><span class="sxs-lookup"><span data-stu-id="0db82-124">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

<span data-ttu-id="0db82-125">Для управления устройствами с использованием базового уровня мобильности и безопасности Начните [отсюда](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span><span class="sxs-lookup"><span data-stu-id="0db82-125">To manage devices using Basic Mobility and Security, start [here](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span></span>
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="0db82-126">Рекомендации по доступу для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="0db82-126">Identity and device access recommendations</span></span>

<span data-ttu-id="0db82-127">Корпорация Майкрософт предоставляет набор рекомендаций для [удостоверений и доступа к устройству](microsoft-365-policies-configurations.md) с целью обеспечения безопасности и эффективности работы сотрудников.</span><span class="sxs-lookup"><span data-stu-id="0db82-127">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="0db82-128">В разделе "доступ к устройству" используйте рекомендации и параметры, приведенные в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="0db82-128">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="0db82-129">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="0db82-129">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="0db82-130">Основные политики доступа для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="0db82-130">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="0db82-131">Сведения об управлении устройствами компанией Contoso для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0db82-131">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="0db82-132">Сведения о том, как в облачных службах Microsoft 365 Cloud [Devices (Управление мобильными устройствами для Contoso](contoso-mdm.md)) развернута инфраструктура управления мобильными устройствами, развернутая в качестве фирменного бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0db82-132">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>
