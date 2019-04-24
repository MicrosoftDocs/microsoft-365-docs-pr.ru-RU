---
title: Настройка параметров защиты приложений для устройств с Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Узнайте, как создать политику управления приложениями и защитить рабочие файлы на устройствах с Windows 10.
ms.openlocfilehash: 289c6a74f6ccb53f6a833612a7b4a5bcddd3ea56
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278197"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="2e7c8-103">Настройка параметров защиты приложений для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="2e7c8-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="2e7c8-104">Создание политики управления приложениями для Windows 10</span><span class="sxs-lookup"><span data-stu-id="2e7c8-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="2e7c8-105">Если у ваших пользователей есть личные устройства с Windows 10, используемые для выполнения рабочих задач, на этих устройствах также можно настроить защиту данных компании.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="2e7c8-106">Войдите в [центр администрирования](https://go.microsoft.com/fwlink/p/?linkid=837890) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-106">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=837890) with global admin credentials.</span></span> <span data-ttu-id="2e7c8-107">Щелкните плитку **Администратор**, чтобы перейти в Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-107">Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="2e7c8-108">В левой панели навигации выберите пункт \*\*\*\* \> **политики** \> устройств **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-108">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="2e7c8-109">На панели **Добавить политику** введите уникальное имя политики.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-109">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="2e7c8-110">В поле **Тип политики** выберите **Управление приложениями для Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-110">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="2e7c8-111">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-111">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="2e7c8-112">Параметр **Шифровать рабочие файлы** включается автоматически.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-112">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="2e7c8-113">Если вы не хотите, чтобы пользователи сохраняли рабочие файлы на компьютере, **включите** параметр **Запретить копирование данных компании в личные файлы и обязать хранить рабочие файлы в OneDrive для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-113">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
8. <span data-ttu-id="2e7c8-114">Expand **Manage how users access Office files on devices** \> configure the settings how you would like.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-114">Expand **Manage how users access Office files on devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="2e7c8-115">The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-115">The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="2e7c8-116">Дополнительные сведения см. в разделе [Доступные параметры](#available-settings).</span><span class="sxs-lookup"><span data-stu-id="2e7c8-116">See [Available settings](#available-settings)for more information.</span></span> 
    
    <span data-ttu-id="2e7c8-117">Вы всегда можете вернуться к значениям по умолчанию с помощью ссылки **Восстановление параметров по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-117">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
9. <span data-ttu-id="2e7c8-118">Разверните раздел **Восстановление данных на устройствах с Windows**. Рекомендуется его **включить**.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-118">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="2e7c8-p103">Прежде чем выбирать сертификат агента восстановления данных, необходимо создать его. Инструкции см. в статье [Создание и проверка сертификата агента восстановления данных (DRA) шифрованной файловой системы (EFS)](https://go.microsoft.com/fwlink/p/?linkid=853700).</span><span class="sxs-lookup"><span data-stu-id="2e7c8-p103">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="2e7c8-p104">По умолчанию рабочие файлы шифруются с помощью секретного ключа, хранящегося на устройстве и связанного с профилем пользователя. Открыть и расшифровать файл может только пользователь. Однако в случае потери устройства или удаления пользователя файл может остаться в зашифрованном виде. Для расшифровки этого файла администратор может воспользоваться сертификатом агента восстановления данных.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-p104">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="2e7c8-p105">Если вы хотите добавить еще домены или расположения SharePoint Online, чтобы защитить файлы во всех указанных приложениях, разверните параметр **Защитить дополнительные сетевые и облачные расположения**. Если в каком-либо поле вам нужно ввести несколько элементов, разделяйте их точкой с запятой (;).</span><span class="sxs-lookup"><span data-stu-id="2e7c8-p105">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span> 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="2e7c8-p106">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-p106">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="2e7c8-131">Нажмите кнопку **Добавить**, чтобы сохранить политику и назначить ее устройствам.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-131">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="2e7c8-132">Доступные параметры</span><span class="sxs-lookup"><span data-stu-id="2e7c8-132">Available settings</span></span>

<span data-ttu-id="2e7c8-133">Управлять доступом пользователей к рабочим файлам Office можно с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="2e7c8-133">The following settings are available to manage how users access Office work files.</span></span>
  
<span data-ttu-id="2e7c8-134">Дополнительные сведения см. в статье [Как функции защиты в Microsoft 365 бизнес соотносятся с параметрами Intune](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="2e7c8-134">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span>
  
|<span data-ttu-id="2e7c8-135">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="2e7c8-135">**Setting**</span></span>|<span data-ttu-id="2e7c8-136">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2e7c8-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2e7c8-137">Запрашивать ПИН-код или отпечаток пальца для доступа к приложениям Office</span><span class="sxs-lookup"><span data-stu-id="2e7c8-137">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="2e7c8-138">Если этот параметр **включен**, пользователям необходимо настроить дополнительный способ аутентификации, помимо ввода имени и пароля, чтобы открыть приложения Office на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-138">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="2e7c8-139">Сбрасывать ПИН-код после указанного числа неудачных попыток входа</span><span class="sxs-lookup"><span data-stu-id="2e7c8-139">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="2e7c8-140">Чтобы запретить несанкционированным пользователям случайным образом подбирать ПИН-код, он будет сброшен после указанного вами числа неудачных попыток ввода.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-140">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="2e7c8-141">Требовать от пользователей повторно выполнять вход, если приложения Office были неактивны в течение указанного времени</span><span class="sxs-lookup"><span data-stu-id="2e7c8-141">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="2e7c8-142">Этот параметр определяет, сколько времени пользователь может оставаться неактивным, прежде чем ему будет предложено выполнить вход повторно.</span><span class="sxs-lookup"><span data-stu-id="2e7c8-142">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
   

