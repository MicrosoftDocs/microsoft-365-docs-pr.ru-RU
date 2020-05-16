---
title: Добавление настраиваемых плиток в средство запуска приложений
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Создайте быстрые ссылки на электронную почту, документы, приложения, сайты SharePoint, внешние сайты и другие ресурсы, добавив настраиваемые плитки в средство запуска приложений. '
ms.openlocfilehash: f099eabef7a22e9ebd8f20b23ccd3d8da142f07f
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262367"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="c9113-103">Добавление настраиваемых плиток в средство запуска приложений</span><span class="sxs-lookup"><span data-stu-id="c9113-103">Add custom tiles to the app launcher</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c9113-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="c9113-104">The admin center is changing.</span></span> <span data-ttu-id="c9113-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="c9113-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="c9113-106">В Microsoft 365 вы можете быстро и легко получить доступ к электронной почте, календарям, документам и приложениям с помощью средства запуска приложений ([Подробнее](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)).</span><span class="sxs-lookup"><span data-stu-id="c9113-106">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)).</span></span> <span data-ttu-id="c9113-107">Это приложения, получаемые с помощью Microsoft 365, а также настраиваемые приложения, которые вы добавляете из [магазина SharePoint](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) или [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span><span class="sxs-lookup"><span data-stu-id="c9113-107">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="c9113-p103">Кроме того, вы можете добавить в средство запуска приложений собственные плитки, указывающие на сайты SharePoint, внешние сайты, устаревшие приложения и т. д. В средстве запуска приложений настраиваемые плитки по умолчанию отображаются на вкладке **Все**, но вы также можете закрепить их на вкладке **Главная** и рассказать пользователям, как сделать то же самое. Таким образом они смогут быстро получать доступ к нужным сайтам, приложениям и ресурсам для работы. В примере ниже показано, как с помощью настраиваемой плитки "Портал Contoso" можно быстро переходить на основной сайт интрасети SharePoint, используемый в организации.</span><span class="sxs-lookup"><span data-stu-id="c9113-p103">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Средство запуска приложений](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="c9113-113">Добавление настраиваемой плитки в средство запуска приложений</span><span class="sxs-lookup"><span data-stu-id="c9113-113">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="c9113-114">В центре администрирования перейдите в **раздел Параметры**  >  **Организации** и выберите вкладку **профиль организации** .</span><span class="sxs-lookup"><span data-stu-id="c9113-114">In the admin center, go to the **Settings** > **Org Settings** and choose **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="c9113-115">На вкладке **профиль организации** выберите **элемент плитка запуска приложений**.</span><span class="sxs-lookup"><span data-stu-id="c9113-115">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="c9113-116">Выберите **добавить настраиваемую плитку**.</span><span class="sxs-lookup"><span data-stu-id="c9113-116">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="c9113-117">Введите **имя плитки** для новой плитки.</span><span class="sxs-lookup"><span data-stu-id="c9113-117">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="c9113-118">Оно будет отображаться на плитке.</span><span class="sxs-lookup"><span data-stu-id="c9113-118">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="c9113-119">Введите **URL-адрес веб-сайта** для плитки.</span><span class="sxs-lookup"><span data-stu-id="c9113-119">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="c9113-120">Это расположение, в которое будут поступать пользователи при выборе плитки в средстве запуска приложений.</span><span class="sxs-lookup"><span data-stu-id="c9113-120">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="c9113-121">В URL-адресе используйте HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c9113-121">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="c9113-122">Совет. Если вы создаете плитку для сайта SharePoint, перейдите на этот сайт, скопируйте URL-адрес и вставьте его здесь.</span><span class="sxs-lookup"><span data-stu-id="c9113-122">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="c9113-123">URL-адрес сайта группы по умолчанию выглядит следующим образом:`https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="c9113-123">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="c9113-124">Введите **URL-адрес изображения** для плитки.</span><span class="sxs-lookup"><span data-stu-id="c9113-124">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="c9113-125">Изображение будет отображаться на странице "Мои приложения" и в средстве запуска приложений.</span><span class="sxs-lookup"><span data-stu-id="c9113-125">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="c9113-126">Совет. изображение должно быть 60x60 пикселями и доступно всем пользователям в вашей организации без необходимости проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c9113-126">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="c9113-127">Введите **описание** плитки.</span><span class="sxs-lookup"><span data-stu-id="c9113-127">Enter a **Description** for the tile.</span></span> <span data-ttu-id="c9113-128">Это отображается, когда вы выбираете плитку на странице "Мои приложения" и выбираете **сведения о приложении**.</span><span class="sxs-lookup"><span data-stu-id="c9113-128">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="c9113-129">Нажмите кнопку **сохранить изменения** , чтобы создать настраиваемую плитку.</span><span class="sxs-lookup"><span data-stu-id="c9113-129">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="c9113-130">Ваша настраиваемая плитка теперь доступна вам и вашим пользователям в средстве запуска приложений на вкладке **Все**.</span><span class="sxs-lookup"><span data-stu-id="c9113-130">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="c9113-131">Повышение уровня плитки до запуска приложения</span><span class="sxs-lookup"><span data-stu-id="c9113-131">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="c9113-132">Нажмите значок средства запуска приложений и выберите **все приложения**.</span><span class="sxs-lookup"><span data-stu-id="c9113-132">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="c9113-133">Перейдите к новому фрагменту для своего приложения, нажмите кнопку с многоточием и выберите пункт **закрепить для запуска**.</span><span class="sxs-lookup"><span data-stu-id="c9113-133">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="c9113-134">Если настраиваемая плитка, созданная в предыдущих шагах, отсутствует, убедитесь, что вам назначен почтовый ящик Exchange Online и что вы входили в него по крайней мере один раз.</span><span class="sxs-lookup"><span data-stu-id="c9113-134">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="c9113-135">Эти действия необходимы для настраиваемых плиток в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9113-135">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c9113-136">Вам и вашим пользователям нужно выполнить эти действия, чтобы добавить настраиваемые плитки элементы со страницы "Мои приложения" в средство запуска приложений.</span><span class="sxs-lookup"><span data-stu-id="c9113-136">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="c9113-137">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="c9113-137">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="c9113-138">В центре администрирования **перейдите на**  >  **Org Settings**  >  вкладку**профиль организации параметров Организации** </a> .</span><span class="sxs-lookup"><span data-stu-id="c9113-138">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile**</a> tab.</span></span>
    
2. <span data-ttu-id="c9113-139">На странице " **профиль организации** " рядом с элементом **Добавление настраиваемых плиток для Организации**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="c9113-139">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="c9113-140">Измените для настраиваемой плитки параметры **Имя плитки**, **URL-адрес**, **Описание** или **URL-адрес изображения** (см. [Добавление настраиваемой плитки в средство запуска приложений](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="c9113-140">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="c9113-141">Нажмите кнопку **Обновить** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="c9113-141">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="c9113-142">Чтобы удалить настраиваемую плитку, в окне **пользовательские плитки** выберите плитку **Удалить Удаление фрагмента**  >  **Delete**.</span><span class="sxs-lookup"><span data-stu-id="c9113-142">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="c9113-143">Что дальше?</span><span class="sxs-lookup"><span data-stu-id="c9113-143">What's next?</span></span>

<span data-ttu-id="c9113-144">В дополнение к добавлению плиток в средство запуска приложений на панель навигации можно добавить плитку запуска приложений ([Подробнее](https://support.office.com/article/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985)).</span><span class="sxs-lookup"><span data-stu-id="c9113-144">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.office.com/article/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="c9113-145">Чтобы настроить внешний вид Microsoft 365 в соответствии с фирменной символикой Организации, ознакомьтесь [со статьей Настройка темы microsoft 365](../setup/customize-your-organization-theme.md).</span><span class="sxs-lookup"><span data-stu-id="c9113-145">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  

