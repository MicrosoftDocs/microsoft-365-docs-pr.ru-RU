---
title: Устранение неполадок с основной мобильностью и безопасностью
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
description: Выполните указанные ниже действия, чтобы отследить основные проблемы с мобильностью и безопасностью
ms.openlocfilehash: 43e7533e598f769dd5f2bcae28c4252f96a9be76
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430275"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="dfbac-103">Устранение неполадок с основной мобильностью и безопасностью</span><span class="sxs-lookup"><span data-stu-id="dfbac-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="dfbac-104">Если при попытке зарегистрировать устройство в базовом мобильном доступе и безопасности возникли проблемы, выполните действия, описанные в этой статье, чтобы проследить проблему.</span><span class="sxs-lookup"><span data-stu-id="dfbac-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="dfbac-105">Если общие действия не устранили проблему, ознакомьтесь с одним из следующих разделов, посвященных определенным действиям для типа устройства.</span><span class="sxs-lookup"><span data-stu-id="dfbac-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="dfbac-106">Действия для первой попытки</span><span class="sxs-lookup"><span data-stu-id="dfbac-106">Steps to try first</span></span>

<span data-ttu-id="dfbac-107">Для начала проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="dfbac-107">To start, check the following:</span></span>

- <span data-ttu-id="dfbac-108">Убедитесь, что устройство еще не зарегистрировано другим поставщиком управления мобильными устройствами, например Intune.</span><span class="sxs-lookup"><span data-stu-id="dfbac-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>
    
- <span data-ttu-id="dfbac-109">Убедитесь, что для устройства заданы правильные дата и время.</span><span class="sxs-lookup"><span data-stu-id="dfbac-109">Make sure that the device is set to the correct date and time.</span></span>
    
- <span data-ttu-id="dfbac-110">Переключитесь на другую сеть Wi-Fi или сотовую сеть на устройстве.</span><span class="sxs-lookup"><span data-stu-id="dfbac-110">Switch to a different WIFI or cellular network on the device.</span></span>
    
- <span data-ttu-id="dfbac-111">Для устройств с Android или iOS удалите и повторно установите приложение корпоративного портала Intune на устройстве.</span><span class="sxs-lookup"><span data-stu-id="dfbac-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="dfbac-112">Телефон или планшет для iOS</span><span class="sxs-lookup"><span data-stu-id="dfbac-112">iOS phone or tablet</span></span>

- <span data-ttu-id="dfbac-113">Убедитесь, что вы настроили сертификат APNs.</span><span class="sxs-lookup"><span data-stu-id="dfbac-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="dfbac-114">Более подробную информацию можно узнать в статье [Создание сертификата APNs для устройств с iOS](create-an-apns-certificate-for-ios-devices.md).</span><span class="sxs-lookup"><span data-stu-id="dfbac-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>
    
- <span data-ttu-id="dfbac-115">В окне **Параметры**   >  **Общий**   >  **профиль (или управление устройствами)** убедитесь, что профиль управления еще не установлен.</span><span class="sxs-lookup"><span data-stu-id="dfbac-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="dfbac-116">Если это так, удалите его.</span><span class="sxs-lookup"><span data-stu-id="dfbac-116">If it is, remove it.</span></span>
    
- <span data-ttu-id="dfbac-117">Если отображается сообщение об ошибке: "устройство не может быть зарегистрировано", войдите в Microsoft 365 и убедитесь, что для пользователя, выполнившего вход на устройство, назначена лицензия, включающая Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dfbac-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="dfbac-118">Если отображается сообщение об ошибке "не удалось установить профиль," выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="dfbac-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>
    
    - <span data-ttu-id="dfbac-119">Убедитесь, что Safari является браузером по умолчанию на устройстве и что файлы cookie не отключены.</span><span class="sxs-lookup"><span data-stu-id="dfbac-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>
    
    - <span data-ttu-id="dfbac-120">Перезагрузите устройство и перейдите к portal.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="dfbac-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="dfbac-121">Войдите с помощью идентификатора пользователя и пароля Microsoft 365 и попытайтесь установить профиль вручную.</span><span class="sxs-lookup"><span data-stu-id="dfbac-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>    

## <a name="windows-rt"></a><span data-ttu-id="dfbac-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="dfbac-122">Windows RT</span></span>

- <span data-ttu-id="dfbac-123">Убедитесь, что ваш домен настроен в Microsoft 365 для работы с базовыми мобильностью и безопасностью.</span><span class="sxs-lookup"><span data-stu-id="dfbac-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="dfbac-124">Более подробную информацию можно узнать в статье [Настройка базовых возможностей мобильной работы и безопасности](set-up.md).</span><span class="sxs-lookup"><span data-stu-id="dfbac-124">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="dfbac-125">Убедитесь, что пользователь выбрал параметр **включить**,   а не выбрать **Присоединение**.</span><span class="sxs-lookup"><span data-stu-id="dfbac-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>    

## <a name="windows-10-pc"></a><span data-ttu-id="dfbac-126">КОМПЬЮТЕР с Windows 10</span><span class="sxs-lookup"><span data-stu-id="dfbac-126">Windows 10 PC</span></span>

- <span data-ttu-id="dfbac-127">Убедитесь, что ваш домен настроен в Microsoft 365 для работы с базовыми мобильностью и безопасностью.</span><span class="sxs-lookup"><span data-stu-id="dfbac-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="dfbac-128">Более подробную информацию можно узнать в статье [Настройка базовых возможностей мобильной работы и безопасности](set-up.md).</span><span class="sxs-lookup"><span data-stu-id="dfbac-128">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="dfbac-129">Если вы не используете Azure Active Directory Premium, убедитесь, что пользователь выбрал **Регистрация только в разделе Управление устройствами**, а не выбрано    **Подключение**.</span><span class="sxs-lookup"><span data-stu-id="dfbac-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="dfbac-130">Телефон или планшет с Android</span><span class="sxs-lookup"><span data-stu-id="dfbac-130">Android phone or tablet</span></span>

- <span data-ttu-id="dfbac-131">Убедитесь, что на устройстве работает Android 4,4 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="dfbac-131">Make sure the device is running Android 4.4 or later.</span></span>
    
- <span data-ttu-id="dfbac-132">Убедитесь, что хром обновлен и выбран в качестве браузера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dfbac-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>
    
- <span data-ttu-id="dfbac-133">Если отображается сообщение об ошибке "не удалось зарегистрировать это устройство", войдите в Microsoft 365 и убедитесь, что для пользователя, выполнившего вход на устройство, назначена лицензия, включающая Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dfbac-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="dfbac-134">Проверьте область уведомлений на устройстве, чтобы убедиться в том, что ожидающие действия конечного пользователя ожидают, и, если они есть, выполните действия.</span><span class="sxs-lookup"><span data-stu-id="dfbac-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>