---
title: Устранение неполадок Базовая мобильность и безопасность
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: Попробуйте эти действия, чтобы отследить проблемы с базовой мобильностью и безопасностью
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876856"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="02e4e-103">Устранение неполадок Базовая мобильность и безопасность</span><span class="sxs-lookup"><span data-stu-id="02e4e-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="02e4e-104">Если при попытке регистрации устройства в Basic Mobility and Security возникла проблема, попробуйте сделать следующие действия, чтобы отследить проблему.</span><span class="sxs-lookup"><span data-stu-id="02e4e-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="02e4e-105">Если общие действия не устраняют проблему, см. один из более поздних разделов с определенными шагами для типа устройства.</span><span class="sxs-lookup"><span data-stu-id="02e4e-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="02e4e-106">Действия, которые необходимо предпринять в первую очередь</span><span class="sxs-lookup"><span data-stu-id="02e4e-106">Steps to try first</span></span>

<span data-ttu-id="02e4e-107">Для начала ознакомьтесь со следующими словами:</span><span class="sxs-lookup"><span data-stu-id="02e4e-107">To start, check the following:</span></span>

- <span data-ttu-id="02e4e-108">Убедитесь, что устройство еще не зарегистрировано с другим поставщиком управления мобильными устройствами, например Intune.</span><span class="sxs-lookup"><span data-stu-id="02e4e-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>

- <span data-ttu-id="02e4e-109">Убедитесь, что устройство настроено на правильную дату и время.</span><span class="sxs-lookup"><span data-stu-id="02e4e-109">Make sure that the device is set to the correct date and time.</span></span>

- <span data-ttu-id="02e4e-110">Переключение на другую WIFI или клеточную сеть на устройстве.</span><span class="sxs-lookup"><span data-stu-id="02e4e-110">Switch to a different WIFI or cellular network on the device.</span></span>

- <span data-ttu-id="02e4e-111">Для устройств с Android или iOS удалить и переустановить приложение Корпоративный портал Intune на устройстве.</span><span class="sxs-lookup"><span data-stu-id="02e4e-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="02e4e-112">iOS-телефон или планшет</span><span class="sxs-lookup"><span data-stu-id="02e4e-112">iOS phone or tablet</span></span>

- <span data-ttu-id="02e4e-113">Убедитесь, что вы создали сертификат apNs.</span><span class="sxs-lookup"><span data-stu-id="02e4e-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="02e4e-114">Дополнительные сведения см. в [справке Создание сертификата APNs для устройств с iOS.](create-an-apns-certificate-for-ios-devices.md)</span><span class="sxs-lookup"><span data-stu-id="02e4e-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>

- <span data-ttu-id="02e4e-115">В **Параметры**   >  **общем**   >  **профиле (или управлении устройствами)** убедитесь, что профиль управления еще не установлен.</span><span class="sxs-lookup"><span data-stu-id="02e4e-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="02e4e-116">Если это так, удалите его.</span><span class="sxs-lookup"><span data-stu-id="02e4e-116">If it is, remove it.</span></span>

- <span data-ttu-id="02e4e-117">Если вы видите сообщение об ошибке, "устройство не зарегистрировалось", вопишитесь в Microsoft 365 и убедитесь, что лицензия, включаемая Exchange Online, была назначена пользователю, который входит на устройство.</span><span class="sxs-lookup"><span data-stu-id="02e4e-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="02e4e-118">Если вы видите сообщение об ошибке, "Профиль не удалось установить", попробуйте одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="02e4e-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>

    - <span data-ttu-id="02e4e-119">Убедитесь, что Safari является браузером по умолчанию на устройстве и чтобы файлы cookie не были отключены.</span><span class="sxs-lookup"><span data-stu-id="02e4e-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>

    - <span data-ttu-id="02e4e-120">Перезагружайте устройство и перейдите к portal.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="02e4e-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="02e4e-121">Войтесь с Microsoft 365 и паролем пользователя и попытайтесь установить профиль вручную.</span><span class="sxs-lookup"><span data-stu-id="02e4e-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>

## <a name="windows-rt"></a><span data-ttu-id="02e4e-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="02e4e-122">Windows RT</span></span>

- <span data-ttu-id="02e4e-123">Убедитесь, что домен настроен в Microsoft 365 для работы с Basic Mobility и Security.</span><span class="sxs-lookup"><span data-stu-id="02e4e-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="02e4e-124">Дополнительные сведения см. [в сайте Настройка базовой мобильности и безопасности.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="02e4e-124">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="02e4e-125">Убедитесь, что пользователь выбирает **включить,** а   не **присоединяться**.</span><span class="sxs-lookup"><span data-stu-id="02e4e-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>

## <a name="windows-10-pc"></a><span data-ttu-id="02e4e-126">Windows 10 PC</span><span class="sxs-lookup"><span data-stu-id="02e4e-126">Windows 10 PC</span></span>

- <span data-ttu-id="02e4e-127">Убедитесь, что домен настроен в Microsoft 365 для работы с Basic Mobility и Security.</span><span class="sxs-lookup"><span data-stu-id="02e4e-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="02e4e-128">Дополнительные сведения см. [в сайте Настройка базовой мобильности и безопасности.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="02e4e-128">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="02e4e-129">Если у вас Azure Active Directory Premium, убедитесь, что пользователь \*\*\*\* выбирает Только регистрация в управлении устройствами, а не    **Подключение**.</span><span class="sxs-lookup"><span data-stu-id="02e4e-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="02e4e-130">Android-телефон или планшет</span><span class="sxs-lookup"><span data-stu-id="02e4e-130">Android phone or tablet</span></span>

- <span data-ttu-id="02e4e-131">Убедитесь, что устройство работает под управлением Android 4.4 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="02e4e-131">Make sure the device is running Android 4.4 or later.</span></span>

- <span data-ttu-id="02e4e-132">Убедитесь, что Chrome устарел и настроен как браузер по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="02e4e-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>

- <span data-ttu-id="02e4e-133">Если вы видите сообщение об ошибке, "Мы не могли зарегистрировать это устройство", вопишитесь в Microsoft 365 и убедитесь, что лицензия, включаемая Exchange Online, была назначена пользователю, который входит на устройство.</span><span class="sxs-lookup"><span data-stu-id="02e4e-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="02e4e-134">Проверьте область уведомлений на устройстве, чтобы узнать, не ожидаются ли необходимые действия конечных пользователей и если они есть, выполните действия.</span><span class="sxs-lookup"><span data-stu-id="02e4e-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>