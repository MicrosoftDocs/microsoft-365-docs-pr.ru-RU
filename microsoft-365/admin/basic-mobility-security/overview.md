---
title: Обзор базовой мобильности и безопасности для Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Используйте basic Mobility and Security, чтобы настроить политики безопасности устройств и правила доступа.
ms.openlocfilehash: 177b0769f3cad928d05a41cfe95d5d62ab2b4786
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430273"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a><span data-ttu-id="2ceca-103">Обзор базовой мобильности и безопасности для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2ceca-103">Overview of Basic Mobility and Security for Microsoft 365</span></span>

<span data-ttu-id="2ceca-104">Вы можете управлять мобильными устройствами и обеспечивать их безопасность при под подключением к вашей организации Microsoft 365 с помощью Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="2ceca-104">You can manage and secure mobile devices when they're connected to your Microsoft 365 organization by using Basic Mobility and Security.</span></span> <span data-ttu-id="2ceca-105">Мобильные устройства, используемые для доступа к рабочей электронной почте, календарю, контактам и документам, например смартфоны и планшетные ПК, играют важную роль в работе сотрудников, где бы они ни находились.</span><span class="sxs-lookup"><span data-stu-id="2ceca-105">Mobile devices like smartphones and tablets that are used to access work email, calendar, contacts, and documents play a big part in making sure that employees get their work done anytime, from anywhere.</span></span> <span data-ttu-id="2ceca-106">Поэтому очень важно защитить информацию организации, когда люди используют устройства.</span><span class="sxs-lookup"><span data-stu-id="2ceca-106">So it’s critical that you help protect your organization's information when people use devices.</span></span> <span data-ttu-id="2ceca-107">Вы можете использовать basic Mobility and Security, чтобы настроить политики безопасности устройств и правила доступа, а также стереть мобильные устройства в случае их потери или кражи.</span><span class="sxs-lookup"><span data-stu-id="2ceca-107">You can use Basic Mobility and Security to set device security policies and access rules, and to wipe mobile devices if they’re lost or stolen.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Базовая настройка мобильности и безопасности":::

## <a name="what-types-of-devices-can-you-manage"></a><span data-ttu-id="2ceca-109">Устройствами каких типов можно управлять?</span><span class="sxs-lookup"><span data-stu-id="2ceca-109">What types of devices can you manage?</span></span>

<span data-ttu-id="2ceca-110">Вы можете использовать basic Mobility and Security для управления многими типами мобильных устройств, таких как Windows Phone, Android, iPhone и iPad.</span><span class="sxs-lookup"><span data-stu-id="2ceca-110">You can use Basic Mobility and Security to manage many types of mobile devices like Windows Phone, Android, iPhone, and iPad.</span></span> <span data-ttu-id="2ceca-111">Для управления мобильными устройствами, используемыми людьми в вашей организации, у каждого человека должна быть применимая лицензия Microsoft 365, а его устройство должно быть зарегистрироваться в basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="2ceca-111">To manage mobile devices used by people in your organization, each person must have an applicable Microsoft 365 license and their device must be enrolled in Basic Mobility and Security.</span></span>

<span data-ttu-id="2ceca-112">Чтобы узнать, какие базовые возможности мобильности и безопасности поддерживаются для каждого типа устройств, см. "Возможности базовой мобильности [и безопасности".](capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="2ceca-112">To see what Basic Mobility and Security supports for each type of device, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>

## <a name="setup-steps-for-basic-mobility-and-security"></a><span data-ttu-id="2ceca-113">Действия по настройке базовой мобильности и безопасности</span><span class="sxs-lookup"><span data-stu-id="2ceca-113">Setup steps for Basic Mobility and Security</span></span>

<span data-ttu-id="2ceca-114">Чтобы активировать и настроить Базовую мобильность и безопасность, глобальный администратор Microsoft 365 должен выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2ceca-114">A Microsoft 365 global admin must complete the following steps to activate and set up Basic Mobility and Security.</span></span> <span data-ttu-id="2ceca-115">Чтобы получить подробные инструкции, следуйте указаниям в [области "Настройка базовой мобильности и безопасности".](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="2ceca-115">For detailed steps, follow the guidance in [Set up Basic Mobility and Security](set-up.md).</span></span> 

<span data-ttu-id="2ceca-116">Вот сводка действий.</span><span class="sxs-lookup"><span data-stu-id="2ceca-116">Here's a summary of the steps:</span></span>

<span data-ttu-id="2ceca-117">**Шаг 1.** Чтобы активировать basic Mobility and Security, с помощью следующих действий  [в области "Настройка базовой мобильности и безопасности".](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="2ceca-117">**Step 1:** Activate Basic Mobility and Security by following steps in the [Set up Basic Mobility and Security](set-up.md).</span></span>

<span data-ttu-id="2ceca-118">**Шаг 2.** Например, чтобы настроить базовую мобильность и безопасность, создайте сертификат APNs для управления устройствами iOS и добавьте запись службы доменных имен (DNS) для вашего домена для поддержки телефонов с Windows.</span><span class="sxs-lookup"><span data-stu-id="2ceca-118">**Step 2:** Set up Basic Mobility and Security by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.</span></span>

<span data-ttu-id="2ceca-119">**Шаг 3.** Создайте политики устройств и применйте их к группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="2ceca-119">**Step 3:** Create device policies and apply them to groups of users.</span></span> <span data-ttu-id="2ceca-120">После этого пользователи получают на своем устройстве сообщение о регистрации, а после регистрации их устройства ограничиваются политиками, которые вы для них настроили.</span><span class="sxs-lookup"><span data-stu-id="2ceca-120">When you do this, your users get an enrollment message on their device, and when they've completed enrollment, their devices are restricted by the policies you've set up for them.</span></span> <span data-ttu-id="2ceca-121">Дополнительные сведения см. в записи [мобильного устройства с помощью Basic Mobility and Security.](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="2ceca-121">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span> 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Основные параметры политики безопасности и мобильности":::

## <a name="device-management-tasks"></a><span data-ttu-id="2ceca-123">Задачи управления устройствами</span><span class="sxs-lookup"><span data-stu-id="2ceca-123">Device management tasks</span></span>

<span data-ttu-id="2ceca-124">После того как вы настроите Basic Mobility and Security и ваши пользователи зарегистрируют свои устройства, вы сможете управлять устройствами, блокировать доступ или при необходимости стирать устройство.</span><span class="sxs-lookup"><span data-stu-id="2ceca-124">After you've got Basic Mobility and Security set up and your users have enrolled their devices, you can manage the devices, block access, or wipe a device, if necessary.</span></span> <span data-ttu-id="2ceca-125">Дополнительные информацию о некоторых распространенных задачах управления устройствами, в том числе о том, где их выполнять, см. в под управлением устройств, зарегистрированных в службе управления мобильными устройствами [Для Microsoft 365.](manage-enrolled-devices.md)</span><span class="sxs-lookup"><span data-stu-id="2ceca-125">To learn more about some common device management tasks, including where to complete the tasks, see [Manage devices enrolled in Mobile Device Management for Microsoft 365](manage-enrolled-devices.md).</span></span>

## <a name="other-ways-to-manage-devices-and-apps"></a><span data-ttu-id="2ceca-126">Другие способы управления устройствами и приложениями</span><span class="sxs-lookup"><span data-stu-id="2ceca-126">Other ways to manage devices and apps</span></span>

<span data-ttu-id="2ceca-127">Если вам просто требуется управление мобильными приложениями (MAM), возможно, для людей, обновляющих проекты на своих устройствах, Intune предоставляет еще один вариант, кроме регистрации устройств и управления ими.</span><span class="sxs-lookup"><span data-stu-id="2ceca-127">If you just need mobile app management (MAM), perhaps for people updating work projects on their own devices, Intune provides another option besides enrolling and managing devices.</span></span> <span data-ttu-id="2ceca-128">Подписка на Intune позволяет настроить политики MAM с помощью портала Azure, даже если устройства пользователей не зарегистрированы в Intune.</span><span class="sxs-lookup"><span data-stu-id="2ceca-128">An Intune subscription allows you to set up MAM policies by using the Azure portal, even if people's devices aren't enrolled in Intune.</span></span> <span data-ttu-id="2ceca-129">Дополнительные сведения [см. в обзоре политик защиты приложений.](https://go.microsoft.com/fwlink/?LinkId=2132517)</span><span class="sxs-lookup"><span data-stu-id="2ceca-129">For more info, see [App protection policies overview](https://go.microsoft.com/fwlink/?LinkId=2132517).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2ceca-130">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="2ceca-130">Related topics</span></span>

[<span data-ttu-id="2ceca-131">Настройка Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="2ceca-131">Set up Basic Mobility and Security</span></span>](set-up.md)

[<span data-ttu-id="2ceca-132">Регистрация мобильного устройства с помощью Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="2ceca-132">Enroll your mobile device using Basic Mobility and Security</span></span>](enroll-your-mobile-device.md)

[<span data-ttu-id="2ceca-133">Управление устройствами, зарегистрированными в службе управления мобильными устройствами для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2ceca-133">Manage devices enrolled in Mobile Device Management for Microsoft 365</span></span>](manage-enrolled-devices.md)

[<span data-ttu-id="2ceca-134">Получить сведения об устройствах, управляемых с помощью Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="2ceca-134">Get details about devices managed by Basic Mobility and Security</span></span>](get-details-about-managed-devices.md)