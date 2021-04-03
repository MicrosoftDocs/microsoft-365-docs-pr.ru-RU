---
title: Проверка параметров защиты приложений на устройствах Android или iOS
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Узнайте, как проверить параметры защиты приложений Microsoft 365 Бизнес Премиум на устройствах Android или iOS.
ms.openlocfilehash: a0a4a6e6cff59f66a506929e97c99d361472a68b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578074"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="44973-103">Проверка параметров защиты приложений на устройствах Android или iOS</span><span class="sxs-lookup"><span data-stu-id="44973-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="44973-104">Следуйте инструкциям в следующих разделах, чтобы проверить параметры защиты приложений на устройствах Android или iOS.</span><span class="sxs-lookup"><span data-stu-id="44973-104">Follow the instructions in the following sections to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="android"></a><span data-ttu-id="44973-105">Android</span><span class="sxs-lookup"><span data-stu-id="44973-105">Android</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="44973-106">Убедитесь, что параметры защиты приложений работают на устройствах пользователей</span><span class="sxs-lookup"><span data-stu-id="44973-106">Check that the app protection settings are working on user devices</span></span>

<span data-ttu-id="44973-107">[Настроив конфигурацию приложений для устройств с Android](app-protection-settings-for-android-and-ios.md) для защиты приложений, проверьте, работают ли выбранные параметры, с помощью инструкций ниже.</span><span class="sxs-lookup"><span data-stu-id="44973-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="44973-108">Во-первых, убедитесь, что политика применяется к приложению, в котором вы собираетесь проверить его.</span><span class="sxs-lookup"><span data-stu-id="44973-108">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="44973-109">В центре администрирования Microsoft 365 Бизнес [Премиум](https://portal.office.com)перейдите к **политике** \> **редактирования политик.**</span><span class="sxs-lookup"><span data-stu-id="44973-109">In the Microsoft 365 Business Premium [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="44973-110">Выберите **политику приложения для Android** для параметров, созданных при настройке, или другую созданную политику, и убедитесь, что она применена для Outlook, например.</span><span class="sxs-lookup"><span data-stu-id="44973-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook, for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="44973-112">Проверка запроса ПИН-кода или отпечатка пальца для доступа к приложениям Office</span><span class="sxs-lookup"><span data-stu-id="44973-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="44973-113">На панели **Изменение политики** рядом с параметром **Управление доступом к документам Office** нажмите **Изменить**, разверните раздел **Контроль над доступом пользователей к файлам Office с мобильных устройств** и убедитесь, что **включен** параметр **Запрашивать ПИН-код или отпечаток пальца для доступа к приложениям Office**.</span><span class="sxs-lookup"><span data-stu-id="44973-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Убедитесь, что для доступа к приложениям Office установлен пин-код или отпечатки пальцев.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="44973-115">На устройстве Android пользователя откройте Outlook и вопишитесь с учетными данными Microsoft 365 Business Premium пользователя.</span><span class="sxs-lookup"><span data-stu-id="44973-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="44973-116">Вам также будет предложено ввести ПИН-код или использовать отпечатки пальцев.</span><span class="sxs-lookup"><span data-stu-id="44973-116">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="44973-118">Проверка сброса ПИН-кода после нескольких неудачных попыток</span><span class="sxs-lookup"><span data-stu-id="44973-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="44973-119">В  области политики редактирования  выберите Изменить рядом с управлением доступом к документам **Office,** расширить  управление доступом пользователей к файлам **Office** на мобильных устройствах и убедитесь, что пин-код сброса после количества неудачных попыток установлен до определенного числа.</span><span class="sxs-lookup"><span data-stu-id="44973-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="44973-120">Это 5 по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44973-120">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="44973-121">На устройстве Android пользователя откройте Outlook и вопишитесь с учетными данными Microsoft 365 Business Premium пользователя.</span><span class="sxs-lookup"><span data-stu-id="44973-121">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="44973-122">Введите неправильный ПИН-код указанное в политике количество раз.</span><span class="sxs-lookup"><span data-stu-id="44973-122">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="44973-123">Вы увидите подсказку, в которую будет заявляется **ограничение попытки ПИН-кода,** достигнутое для сброса ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="44973-123">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="44973-125">Нажмите кнопку **Сброс ПИН-кода**.</span><span class="sxs-lookup"><span data-stu-id="44973-125">Press **Reset PIN**.</span></span> <span data-ttu-id="44973-126">Вам будет предложено войти с учетными данными Microsoft 365 Бизнес Премиум пользователя, а затем установить новый ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="44973-126">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="44973-127">Проверка принудительного сохранения всех рабочих файлов в OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="44973-127">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="44973-128">На панели **Изменение политики** рядом с параметром **Защита от потери или кражи устройств** нажмите **Изменить**, разверните раздел **Защита рабочих файлов при краже или потере устройств** и убедитесь, что **включен** параметр **Обеспечить принудительное сохранение всех рабочих файлов пользователей в OneDrive для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="44973-128">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="44973-130">На устройстве Android пользователя откройте Outlook и войдите с учетными данными Microsoft 365 Бизнес Премиум и введите ПИН-код по запросу.</span><span class="sxs-lookup"><span data-stu-id="44973-130">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="44973-131">Откройте сообщение электронной почты с вложением и коснитесь значка со стрелкой вниз рядом со сведениями о вложении.</span><span class="sxs-lookup"><span data-stu-id="44973-131">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="44973-133">В нижней части экрана будет **видно,** как не удается сохранить устройство.</span><span class="sxs-lookup"><span data-stu-id="44973-133">You'll see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="44973-135">Сохранение в OneDrive для бизнеса сейчас не включено для Android, поэтому вы можете только увидеть, что локальное сохранение заблокировано.</span><span class="sxs-lookup"><span data-stu-id="44973-135">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="44973-136">Проверка требования повторного входа при неактивности приложений Office в течение указанного времени</span><span class="sxs-lookup"><span data-stu-id="44973-136">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="44973-137">В  области политики редактирования  выберите Изменить рядом с управлением доступом к документам **Office,** расширить управление доступом пользователей к файлам **Office** на мобильных устройствах и убедитесь, что требуется, чтобы пользователи снова впускались после того, как приложения **Office** простаивали, задав определенное количество минут.</span><span class="sxs-lookup"><span data-stu-id="44973-137">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="44973-138">Это 30 минут по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44973-138">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="44973-139">На устройстве Android пользователя откройте Outlook и войдите с учетными данными Microsoft 365 Бизнес Премиум и введите ПИН-код по запросу.</span><span class="sxs-lookup"><span data-stu-id="44973-139">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="44973-p105">Вы должны увидеть папку входящих сообщений в Outlook. Оставьте устройство с Android в неактивном состоянии в течение 30 минут (или другого количества времени, превышающего указанное в политике). Скорее всего, экран устройства погаснет.</span><span class="sxs-lookup"><span data-stu-id="44973-p105">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="44973-143">Снова доступ к Outlook на устройстве Android.</span><span class="sxs-lookup"><span data-stu-id="44973-143">Access Outlook on the Android device again.</span></span>
    
4. <span data-ttu-id="44973-144">Вам будет предложено ввести ПИН-код, прежде чем снова получить доступ к Outlook.</span><span class="sxs-lookup"><span data-stu-id="44973-144">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="44973-145">Проверка защиты рабочих файлов шифрованием</span><span class="sxs-lookup"><span data-stu-id="44973-145">Validate Protect work files with encryption</span></span>

<span data-ttu-id="44973-146">На панели **Изменение политики** рядом с параметром **Защита от потери или кражи устройств** нажмите **Изменить**, разверните раздел **Защита рабочих файлов при краже или потере устройств** и убедитесь, что параметр **Шифровать рабочие файлы**  **включен**, а параметр **Обеспечить принудительное сохранение всех рабочих файлов пользователей в OneDrive для бизнеса**  **выключен**.</span><span class="sxs-lookup"><span data-stu-id="44973-146">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="44973-147">На устройстве Android пользователя откройте Outlook и войдите с учетными данными Microsoft 365 Бизнес Премиум и введите ПИН-код по запросу.</span><span class="sxs-lookup"><span data-stu-id="44973-147">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="44973-148">Откройте электронную почту, содержаную несколько вложений в файл изображений.</span><span class="sxs-lookup"><span data-stu-id="44973-148">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="44973-149">Коснитесь значка со стрелкой вниз рядом с вложением, чтобы сохранить его.</span><span class="sxs-lookup"><span data-stu-id="44973-149">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="44973-p106">Вам будет предложено разрешить приложению Outlook доступ к фотографиям, мультимедийным и прочим файлам на устройстве. Нажмите **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="44973-p106">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="44973-153">Внизу экрана выберите команду **Сохранить на устройстве** и откройте приложение **Галерея**.</span><span class="sxs-lookup"><span data-stu-id="44973-153">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="44973-p107">Вы должны увидеть в списке зашифрованную фотографию (или несколько, если сохранили несколько вложенных файлов изображений). В списке изображений она может отображаться в виде серого квадрата, в центре которого изображен белый восклицательный знак внутри белой окружности.</span><span class="sxs-lookup"><span data-stu-id="44973-p107">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a><span data-ttu-id="44973-157">iOS</span><span class="sxs-lookup"><span data-stu-id="44973-157">iOS</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="44973-158">Проверка работоспособности параметров защиты приложений на пользовательских устройствах</span><span class="sxs-lookup"><span data-stu-id="44973-158">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="44973-159">[Настроив конфигурацию приложений для устройств с iOS](app-protection-settings-for-android-and-ios.md) для защиты приложений, проверьте, работают ли выбранные параметры, с помощью инструкций ниже.</span><span class="sxs-lookup"><span data-stu-id="44973-159">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="44973-160">Во-первых, убедитесь, что политика применяется к приложению, в котором вы собираетесь проверить его.</span><span class="sxs-lookup"><span data-stu-id="44973-160">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="44973-161">В центре администрирования Microsoft 365 Бизнес [Премиум](https://portal.office.com)перейдите к **политике** \> **редактирования политик.**</span><span class="sxs-lookup"><span data-stu-id="44973-161">In the Microsoft 365 Business Premium [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="44973-162">Выберите **политику приложения для iOS** для параметров, созданных при установке, или другую созданную политику, и убедитесь, что она применена для Outlook, например.</span><span class="sxs-lookup"><span data-stu-id="44973-162">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="44973-164">Проверка запроса ПИН-кода для доступа к приложениям Office</span><span class="sxs-lookup"><span data-stu-id="44973-164">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="44973-165">На панели **Изменение политики** рядом с параметром **Управление доступом к документам Office** нажмите **Изменить**, разверните раздел **Контроль над доступом пользователей к файлам Office с мобильных устройств** и убедитесь, что **включен** параметр **Запрашивать ПИН-код или отпечаток пальца для доступа к приложениям Office**.</span><span class="sxs-lookup"><span data-stu-id="44973-165">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Убедитесь, что для доступа к приложениям Office установлен пин-код или отпечатки пальцев.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="44973-167">На устройстве iOS пользователя откройте Outlook и вопишитесь с учетными данными Microsoft 365 Business Premium пользователя.</span><span class="sxs-lookup"><span data-stu-id="44973-167">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="44973-168">Вам также будет предложено ввести ПИН-код или использовать отпечатки пальцев.</span><span class="sxs-lookup"><span data-stu-id="44973-168">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="44973-170">Проверка сброса ПИН-кода после нескольких неудачных попыток</span><span class="sxs-lookup"><span data-stu-id="44973-170">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="44973-171">В  области политики редактирования  выберите Изменить рядом с управлением доступом к документам **Office,** расширить  управление доступом пользователей к файлам **Office** на мобильных устройствах и убедитесь, что пин-код сброса после количества неудачных попыток установлен до определенного числа.</span><span class="sxs-lookup"><span data-stu-id="44973-171">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="44973-172">Это 5 по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44973-172">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="44973-173">На устройстве iOS пользователя откройте Outlook и вопишитесь с учетными данными Microsoft 365 Business Premium пользователя.</span><span class="sxs-lookup"><span data-stu-id="44973-173">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="44973-174">Введите неправильный ПИН-код указанное в политике количество раз.</span><span class="sxs-lookup"><span data-stu-id="44973-174">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="44973-175">Вы увидите подсказку, в которую будет заявляется **ограничение попытки ПИН-кода,** достигнутое для сброса ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="44973-175">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="44973-177">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="44973-177">Press **OK**.</span></span> <span data-ttu-id="44973-178">Вам будет предложено войти с учетными данными Microsoft 365 Бизнес Премиум пользователя, а затем установить новый ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="44973-178">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="44973-179">Проверка принудительного сохранения всех рабочих файлов в OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="44973-179">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="44973-180">На панели **Изменение политики** рядом с параметром **Защита от потери или кражи устройств** нажмите **Изменить**, разверните раздел **Защита рабочих файлов при краже или потере устройств** и убедитесь, что **включен** параметр **Обеспечить принудительное сохранение всех рабочих файлов пользователей в OneDrive для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="44973-180">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="44973-182">На устройстве iOS пользователя откройте Outlook и войдите в него с учетными данными Microsoft 365 Бизнес Премиум и введите ПИН-код по запросу.</span><span class="sxs-lookup"><span data-stu-id="44973-182">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="44973-183">Откройте сообщение электронной почты с вложением, откройте вложение и внизу экрана нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="44973-183">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="44973-185">У вас должен быть только один вариант  OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="44973-185">You should only see an option for OneDrive for Business.</span></span> <span data-ttu-id="44973-186">Если нет, нажмите **кнопку Добавить учетную** запись и выберите **OneDrive для бизнеса** с экрана **учетной записи добавить** хранилище.</span><span class="sxs-lookup"><span data-stu-id="44973-186">If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen.</span></span> <span data-ttu-id="44973-187">Предопишите пользователю Microsoft 365 Business Premium для входов по запросу.</span><span class="sxs-lookup"><span data-stu-id="44973-187">Provide the end user's Microsoft 365 Business Premium to sign in when prompted.</span></span> 
    
    <span data-ttu-id="44973-188">Нажмите **Сохранить** и выберите **OneDrive для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="44973-188">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="44973-189">Проверка требования повторного входа при неактивности приложений Office в течение указанного времени</span><span class="sxs-lookup"><span data-stu-id="44973-189">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="44973-190">В  области политики редактирования  выберите Изменить рядом с управлением доступом к документам **Office,** расширить управление доступом пользователей к файлам **Office** на мобильных устройствах и убедитесь, что требуется, чтобы пользователи снова впускались после того, как приложения **Office** простаивали, задав определенное количество минут.</span><span class="sxs-lookup"><span data-stu-id="44973-190">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="44973-191">Это 30 минут по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44973-191">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="44973-192">На устройстве iOS пользователя откройте Outlook и войдите в него с учетными данными Microsoft 365 Бизнес Премиум и введите ПИН-код по запросу.</span><span class="sxs-lookup"><span data-stu-id="44973-192">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="44973-p113">Вы должны увидеть папку входящих сообщений в Outlook. Не трогайте устройство с iOS в течение 30 минут (или другого количества времени, превышающего указанное в политике). Скорее всего, экран устройства погаснет.</span><span class="sxs-lookup"><span data-stu-id="44973-p113">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="44973-196">Снова доступ к Outlook на устройстве iOS.</span><span class="sxs-lookup"><span data-stu-id="44973-196">Access Outlook on the iOS device again.</span></span>
    
4. <span data-ttu-id="44973-197">Вам будет предложено ввести ПИН-код, прежде чем снова получить доступ к Outlook.</span><span class="sxs-lookup"><span data-stu-id="44973-197">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="44973-198">Проверка защиты рабочих файлов шифрованием</span><span class="sxs-lookup"><span data-stu-id="44973-198">Validate Protect work files with encryption</span></span>

<span data-ttu-id="44973-199">На панели **Изменение политики** рядом с параметром **Защита от потери или кражи устройств** нажмите **Изменить**, разверните раздел **Защита рабочих файлов при краже или потере устройств** и убедитесь, что параметр **Шифровать рабочие файлы**  **включен**, а параметр **Обеспечить принудительное сохранение всех рабочих файлов пользователей в OneDrive для бизнеса**  **выключен**.</span><span class="sxs-lookup"><span data-stu-id="44973-199">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="44973-200">На устройстве iOS пользователя откройте Outlook и войдите в него с учетными данными Microsoft 365 Бизнес Премиум и введите ПИН-код по запросу.</span><span class="sxs-lookup"><span data-stu-id="44973-200">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="44973-201">Откройте электронную почту, содержаную несколько вложений в файл изображений.</span><span class="sxs-lookup"><span data-stu-id="44973-201">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="44973-202">Нажмите вложение, а затем команду **Сохранить** под ним.</span><span class="sxs-lookup"><span data-stu-id="44973-202">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="44973-p114">На главном экране откройте приложение **Фотографии**. Вы должны увидеть в списке сохраненную и зашифрованную фотографию (или несколько, если сохранили несколько вложенных файлов изображений).</span><span class="sxs-lookup"><span data-stu-id="44973-p114">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

