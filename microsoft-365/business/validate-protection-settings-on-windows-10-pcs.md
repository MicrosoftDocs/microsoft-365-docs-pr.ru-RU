---
title: Проверка параметров защиты приложений на компьютерах с Windows 10
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Проверка параметров защиты приложений Microsoft 365 Бизнес Премиум на устройствах Windows 10 и проверка того, что пользователи не могут копировать данные компании в личные файлы или неуправимые приложения.
ms.openlocfilehash: e319ffa5149f055b5de45078facc8899acffc223
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579869"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="bd5f5-103">Проверка параметров защиты приложений на компьютерах с Windows 10</span><span class="sxs-lookup"><span data-stu-id="bd5f5-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="bd5f5-104">Проверка отсутствия у пользователей возможности копирования данных компании в личные файлы на корпоративных устройствах</span><span class="sxs-lookup"><span data-stu-id="bd5f5-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="bd5f5-105">После [того, как](protection-settings-for-windows-10-devices.md)вы настроили политики защиты приложений, может потребоваться до нескольких часов, чтобы политика вступила в силу на устройствах пользователей.</span><span class="sxs-lookup"><span data-stu-id="bd5f5-105">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="bd5f5-106">Если вы  включили службу Предотвращение копирования данных компании в личные файлы и принудительное сохранение файлов работы в **параметре OneDrive для** бизнеса для устройств, которые принадлежат компании, вы можете проверить это на устройстве пользователя после подключения к Azure AD и регистрации.</span><span class="sxs-lookup"><span data-stu-id="bd5f5-106">If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they've connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="bd5f5-107">**Проверка параметров подключения**</span><span class="sxs-lookup"><span data-stu-id="bd5f5-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="bd5f5-108">После входа с учетными данными Microsoft 365 Бизнес Премиум и подключения к Azure AD, как описано в настройках устройств Windows для пользователей [Microsoft 365 Бизнес](set-up-windows-devices.md)Премиум, перейдите к работе или школе доступа к учетным записям **Windows.** \>  \> </span><span class="sxs-lookup"><span data-stu-id="bd5f5-108">After you sign in with Microsoft 365 Business Premium credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**.</span></span> <span data-ttu-id="bd5f5-109">Выберите **подключение к Azure \<tenant name\> AD,** а затем выберите **Info**.</span><span class="sxs-lookup"><span data-stu-id="bd5f5-109">Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="bd5f5-111">На странице **Управляемый за** страницей можно увидеть сведения о подключении, включаемом адрес сервера управления, похожий на адрес, показанный \<tenant name\> на следующем рисунке.  </span><span class="sxs-lookup"><span data-stu-id="bd5f5-111">On the **Managed by** \<tenant name\> page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="bd5f5-113">**Убедитесь, что нельзя вклеить данные компании в неуправяемом приложении**</span><span class="sxs-lookup"><span data-stu-id="bd5f5-113">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="bd5f5-114">Open Outlook 2016, установленный Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="bd5f5-114">Open Outlook 2016 that was installed by Microsoft 365 Business Premium.</span></span>
    
2. <span data-ttu-id="bd5f5-115">Откройте письмо и скопируйте его фрагмент.</span><span class="sxs-lookup"><span data-stu-id="bd5f5-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="bd5f5-116">Откройте Блокнот и попытайтесь вставить в него содержимое.</span><span class="sxs-lookup"><span data-stu-id="bd5f5-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="bd5f5-117">Вы получите ошибку, из-за которую приложение не может получить доступ к содержимому.</span><span class="sxs-lookup"><span data-stu-id="bd5f5-117">You'll receive an error that states the app can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="bd5f5-119">Однако это же содержимое можно вставить в Word 2016.</span><span class="sxs-lookup"><span data-stu-id="bd5f5-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="bd5f5-120">Проверка отсутствия у пользователей возможности копирования данных компании в личные файлы на личных устройствах</span><span class="sxs-lookup"><span data-stu-id="bd5f5-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="bd5f5-121">**Проверка параметров подключения**</span><span class="sxs-lookup"><span data-stu-id="bd5f5-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="bd5f5-122">На личном устройстве Windows 10, на котором вы вошли в качестве локального  пользователя, перейдите в **параметры Windows** и нажмите кнопку или нажмите кнопку Учетные записи Доступ к работе или \> **школе**.</span><span class="sxs-lookup"><span data-stu-id="bd5f5-122">On your Windows 10 personal device where you're logged in as a local user, go to **Windows Settings**, and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="bd5f5-123">На странице **Доступ к учетной записи места работы или учебного заведения** выберите команду **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="bd5f5-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="bd5f5-124">Введите учетные данные Microsoft 365 Бизнес Премиум в диалоговое окно Настройка входа в рабочий или школьный  \> **учетную запись.**</span><span class="sxs-lookup"><span data-stu-id="bd5f5-124">Enter your Microsoft 365 Business Premium credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="bd5f5-125">На странице **Доступ к учетной записи места работы или учебного заведения** выберите элемент **Рабочая или учебная учетная запись** и нажмите кнопку **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="bd5f5-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Щелкните или нажмите кнопку Info в диалоговом окте "Работа" или "Школьная учетная запись".](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="bd5f5-127">На странице Access **work или school**  можно увидеть сведения  о подключении, включаемом адрес сервера управления, похожий на тот, который показан на следующем рисунке, и включает слова *wip* и *mam* внутри.</span><span class="sxs-lookup"><span data-stu-id="bd5f5-127">On the **Access work or school** page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="bd5f5-129">**Убедитесь, что нельзя вклеить данные компании в неуправяемом приложении**</span><span class="sxs-lookup"><span data-stu-id="bd5f5-129">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="bd5f5-130">Откройте Outlook 2016 и добавьте учетную запись Microsoft 365 Бизнес Премиум при необходимости и войте учетные данные Microsoft 365 Бизнес Премиум.</span><span class="sxs-lookup"><span data-stu-id="bd5f5-130">Open Outlook 2016 and add your Microsoft 365 Business Premium account if necessary and sign in with your Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="bd5f5-131">Откройте письмо и скопируйте его фрагмент.</span><span class="sxs-lookup"><span data-stu-id="bd5f5-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="bd5f5-132">Откройте Блокнот и попытайтесь вставить в него содержимое.</span><span class="sxs-lookup"><span data-stu-id="bd5f5-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="bd5f5-133">Вы получите ошибку, из-за которую приложение не может получить доступ к содержимому.</span><span class="sxs-lookup"><span data-stu-id="bd5f5-133">You'll receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="bd5f5-135">Однако это же содержимое можно вставить в Word 2016.</span><span class="sxs-lookup"><span data-stu-id="bd5f5-135">You can, however, paste the same content into Word 2016.</span></span>
    

