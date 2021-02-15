---
title: Устранение неполадок базовой мобильности и безопасности
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
description: Попробуйте следующие действия для отслеживания проблем с базовой мобильностью и безопасностью
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876856"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="233b8-103">Устранение неполадок базовой мобильности и безопасности</span><span class="sxs-lookup"><span data-stu-id="233b8-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="233b8-104">Если у вас возникла проблема при попытке зарегистрировать устройство в Basic Mobility and Security, попробуйте найти эту проблему.</span><span class="sxs-lookup"><span data-stu-id="233b8-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="233b8-105">Если общие действия не устраняют проблему, см. один из последующих разделов с конкретными действиями для вашего типа устройства.</span><span class="sxs-lookup"><span data-stu-id="233b8-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="233b8-106">Действия, которые необходимо предпринять в первую очередь</span><span class="sxs-lookup"><span data-stu-id="233b8-106">Steps to try first</span></span>

<span data-ttu-id="233b8-107">Чтобы начать, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="233b8-107">To start, check the following:</span></span>

- <span data-ttu-id="233b8-108">Убедитесь, что устройство еще не зарегистрировать у другого поставщика управления мобильными устройствами, например Intune.</span><span class="sxs-lookup"><span data-stu-id="233b8-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>

- <span data-ttu-id="233b8-109">Убедитесь, что на устройстве установлены правильные дата и время.</span><span class="sxs-lookup"><span data-stu-id="233b8-109">Make sure that the device is set to the correct date and time.</span></span>

- <span data-ttu-id="233b8-110">Переключение на другую сеть WIFI или сотовую сеть на устройстве.</span><span class="sxs-lookup"><span data-stu-id="233b8-110">Switch to a different WIFI or cellular network on the device.</span></span>

- <span data-ttu-id="233b8-111">Для устройств с Android или iOS можно удалить и переустановить приложение "Портал компании Intune" на устройстве.</span><span class="sxs-lookup"><span data-stu-id="233b8-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="233b8-112">Телефон или планшет с iOS</span><span class="sxs-lookup"><span data-stu-id="233b8-112">iOS phone or tablet</span></span>

- <span data-ttu-id="233b8-113">Убедитесь, что вы настроили сертификат APNs.</span><span class="sxs-lookup"><span data-stu-id="233b8-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="233b8-114">Дополнительные сведения см. в [справке по созданию сертификата APNs для устройств с iOS.](create-an-apns-certificate-for-ios-devices.md)</span><span class="sxs-lookup"><span data-stu-id="233b8-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>

- <span data-ttu-id="233b8-115">В **параметрах** общего профиля (или управления устройствами)   >  \*\*\*\*   >  \*\*\*\* убедитесь, что профиль управления еще не установлен.</span><span class="sxs-lookup"><span data-stu-id="233b8-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="233b8-116">Если да, удалите его.</span><span class="sxs-lookup"><span data-stu-id="233b8-116">If it is, remove it.</span></span>

- <span data-ttu-id="233b8-117">Если вы видите сообщение об ошибке "Устройство не зарегистрировалось", войдут в Microsoft 365 и убедитесь, что пользователю, выписавшего устройство, назначена лицензия, включаемая Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="233b8-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="233b8-118">Если вы видите сообщение об ошибке "Не удалось установить профиль", попробуйте одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="233b8-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>

    - <span data-ttu-id="233b8-119">Убедитесь, что Safari является браузером по умолчанию на устройстве и файлы cookie не отключены.</span><span class="sxs-lookup"><span data-stu-id="233b8-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>

    - <span data-ttu-id="233b8-120">Перезагружайте устройство и перейдите к portal.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="233b8-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="233b8-121">Во sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span><span class="sxs-lookup"><span data-stu-id="233b8-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>

## <a name="windows-rt"></a><span data-ttu-id="233b8-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="233b8-122">Windows RT</span></span>

- <span data-ttu-id="233b8-123">Убедитесь, что ваш домен настроен в Microsoft 365 для работы с базовой мобильностью и безопасностью.</span><span class="sxs-lookup"><span data-stu-id="233b8-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="233b8-124">Дополнительные сведения см. в [подстройки "Настройка базовой мобильности и безопасности".](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="233b8-124">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="233b8-125">Убедитесь, что пользователь выбирает **"Включить",**   а не "Присоединиться". \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="233b8-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>

## <a name="windows-10-pc"></a><span data-ttu-id="233b8-126">Компьютер с Windows 10</span><span class="sxs-lookup"><span data-stu-id="233b8-126">Windows 10 PC</span></span>

- <span data-ttu-id="233b8-127">Убедитесь, что ваш домен настроен в Microsoft 365 для работы с базовой мобильностью и безопасностью.</span><span class="sxs-lookup"><span data-stu-id="233b8-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="233b8-128">Дополнительные сведения [см. в подстройки "Настройка базовой мобильности и безопасности".](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="233b8-128">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="233b8-129">Если у вас нет Azure Active Directory Premium, \*\*\*\* убедитесь, что пользователь выбирает только регистрацию в службе управления устройствами, а не   подключение. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="233b8-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="233b8-130">Телефон или планшет с Android</span><span class="sxs-lookup"><span data-stu-id="233b8-130">Android phone or tablet</span></span>

- <span data-ttu-id="233b8-131">Убедитесь, что устройство работает под управлением Android 4.4 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="233b8-131">Make sure the device is running Android 4.4 or later.</span></span>

- <span data-ttu-id="233b8-132">Убедитесь, что Браузер Chrome установлен в качестве браузера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="233b8-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>

- <span data-ttu-id="233b8-133">Если вы видите сообщение об ошибке "Нам не удалось зарегистрировать это устройство", войдут в Microsoft 365 и убедитесь, что пользователю, выписавшего устройство, назначена лицензия, включаемая Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="233b8-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="233b8-134">Проверьте область уведомлений на устройстве, чтобы узнать, ожидаются ли какие-либо необходимые действия конечных пользователей и если они есть, выполнить эти действия.</span><span class="sxs-lookup"><span data-stu-id="233b8-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>