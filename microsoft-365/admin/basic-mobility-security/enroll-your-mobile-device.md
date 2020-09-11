---
title: Регистрация мобильного устройства с помощью базовой мобильной работы и безопасности
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
description: Прежде чем вы сможете использовать службы Microsoft 365 с устройством, вам может потребоваться сначала зарегистрировать его в базовом мобильном доступе и системе безопасности для Microsoft 365.
ms.openlocfilehash: e31054621ba44a4d5f08de9b366fa0978b738cd9
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430285"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="7988a-103">Регистрация мобильного устройства с помощью базовой мобильной работы и безопасности</span><span class="sxs-lookup"><span data-stu-id="7988a-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="7988a-104">Использование телефона, планшета и других мобильных устройств для работы — это отличный способ следить за работой и работать над бизнес-проектами, пока вы не находитесь в офисе.</span><span class="sxs-lookup"><span data-stu-id="7988a-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="7988a-105">Прежде чем вы сможете использовать службы Microsoft 365 с устройством, вам может понадобиться сначала зарегистрировать его в базовом мобильном доступе и системе безопасности для Microsoft 365 с помощью корпоративного портала Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="7988a-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="7988a-106">В организациях выбирается базовая мобильность и безопасность, чтобы сотрудники могли использовать свои мобильные устройства для безопасного доступа к рабочим электронным сообщениям, календарям и документам, в то время как бизнес защищает важные данные и отвечает требованиям их соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="7988a-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="7988a-107">Чтобы узнать больше, ознакомьтесь [со статьей обзор базовых сведений о мобильности и безопасности для Microsoft 365](overview.md).</span><span class="sxs-lookup"><span data-stu-id="7988a-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="7988a-108">Для получения дополнительных сведений Узнайте, [какие сведения могут видеть моя организация при регистрации устройства?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span><span class="sxs-lookup"><span data-stu-id="7988a-108">For more info, see [What information can my organization see when I enroll my device?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="7988a-109">Когда вы регистрируете устройство в базовых службах мобильной связи и безопасности для Microsoft 365, может потребоваться настроить пароль вместе с возможностью для вашей рабочей организации очистить устройство.</span><span class="sxs-lookup"><span data-stu-id="7988a-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="7988a-110">Очистку устройства можно выполнить из центра администрирования Microsoft 365, например, чтобы удалить все данные с устройства, если пароль неправильно введен слишком много раз или при нарушении условий использования.</span><span class="sxs-lookup"><span data-stu-id="7988a-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="7988a-111">Поддерживаемые устройства</span><span class="sxs-lookup"><span data-stu-id="7988a-111">Supported devices</span></span>

<span data-ttu-id="7988a-112">Базовые мобильность и безопасность для Microsoft 365, размещенных в службе Intune, работают с большинством, но не со всеми мобильными устройствами.</span><span class="sxs-lookup"><span data-stu-id="7988a-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="7988a-113">Следующие компоненты поддерживаются с помощью базовых функций обеспечения мобильности и безопасности:</span><span class="sxs-lookup"><span data-stu-id="7988a-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="7988a-114">iOS 10,0 или более поздняя версия</span><span class="sxs-lookup"><span data-stu-id="7988a-114">iOS 10.0 or later</span></span>
    
- <span data-ttu-id="7988a-115">Android 4,4 или более поздняя версия</span><span class="sxs-lookup"><span data-stu-id="7988a-115">Android 4.4 or later</span></span>
    
- <span data-ttu-id="7988a-116">Windows 8,1 и Windows 10 (телефон и ПК)</span><span class="sxs-lookup"><span data-stu-id="7988a-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>
    
<span data-ttu-id="7988a-117">Если устройство не указано выше и его необходимо использовать с базовыми мобильностью и безопасностью, обратитесь к рабочему или учебному администратору.</span><span class="sxs-lookup"><span data-stu-id="7988a-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP] 
><span data-ttu-id="7988a-118">Если у вас возникли проблемы с регистрацией устройства, ознакомьтесь со статьей [Устранение неполадок, связанных с основными мобильностью и безопасностью](troubleshoot.md).</span><span class="sxs-lookup"><span data-stu-id="7988a-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="7988a-119">Настройка мобильного устройства с помощью Intune и базовой мобильной работы и безопасности</span><span class="sxs-lookup"><span data-stu-id="7988a-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="7988a-120">Корпоративный портал Intune позволяет управлять устройством в Microsoft 365 и базовом мобильном обеспечении и безопасности.</span><span class="sxs-lookup"><span data-stu-id="7988a-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="7988a-121">iPhone или iPad</span><span class="sxs-lookup"><span data-stu-id="7988a-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="7988a-122">Вы не сможете отправлять и получать электронную почту, пока не завершите это действие.</span><span class="sxs-lookup"><span data-stu-id="7988a-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="7988a-123">Перейдите в магазин приложений Apple, а затем скачайте и установите корпоративный портал Intune.</span><span class="sxs-lookup"><span data-stu-id="7988a-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="7988a-124">Чтобы подключить и настроить мобильный телефон или планшет с корпоративным порталом до Office 365, ознакомьтесь со статьей [Настройка доступа устройств iOS к ресурсам компании](https://go.microsoft.com/fwlink/?linkid=875316).</span><span class="sxs-lookup"><span data-stu-id="7988a-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](https://go.microsoft.com/fwlink/?linkid=875316).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="7988a-125">Телефон или планшет с Android</span><span class="sxs-lookup"><span data-stu-id="7988a-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="7988a-126">Вы не сможете отправлять и получать электронную почту, пока не завершите это действие.</span><span class="sxs-lookup"><span data-stu-id="7988a-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="7988a-127">Перейдите в магазин Google Играйте и скачайте и установите портал компании Intune.</span><span class="sxs-lookup"><span data-stu-id="7988a-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="7988a-128">Чтобы подключить и настроить мобильный телефон или планшет с корпоративным порталом до Microsoft 365, обратитесь к разделу [Регистрация устройства с помощью портала компании](https://go.microsoft.com/fwlink/?linkid=875317).</span><span class="sxs-lookup"><span data-stu-id="7988a-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="7988a-129">Windows 8,1 и Windows 10</span><span class="sxs-lookup"><span data-stu-id="7988a-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="7988a-130">Перейдите в Microsoft Store, скачайте и установите корпоративный портал Intune</span><span class="sxs-lookup"><span data-stu-id="7988a-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="7988a-131">Чтобы подключить и настроить Windows Phone или PC с корпоративным порталом до Microsoft 365, обратитесь к разделу [Регистрация устройств Windows на портале компании Intune](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span><span class="sxs-lookup"><span data-stu-id="7988a-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="7988a-132">Что дальше?</span><span class="sxs-lookup"><span data-stu-id="7988a-132">What's next?</span></span>

<span data-ttu-id="7988a-133">После регистрации устройства в базовой мобильности и безопасности можно приступить к использованию приложений Office на устройстве для работы с электронной почтой, календарем, контактами и документами.</span><span class="sxs-lookup"><span data-stu-id="7988a-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>