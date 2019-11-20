---
title: Проверка параметров защиты приложений на компьютерах с Windows 10
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
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Узнайте, как проверить параметры защиты Microsoft 365 бизнес-приложений на устройствах с Windows 10.
ms.openlocfilehash: c54b053c1f6efbca8fd02431c416793a044c6821
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2019
ms.locfileid: "38721867"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="3787e-103">Проверка параметров защиты приложений на компьютерах с Windows 10</span><span class="sxs-lookup"><span data-stu-id="3787e-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="3787e-104">Проверка отсутствия у пользователей возможности копирования данных компании в личные файлы на корпоративных устройствах</span><span class="sxs-lookup"><span data-stu-id="3787e-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="3787e-105">После [настройки политик защиты приложений](protection-settings-for-windows-10-devices.md)это может занять несколько часов, чтобы политика вступила в силу на устройствах пользователей.</span><span class="sxs-lookup"><span data-stu-id="3787e-105">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="3787e-106">Если **вы включили** параметр **запретить пользователям копировать данные компании в личные файлы и принудительно сохранить рабочие файлы в настройках OneDrive для бизнеса** для устройств, принадлежащих компании, вы можете проверить это на устройстве пользователя после подключения к Azure AD и входа в систему.</span><span class="sxs-lookup"><span data-stu-id="3787e-106">If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they've connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="3787e-107">**Проверка параметров подключения**</span><span class="sxs-lookup"><span data-stu-id="3787e-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="3787e-p102">После входа с помощью учетных данных Office 365 бизнес и подключения к Azure AD, как описано в статье [Настройка устройств с Windows для пользователей Microsoft 365 бизнес](set-up-windows-devices.md), откройте **Параметры Windows** \> **Учетные записи** \> **Доступ к учетной записи места работы или учебного заведения**. Выберите пункт **Подключено к Azure AD \<имя клиента\>**, а затем нажмите кнопку **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="3787e-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="3787e-111">На странице " **Управление с помощью** \<имени\> клиента" можно просмотреть **сведения о подключении** , включающие **адрес сервера управления** , как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="3787e-111">On the **Managed by** \<tenant name\> page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="3787e-113">**Проверка отсутствия возможности вставки данных компании в неуправляемое приложение**</span><span class="sxs-lookup"><span data-stu-id="3787e-113">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="3787e-114">Откройте приложение Outlook 2016, установленное с помощью Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="3787e-114">Open Outlook 2016 that was installed by Microsoft 365 Business.</span></span>
    
2. <span data-ttu-id="3787e-115">Откройте письмо и скопируйте его фрагмент.</span><span class="sxs-lookup"><span data-stu-id="3787e-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="3787e-116">Откройте Блокнот и попытайтесь вставить в него содержимое.</span><span class="sxs-lookup"><span data-stu-id="3787e-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="3787e-117">Вы получите сообщение об ошибке, в котором говорится, что приложение не может получить доступ к контенту.</span><span class="sxs-lookup"><span data-stu-id="3787e-117">You'll receive an error that states the app can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="3787e-119">Однако это же содержимое можно вставить в Word 2016.</span><span class="sxs-lookup"><span data-stu-id="3787e-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="3787e-120">Проверка отсутствия у пользователей возможности копирования данных компании в личные файлы на личных устройствах</span><span class="sxs-lookup"><span data-stu-id="3787e-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="3787e-121">**Проверка параметров подключения**</span><span class="sxs-lookup"><span data-stu-id="3787e-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="3787e-122">На персональном устройстве с Windows 10, в котором вы вошли как локальный пользователь, перейдите в раздел **Параметры Windows**, а затем щелкните или выберите **учетные записи** \> **доступ к работе или учебному заведению**.</span><span class="sxs-lookup"><span data-stu-id="3787e-122">On your Windows 10 personal device where you're logged in as a local user, go to **Windows Settings**, and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="3787e-123">На странице **Доступ к учетной записи места работы или учебного заведения** выберите команду **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="3787e-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="3787e-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span><span class="sxs-lookup"><span data-stu-id="3787e-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="3787e-125">На странице **Доступ к учетной записи места работы или учебного заведения** выберите элемент **Рабочая или учебная учетная запись** и нажмите кнопку **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="3787e-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Щелкните или нажмите кнопку Сведения в диалоговом окне Рабочая или учебная учетная запись.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="3787e-127">На странице "доступ" на **рабочем месте или учебном заведении** можно просмотреть **сведения о подключении** , включающие **адрес сервера управления** , как показано на следующем рисунке, и содержит слова " *НЗП* " и " *MAM* " в.</span><span class="sxs-lookup"><span data-stu-id="3787e-127">On the **Access work or school** page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="3787e-129">**Проверка отсутствия возможности вставки данных компании в неуправляемое приложение**</span><span class="sxs-lookup"><span data-stu-id="3787e-129">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="3787e-130">Откройте Outlook 2016, при необходимости добавьте свою учетную запись Office 365 бизнес и выполните вход с помощью учетных данных Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="3787e-130">Open Outlook 2016 and add your Microsoft 365 Business account if necessary and sign in with your Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="3787e-131">Откройте письмо и скопируйте его фрагмент.</span><span class="sxs-lookup"><span data-stu-id="3787e-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="3787e-132">Откройте Блокнот и попытайтесь вставить в него содержимое.</span><span class="sxs-lookup"><span data-stu-id="3787e-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="3787e-133">Вы получите сообщение об ошибке, в котором приложение не может получить доступ к контенту.</span><span class="sxs-lookup"><span data-stu-id="3787e-133">You'll receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="3787e-135">Однако это же содержимое можно вставить в Word 2016.</span><span class="sxs-lookup"><span data-stu-id="3787e-135">You can, however, paste the same content into Word 2016.</span></span>
    

