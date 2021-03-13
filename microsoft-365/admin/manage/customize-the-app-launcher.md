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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Создайте быстрые ссылки на электронную почту, документы, приложения, сайты SharePoint, внешние сайты и другие ресурсы, добавляя настраиваемые плитки в пусковую точку приложения. '
ms.openlocfilehash: 809788033d0e8ef414511af5ab89857974d8b175
ms.sourcegitcommit: 89095172c9c4793d56645b4c885ac8e30936bd0a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/13/2021
ms.locfileid: "50766447"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="f728a-103">Добавление настраиваемых плиток в средство запуска приложений</span><span class="sxs-lookup"><span data-stu-id="f728a-103">Add custom tiles to the app launcher</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f728a-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="f728a-104">The admin center is changing.</span></span> <span data-ttu-id="f728a-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="f728a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="f728a-106">В Microsoft 365 вы можете быстро и легко добраться до электронной почты, календарей, документов и приложений с помощью запуска приложения[(подробнее](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span><span class="sxs-lookup"><span data-stu-id="f728a-106">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="f728a-107">Это приложения, которые вы получаете с Microsoft 365, а также настраиваемые приложения, которые вы добавляете из [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) или [Azure AD.](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)</span><span class="sxs-lookup"><span data-stu-id="f728a-107">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="f728a-p103">Кроме того, вы можете добавить в средство запуска приложений собственные плитки, указывающие на сайты SharePoint, внешние сайты, устаревшие приложения и т. д. В средстве запуска приложений настраиваемые плитки по умолчанию отображаются на вкладке **Все**, но вы также можете закрепить их на вкладке **Главная** и рассказать пользователям, как сделать то же самое. Таким образом они смогут быстро получать доступ к нужным сайтам, приложениям и ресурсам для работы. В примере ниже показано, как с помощью настраиваемой плитки "Портал Contoso" можно быстро переходить на основной сайт интрасети SharePoint, используемый в организации.</span><span class="sxs-lookup"><span data-stu-id="f728a-p103">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Пусковая](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="f728a-113">Добавление настраиваемой плитки в средство запуска приложений</span><span class="sxs-lookup"><span data-stu-id="f728a-113">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="f728a-114">Войдите в центр администрирования в качестве глобального администратора, перейдите в **параметры** параметров организации и выберите  >  вкладку **профилей** организации.</span><span class="sxs-lookup"><span data-stu-id="f728a-114">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="f728a-115">На **вкладке профилей Организации** выберите **настраиваемые плитки запуска приложений.**</span><span class="sxs-lookup"><span data-stu-id="f728a-115">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="f728a-116">Выберите **Добавить настраиваемую плитку.**</span><span class="sxs-lookup"><span data-stu-id="f728a-116">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="f728a-117">Введите **имя плитки** для новой плитки.</span><span class="sxs-lookup"><span data-stu-id="f728a-117">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="f728a-118">Оно будет отображаться на плитке.</span><span class="sxs-lookup"><span data-stu-id="f728a-118">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="f728a-119">Введите **URL-адрес веб-сайта** для плитки.</span><span class="sxs-lookup"><span data-stu-id="f728a-119">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="f728a-120">Это расположение, куда необходимо, чтобы пользователи могли перейти при выборе плитки в пусковом</span><span class="sxs-lookup"><span data-stu-id="f728a-120">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="f728a-121">Используйте HTTPS в URL-адресе.</span><span class="sxs-lookup"><span data-stu-id="f728a-121">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="f728a-122">СОВЕТ. Если вы создаете плитку для сайта SharePoint, перейдите на этот сайт, скопируйте URL-адрес и вклейте его здесь.</span><span class="sxs-lookup"><span data-stu-id="f728a-122">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="f728a-123">URL-адрес сайта группы по умолчанию выглядит так: `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="f728a-123">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="f728a-124">Введите **URL-адрес изображения** для плитки.</span><span class="sxs-lookup"><span data-stu-id="f728a-124">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="f728a-125">Изображение будет отображаться на странице "Мои приложения" и в средстве запуска приложений.</span><span class="sxs-lookup"><span data-stu-id="f728a-125">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="f728a-126">СОВЕТ. Изображение должно быть 60x60 пикселей и быть доступным для всех в вашей организации без необходимости проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f728a-126">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="f728a-127">Введите **описание** плитки.</span><span class="sxs-lookup"><span data-stu-id="f728a-127">Enter a **Description** for the tile.</span></span> <span data-ttu-id="f728a-128">Это видно при выборе плитки на странице Мои приложения и выборе **сведений о приложении.**</span><span class="sxs-lookup"><span data-stu-id="f728a-128">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="f728a-129">Выберите **Сохранить изменения** для создания настраиваемой плитки.</span><span class="sxs-lookup"><span data-stu-id="f728a-129">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="f728a-130">Ваша настраиваемая плитка теперь доступна вам и вашим пользователям в средстве запуска приложений на вкладке **Все**.</span><span class="sxs-lookup"><span data-stu-id="f728a-130">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="f728a-131">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="f728a-131">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="f728a-132">В центре администрирования перейдите на вкладку **Параметры**  >  **организации параметров** организации  >   </a> параметров.</span><span class="sxs-lookup"><span data-stu-id="f728a-132">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile**</a> tab.</span></span>
    
2. <span data-ttu-id="f728a-133">На странице **профилей Организации,** рядом с   **добавлением настраиваемой плитки для организации,** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="f728a-133">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="f728a-134">Измените для настраиваемой плитки параметры **Имя плитки**, **URL-адрес**, **Описание** или **URL-адрес изображения** (см. [Добавление настраиваемой плитки в средство запуска приложений](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="f728a-134">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="f728a-135">Выберите **Обновление** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f728a-135">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="f728a-136">Чтобы удалить настраиваемую плитку из окна **Настраиваемые** плитки, выберите плитку, выберите **Удалить плитку**  >  **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f728a-136">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="f728a-137">Что дальше?</span><span class="sxs-lookup"><span data-stu-id="f728a-137">What's next?</span></span>

<span data-ttu-id="f728a-138">В дополнение к добавлению плитки в пусковую систему приложения можно добавить плитки для запуска приложений в панели навигации[(дополнительные).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)</span><span class="sxs-lookup"><span data-stu-id="f728a-138">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="f728a-139">Чтобы настроить внешний вид Microsoft 365 в соответствие с брендом организации, см. в руб. [Настройка темы Microsoft 365.](../setup/customize-your-organization-theme.md)</span><span class="sxs-lookup"><span data-stu-id="f728a-139">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  
