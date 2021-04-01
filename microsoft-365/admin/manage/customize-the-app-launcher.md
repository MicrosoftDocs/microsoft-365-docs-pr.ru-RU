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
ms.openlocfilehash: b6ae4deed1566492574e30cf8cb66a750c9858c8
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470635"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="d624e-103">Добавление настраиваемых плиток в средство запуска приложений</span><span class="sxs-lookup"><span data-stu-id="d624e-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="d624e-104">В Microsoft 365 вы можете быстро и легко добраться до электронной почты, календарей, документов и приложений с помощью запуска приложения[(подробнее](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span><span class="sxs-lookup"><span data-stu-id="d624e-104">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="d624e-105">Это приложения, которые вы получаете с Microsoft 365, а также настраиваемые приложения, которые вы добавляете из [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) или [Azure AD.](/previous-versions/office/office-365-api/)</span><span class="sxs-lookup"><span data-stu-id="d624e-105">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](/previous-versions/office/office-365-api/).</span></span>
  
<span data-ttu-id="d624e-p102">Кроме того, вы можете добавить в средство запуска приложений собственные плитки, указывающие на сайты SharePoint, внешние сайты, устаревшие приложения и т. д. В средстве запуска приложений настраиваемые плитки по умолчанию отображаются на вкладке **Все**, но вы также можете закрепить их на вкладке **Главная** и рассказать пользователям, как сделать то же самое. Таким образом они смогут быстро получать доступ к нужным сайтам, приложениям и ресурсам для работы. В примере ниже показано, как с помощью настраиваемой плитки "Портал Contoso" можно быстро переходить на основной сайт интрасети SharePoint, используемый в организации.</span><span class="sxs-lookup"><span data-stu-id="d624e-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Пусковая](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="d624e-111">Добавление настраиваемой плитки в средство запуска приложений</span><span class="sxs-lookup"><span data-stu-id="d624e-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="d624e-112">Войдите в центр администрирования в качестве глобального администратора, перейдите в **параметры** параметров организации и выберите  >  вкладку **профилей** организации.</span><span class="sxs-lookup"><span data-stu-id="d624e-112">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="d624e-113">На **вкладке профилей Организации** выберите **настраиваемые плитки запуска приложений.**</span><span class="sxs-lookup"><span data-stu-id="d624e-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="d624e-114">Выберите **Добавить настраиваемую плитку.**</span><span class="sxs-lookup"><span data-stu-id="d624e-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="d624e-115">Введите **имя плитки** для новой плитки.</span><span class="sxs-lookup"><span data-stu-id="d624e-115">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="d624e-116">Оно будет отображаться на плитке.</span><span class="sxs-lookup"><span data-stu-id="d624e-116">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="d624e-117">Введите **URL-адрес веб-сайта** для плитки.</span><span class="sxs-lookup"><span data-stu-id="d624e-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="d624e-118">Это расположение, куда необходимо, чтобы пользователи могли перейти при выборе плитки в пусковом</span><span class="sxs-lookup"><span data-stu-id="d624e-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="d624e-119">Используйте HTTPS в URL-адресе.</span><span class="sxs-lookup"><span data-stu-id="d624e-119">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="d624e-120">СОВЕТ. Если вы создаете плитку для сайта SharePoint, перейдите на этот сайт, скопируйте URL-адрес и вклейте его здесь.</span><span class="sxs-lookup"><span data-stu-id="d624e-120">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="d624e-121">URL-адрес сайта группы по умолчанию выглядит так: `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="d624e-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="d624e-122">Введите **URL-адрес изображения** для плитки.</span><span class="sxs-lookup"><span data-stu-id="d624e-122">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="d624e-123">Изображение будет отображаться на странице "Мои приложения" и в средстве запуска приложений.</span><span class="sxs-lookup"><span data-stu-id="d624e-123">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="d624e-124">СОВЕТ. Изображение должно быть 60x60 пикселей и быть доступным для всех в вашей организации без необходимости проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d624e-124">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="d624e-125">Введите **описание** плитки.</span><span class="sxs-lookup"><span data-stu-id="d624e-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="d624e-126">Это видно при выборе плитки на странице Мои приложения и выборе **сведений о приложении.**</span><span class="sxs-lookup"><span data-stu-id="d624e-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="d624e-127">Выберите **Сохранить изменения** для создания настраиваемой плитки.</span><span class="sxs-lookup"><span data-stu-id="d624e-127">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="d624e-128">Ваша настраиваемая плитка теперь доступна вам и вашим пользователям в средстве запуска приложений на вкладке **Все**.</span><span class="sxs-lookup"><span data-stu-id="d624e-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="d624e-129">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="d624e-129">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="d624e-130">В центре администрирования перейдите на вкладку **Параметры**  >  **организации параметров** организации  >   </a> параметров.</span><span class="sxs-lookup"><span data-stu-id="d624e-130">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile**</a> tab.</span></span>
    
2. <span data-ttu-id="d624e-131">На странице **профилей Организации,** рядом с   **добавлением настраиваемой плитки для организации,** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="d624e-131">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="d624e-132">Измените для настраиваемой плитки параметры **Имя плитки**, **URL-адрес**, **Описание** или **URL-адрес изображения** (см. [Добавление настраиваемой плитки в средство запуска приложений](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="d624e-132">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="d624e-133">Выберите **Обновление** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="d624e-133">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="d624e-134">Чтобы удалить настраиваемую плитку из окна **Настраиваемые** плитки, выберите плитку, выберите **Удалить плитку**  >  **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d624e-134">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="d624e-135">Что дальше?</span><span class="sxs-lookup"><span data-stu-id="d624e-135">What's next?</span></span>

<span data-ttu-id="d624e-136">В дополнение к добавлению плитки в пусковую систему приложения можно добавить плитки для запуска приложений в панели навигации[(дополнительные).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)</span><span class="sxs-lookup"><span data-stu-id="d624e-136">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="d624e-137">Чтобы настроить внешний вид Microsoft 365 в соответствие с брендом организации, см. в руб. [Настройка темы Microsoft 365.](../setup/customize-your-organization-theme.md)</span><span class="sxs-lookup"><span data-stu-id="d624e-137">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
