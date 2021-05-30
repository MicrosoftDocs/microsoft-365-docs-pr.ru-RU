---
title: Регистрация мобильного устройства с помощью Basic Mobility and Security
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
description: Прежде чем использовать Microsoft 365 с устройством, может потребоваться сначала записать его в Basic Mobility and Security for Microsoft 365.
ms.openlocfilehash: 2ad0aac331969696bbf53d0b06c18ee5c0ee90f6
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706170"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="9eb02-103">Регистрация мобильного устройства с помощью Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="9eb02-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="9eb02-104">Использование телефона, планшета и других мобильных устройств для работы — это отличный способ оставаться в курсе дел и работать над бизнес-проектами, находясь вдали от офиса.</span><span class="sxs-lookup"><span data-stu-id="9eb02-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="9eb02-105">Прежде чем использовать Microsoft 365 с устройством, вам может потребоваться сначала записать его в Basic Mobility and Security для Microsoft 365 с помощью Microsoft Intune Корпоративный портал.</span><span class="sxs-lookup"><span data-stu-id="9eb02-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="9eb02-106">Организации выбирают Basic Mobility and Security, чтобы сотрудники могли безопасно получать доступ к рабочей электронной почте, календарям и документам, а бизнес обеспечивает безопасность важных данных и соответствует их требованиям.</span><span class="sxs-lookup"><span data-stu-id="9eb02-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="9eb02-107">Дополнительные сведения см. в [обзоре базовой мобильности](overview.md)и безопасности для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9eb02-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="9eb02-108">Дополнительные сведения см. в дополнительных сведениях, которые можно увидеть в организации при [регистрации устройства?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span><span class="sxs-lookup"><span data-stu-id="9eb02-108">For more info, see [What information can my organization see when I enroll my device?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="9eb02-109">При регистрации устройства в Basic Mobility and Security для Microsoft 365, возможно, потребуется настроить пароль, а также разрешить рабочей организации стереть устройство.</span><span class="sxs-lookup"><span data-stu-id="9eb02-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="9eb02-110">Например, из центра администрирования Microsoft 365 для удаления всех данных с устройства, если пароль вошел неправильно слишком много раз или если условия использования нарушены.</span><span class="sxs-lookup"><span data-stu-id="9eb02-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="9eb02-111">Поддерживаемые устройства</span><span class="sxs-lookup"><span data-stu-id="9eb02-111">Supported devices</span></span>

<span data-ttu-id="9eb02-112">Базовая мобильность и безопасность для Microsoft 365 службы Intune работает с большинством мобильных устройств, но не со всеми.</span><span class="sxs-lookup"><span data-stu-id="9eb02-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="9eb02-113">Ниже приводится поддержка базовой мобильности и безопасности:</span><span class="sxs-lookup"><span data-stu-id="9eb02-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="9eb02-114">iOS 10.0 или более поздней</span><span class="sxs-lookup"><span data-stu-id="9eb02-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="9eb02-115">Android 4.4 или более поздний</span><span class="sxs-lookup"><span data-stu-id="9eb02-115">Android 4.4 or later</span></span>

- <span data-ttu-id="9eb02-116">Windows 8.1 и Windows 10 (Телефон и ПК)</span><span class="sxs-lookup"><span data-stu-id="9eb02-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="9eb02-117">Если устройство не указано выше, и его необходимо использовать с помощью Basic Mobility and Security, обратитесь к вашей работе или администратору учебного заведения.</span><span class="sxs-lookup"><span data-stu-id="9eb02-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP]
><span data-ttu-id="9eb02-118">Если у вас возникли проблемы с регистрацией устройства, см. в записи [Устранение неполадок с базовой мобильностью и безопасностью.](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="9eb02-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="9eb02-119">Настройка мобильного устройства с помощью Intune и Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="9eb02-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="9eb02-120">Этот Корпоративный портал Intune позволяет управлять устройством с помощью Microsoft 365 и базовой мобильности и безопасности.</span><span class="sxs-lookup"><span data-stu-id="9eb02-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="9eb02-121">iPhone или iPad</span><span class="sxs-lookup"><span data-stu-id="9eb02-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="9eb02-122">Вы не сможете отправлять и получать электронную почту, пока не выполните этот шаг.</span><span class="sxs-lookup"><span data-stu-id="9eb02-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="9eb02-123">Перейдите в Магазин приложений Apple, скачайте и установите Корпоративный портал Intune.</span><span class="sxs-lookup"><span data-stu-id="9eb02-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="9eb02-124">Чтобы подключить и настроить iOS-телефон или планшет с порталом компании для Office 365, см. в этой ссылке настройка доступа устройств iOS к [ресурсам вашей компании.](/mem/intune/user-help/enroll-your-device-in-intune-ios)</span><span class="sxs-lookup"><span data-stu-id="9eb02-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](/mem/intune/user-help/enroll-your-device-in-intune-ios).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="9eb02-125">Android-телефон или планшет</span><span class="sxs-lookup"><span data-stu-id="9eb02-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="9eb02-126">Вы не сможете отправлять и получать электронную почту, пока не выполните этот шаг.</span><span class="sxs-lookup"><span data-stu-id="9eb02-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="9eb02-127">Перейдите в магазин Google Play и скачайте и установите Корпоративный портал Intune.</span><span class="sxs-lookup"><span data-stu-id="9eb02-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="9eb02-128">Для подключения и настройки телефона или планшета Android с порталом компании для Microsoft 365 см. в [Корпоративный портал.](/mem/intune/user-help/enroll-device-android-company-portal)</span><span class="sxs-lookup"><span data-stu-id="9eb02-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="9eb02-129">Windows 8.1 и Windows 10</span><span class="sxs-lookup"><span data-stu-id="9eb02-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="9eb02-130">Перейдите в Microsoft Store, скачайте и установите Корпоративный портал Intune</span><span class="sxs-lookup"><span data-stu-id="9eb02-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="9eb02-131">Чтобы подключить и настроить Windows или ПК с порталом компании для Microsoft 365, см. Windows регистрации [устройства в Корпоративный портал Intune](/intune-user-help/windows-enrollment-company-portal).</span><span class="sxs-lookup"><span data-stu-id="9eb02-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9eb02-132">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="9eb02-132">Next steps</span></span>

<span data-ttu-id="9eb02-133">После регистрации устройства в Basic Mobility and Security вы можете начать использовать Office на устройстве для работы с электронной почтой, календарем, контактами и документами.</span><span class="sxs-lookup"><span data-stu-id="9eb02-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>