---
title: Проверка параметров защиты приложений на компьютерах с Windows 10
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
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Узнайте, как проверить параметры защиты Microsoft 365 бизнес-приложений на устройствах с Windows 10.
ms.openlocfilehash: 4f1f0993dff0ef8d3f6858a3749e063c7b5579c7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280018"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="92e2a-103">Проверка параметров защиты приложений на компьютерах с Windows 10</span><span class="sxs-lookup"><span data-stu-id="92e2a-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="92e2a-104">Проверка отсутствия у пользователей возможности копирования данных компании в личные файлы на корпоративных устройствах</span><span class="sxs-lookup"><span data-stu-id="92e2a-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="92e2a-p101">Политики защиты приложений для пользовательских устройств могут вступить в силу через несколько часов после их [настройки](protection-settings-for-windows-10-devices.md). Если для корпоративных устройств установить значение **Вкл.** для параметра **Запретить копирование данных компании в личные файлы и обязать хранить рабочие файлы в OneDrive для бизнеса**, его действие можно будет проверить на устройстве пользователя после подключения к Azure AD и входа.</span><span class="sxs-lookup"><span data-stu-id="92e2a-p101">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices. If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they have connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="92e2a-107">**Проверка параметров подключения**</span><span class="sxs-lookup"><span data-stu-id="92e2a-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="92e2a-p102">После входа с помощью учетных данных Office 365 бизнес и подключения к Azure AD, как описано в статье [Настройка устройств с Windows для пользователей Microsoft 365 бизнес](set-up-windows-devices.md), откройте **Параметры Windows** \> **Учетные записи** \> **Доступ к учетной записи места работы или учебного заведения**. Выберите пункт **Подключено к Azure AD \<имя клиента\>**, а затем нажмите кнопку **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="92e2a-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="92e2a-111">На странице **Управляется** \<имя клиента\> просмотрите раздел **Сведения о подключении**, который содержит **Адрес сервера управления**, как показано на приведенном ниже рисунке.</span><span class="sxs-lookup"><span data-stu-id="92e2a-111">On the **Managed by** \<tenant name\> page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="92e2a-113">**Проверка отсутствия возможности вставки данных компании в неуправляемое приложение**</span><span class="sxs-lookup"><span data-stu-id="92e2a-113">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="92e2a-114">Откройте приложение Outlook 2016, установленное с помощью Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="92e2a-114">Open Outlook 2016 that was installed by Microsoft 365 Business.</span></span>
    
2. <span data-ttu-id="92e2a-115">Откройте письмо и скопируйте его фрагмент.</span><span class="sxs-lookup"><span data-stu-id="92e2a-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="92e2a-116">Откройте Блокнот и попытайтесь вставить в него содержимое.</span><span class="sxs-lookup"><span data-stu-id="92e2a-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="92e2a-117">Появляется предупреждение о том, что приложению не удается получить доступ к содержимому.</span><span class="sxs-lookup"><span data-stu-id="92e2a-117">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="92e2a-119">Однако это же содержимое можно вставить в Word 2016.</span><span class="sxs-lookup"><span data-stu-id="92e2a-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="92e2a-120">Проверка отсутствия у пользователей возможности копирования данных компании в личные файлы на личных устройствах</span><span class="sxs-lookup"><span data-stu-id="92e2a-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="92e2a-121">**Проверка параметров подключения**</span><span class="sxs-lookup"><span data-stu-id="92e2a-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="92e2a-122">On your Windows 10 personal device where you are logged in as a local user, go to **Windows Settings** and click or tap **Accounts** \> **Access work or school**.</span><span class="sxs-lookup"><span data-stu-id="92e2a-122">On your Windows 10 personal device where you are logged in as a local user, go to **Windows Settings** and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="92e2a-123">На странице **Доступ к учетной записи места работы или учебного заведения** выберите команду **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="92e2a-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="92e2a-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span><span class="sxs-lookup"><span data-stu-id="92e2a-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="92e2a-125">На странице **Доступ к учетной записи места работы или учебного заведения** выберите элемент **Рабочая или учебная учетная запись** и нажмите кнопку **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="92e2a-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="92e2a-127">На странице **Доступ к учетной записи места работы или учебного заведения** просмотрите раздел **Сведения о подключении**, который содержит **Адрес сервера управления** со словами  *wip*  и  *mam*  , как показано на приведенном ниже рисунке.</span><span class="sxs-lookup"><span data-stu-id="92e2a-127">On the **Access work or school** page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="92e2a-129">**Проверка отсутствия возможности вставки данных компании в неуправляемое приложение**</span><span class="sxs-lookup"><span data-stu-id="92e2a-129">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="92e2a-130">Откройте Outlook 2016, при необходимости добавьте свою учетную запись Office 365 бизнес и выполните вход с помощью учетных данных Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="92e2a-130">Open Outlook 2016 and add your Microsoft 365 Business account if necessary and sign in with your Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="92e2a-131">Откройте письмо и скопируйте его фрагмент.</span><span class="sxs-lookup"><span data-stu-id="92e2a-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="92e2a-132">Откройте Блокнот и попытайтесь вставить в него содержимое.</span><span class="sxs-lookup"><span data-stu-id="92e2a-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="92e2a-133">Появляется предупреждение о том, что приложению не удается получить доступ к содержимому.</span><span class="sxs-lookup"><span data-stu-id="92e2a-133">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="92e2a-135">Однако это же содержимое можно вставить в Word 2016.</span><span class="sxs-lookup"><span data-stu-id="92e2a-135">You can, however, paste the same content into Word 2016.</span></span>
    

