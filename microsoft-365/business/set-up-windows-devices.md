---
title: Настройка устройств с Windows для пользователей Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 'Узнайте, как настроить устройства Windows, работающие под управлением Windows 10 профессиональная для Microsoft 365 Business Users. '
ms.openlocfilehash: f93257bd9a68385fca4f178a2e09c5c11506ee2c
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32284421"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a><span data-ttu-id="0605b-103">Настройка устройств с Windows для пользователей Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="0605b-103">Set up Windows devices for Microsoft 365 Business users</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0605b-104">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="0605b-104">Prerequisites</span></span>

<span data-ttu-id="0605b-p101">Перед настройкой устройств с Windows для пользователей Microsoft 365 Business убедитесь, что на всех устройствах установлена система Windows 10 Pro версии 1703 (обновление Creators Update). Наличие ОС Windows 10 Pro является необходимым условием для развертывания Windows 10 Business  набора облачных служб и функций управления устройствами, который дополняет возможности этой операционной системы и предназначен для централизованного управления средой Windows 365 Business и ее безопасностью.</span><span class="sxs-lookup"><span data-stu-id="0605b-p101">Before you can set up Windows devices for Microsoft 365 Business users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update). Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business.</span></span>
  
<span data-ttu-id="0605b-107">Если у вас есть устройства с Windows под управлением операционной системы Windows 7 Pro, Windows 8 Pro или Windows 8.1 Pro, вы можете перейти на Windows 10 в рамках подписки Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="0605b-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="0605b-108">Дополнительные сведения о переводе устройств с Windows на версию Windows 10 Pro Creators Update приведены в следующей статье: [Обновление устройств с Windows до Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md)</span><span class="sxs-lookup"><span data-stu-id="0605b-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="0605b-109">Ознакомьтесь со статьей убедитесь, что [устройство подключено к Azure AD](#verify-the-device-is-connected-to-azure-ad) , чтобы проверить, что у вас есть обновление, или чтобы убедиться в том, что обновление работало.</span><span class="sxs-lookup"><span data-stu-id="0605b-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span> 
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="0605b-110">Добавление устройств с Windows 10 в каталог Azure AD организации</span><span class="sxs-lookup"><span data-stu-id="0605b-110">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="0605b-p102">После перевода всех корпоративных устройств с Windows 10 на версию Windows 10 Pro Creators Update их можно добавить в каталог Azure Active Directory организации. Добавленные устройства автоматически переводятся на версию Windows 10 для бизнеса, которая входит в состав подписки на Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="0605b-p102">Once all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory. Once the devices are joined, they will automatically be upgraded to Windows 10 Business, which is part of your Microsoft 365 Business subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="0605b-113">Для новых (или недавно переведенных) устройств с Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="0605b-113">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="0605b-114">Для новых устройств с системой Windows 10 Pro Creators Update и устройств, которые были переведены на эту версию, но для которых еще не выполнена настройка Windows 10, следуйте инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="0605b-114">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="0605b-115">Начните настройку Windows 10 на устройстве и дойдите до страницы **Выбор способа настройки**.</span><span class="sxs-lookup"><span data-stu-id="0605b-115">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="0605b-117">Выберите вариант **Настроить для организации** и введите имя пользователя и пароль для Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="0605b-117">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business.</span></span> 
    
3. <span data-ttu-id="0605b-118">Завершите настройку Windows 10 на устройстве.</span><span class="sxs-lookup"><span data-stu-id="0605b-118">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="0605b-p103">После завершения этой процедуры пользователь будет добавлен в каталог Azure AD организации. Чтобы проверить, так ли это, ознакомьтесь со статьей [Проверка подключения устройства к Azure AD](#verify-the-device-is-connected-to-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="0605b-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="0605b-121">Для устройства, на котором уже установлена и настроена система Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="0605b-121">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="0605b-122">**Подключение пользователей к Azure AD**</span><span class="sxs-lookup"><span data-stu-id="0605b-122">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="0605b-123">На пользовательском компьютере под управлением Windows 10 Pro версии 1703 (Creators Update) (см. [необходимые условия](pre-requisites-for-data-protection.md)) щелкните логотип Windows, а затем значок параметров.</span><span class="sxs-lookup"><span data-stu-id="0605b-123">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="0605b-125">В окне **Параметры** выберите элемент **Учетные записи**.</span><span class="sxs-lookup"><span data-stu-id="0605b-125">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="0605b-127">На странице **Ваши данные** выберите **Доступ к учетной записи места работы или учебного заведения** \> **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="0605b-127">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="0605b-129">В диалоговом окне **Настроить учетную запись компании или учебного заведения** в разделе **Другие действия** выберите **Присоединить это устройство к Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0605b-129">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="0605b-131">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="0605b-131">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="0605b-132">On the **Enter password** page, enter your password \> **Sign in**.</span><span class="sxs-lookup"><span data-stu-id="0605b-132">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="0605b-134">Убедитесь, что на странице **ваша организация** указана правильная информация, и нажмите кнопку присоединиться \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="0605b-134">On the **Make sure this is your organization** page, verify that the information is correct, and click **Join**.</span></span>
  
   <span data-ttu-id="0605b-p104">На странице **Готово!** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="0605b-p104">On the **You're all set!** page, click **Done**.</span></span>
  
   ![On the Make sure this is your organization screen, click Join](media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="0605b-p105">Если вы добавляете файлы в OneDrive для бизнеса, синхронизируйте их в обратном направлении. Если вы используете стороннюю программу для переноса профиля и файлов, синхронизируйте их тоже с новым профилем.</span><span class="sxs-lookup"><span data-stu-id="0605b-p105">If you uploaded files to OneDrive for Business, sync them back down. If you used a third party tool to migrate profile and files, sync those also to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="0605b-140">Проверка подключения устройства к Azure AD</span><span class="sxs-lookup"><span data-stu-id="0605b-140">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="0605b-p106">Чтобы проверить состояние синхронизации, на странице **Доступ к учетной записи места работы или учебного заведения** окна **Параметры** щелкните в области **Подключен к** _ \<organization name\> _, чтобы появились кнопки **Сведения** и **Отключить**. Чтобы узнать состояние синхронизации, нажмите кнопку **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="0605b-p106">To verify your sync status, on the **Access work or school** page in **Settings**, click in the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**. Click on **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="0605b-143">На странице состояния синхронизации нажмите кнопку "Синхронизировать", чтобы получить сведения о последних политиках мобильных устройств на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0605b-143">On the Sync status page, click Sync to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="0605b-p107">Чтобы начать пользоваться учетной записью Office 365 бизнес, перейдите в **начальное** меню Windows, щелкните правой кнопкой мыши картинку текущей учетной записи и выберите команду **Сменить учетную запись**. Войдите, используя адрес электронной почты и пароль организации.</span><span class="sxs-lookup"><span data-stu-id="0605b-p107">To start using the Microsoft 365 Business account, go to the Windows **Start** button, right-click your current account picture and then **Switch account**. Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a><span data-ttu-id="0605b-147">Проверка перевода устройства на Windows 10 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0605b-147">Verify the device is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="0605b-148">Убедитесь, что устройства с Windows 10, добавленные в домен Azure AD, переведены на версию Windows 10 для бизнеса в составе подписки на Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="0605b-148">Verify that your Azure AD joined Windows 10 devices were upgraded to Windows 10 Business as part of your Microsoft 365 Business subscription.</span></span>
  
1. <span data-ttu-id="0605b-149">Выберите **Параметры** \> **Система** \> **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="0605b-149">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="0605b-150">Убедитесь, что в поле **Выпуск** указано **Windows 10 для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="0605b-150">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="0605b-152">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="0605b-152">Next steps</span></span>

<span data-ttu-id="0605b-153">Сведения о настройке мобильных устройств см. в статьях [Настройка мобильных устройств для пользователей Microsoft 365 Business](set-up-mobile-devices.md), о настройке защиты и политик защиты устройств  в статье [Управление Microsoft 365 Business](manage.md).</span><span class="sxs-lookup"><span data-stu-id="0605b-153">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 Business](manage.md).</span></span>
  
