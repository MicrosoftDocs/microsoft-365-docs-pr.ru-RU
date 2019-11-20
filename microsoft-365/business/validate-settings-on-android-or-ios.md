---
title: Проверка параметров защиты приложений на устройствах с Android или iOS
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Learn how to validate the Microsoft 365 Business app protection settings in your Android or iOS devices.
ms.openlocfilehash: 3879084b42e8c00cc4abcd86c1a3d6761c0697a6
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2019
ms.locfileid: "38718906"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="3781e-103">Проверка параметров защиты приложений на устройствах с Android или iOS</span><span class="sxs-lookup"><span data-stu-id="3781e-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="3781e-104">Следуйте инструкциям, приведенным в следующих разделах, чтобы проверить параметры защиты приложений на устройствах с Android или iOS.</span><span class="sxs-lookup"><span data-stu-id="3781e-104">Follow the instructions in the following sections to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="android"></a><span data-ttu-id="3781e-105">Android</span><span class="sxs-lookup"><span data-stu-id="3781e-105">Android</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="3781e-106">Проверка работы параметров защиты приложений на устройствах пользователя</span><span class="sxs-lookup"><span data-stu-id="3781e-106">Check that the app protection settings are working on user devices</span></span>

<span data-ttu-id="3781e-107">[Настроив конфигурацию приложений для устройств с Android](app-protection-settings-for-android-and-ios.md) для защиты приложений, проверьте, работают ли выбранные параметры, с помощью инструкций ниже.</span><span class="sxs-lookup"><span data-stu-id="3781e-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="3781e-108">Сначала убедитесь, что политика применяется к приложению, в котором вы собираетесь проверить его.</span><span class="sxs-lookup"><span data-stu-id="3781e-108">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="3781e-109">В [центре администрирования](https://portal.office.com) Microsoft 365 Business выберите **Политики** \> **Изменить политику**.</span><span class="sxs-lookup"><span data-stu-id="3781e-109">In the Microsoft 365 Business [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="3781e-110">Выберите **Политика приложений для Android** для параметров, созданных при установке, или другую созданную политику и убедитесь, что она применяется для Outlook, например.</span><span class="sxs-lookup"><span data-stu-id="3781e-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook, for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="3781e-112">Проверка запроса ПИН-кода или отпечатка пальца для доступа к приложениям Office</span><span class="sxs-lookup"><span data-stu-id="3781e-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="3781e-113">На панели **Изменение политики** рядом с параметром **Управление доступом к документам Office** нажмите **Изменить**, разверните раздел **Контроль над доступом пользователей к файлам Office с мобильных устройств** и убедитесь, что **включен** параметр **Запрашивать ПИН-код или отпечаток пальца для доступа к приложениям Office**.</span><span class="sxs-lookup"><span data-stu-id="3781e-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Убедитесь, что для параметра требовать ПИН-код или отпечаток для доступа к приложениям Office задано значение Вкл.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="3781e-115">На пользовательском устройстве с Android откройте приложение Outlook и войдите в него с учетными данными пользователя Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="3781e-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="3781e-116">Кроме того, вам будет предложено ввести ПИН-код или использовать отпечаток пальца.</span><span class="sxs-lookup"><span data-stu-id="3781e-116">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="3781e-118">Проверка сброса ПИН-кода после нескольких неудачных попыток</span><span class="sxs-lookup"><span data-stu-id="3781e-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="3781e-119">В области **Политика изменения** нажмите кнопку **изменить** рядом с **элементом Управление доступом к документам Office**, разверните **Управление доступом пользователей к файлам Office на мобильных устройствах**и убедитесь, что **ПИН-код сбрасывается после количества неудачных попыток** , для которых задано количество неудачных попыток.</span><span class="sxs-lookup"><span data-stu-id="3781e-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="3781e-120">По умолчанию это 5.</span><span class="sxs-lookup"><span data-stu-id="3781e-120">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="3781e-121">На пользовательском устройстве с Android откройте приложение Outlook и войдите в него с учетными данными пользователя Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="3781e-121">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="3781e-122">Введите неправильный ПИН-код указанное в политике количество раз.</span><span class="sxs-lookup"><span data-stu-id="3781e-122">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="3781e-123">Вы увидите сообщение о том, что **достигнуто максимальное количество попыток ПИН-** кода, чтобы сбросить ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="3781e-123">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="3781e-125">Нажмите кнопку **Сброс ПИН-кода**.</span><span class="sxs-lookup"><span data-stu-id="3781e-125">Press **Reset PIN**.</span></span> <span data-ttu-id="3781e-126">Вам будет предложено войти в систему, используя учетные данные пользователя Microsoft 365, а затем указать новый ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="3781e-126">You'll be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="3781e-127">Проверка принудительного сохранения всех рабочих файлов в OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3781e-127">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="3781e-128">На панели **Изменение политики** рядом с параметром **Защита от потери или кражи устройств** нажмите **Изменить**, разверните раздел **Защита рабочих файлов при краже или потере устройств** и убедитесь, что **включен** параметр **Обеспечить принудительное сохранение всех рабочих файлов пользователей в OneDrive для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="3781e-128">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="3781e-130">На пользовательском устройстве с Android откройте приложение Outlook, войдите в него с учетными данными пользователя Office 365 бизнес и введите ПИН-код, если появится соответствующий запрос.</span><span class="sxs-lookup"><span data-stu-id="3781e-130">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="3781e-131">Откройте сообщение электронной почты с вложением и коснитесь значка со стрелкой вниз рядом со сведениями о вложении.</span><span class="sxs-lookup"><span data-stu-id="3781e-131">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="3781e-133">В нижней части экрана вы увидите команду **сохранить на устройстве** .</span><span class="sxs-lookup"><span data-stu-id="3781e-133">You'll see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="3781e-135">Сохранение в OneDrive для бизнеса сейчас не включено для Android, поэтому вы можете только увидеть, что локальное сохранение заблокировано.</span><span class="sxs-lookup"><span data-stu-id="3781e-135">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="3781e-136">Проверка требования повторного входа при неактивности приложений Office в течение указанного времени</span><span class="sxs-lookup"><span data-stu-id="3781e-136">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="3781e-137">В области " **изменение политики** " выберите пункт **изменить** рядом с **элементом Управление доступом к документам Office**, разверните **Управление доступом пользователей к файлам Office на мобильных устройствах**и убедитесь, что пользователям требуется **повторно входить в систему после неактивности для приложений Office** в течение определенного количества минут.</span><span class="sxs-lookup"><span data-stu-id="3781e-137">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="3781e-138">По умолчанию это 30 минут.</span><span class="sxs-lookup"><span data-stu-id="3781e-138">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="3781e-139">На пользовательском устройстве с Android откройте приложение Outlook, войдите в него с учетными данными пользователя Office 365 бизнес и введите ПИН-код, если появится соответствующий запрос.</span><span class="sxs-lookup"><span data-stu-id="3781e-139">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="3781e-p105">Вы должны увидеть папку входящих сообщений в Outlook. Оставьте устройство с Android в неактивном состоянии в течение 30 минут (или другого количества времени, превышающего указанное в политике). Скорее всего, экран устройства погаснет.</span><span class="sxs-lookup"><span data-stu-id="3781e-p105">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="3781e-143">Снова получите доступ к Outlook на устройстве с Android.</span><span class="sxs-lookup"><span data-stu-id="3781e-143">Access Outlook on the Android device again.</span></span>
    
4. <span data-ttu-id="3781e-144">Вам будет предложено ввести ПИН-код, прежде чем вы сможете снова получить доступ к Outlook.</span><span class="sxs-lookup"><span data-stu-id="3781e-144">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="3781e-145">Проверка защиты рабочих файлов шифрованием</span><span class="sxs-lookup"><span data-stu-id="3781e-145">Validate Protect work files with encryption</span></span>

<span data-ttu-id="3781e-146">На панели **Изменение политики** рядом с параметром **Защита от потери или кражи устройств** нажмите **Изменить**, разверните раздел **Защита рабочих файлов при краже или потере устройств** и убедитесь, что параметр **Шифровать рабочие файлы**  **включен**, а параметр **Обеспечить принудительное сохранение всех рабочих файлов пользователей в OneDrive для бизнеса**  **выключен**.</span><span class="sxs-lookup"><span data-stu-id="3781e-146">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="3781e-147">На пользовательском устройстве с Android откройте приложение Outlook, войдите в него с учетными данными пользователя Office 365 бизнес и введите ПИН-код, если появится соответствующий запрос.</span><span class="sxs-lookup"><span data-stu-id="3781e-147">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="3781e-148">Откройте сообщение электронной почты, которое содержит несколько вложенных файлов изображений.</span><span class="sxs-lookup"><span data-stu-id="3781e-148">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="3781e-149">Коснитесь значка со стрелкой вниз рядом с вложением, чтобы сохранить его.</span><span class="sxs-lookup"><span data-stu-id="3781e-149">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="3781e-p106">Вам будет предложено разрешить приложению Outlook доступ к фотографиям, мультимедийным и прочим файлам на устройстве. Нажмите **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="3781e-p106">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="3781e-153">Внизу экрана выберите команду **Сохранить на устройстве** и откройте приложение **Галерея**.</span><span class="sxs-lookup"><span data-stu-id="3781e-153">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="3781e-p107">Вы должны увидеть в списке зашифрованную фотографию (или несколько, если сохранили несколько вложенных файлов изображений). В списке изображений она может отображаться в виде серого квадрата, в центре которого изображен белый восклицательный знак внутри белой окружности.</span><span class="sxs-lookup"><span data-stu-id="3781e-p107">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a><span data-ttu-id="3781e-157">iOS</span><span class="sxs-lookup"><span data-stu-id="3781e-157">iOS</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="3781e-158">Проверка работоспособности параметров защиты приложений на пользовательских устройствах</span><span class="sxs-lookup"><span data-stu-id="3781e-158">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="3781e-159">[Настроив конфигурацию приложений для устройств с iOS](app-protection-settings-for-android-and-ios.md) для защиты приложений, проверьте, работают ли выбранные параметры, с помощью инструкций ниже.</span><span class="sxs-lookup"><span data-stu-id="3781e-159">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="3781e-160">Сначала убедитесь, что политика применяется к приложению, в котором вы собираетесь проверить его.</span><span class="sxs-lookup"><span data-stu-id="3781e-160">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="3781e-161">В [центре администрирования](https://portal.office.com) Microsoft 365 Business выберите **Политики** \> **Изменить политику**.</span><span class="sxs-lookup"><span data-stu-id="3781e-161">In the Microsoft 365 Business [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="3781e-162">Выберите **Политика приложений для iOS** для параметров, созданных при установке, или другую созданную политику и убедитесь, что она применяется для Outlook, например.</span><span class="sxs-lookup"><span data-stu-id="3781e-162">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="3781e-164">Проверка запроса ПИН-кода для доступа к приложениям Office</span><span class="sxs-lookup"><span data-stu-id="3781e-164">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="3781e-165">На панели **Изменение политики** рядом с параметром **Управление доступом к документам Office** нажмите **Изменить**, разверните раздел **Контроль над доступом пользователей к файлам Office с мобильных устройств** и убедитесь, что **включен** параметр **Запрашивать ПИН-код или отпечаток пальца для доступа к приложениям Office**.</span><span class="sxs-lookup"><span data-stu-id="3781e-165">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Убедитесь, что для параметра требовать ПИН-код или отпечаток для доступа к приложениям Office задано значение Вкл.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="3781e-167">На пользовательском устройстве с iOS откройте приложение Outlook и войдите в него с учетными данными пользователя Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="3781e-167">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="3781e-168">Кроме того, вам будет предложено ввести ПИН-код или использовать отпечаток пальца.</span><span class="sxs-lookup"><span data-stu-id="3781e-168">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="3781e-170">Проверка сброса ПИН-кода после нескольких неудачных попыток</span><span class="sxs-lookup"><span data-stu-id="3781e-170">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="3781e-171">В области **Политика изменения** нажмите кнопку **изменить** рядом с **элементом Управление доступом к документам Office**, разверните **Управление доступом пользователей к файлам Office на мобильных устройствах**и убедитесь, что **ПИН-код сбрасывается после количества неудачных попыток** , для которых задано количество неудачных попыток.</span><span class="sxs-lookup"><span data-stu-id="3781e-171">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="3781e-172">По умолчанию это 5.</span><span class="sxs-lookup"><span data-stu-id="3781e-172">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="3781e-173">На пользовательском устройстве с iOS откройте приложение Outlook и войдите в него с учетными данными пользователя Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="3781e-173">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="3781e-174">Введите неправильный ПИН-код указанное в политике количество раз.</span><span class="sxs-lookup"><span data-stu-id="3781e-174">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="3781e-175">Вы увидите сообщение о том, что **достигнуто максимальное количество попыток ПИН-** кода, чтобы сбросить ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="3781e-175">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="3781e-177">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3781e-177">Press **OK**.</span></span> <span data-ttu-id="3781e-178">Вам будет предложено войти в систему, используя учетные данные пользователя Microsoft 365, а затем указать новый ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="3781e-178">You'll be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="3781e-179">Проверка принудительного сохранения всех рабочих файлов в OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3781e-179">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="3781e-180">На панели **Изменение политики** рядом с параметром **Защита от потери или кражи устройств** нажмите **Изменить**, разверните раздел **Защита рабочих файлов при краже или потере устройств** и убедитесь, что **включен** параметр **Обеспечить принудительное сохранение всех рабочих файлов пользователей в OneDrive для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="3781e-180">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="3781e-182">На пользовательском устройстве с iOS откройте приложение Outlook, войдите в него с учетными данными пользователя Office 365 бизнес и введите ПИН-код, если появится соответствующий запрос.</span><span class="sxs-lookup"><span data-stu-id="3781e-182">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="3781e-183">Откройте сообщение электронной почты с вложением, откройте вложение и внизу экрана нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3781e-183">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="3781e-185">У вас должен быть только один вариант  OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3781e-185">You should only see an option for OneDrive for Business.</span></span> <span data-ttu-id="3781e-186">В противном случае нажмите кнопку **Добавить учетную запись** и выберите **OneDrive для бизнеса** в окне **Добавление учетной записи хранения** .</span><span class="sxs-lookup"><span data-stu-id="3781e-186">If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen.</span></span> <span data-ttu-id="3781e-187">При появлении соответствующего запроса укажите учетные данные пользователя Office 365 бизнес для входа.</span><span class="sxs-lookup"><span data-stu-id="3781e-187">Provide the end user's Microsoft 365 Business to sign in when prompted.</span></span> 
    
    <span data-ttu-id="3781e-188">Нажмите **Сохранить** и выберите **OneDrive для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="3781e-188">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="3781e-189">Проверка требования повторного входа при неактивности приложений Office в течение указанного времени</span><span class="sxs-lookup"><span data-stu-id="3781e-189">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="3781e-190">В области " **изменение политики** " выберите пункт **изменить** рядом с **элементом Управление доступом к документам Office**, разверните **Управление доступом пользователей к файлам Office на мобильных устройствах**и убедитесь, что пользователям требуется **повторно входить в систему после неактивности для приложений Office** в течение определенного количества минут.</span><span class="sxs-lookup"><span data-stu-id="3781e-190">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="3781e-191">По умолчанию это 30 минут.</span><span class="sxs-lookup"><span data-stu-id="3781e-191">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="3781e-192">На пользовательском устройстве с iOS откройте приложение Outlook, войдите в него с учетными данными пользователя Office 365 бизнес и введите ПИН-код, если появится соответствующий запрос.</span><span class="sxs-lookup"><span data-stu-id="3781e-192">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="3781e-p113">Вы должны увидеть папку входящих сообщений в Outlook. Не трогайте устройство с iOS в течение 30 минут (или другого количества времени, превышающего указанное в политике). Скорее всего, экран устройства погаснет.</span><span class="sxs-lookup"><span data-stu-id="3781e-p113">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="3781e-196">Снова получите доступ к Outlook на устройстве iOS.</span><span class="sxs-lookup"><span data-stu-id="3781e-196">Access Outlook on the iOS device again.</span></span>
    
4. <span data-ttu-id="3781e-197">Вам будет предложено ввести ПИН-код, прежде чем вы сможете снова получить доступ к Outlook.</span><span class="sxs-lookup"><span data-stu-id="3781e-197">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="3781e-198">Проверка защиты рабочих файлов шифрованием</span><span class="sxs-lookup"><span data-stu-id="3781e-198">Validate Protect work files with encryption</span></span>

<span data-ttu-id="3781e-199">На панели **Изменение политики** рядом с параметром **Защита от потери или кражи устройств** нажмите **Изменить**, разверните раздел **Защита рабочих файлов при краже или потере устройств** и убедитесь, что параметр **Шифровать рабочие файлы**  **включен**, а параметр **Обеспечить принудительное сохранение всех рабочих файлов пользователей в OneDrive для бизнеса**  **выключен**.</span><span class="sxs-lookup"><span data-stu-id="3781e-199">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="3781e-200">На пользовательском устройстве с iOS откройте приложение Outlook, войдите в него с учетными данными пользователя Office 365 бизнес и введите ПИН-код, если появится соответствующий запрос.</span><span class="sxs-lookup"><span data-stu-id="3781e-200">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="3781e-201">Откройте сообщение электронной почты, которое содержит несколько вложенных файлов изображений.</span><span class="sxs-lookup"><span data-stu-id="3781e-201">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="3781e-202">Нажмите вложение, а затем команду **Сохранить** под ним.</span><span class="sxs-lookup"><span data-stu-id="3781e-202">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="3781e-p114">На главном экране откройте приложение **Фотографии**. Вы должны увидеть в списке сохраненную и зашифрованную фотографию (или несколько, если сохранили несколько вложенных файлов изображений).</span><span class="sxs-lookup"><span data-stu-id="3781e-p114">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

