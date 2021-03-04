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
description: Прежде чем использовать службы Microsoft 365 с устройством, может потребоваться сначала записать его в Basic Mobility and Security для Microsoft 365.
ms.openlocfilehash: 2a9c0bd9faf670d7dca340d3bc4e9f6586bd6b66
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423205"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="2bd42-103">Регистрация мобильного устройства с помощью Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="2bd42-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="2bd42-104">Использование телефона, планшета и других мобильных устройств для работы — это отличный способ оставаться в курсе дел и работать над бизнес-проектами, находясь вдали от офиса.</span><span class="sxs-lookup"><span data-stu-id="2bd42-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="2bd42-105">Прежде чем использовать службы Microsoft 365 с устройством, вам может потребоваться сначала записать его в Basic Mobility and Security для Microsoft 365 с помощью портала microsoft Intune Company Portal.</span><span class="sxs-lookup"><span data-stu-id="2bd42-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="2bd42-106">Организации выбирают Basic Mobility and Security, чтобы сотрудники могли безопасно получать доступ к рабочей электронной почте, календарям и документам, а бизнес обеспечивает безопасность важных данных и соответствует их требованиям.</span><span class="sxs-lookup"><span data-stu-id="2bd42-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="2bd42-107">Дополнительные сведения см. в [обзоре базовой мобильности и безопасности для Microsoft 365.](overview.md)</span><span class="sxs-lookup"><span data-stu-id="2bd42-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="2bd42-108">Дополнительные сведения см. в дополнительных сведениях, которые можно увидеть в организации при [регистрации устройства?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span><span class="sxs-lookup"><span data-stu-id="2bd42-108">For more info, see [What information can my organization see when I enroll my device?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="2bd42-109">При регистрации устройства в Базовой мобильности и безопасности для Microsoft 365 может потребоваться настроить пароль, а также разрешить рабочей организации стереть устройство.</span><span class="sxs-lookup"><span data-stu-id="2bd42-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="2bd42-110">Например, в центре администрирования Microsoft 365 можно выполнить стирка устройства, чтобы удалить все данные с устройства, если пароль вошел слишком много раз неправильно или если условия использования нарушены.</span><span class="sxs-lookup"><span data-stu-id="2bd42-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="2bd42-111">Поддерживаемые устройства</span><span class="sxs-lookup"><span data-stu-id="2bd42-111">Supported devices</span></span>

<span data-ttu-id="2bd42-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span><span class="sxs-lookup"><span data-stu-id="2bd42-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="2bd42-113">Ниже приводится поддержка базовой мобильности и безопасности:</span><span class="sxs-lookup"><span data-stu-id="2bd42-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="2bd42-114">iOS 10.0 или более поздней</span><span class="sxs-lookup"><span data-stu-id="2bd42-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="2bd42-115">Android 4.4 или более поздний</span><span class="sxs-lookup"><span data-stu-id="2bd42-115">Android 4.4 or later</span></span>

- <span data-ttu-id="2bd42-116">Windows 8.1 и Windows 10 (телефон и КОМПЬЮТЕР)</span><span class="sxs-lookup"><span data-stu-id="2bd42-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="2bd42-117">Если устройство не указано выше, и его необходимо использовать с помощью Basic Mobility and Security, обратитесь к вашей работе или администратору учебного заведения.</span><span class="sxs-lookup"><span data-stu-id="2bd42-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP]
><span data-ttu-id="2bd42-118">Если у вас возникли проблемы с регистрацией устройства, см. в записи [Устранение неполадок с базовой мобильностью и безопасностью.](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="2bd42-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="2bd42-119">Настройка мобильного устройства с помощью Intune и Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="2bd42-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="2bd42-120">Портал компании Intune позволяет управлять устройством с помощью Microsoft 365 и Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="2bd42-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="2bd42-121">iPhone или iPad</span><span class="sxs-lookup"><span data-stu-id="2bd42-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="2bd42-122">Вы не сможете отправлять и получать электронную почту, пока не выполните этот шаг.</span><span class="sxs-lookup"><span data-stu-id="2bd42-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="2bd42-123">Перейдите в Магазин приложений Apple, скачайте и установите портал компании Intune.</span><span class="sxs-lookup"><span data-stu-id="2bd42-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="2bd42-124">Чтобы подключить и настроить iOS-телефон или планшет с порталом Компании на Office 365, см. в этой ссылке Настройка доступа устройств iOS к [ресурсам вашей компании.](https://go.microsoft.com/fwlink/?linkid=875316)</span><span class="sxs-lookup"><span data-stu-id="2bd42-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](https://go.microsoft.com/fwlink/?linkid=875316).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="2bd42-125">Android-телефон или планшет</span><span class="sxs-lookup"><span data-stu-id="2bd42-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="2bd42-126">Вы не сможете отправлять и получать электронную почту, пока не выполните этот шаг.</span><span class="sxs-lookup"><span data-stu-id="2bd42-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="2bd42-127">Перейдите в магазин Google Play и скачайте и установите портал компании Intune.</span><span class="sxs-lookup"><span data-stu-id="2bd42-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="2bd42-128">Чтобы подключить и настроить android-телефон или планшет с помощью портала Компании в Microsoft 365, см. в этой ссылке запись устройства [на портале компании.](https://go.microsoft.com/fwlink/?linkid=875317)</span><span class="sxs-lookup"><span data-stu-id="2bd42-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="2bd42-129">Windows 8.1 и Windows 10</span><span class="sxs-lookup"><span data-stu-id="2bd42-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="2bd42-130">Перейдите в Microsoft Store и скачайте и установите портал компании Intune</span><span class="sxs-lookup"><span data-stu-id="2bd42-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="2bd42-131">Чтобы подключить и настроить windows-телефон или компьютер с порталом компании на Microsoft 365, см. в записи устройства Windows на [портале компании Intune.](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal)</span><span class="sxs-lookup"><span data-stu-id="2bd42-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="2bd42-132">Что дальше?</span><span class="sxs-lookup"><span data-stu-id="2bd42-132">What's next?</span></span>

<span data-ttu-id="2bd42-133">После регистрации устройства в Basic Mobility and Security вы можете начать использовать приложения Office на устройстве для работы с электронной почтой, календарем, контактами и документами.</span><span class="sxs-lookup"><span data-stu-id="2bd42-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>
