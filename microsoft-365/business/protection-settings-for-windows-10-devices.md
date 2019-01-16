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
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Узнайте, как создавать политику управления приложения и защиты рабочих файлов на устройствах Windows 10.
ms.openlocfilehash: acf19a72d994185a35b2e425f8334a73a121ee10
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870641"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="e537e-103">Настройка параметров защиты приложений для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="e537e-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="e537e-104">Создание политики управления приложениями для Windows 10</span><span class="sxs-lookup"><span data-stu-id="e537e-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="e537e-105">Если у ваших пользователей есть личные устройства с Windows 10, используемые для выполнения рабочих задач, на этих устройствах также можно настроить защиту данных компании.</span><span class="sxs-lookup"><span data-stu-id="e537e-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="e537e-p101">Войдите в [Microsoft 365 Business](https://portal.office.com) с учетными данными глобального администратора. Щелкните плитку **Администратор**, чтобы перейти в Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="e537e-p101">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="e537e-108">На портале администрирования на карточке **Политики устройств** выберите команду **Добавить политику**.</span><span class="sxs-lookup"><span data-stu-id="e537e-108">On the **Device policies** card of the admin portal, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="e537e-110">На панели **Добавить политику** введите уникальное имя политики.</span><span class="sxs-lookup"><span data-stu-id="e537e-110">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="e537e-111">В поле **Тип политики** выберите **Управление приложениями для Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="e537e-111">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="e537e-112">В разделе \*\* тип устройства \*\*, выберите пункт **личный** или **Во владении организации**.</span><span class="sxs-lookup"><span data-stu-id="e537e-112">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="e537e-113">Параметр **Шифровать рабочие файлы** включается автоматически.</span><span class="sxs-lookup"><span data-stu-id="e537e-113">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="e537e-114">Если вы не хотите, чтобы пользователи сохраняли рабочие файлы на компьютере, **включите** параметр **Запретить копирование данных компании в личные файлы и обязать хранить рабочие файлы в OneDrive для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="e537e-114">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
8. <span data-ttu-id="e537e-p102">Разверните узел **Управление доступа пользователей к файлов Office на устройствах** \> настройте параметры, как вы. \*\* **Управление доступом пользователей устройств Office на мобильных устройствах** по умолчанию отключен\*\* , но рекомендуется **Включить эту возможность** и примите значения по умолчанию. Для получения дополнительных сведений см. [Доступные параметры](protection-settings-for-windows-10-devices.md#bkmk_settings) .</span><span class="sxs-lookup"><span data-stu-id="e537e-p102">Expand **Manage how users access Office files on devices** \> configure the settings how you would like. The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. See [Available settings](protection-settings-for-windows-10-devices.md#bkmk_settings) for more information.</span></span> 
    
    <span data-ttu-id="e537e-118">Вы всегда можете вернуться к значениям по умолчанию с помощью ссылки **Восстановление параметров по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="e537e-118">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
9. <span data-ttu-id="e537e-119">Разверните раздел **Восстановление данных на устройствах с Windows**. Рекомендуется его **включить**.</span><span class="sxs-lookup"><span data-stu-id="e537e-119">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="e537e-p103">Прежде чем выбирать сертификат агента восстановления данных, необходимо создать его. Инструкции см. в статье [Создание и проверка сертификата агента восстановления данных (DRA) шифрованной файловой системы (EFS)](https://go.microsoft.com/fwlink/p/?linkid=853700).</span><span class="sxs-lookup"><span data-stu-id="e537e-p103">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="e537e-p104">По умолчанию рабочие файлы шифруются с помощью секретного ключа, хранящегося на устройстве и связанного с профилем пользователя. Открыть и расшифровать файл может только пользователь. Однако в случае потери устройства или удаления пользователя файл может остаться в зашифрованном виде. Для расшифровки этого файла администратор может воспользоваться сертификатом агента восстановления данных.</span><span class="sxs-lookup"><span data-stu-id="e537e-p104">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="e537e-p105">Если вы хотите добавить еще домены или расположения SharePoint Online, чтобы защитить файлы во всех указанных приложениях, разверните параметр **Защитить дополнительные сетевые и облачные расположения**. Если в каком-либо поле вам нужно ввести несколько элементов, разделяйте их точкой с запятой (;).</span><span class="sxs-lookup"><span data-stu-id="e537e-p105">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span> 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="e537e-p106">Далее решить **пользователей, которые получит эти параметры?** Если вы не хотите использовать группы безопасности по умолчанию **Все пользователи** , нажмите кнопку **Изменить**, Выбор групп безопасности, которые получит эти параметры \> **выберите**.</span><span class="sxs-lookup"><span data-stu-id="e537e-p106">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="e537e-132">Нажмите кнопку **Добавить**, чтобы сохранить политику и назначить ее устройствам.</span><span class="sxs-lookup"><span data-stu-id="e537e-132">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="e537e-133">Доступные параметры</span><span class="sxs-lookup"><span data-stu-id="e537e-133">Available settings</span></span>

<span data-ttu-id="e537e-134">Управлять доступом пользователей к рабочим файлам Office можно с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="e537e-134">The following settings are available to manage how users access Office work files.</span></span>
  
<span data-ttu-id="e537e-135">Дополнительные сведения см. в статье [Как функции защиты в Microsoft 365 бизнес соотносятся с параметрами Intune](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e537e-135">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span>
  
|<span data-ttu-id="e537e-136">**Настройка**</span><span class="sxs-lookup"><span data-stu-id="e537e-136">**Setting**</span></span>|<span data-ttu-id="e537e-137">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e537e-137">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e537e-138">Запрашивать ПИН-код или отпечаток пальца для доступа к приложениям Office</span><span class="sxs-lookup"><span data-stu-id="e537e-138">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="e537e-139">Если этот параметр **включен**, пользователям необходимо настроить дополнительный способ проверки подлинности, помимо ввода имени и пароля, чтобы открыть приложения Office на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="e537e-139">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="e537e-140">Сбрасывать ПИН-код после указанного числа неудачных попыток входа</span><span class="sxs-lookup"><span data-stu-id="e537e-140">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="e537e-141">ПИН-код будет сбрасываться после указанного вами числа неудачных попыток ввода, чтобы несанкционированные пользователи не могли подобрать его случайным образом.</span><span class="sxs-lookup"><span data-stu-id="e537e-141">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="e537e-142">Требовать от пользователей повторно выполнять вход, если приложения Office были неактивны в течение указанного времени</span><span class="sxs-lookup"><span data-stu-id="e537e-142">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="e537e-143">Этот параметр определяет, сколько времени пользователь может оставаться неактивным, прежде чем ему будет предложено выполнить вход повторно.</span><span class="sxs-lookup"><span data-stu-id="e537e-143">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
   

