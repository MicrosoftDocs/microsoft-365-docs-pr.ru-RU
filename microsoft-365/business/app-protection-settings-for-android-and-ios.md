---
title: Настройка параметров защиты приложений для устройств с Android и iOS
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Узнайте, как создать, изменить или удалить политику управления приложениями и защитить рабочие файлы на устройствах Android или iOS.
ms.openlocfilehash: 2e157737990c7aca6e87a676e90f62f0d40ad372
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580301"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="5ef5a-103">Настройка параметров защиты приложений для устройств с Android и iOS</span><span class="sxs-lookup"><span data-stu-id="5ef5a-103">Set app protection settings for Android or iOS devices</span></span>

<span data-ttu-id="5ef5a-104">Эта статья применима к Microsoft 365 Бизнес Премиум.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="create-an-app-management-policy"></a><span data-ttu-id="5ef5a-105">Создание политики управления приложениями</span><span class="sxs-lookup"><span data-stu-id="5ef5a-105">Create an app management policy</span></span>

1. <span data-ttu-id="5ef5a-106">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="5ef5a-107">В левом nav выберите **Политики устройств** \>  \> **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="5ef5a-108">На панели **Добавить политику** введите уникальное имя политики.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="5ef5a-109">В **соответствии с типом** политики выберите управление приложениями для **Android** или Application Management **для iOS** в зависимости от набора политик, которые вы хотите создать.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS**, depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="5ef5a-110">**Расширите защиту файлов, когда устройства** потеряны или украдены, и управляйте доступом пользователей к **файлам Office на мобильных устройствах.**</span><span class="sxs-lookup"><span data-stu-id="5ef5a-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices**.</span></span> <span data-ttu-id="5ef5a-111">Настройте параметры так, как вам хотелось бы.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-111">Configure the settings how you would like.</span></span> <span data-ttu-id="5ef5a-112">**Управление доступом пользователей к файлам Office** на мобильных устройствах  отключено по умолчанию, но рекомендуется включить его и принять значения по умолчанию. </span><span class="sxs-lookup"><span data-stu-id="5ef5a-112">**Manage how users access Office files on mobile devices** is **Off** by default, but we recommend that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="5ef5a-113">Дополнительные сведения см. в [сайте Доступные параметры](#available-settings).</span><span class="sxs-lookup"><span data-stu-id="5ef5a-113">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="5ef5a-114">Вы всегда можете вернуться к значениям по умолчанию с помощью ссылки **Восстановление параметров по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-114">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="5ef5a-116">Next decide **Who will get these settings?**</span><span class="sxs-lookup"><span data-stu-id="5ef5a-116">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="5ef5a-117">Если вы не хотите использовать  группу безопасности всех пользователей по умолчанию, выберите **Изменение**, выберите группы безопасности, которые получают эти параметры \> **Выберите**.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-117">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups that get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="5ef5a-118">Нажмите кнопку **Готово**, чтобы сохранить политику и назначить ее устройствам.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-118">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="5ef5a-119">Изменение политики управления приложениями</span><span class="sxs-lookup"><span data-stu-id="5ef5a-119">Edit an app management policy</span></span>

1. <span data-ttu-id="5ef5a-120">На карте **Политики** выберите политику **Редактирование**.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-120">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="5ef5a-121">На панели **Изменить политику** выберите политику, которую хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-121">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="5ef5a-122">Щелкните **Изменить** рядом с каждым параметром политики, чтобы изменить его значение.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-122">Choose **Edit** next to each setting to change the values in the policy.</span></span> <span data-ttu-id="5ef5a-123">При изменении значения оно автоматически сохранено в политике.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-123">When you change a value, it's automatically saved in the policy.</span></span>
    
4. <span data-ttu-id="5ef5a-124">По завершению закрой области **политики редактирования.**</span><span class="sxs-lookup"><span data-stu-id="5ef5a-124">When you're finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="5ef5a-125">Удаление политики управления приложениями</span><span class="sxs-lookup"><span data-stu-id="5ef5a-125">Delete an app management policy</span></span>

1. <span data-ttu-id="5ef5a-126">На странице **Политики** выберите политику и **удалите**.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-126">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="5ef5a-127">На области **Политики удаления** выберите **Подтвердите** удаление выбранной политики или политик.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-127">On the **Delete policy** pane, choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="5ef5a-128">Доступные параметры</span><span class="sxs-lookup"><span data-stu-id="5ef5a-128">Available settings</span></span>

<span data-ttu-id="5ef5a-129">В следующих таблицах подробно описаны параметры, доступные для защиты файлов работы на устройствах, а также параметры, которые контролируют доступ пользователей к файлам Office с мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-129">The following tables give detailed information about settings available to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="5ef5a-130">Дополнительные сведения см. в [веб-сайте How do protection features in Microsoft 365 Business Premium map to Intune settings.](map-protection-features-to-intune-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5ef5a-130">For more information, see [How do protection features in Microsoft 365 Business Premium map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="5ef5a-131">Параметры для защиты рабочих файлов</span><span class="sxs-lookup"><span data-stu-id="5ef5a-131">Settings that protect work files</span></span>

<span data-ttu-id="5ef5a-132">Для защиты рабочих файлов в случае потери или кражи устройства доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="5ef5a-132">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5ef5a-133">Setting</span><span class="sxs-lookup"><span data-stu-id="5ef5a-133">Setting</span></span>  <br/> |<span data-ttu-id="5ef5a-134">Описание</span><span class="sxs-lookup"><span data-stu-id="5ef5a-134">Description</span></span>  <br/> |
|<span data-ttu-id="5ef5a-135">Удалять рабочие файлы с неактивного устройства через указанное количество дней</span><span class="sxs-lookup"><span data-stu-id="5ef5a-135">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="5ef5a-136">Если устройство не используется в течение определенного числа дней, все файлы работы, хранимые на устройстве, будут удалены автоматически.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-136">If a device isn't used for the number of days that you specify here, any work files stored on the device will be deleted automatically.</span></span>  <br/> |
|<span data-ttu-id="5ef5a-137">Обеспечить принудительное сохранение всех рабочих файлов пользователей в OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5ef5a-137">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="5ef5a-138">Если этот параметр **работает,** единственным доступным расположением сохранения для файлов работы является OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-138">If this setting is **On**, the only available save location for work files is OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="5ef5a-139">Шифровать рабочие файлы</span><span class="sxs-lookup"><span data-stu-id="5ef5a-139">Encrypt work files</span></span>  <br/> |<span data-ttu-id="5ef5a-140">Оставьте этот параметр **включенным**, чтобы защитить рабочие файлы с помощью шифрования.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-140">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="5ef5a-141">Даже если устройство потеряно или украдено, никто не может прочитать данные вашей компании.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-141">Even if the device is lost or stolen, no one can read your company data.</span></span>  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="5ef5a-142">Параметры, управляющие доступом пользователей к файлам Office с мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="5ef5a-142">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="5ef5a-143">Управлять доступом пользователей к рабочим файлам Office можно с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="5ef5a-143">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5ef5a-144">Setting</span><span class="sxs-lookup"><span data-stu-id="5ef5a-144">Setting</span></span>  <br/> |<span data-ttu-id="5ef5a-145">Описание</span><span class="sxs-lookup"><span data-stu-id="5ef5a-145">Description</span></span>  <br/> |
|<span data-ttu-id="5ef5a-146">Запрашивать ПИН-код или отпечаток пальца для доступа к приложениям Office</span><span class="sxs-lookup"><span data-stu-id="5ef5a-146">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="5ef5a-147">Если этот параметр **используется** для пользователей, необходимо предоставить другую форму проверки подлинности, помимо имени пользователя и пароля, прежде чем они смогут использовать приложения Office на своих мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-147">If this setting is **On** users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile devices.</span></span><br/> |
|<span data-ttu-id="5ef5a-148">Сбрасывать ПИН-код после указанного числа неудачных попыток входа</span><span class="sxs-lookup"><span data-stu-id="5ef5a-148">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="5ef5a-149">Чтобы запретить несанкционированным пользователям случайным образом подбирать ПИН-код, он будет сброшен после указанного вами числа неудачных попыток ввода.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-149">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="5ef5a-150">Требовать от пользователей повторно выполнять вход, если приложения Office были неактивны в течение указанного времени</span><span class="sxs-lookup"><span data-stu-id="5ef5a-150">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="5ef5a-151">Этот параметр определяет, как долго пользователь может простаивать до того, как им будет предложено войти снова.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-151">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="5ef5a-152">Запретить доступ к рабочим файлам на устройствах со снятой защитой или с включенным привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="5ef5a-152">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="5ef5a-p105">На устройствах технически осведомленных пользователей может быть снята защита или включен привилегированный доступ. Это означает, что пользователь может изменять операционную систему, из-за чего устройство может стать более уязвимым к вредоносным программам. Когда этот параметр **включен**, такие устройства блокируются.  </span><span class="sxs-lookup"><span data-stu-id="5ef5a-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="5ef5a-156">Не позволяйте пользователям копировать контент из приложений Office в личные приложения</span><span class="sxs-lookup"><span data-stu-id="5ef5a-156">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="5ef5a-157">По умолчанию такая возможность существует, но если этот параметр **включен**, то пользователь может копировать сведения из рабочих файлов в личные.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-157">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="5ef5a-158">Если этот параметр **отключен**, пользователь не сможет копировать сведения из рабочей учетной записи в личные приложения или учетные записи.</span><span class="sxs-lookup"><span data-stu-id="5ef5a-158">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
