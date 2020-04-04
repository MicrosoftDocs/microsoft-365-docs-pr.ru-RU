---
title: Добавление настраиваемых плиток в средство запуска приложений
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
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
ms.openlocfilehash: fff65c7263e40bf376f53e5f150daea7a24ff55d
ms.sourcegitcommit: 256184cf731c1851b04a07dd7d59ecf020d02635
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "43131535"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="36220-103">Добавление настраиваемых плиток в средство запуска приложений</span><span class="sxs-lookup"><span data-stu-id="36220-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="36220-p101">В Office 365 вы можете легко и быстро перейти к электронной почте, календарям, документам и приложениям, воспользовавшись средством запуска приложений Office 365 ([подробнее](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). С его помощью можно запускать приложения, доступные в рамках подписки на Office 365, а также пользовательские приложения, добавленные из [магазина SharePoint](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) или [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span><span class="sxs-lookup"><span data-stu-id="36220-p101">In Office 365, you can quickly and easily get to your email, calendars, documents, and apps using the Office 365 app launcher ([learn more](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). These are apps you get with Office 365 as well as custom apps that you add from the [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="36220-p102">Кроме того, вы можете добавить в средство запуска приложений собственные плитки, указывающие на сайты SharePoint, внешние сайты, устаревшие приложения и т. д. В средстве запуска приложений настраиваемые плитки по умолчанию отображаются на вкладке **Все**, но вы также можете закрепить их на вкладке **Главная** и рассказать пользователям, как сделать то же самое. Таким образом они смогут быстро получать доступ к нужным сайтам, приложениям и ресурсам для работы. В примере ниже показано, как с помощью настраиваемой плитки "Портал Contoso" можно быстро переходить на основной сайт интрасети SharePoint, используемый в организации.</span><span class="sxs-lookup"><span data-stu-id="36220-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Средство запуска приложений Office 365](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="36220-111">Добавление настраиваемой плитки в средство запуска приложений</span><span class="sxs-lookup"><span data-stu-id="36220-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="36220-112">В центре администрирования перейдите к**Settings**  > разделу Параметры **и**выберите вкладку **профиль организации** .</span><span class="sxs-lookup"><span data-stu-id="36220-112">In the admin center, go to the **Settings** > **Settings** and choose **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="36220-113">На вкладке **профиль организации** выберите **элемент плитка запуска приложений**.</span><span class="sxs-lookup"><span data-stu-id="36220-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="36220-114">Выберите **добавить настраиваемую плитку**.</span><span class="sxs-lookup"><span data-stu-id="36220-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="36220-115">Введите **имя плитки** для новой плитки.</span><span class="sxs-lookup"><span data-stu-id="36220-115">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="36220-116">Оно будет отображаться на плитке.</span><span class="sxs-lookup"><span data-stu-id="36220-116">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="36220-117">Введите **URL-адрес веб-сайта** для плитки.</span><span class="sxs-lookup"><span data-stu-id="36220-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="36220-118">Это расположение, в которое будут поступать пользователи при выборе плитки в средстве запуска приложений.</span><span class="sxs-lookup"><span data-stu-id="36220-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="36220-119">В URL-адресе используйте HTTPS.</span><span class="sxs-lookup"><span data-stu-id="36220-119">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="36220-120">Совет. Если вы создаете плитку для сайта SharePoint, перейдите на этот сайт, скопируйте URL-адрес и вставьте его здесь.</span><span class="sxs-lookup"><span data-stu-id="36220-120">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="36220-121">URL-адрес сайта группы по умолчанию выглядит следующим образом:`https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="36220-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="36220-122">Введите **URL-адрес изображения** для плитки.</span><span class="sxs-lookup"><span data-stu-id="36220-122">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="36220-123">Изображение будет отображаться на странице "Мои приложения" и в средстве запуска приложений.</span><span class="sxs-lookup"><span data-stu-id="36220-123">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="36220-124">Совет. изображение должно быть 60x60 пикселями и доступно всем пользователям в вашей организации без необходимости проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="36220-124">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="36220-125">Введите **описание** плитки.</span><span class="sxs-lookup"><span data-stu-id="36220-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="36220-126">Это отображается, когда вы выбираете плитку на странице "Мои приложения" и выбираете **сведения о приложении**.</span><span class="sxs-lookup"><span data-stu-id="36220-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="36220-127">Нажмите кнопку **сохранить изменения** , чтобы создать настраиваемую плитку.</span><span class="sxs-lookup"><span data-stu-id="36220-127">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="36220-128">Ваша настраиваемая плитка теперь доступна вам и вашим пользователям в средстве запуска приложений на вкладке **Все**.</span><span class="sxs-lookup"><span data-stu-id="36220-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="36220-129">Повышение уровня плитки до запуска приложения</span><span class="sxs-lookup"><span data-stu-id="36220-129">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="36220-130">Нажмите значок средства запуска приложений и выберите **все приложения**.</span><span class="sxs-lookup"><span data-stu-id="36220-130">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="36220-131">Перейдите к новому фрагменту для своего приложения, нажмите кнопку с многоточием и выберите пункт **закрепить для запуска**.</span><span class="sxs-lookup"><span data-stu-id="36220-131">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="36220-p108">Если настраиваемая плитка, созданная в предыдущих шагах, отсутствует, убедитесь, что вам назначен почтовый ящик Exchange Online и что вы входили в него по крайней мере один раз. Эти действия необходимы для добавления настраиваемых плиток в Office 365.</span><span class="sxs-lookup"><span data-stu-id="36220-p108">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once. These steps are required for custom tiles in Office 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="36220-134">Вам и вашим пользователям нужно выполнить эти действия, чтобы добавить настраиваемые плитки элементы со страницы "Мои приложения" в средство запуска приложений.</span><span class="sxs-lookup"><span data-stu-id="36220-134">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="36220-135">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="36220-135">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="36220-136">В центре администрирования перейдите на вкладку "<a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">профиль организации</a> в**настройках** >  **параметров** > ".</span><span class="sxs-lookup"><span data-stu-id="36220-136">In the admin center, go to the **Settings** > **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">Organization profile</a> tab.</span></span>
    
2. <span data-ttu-id="36220-137">На странице " **профиль организации** " рядом с элементом **Добавление настраиваемых плиток для Организации**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="36220-137">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="36220-138">Измените для настраиваемой плитки параметры **Имя плитки**, **URL-адрес**, **Описание** или **URL-адрес изображения** (см. [Добавление настраиваемой плитки в средство запуска приложений](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="36220-138">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="36220-139">Нажмите кнопку **Обновить** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="36220-139">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="36220-140">Чтобы удалить настраиваемую плитку, в окне **пользовательские плитки** выберите плитку удалить**Удаление** **фрагмента** > .</span><span class="sxs-lookup"><span data-stu-id="36220-140">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="36220-141">Что дальше?</span><span class="sxs-lookup"><span data-stu-id="36220-141">What's next?</span></span>

<span data-ttu-id="36220-p109">Помимо добавления плиток в средство запуска приложений вы можете добавлять их из этого средства на панель навигации Office 365 ([подробнее](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). Сведения о настройке внешнего вида Office 365 на основе корпоративного фирменного стиля см. в разделе [Настройка темы Office 365](../setup/customize-your-organization-theme.md).</span><span class="sxs-lookup"><span data-stu-id="36220-p109">In addition to adding tiles to the app launcher, you can add app launcher tiles to the Office 365 navigation bar ([learn more](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). To customize the look and feel of Office 365 to match your organization's brand, see [Customize the Office 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  

