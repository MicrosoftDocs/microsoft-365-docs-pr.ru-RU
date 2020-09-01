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
ms.openlocfilehash: 1a1bdb449aa1d1ba12cf1de422b3e279df6c1376
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315745"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="d55f9-104">Схема управления устройствами для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d55f9-104">Device management roadmap for Microsoft 365</span></span>


<span data-ttu-id="d55f9-105">Microsoft 365 для предприятий включает функции, помогающие управлять устройствами и их приложениями в Организации.</span><span class="sxs-lookup"><span data-stu-id="d55f9-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="d55f9-106">Управление мобильными устройствами помогает защитить и защитить ресурсы Организации.</span><span class="sxs-lookup"><span data-stu-id="d55f9-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="d55f9-107">Существует два способа управления устройствами.</span><span class="sxs-lookup"><span data-stu-id="d55f9-107">There are two options for device management.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="d55f9-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d55f9-108">Microsoft Intune</span></span>

<span data-ttu-id="d55f9-109">Intune предоставляет возможности для управления доступом к Организации с помощью управления мобильными устройствами (MDM) или управления мобильными приложениями (MAM).</span><span class="sxs-lookup"><span data-stu-id="d55f9-109">Intune gives you options to manage access to your organization using Mobile Device Management (MDM) or Mobile Application Management (MAM).</span></span> <span data-ttu-id="d55f9-110">MDM — когда пользователи регистрируют свои устройства в Intune.</span><span class="sxs-lookup"><span data-stu-id="d55f9-110">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="d55f9-111">После регистрации они будут управляемыми устройствами и могут получать любые политики, правила и параметры, используемые вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="d55f9-111">Once enrolled, they are managed devices, and can receive any policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="d55f9-112">Например, можно установить конкретные приложения, создать политику паролей, установить VPN-подключение и т. д.</span><span class="sxs-lookup"><span data-stu-id="d55f9-112">For example, you can install specifics apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="d55f9-113">Пользователи с личными устройствами могут не заносить свои устройства или управляться Intune и политиками.</span><span class="sxs-lookup"><span data-stu-id="d55f9-113">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your policies.</span></span> <span data-ttu-id="d55f9-114">Но по-прежнему необходимо защищать ресурсы и данные Организации.</span><span class="sxs-lookup"><span data-stu-id="d55f9-114">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="d55f9-115">В этом сценарии можно защитить приложения с помощью MAM.</span><span class="sxs-lookup"><span data-stu-id="d55f9-115">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="d55f9-116">Например, вы можете использовать политику MAM, требующую от пользователя ввода ПИН-кода при доступе к SharePoint на устройстве.</span><span class="sxs-lookup"><span data-stu-id="d55f9-116">For example, you can use a MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="d55f9-117">Кроме того, вы узнаете, как вы будете управлять личными или принадлежащими организацией устройствами.</span><span class="sxs-lookup"><span data-stu-id="d55f9-117">You'll also determine how you're going to manage personal or organization-owned devices.</span></span> <span data-ttu-id="d55f9-118">В зависимости от их использования устройства могут работать по-разному.</span><span class="sxs-lookup"><span data-stu-id="d55f9-118">You may want to treat devices differently, depending on their use.</span></span> 

<span data-ttu-id="d55f9-119">Начните [отсюда](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span><span class="sxs-lookup"><span data-stu-id="d55f9-119">Start [here](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="d55f9-120">Базовые мобильность и безопасность</span><span class="sxs-lookup"><span data-stu-id="d55f9-120">Basic Mobility and Security</span></span>
 
<span data-ttu-id="d55f9-121">Эта возможность встроена в Microsoft 365 и помогает защищать мобильные устройства пользователей, такие как iPhone, iPad, Андроидс и Windows phones, и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="d55f9-121">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="d55f9-122">Вы можете создавать политики безопасности устройств и управлять ими, удаленно очищать устройства и просматривать подробные отчеты об устройствах.</span><span class="sxs-lookup"><span data-stu-id="d55f9-122">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span> 

<span data-ttu-id="d55f9-123">Начните [отсюда](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span><span class="sxs-lookup"><span data-stu-id="d55f9-123">Start [here](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span></span>
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="d55f9-124">Рекомендации по доступу для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="d55f9-124">Identity and device access recommendations</span></span>

<span data-ttu-id="d55f9-125">Корпорация Майкрософт предоставляет набор рекомендаций для [удостоверений и доступа к устройству](microsoft-365-policies-configurations.md) с целью обеспечения безопасности и эффективности работы сотрудников.</span><span class="sxs-lookup"><span data-stu-id="d55f9-125">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="d55f9-126">В разделе "доступ к устройству" используйте рекомендации и параметры, приведенные в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="d55f9-126">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="d55f9-127">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="d55f9-127">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="d55f9-128">Основные политики доступа для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="d55f9-128">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="d55f9-129">Сведения об управлении устройствами компанией Contoso для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d55f9-129">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="d55f9-130">Узнайте, как Корпорация Contoso, вымышленная, но предопределяющая многонациональная организация, [развернула инфраструктуру управления мобильными устройствами](contoso-mdm.md) с Microsoft 365 Cloud Services.</span><span class="sxs-lookup"><span data-stu-id="d55f9-130">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed their mobile device management infrastructure](contoso-mdm.md) with Microsoft 365 cloud services.</span></span>
