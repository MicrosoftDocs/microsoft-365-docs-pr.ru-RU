---
title: Настройка устройств с Windows для пользователей Microsoft 365 Business
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
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 'Узнайте, как настроить устройства Windows, работающие под управлением Windows 10 профессиональная для Microsoft 365 Business Users. '
ms.openlocfilehash: b377c1e69d117b893b256880cd3b9972e33345c7
ms.sourcegitcommit: 8fda7852b2a5baa92b8a365865b014ea6d100bbc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "39812885"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a><span data-ttu-id="16663-103">Настройка устройств с Windows для пользователей Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="16663-103">Set up Windows devices for Microsoft 365 Business users</span></span>

## <a name="prerequisites"></a><span data-ttu-id="16663-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="16663-104">Prerequisites</span></span>

<span data-ttu-id="16663-p101">Перед настройкой устройств с Windows для пользователей Microsoft 365 Business убедитесь, что на всех устройствах установлена система Windows 10 Pro версии 1703 (обновление Creators Update). Наличие ОС Windows 10 Pro является необходимым условием для развертывания Windows 10 Business  набора облачных служб и функций управления устройствами, который дополняет возможности этой операционной системы и предназначен для централизованного управления средой Windows 365 Business и ее безопасностью.</span><span class="sxs-lookup"><span data-stu-id="16663-p101">Before you can set up Windows devices for Microsoft 365 Business users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update). Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business.</span></span>
  
<span data-ttu-id="16663-107">Если у вас есть устройства с Windows под управлением операционной системы Windows 7 Pro, Windows 8 Pro или Windows 8.1 Pro, вы можете перейти на Windows 10 в рамках подписки Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="16663-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="16663-108">Дополнительные сведения о переводе устройств с Windows на версию Windows 10 Pro Creators Update приведены в следующей статье: [Обновление устройств с Windows до Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md)</span><span class="sxs-lookup"><span data-stu-id="16663-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="16663-109">Ознакомьтесь со статьей убедитесь, что [устройство подключено к Azure AD](#verify-the-device-is-connected-to-azure-ad) , чтобы проверить, что у вас есть обновление, или чтобы убедиться в том, что обновление работало.</span><span class="sxs-lookup"><span data-stu-id="16663-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

<span data-ttu-id="16663-110">Посмотрите короткое видео о подключении Windows к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="16663-110">Watch a short video about connecting Windows to Microsoft 365.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="16663-111">Если вы нашли это видео, изучите [полную серию обучающих материалов для малых предприятий и новых в Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="16663-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="16663-112">Добавление устройств с Windows 10 в каталог Azure AD организации</span><span class="sxs-lookup"><span data-stu-id="16663-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="16663-113">Когда все устройства с Windows в вашей организации обновлены до версии Windows 10 профессиональная Creators или уже запущены обновление Windows 10 Pro Creators, вы можете присоединить эти устройства к Azure Active Directory вашей организации.</span><span class="sxs-lookup"><span data-stu-id="16663-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="16663-114">После подключения к устройствам они будут автоматически обновлены до Windows 10 Business, которая входит в состав подписки на Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="16663-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="16663-115">Для новых (или недавно переведенных) устройств с Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="16663-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="16663-116">Для новых устройств с системой Windows 10 Pro Creators Update и устройств, которые были переведены на эту версию, но для которых еще не выполнена настройка Windows 10, следуйте инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="16663-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="16663-117">Начните настройку Windows 10 на устройстве и дойдите до страницы **Выбор способа настройки**.</span><span class="sxs-lookup"><span data-stu-id="16663-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="16663-119">Выберите вариант **Настроить для организации** и введите имя пользователя и пароль для Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="16663-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business.</span></span> 
    
3. <span data-ttu-id="16663-120">Завершите настройку Windows 10 на устройстве.</span><span class="sxs-lookup"><span data-stu-id="16663-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="16663-p103">После завершения этой процедуры пользователь будет добавлен в каталог Azure AD организации. Чтобы проверить, так ли это, ознакомьтесь со статьей [Проверка подключения устройства к Azure AD](#verify-the-device-is-connected-to-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="16663-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="16663-123">Для устройства, на котором уже установлена и настроена система Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="16663-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="16663-124">**Подключение пользователей к Azure AD**</span><span class="sxs-lookup"><span data-stu-id="16663-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="16663-125">На пользовательском компьютере под управлением Windows 10 Pro версии 1703 (Creators Update) (см. [необходимые условия](pre-requisites-for-data-protection.md)) щелкните логотип Windows, а затем значок параметров.</span><span class="sxs-lookup"><span data-stu-id="16663-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="16663-127">В окне **Параметры** выберите элемент **Учетные записи**.</span><span class="sxs-lookup"><span data-stu-id="16663-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="16663-129">На странице **Ваши данные** выберите **Доступ к учетной записи места работы или учебного заведения** \> **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="16663-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="16663-131">В диалоговом окне **Настроить учетную запись компании или учебного заведения** в разделе **Другие действия** выберите **Присоединить это устройство к Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="16663-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="16663-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="16663-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="16663-134">On the **Enter password** page, enter your password \> **Sign in**.</span><span class="sxs-lookup"><span data-stu-id="16663-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="16663-136">Убедитесь, что на странице **ваша организация** указана правильная информация, и нажмите кнопку **присоединиться**.</span><span class="sxs-lookup"><span data-stu-id="16663-136">On the **Make sure this is your organization** page, verify that the information is correct, and click **Join**.</span></span>
  
   <span data-ttu-id="16663-p104">На странице **Готово!** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="16663-p104">On the **You're all set!** page, click **Done**.</span></span>
  
   ![On the Make sure this is your organization screen, click Join](media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="16663-140">Если вы добавляете файлы в OneDrive для бизнеса, синхронизируйте их в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="16663-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="16663-141">Если для переноса профилей и файлов использовалось стороннее средство, также синхронизируйте их с новым профилем.</span><span class="sxs-lookup"><span data-stu-id="16663-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="16663-142">Проверка подключения устройства к Azure AD</span><span class="sxs-lookup"><span data-stu-id="16663-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="16663-p106">Чтобы проверить состояние синхронизации, на странице **Доступ к учетной записи места работы или учебного заведения** окна **Параметры** щелкните в области **Подключен к** _ \<organization name\> _, чтобы появились кнопки **Сведения** и **Отключить**. Чтобы узнать состояние синхронизации, нажмите кнопку **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="16663-p106">To verify your sync status, on the **Access work or school** page in **Settings**, click in the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**. Click on **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="16663-145">На странице состояния синхронизации нажмите кнопку "Синхронизировать", чтобы получить сведения о последних политиках мобильных устройств на компьютере.</span><span class="sxs-lookup"><span data-stu-id="16663-145">On the Sync status page, click Sync to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="16663-146">Чтобы начать работу с учетной записью Microsoft 365 Business, перейдите к кнопке **Пуск** Windows, щелкните правой кнопкой мыши текущий рисунок учетной записи, а затем **Переключить учетную запись**.</span><span class="sxs-lookup"><span data-stu-id="16663-146">To start using the Microsoft 365 Business account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="16663-147">Войдите, используя адрес электронной почты и пароль организации.</span><span class="sxs-lookup"><span data-stu-id="16663-147">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a><span data-ttu-id="16663-149">Проверка перевода устройства на Windows 10 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="16663-149">Verify the device is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="16663-150">Убедитесь, что устройства с Windows 10, добавленные в домен Azure AD, переведены на версию Windows 10 для бизнеса в составе подписки на Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="16663-150">Verify that your Azure AD joined Windows 10 devices were upgraded to Windows 10 Business as part of your Microsoft 365 Business subscription.</span></span>
  
1. <span data-ttu-id="16663-151">Выберите **Параметры** \> **Система** \> **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="16663-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="16663-152">Убедитесь, что в поле **Выпуск** указано **Windows 10 для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="16663-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="16663-154">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="16663-154">Next steps</span></span>

<span data-ttu-id="16663-155">Сведения о настройке мобильных устройств см. в статьях [Настройка мобильных устройств для пользователей Microsoft 365 Business](set-up-mobile-devices.md), о настройке защиты и политик защиты устройств  в статье [Управление Microsoft 365 Business](manage.md).</span><span class="sxs-lookup"><span data-stu-id="16663-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 Business](manage.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="16663-156">См. также</span><span class="sxs-lookup"><span data-stu-id="16663-156">See also</span></span>

[<span data-ttu-id="16663-157">Видеоролики по бизнес-обучению Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="16663-157">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
