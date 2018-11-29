---
title: Настройка параметров защиты приложений для устройств с Android и iOS
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Узнайте, как создавать, изменять, или удалить политику управления приложения и защиты рабочих файлов на устройствах Android или операций ввода-вывода.
ms.openlocfilehash: ed03227496120369b94bf2396974eebfd7798678
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871009"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="211cc-103">Настройка параметров защиты приложений для устройств с Android и iOS</span><span class="sxs-lookup"><span data-stu-id="211cc-103">Set app protection settings for Android or iOS devices</span></span>

## <a name="create-an-app-management-policy"></a><span data-ttu-id="211cc-104">Создание политики управления приложениями</span><span class="sxs-lookup"><span data-stu-id="211cc-104">Create an app management policy</span></span>

1. <span data-ttu-id="211cc-105">Войдите в [Microsoft 365 Business](https://portal.office.com) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="211cc-105">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="211cc-106">В центре администрирования на карточке **Политики устройств** выберите команду **Добавить политику**.</span><span class="sxs-lookup"><span data-stu-id="211cc-106">In the admin center, on the **Device policies** card, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="211cc-108">На панели **Добавить политику** введите уникальное имя политики.</span><span class="sxs-lookup"><span data-stu-id="211cc-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="211cc-109">В поле **Тип политики** выберите **Управление приложениями для Android** или **Управление приложениями для iOS** для создания соответствующего набора политик.</span><span class="sxs-lookup"><span data-stu-id="211cc-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS** depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="211cc-p101">Разверните узел **защитить рабочих файлов при кражи или потери устройств** и **управление ими доступа пользователей к файлов Office на мобильных устройствах** \> настройте параметры, как вы. \*\* **Управление доступа пользователей к файлов Office на мобильных устройствах** по умолчанию отключен\*\* , но рекомендуется **Включить эту возможность** и примите значения по умолчанию. Для получения дополнительных сведений см. [Доступные параметры](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) .</span><span class="sxs-lookup"><span data-stu-id="211cc-p101">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like. The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. See [Available settings](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) for more information.</span></span> 
    
    <span data-ttu-id="211cc-113">Вы всегда можете вернуться к значениям по умолчанию с помощью ссылки **Восстановление параметров по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="211cc-113">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="211cc-p102">Далее решить **пользователей, которые получит эти параметры?** Если вы не хотите использовать группы безопасности по умолчанию **Все пользователи** , нажмите кнопку **Изменить**, Выбор групп безопасности, которые получит эти параметры \> **выберите**.</span><span class="sxs-lookup"><span data-stu-id="211cc-p102">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="211cc-117">Нажмите кнопку **Готово**, чтобы сохранить политику и назначить ее устройствам.</span><span class="sxs-lookup"><span data-stu-id="211cc-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="211cc-118">Изменение политики управления приложениями</span><span class="sxs-lookup"><span data-stu-id="211cc-118">Edit an app management policy</span></span>

1. <span data-ttu-id="211cc-119">В карточке **политики** выберите **Изменение политики**.</span><span class="sxs-lookup"><span data-stu-id="211cc-119">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="211cc-120">На панели **Изменить политику** выберите политику, которую хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="211cc-120">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="211cc-p103">Щелкните **Изменить** рядом с каждым параметром политики, чтобы изменить его значение. Измененное значение автоматически сохраняется в политике.</span><span class="sxs-lookup"><span data-stu-id="211cc-p103">Choose **Edit** next to each setting to change the values in the policy. When you change a value, it is automatically saved into the policy</span></span> 
    
4. <span data-ttu-id="211cc-123">Завершив изменение значений, закройте панель **Изменить политику**.</span><span class="sxs-lookup"><span data-stu-id="211cc-123">When you are finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="211cc-124">Удаление политики управления приложениями</span><span class="sxs-lookup"><span data-stu-id="211cc-124">Delete an app management policy</span></span>

1. <span data-ttu-id="211cc-125">На карточке **Политики** выберите команду **Удалить политику**.</span><span class="sxs-lookup"><span data-stu-id="211cc-125">On the **Policies** card, choose **Delete policy**.</span></span>
    
2. <span data-ttu-id="211cc-126">В панели **Удаление политики** выбрать политики, которую требуется удалить \> **выберите **Подтверждение** для удаления политики или политики, выбранный**.</span><span class="sxs-lookup"><span data-stu-id="211cc-126">On the **Delete policy** pane, choose the policies you want to delete \> **Select**, then **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="211cc-127">Доступные параметры</span><span class="sxs-lookup"><span data-stu-id="211cc-127">Available settings</span></span>

<span data-ttu-id="211cc-128">В таблицах ниже подробно описаны доступные параметры, позволяющие защитить рабочие файлы на устройствах и управлять доступом к файлам Office с мобильных устройств пользователей.</span><span class="sxs-lookup"><span data-stu-id="211cc-128">The following tables give detailed information about the available settings to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="211cc-129">Дополнительные сведения см. в статье [Как функции защиты в Microsoft 365 бизнес соотносятся с параметрами Intune](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="211cc-129">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="211cc-130">Параметры для защиты рабочих файлов</span><span class="sxs-lookup"><span data-stu-id="211cc-130">Settings that protect work files</span></span>

<span data-ttu-id="211cc-131">Для защиты рабочих файлов в случае потери или кражи устройства доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="211cc-131">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="211cc-132">Параметр</span><span class="sxs-lookup"><span data-stu-id="211cc-132">Setting</span></span>  <br/> |<span data-ttu-id="211cc-133">Описание</span><span class="sxs-lookup"><span data-stu-id="211cc-133">Description</span></span>  <br/> |
|<span data-ttu-id="211cc-134">Удалять рабочие файлы с неактивного устройства через указанное количество дней</span><span class="sxs-lookup"><span data-stu-id="211cc-134">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="211cc-135">Если устройство не используется на протяжении указанного в этом параметре количества дней, с него будут автоматически удалены все рабочие файлы.</span><span class="sxs-lookup"><span data-stu-id="211cc-135">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="211cc-136">Обеспечить принудительное сохранение всех рабочих файлов пользователей в OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="211cc-136">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="211cc-137">Если этот параметр **включен**, единственным доступным местом для сохранения рабочих файлов будет OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="211cc-137">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="211cc-138">Шифровать рабочие файлы</span><span class="sxs-lookup"><span data-stu-id="211cc-138">Encrypt work files</span></span>  <br/> |<span data-ttu-id="211cc-p104">Оставьте этот параметр **включенным**, чтобы защитить рабочие файлы с помощью шифрования. Даже в случае потери или кражи устройства никто не сможет прочитать ваши корпоративные данные.  </span><span class="sxs-lookup"><span data-stu-id="211cc-p104">Keep this setting **On** so that work files are protected by encryption. Even if the device is lost or stolen, no one will be able to read your company data.  </span></span><br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="211cc-141">Параметры, управляющие доступом пользователей к файлам Office с мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="211cc-141">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="211cc-142">Управлять доступом пользователей к рабочим файлам Office можно с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="211cc-142">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="211cc-143">Параметр</span><span class="sxs-lookup"><span data-stu-id="211cc-143">Setting</span></span>  <br/> |<span data-ttu-id="211cc-144">Описание</span><span class="sxs-lookup"><span data-stu-id="211cc-144">Description</span></span>  <br/> |
|<span data-ttu-id="211cc-145">Запрашивать ПИН-код или отпечаток пальца для доступа к приложениям Office</span><span class="sxs-lookup"><span data-stu-id="211cc-145">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="211cc-146">Если этот параметр **включен**, пользователям необходимо настроить дополнительный способ проверки подлинности, помимо ввода имени и пароля, чтобы открыть приложения Office на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="211cc-146">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="211cc-147">Сбрасывать ПИН-код после указанного числа неудачных попыток входа</span><span class="sxs-lookup"><span data-stu-id="211cc-147">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="211cc-148">ПИН-код будет сбрасываться после указанного вами числа неудачных попыток ввода, чтобы несанкционированные пользователи не могли подобрать его случайным образом.</span><span class="sxs-lookup"><span data-stu-id="211cc-148">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="211cc-149">Требовать от пользователей повторно выполнять вход, если приложения Office были неактивны в течение указанного времени</span><span class="sxs-lookup"><span data-stu-id="211cc-149">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="211cc-150">Этот параметр определяет, сколько времени пользователь может оставаться неактивным, прежде чем ему будет предложено выполнить вход повторно.</span><span class="sxs-lookup"><span data-stu-id="211cc-150">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="211cc-151">Запретить доступ к рабочим файлам на устройствах со снятой защитой или с включенным привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="211cc-151">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="211cc-p105">На устройствах технически осведомленных пользователей может быть снята защита или включен привилегированный доступ. Это означает, что пользователь может изменять операционную систему, из-за чего устройство может стать более уязвимым для вредоносных программ. Когда этот параметр **включен**, такие устройства блокируются.  </span><span class="sxs-lookup"><span data-stu-id="211cc-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="211cc-155">Разрешить пользователям копировать содержимое из приложений Office в личные приложения</span><span class="sxs-lookup"><span data-stu-id="211cc-155">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="211cc-p106">Это разрешение по умолчанию, но если **параметр включен,** пользователь может скопировать сведения в файле рабочего файл личных. Если **параметр выключен,** пользователь будет невозможно копирование данных из учетной записи работой в личный приложения или личной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="211cc-p106">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file. If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.  </span></span><br/> |
   

  

