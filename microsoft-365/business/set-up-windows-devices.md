---
title: Настройка Windows устройств для Microsoft 365 бизнес премиум пользователей
f1.keywords:
- CSH
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
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Настройка устройств Windows, Windows 10 Pro для Microsoft 365 бизнес премиум пользователей, что позволяет централизованно контролировать управление и безопасность.
ms.openlocfilehash: 7a9c75f6ec14605225d40c103c18e62937e773bf
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635881"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="a9490-103">Настройка Windows устройств для Microsoft 365 бизнес премиум пользователей</span><span class="sxs-lookup"><span data-stu-id="a9490-103">Set up Windows devices for Microsoft 365 Business Premium users</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a9490-104">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="a9490-104">Before you begin</span></span>

<span data-ttu-id="a9490-105">Прежде чем настроить Windows для Microsoft 365 бизнес премиум пользователей, убедитесь, что все Windows работают Windows 10 Pro версии 1703 (Creators Update).</span><span class="sxs-lookup"><span data-stu-id="a9490-105">Before you can set up Windows devices for Microsoft 365 Business Premium users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update).</span></span> <span data-ttu-id="a9490-106">Windows 10 Pro является обязательным условием для развертывания Windows 10 для бизнеса, который представляет собой набор облачных служб и возможностей управления устройствами, которые дополняют Windows 10 Pro и обеспечивают централизованное управление и управление безопасностью Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="a9490-106">Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business Premium.</span></span>
  
<span data-ttu-id="a9490-107">Если у вас Windows устройств с Windows 7 Pro, Windows 8 Профессиональная или Windows 8.1 Профессиональная, ваша Microsoft 365 бизнес премиум подписка дает вам право на Windows 10 обновления.</span><span class="sxs-lookup"><span data-stu-id="a9490-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business Premium subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="a9490-108">Дополнительные сведения о переводе устройств с Windows на версию Windows 10 Pro Creators Update приведены в следующей статье: [Обновление устройств с Windows до Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md)</span><span class="sxs-lookup"><span data-stu-id="a9490-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="a9490-109">Проверьте, подключено ли устройство к [Azure AD,](#verify-the-device-is-connected-to-azure-ad) чтобы убедиться, что обновление обновлено, или убедиться, что обновление сработало.</span><span class="sxs-lookup"><span data-stu-id="a9490-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

## <a name="watch-connect-your-pc-to-microsoft-365-business"></a><span data-ttu-id="a9490-110">Часы: Подключение компьютер Microsoft 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="a9490-110">Watch: Connect your PC to Microsoft 365 Business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="a9490-111">Если это видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="a9490-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../business-video/index.yml).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="a9490-112">Добавление устройств с Windows 10 в каталог Azure AD организации</span><span class="sxs-lookup"><span data-stu-id="a9490-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="a9490-113">Если все Windows в организации были обновлены до Windows 10 Pro Creators Update или уже запущены Windows 10 Pro Creators Update, вы можете присоединиться к этим устройствам в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a9490-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="a9490-114">После того как устройства будут соединены, они будут автоматически обновлены до Windows 10 для бизнеса, что является частью Microsoft 365 бизнес премиум подписки.</span><span class="sxs-lookup"><span data-stu-id="a9490-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business Premium subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="a9490-115">Для новых (или недавно переведенных) устройств с Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="a9490-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="a9490-116">Для новых устройств с системой Windows 10 Pro Creators Update и устройств, которые были переведены на эту версию, но для которых еще не выполнена настройка Windows 10, следуйте инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="a9490-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="a9490-117">Начните настройку Windows 10 на устройстве и дойдите до страницы **Выбор способа настройки**.</span><span class="sxs-lookup"><span data-stu-id="a9490-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="a9490-119">Здесь выберите **Настройка для организации,** а затем введите имя пользователя и пароль для Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="a9490-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business Premium.</span></span> 
    
3. <span data-ttu-id="a9490-120">Завершите настройку Windows 10 на устройстве.</span><span class="sxs-lookup"><span data-stu-id="a9490-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="a9490-p103">После завершения этой процедуры пользователь будет добавлен в каталог Azure AD организации. Чтобы проверить, так ли это, ознакомьтесь со статьей [Проверка подключения устройства к Azure AD](#verify-the-device-is-connected-to-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="a9490-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="a9490-123">Для устройства, на котором уже установлена и настроена система Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="a9490-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="a9490-124">**Подключение пользователей к Azure AD**</span><span class="sxs-lookup"><span data-stu-id="a9490-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="a9490-125">На пользовательском компьютере под управлением Windows 10 Pro версии 1703 (Creators Update) (см. [необходимые условия](pre-requisites-for-data-protection.md)) щелкните логотип Windows, а затем значок параметров.</span><span class="sxs-lookup"><span data-stu-id="a9490-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="a9490-127">В окне **Параметры** выберите элемент **Учетные записи**.</span><span class="sxs-lookup"><span data-stu-id="a9490-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="a9490-129">На странице **Ваши данные** выберите **Доступ к учетной записи места работы или учебного заведения** \> **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="a9490-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="a9490-131">В диалоговом окне **Настроить учетную запись компании или учебного заведения** в разделе **Другие действия** выберите **Присоединить это устройство к Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a9490-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="a9490-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="a9490-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="a9490-134">On the **Enter password** page, enter your password \> **Sign in**.</span><span class="sxs-lookup"><span data-stu-id="a9490-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="a9490-136">На странице **Убедитесь, что это** ваша страница организации, убедитесь, что информация верна, и выберите **Присоединиться**.</span><span class="sxs-lookup"><span data-stu-id="a9490-136">On the **Make sure this is your organization** page, verify that the information is correct, and choose **Join**.</span></span>
  
   <span data-ttu-id="a9490-137">На странице **Готово!**</span><span class="sxs-lookup"><span data-stu-id="a9490-137">On the **You're all set!**</span></span> <span data-ttu-id="a9490-138">страница, chosse **Готово**.</span><span class="sxs-lookup"><span data-stu-id="a9490-138">page, chosse **Done**.</span></span>
  
   ![На экране Убедитесь, что это ваш экран организации, выберите Присоединиться](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="a9490-140">Если вы добавляете файлы в OneDrive для бизнеса, синхронизируйте их в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="a9490-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="a9490-141">Если для переноса профилей и файлов используется сторонний инструмент, синхронизируйте их с новым профилем.</span><span class="sxs-lookup"><span data-stu-id="a9490-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="a9490-142">Проверка подключения устройства к Azure AD</span><span class="sxs-lookup"><span data-stu-id="a9490-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="a9490-143">Чтобы проверить состояние синхронизации, на странице **Access work** или school **в Параметры** выберите область Подключенная к **_** _, чтобы выставить кнопки \<organization name\> **Info** и **Disconnect**.</span><span class="sxs-lookup"><span data-stu-id="a9490-143">To verify your sync status, on the **Access work or school** page in **Settings**, select the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**.</span></span> <span data-ttu-id="a9490-144">Выберите **Info,** чтобы получить состояние синхронизации.</span><span class="sxs-lookup"><span data-stu-id="a9490-144">Choose **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="a9490-145">На странице **Состояние синхронизации** выберите **Синхронизация,** чтобы получить последние политики управления мобильными устройствами на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a9490-145">On the **Sync status** page, choose **Sync** to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="a9490-146">Чтобы начать использовать учетную запись Microsoft 365 бизнес премиум, перейдите  Windows кнопку Начните, щелкните правой кнопкой мыши текущую учетную запись, а затем **переключите учетную запись**.</span><span class="sxs-lookup"><span data-stu-id="a9490-146">To start using the Microsoft 365 Business Premium account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="a9490-147">Войдите, используя адрес электронной почты и пароль организации.</span><span class="sxs-lookup"><span data-stu-id="a9490-147">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a><span data-ttu-id="a9490-149">Убедитесь, что компьютер обновлен до Windows 10 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a9490-149">Verify the PC is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="a9490-150">Убедитесь, что ваши Windows 10 Azure AD обновляются до Windows 10 для бизнеса в рамках Microsoft 365 бизнес премиум подписки.</span><span class="sxs-lookup"><span data-stu-id="a9490-150">Verify that your Azure AD joined Windows 10 devices are upgraded to Windows 10 Business as part of your Microsoft 365 Business Premium subscription.</span></span>
  
1. <span data-ttu-id="a9490-151">Выберите **Параметры** \> **Система** \> **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="a9490-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="a9490-152">Убедитесь, что в поле **Выпуск** указано **Windows 10 для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="a9490-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="a9490-154">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="a9490-154">Next steps</span></span>

<span data-ttu-id="a9490-155">Чтобы настроить мобильные устройства, см. в Microsoft 365 бизнес премиум настройка мобильных устройств [для](set-up-mobile-devices.md)пользователей, чтобы установить политики защиты устройств или приложений, см. в Microsoft 365 [для бизнеса.](manage.md)</span><span class="sxs-lookup"><span data-stu-id="a9490-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 for business](manage.md).</span></span>
  
## <a name="related-content"></a><span data-ttu-id="a9490-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="a9490-156">Related content</span></span>

<span data-ttu-id="a9490-157">[Microsoft 365 для видео обучения бизнесу](../business-video/index.yml) (страница ссылки)</span><span class="sxs-lookup"><span data-stu-id="a9490-157">[Microsoft 365 for business training videos](../business-video/index.yml) (link page)</span></span>
