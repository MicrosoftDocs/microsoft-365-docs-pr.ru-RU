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
description: 'Создайте быстрые ссылки на электронную почту, документы, приложения, сайты SharePoint, внешние сайты и другие ресурсы, добавив пользовательские плитки в средстве запуска приложений. '
ms.openlocfilehash: 2bbcf64b807754aed199c441f6df028d5fe20a97
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926238"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="57445-103">Добавление настраиваемых плиток в средство запуска приложений</span><span class="sxs-lookup"><span data-stu-id="57445-103">Add custom tiles to the app launcher</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="57445-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="57445-104">The admin center is changing.</span></span> <span data-ttu-id="57445-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="57445-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="57445-106">В Microsoft 365 вы можете быстро и легко получить электронную почту, календари, документы и приложения с помощью запуска приложений[(подробнее).](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)</span><span class="sxs-lookup"><span data-stu-id="57445-106">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="57445-107">Это приложения, которые вы получаете с помощью Microsoft 365, а также настраиваемые приложения, добавляемые из [Магазина SharePoint](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) или [Azure AD.](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)</span><span class="sxs-lookup"><span data-stu-id="57445-107">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="57445-p103">Кроме того, вы можете добавить в средство запуска приложений собственные плитки, указывающие на сайты SharePoint, внешние сайты, устаревшие приложения и т. д. В средстве запуска приложений настраиваемые плитки по умолчанию отображаются на вкладке **Все**, но вы также можете закрепить их на вкладке **Главная** и рассказать пользователям, как сделать то же самое. Таким образом они смогут быстро получать доступ к нужным сайтам, приложениям и ресурсам для работы. В примере ниже показано, как с помощью настраиваемой плитки "Портал Contoso" можно быстро переходить на основной сайт интрасети SharePoint, используемый в организации.</span><span class="sxs-lookup"><span data-stu-id="57445-p103">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Запуск приложений](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="57445-113">Добавление настраиваемой плитки в средство запуска приложений</span><span class="sxs-lookup"><span data-stu-id="57445-113">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="57445-114">Войдите в Центр администрирования от имени глобального администратора, перейдите в "Параметры организации" и выберите вкладку  >   **"Профиль организации".**</span><span class="sxs-lookup"><span data-stu-id="57445-114">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="57445-115">На **вкладке "Профиль организации"** выберите плитки **пользовательского запуска приложений.**</span><span class="sxs-lookup"><span data-stu-id="57445-115">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="57445-116">Выберите **"Добавить настраиваемую плитку".**</span><span class="sxs-lookup"><span data-stu-id="57445-116">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="57445-117">Введите **имя плитки** для новой плитки.</span><span class="sxs-lookup"><span data-stu-id="57445-117">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="57445-118">Оно будет отображаться на плитке.</span><span class="sxs-lookup"><span data-stu-id="57445-118">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="57445-119">Введите **URL-адрес веб-сайта** для плитки.</span><span class="sxs-lookup"><span data-stu-id="57445-119">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="57445-120">Это расположение, куда должны переходить пользователи при выборе плитки в окле запуска приложений.</span><span class="sxs-lookup"><span data-stu-id="57445-120">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="57445-121">Используйте HTTPS в URL-адресе.</span><span class="sxs-lookup"><span data-stu-id="57445-121">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="57445-122">Совет. Если вы создаете плитку для сайта SharePoint, перейдите на этот сайт, скопируйте URL-адрес и в paste it here.</span><span class="sxs-lookup"><span data-stu-id="57445-122">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="57445-123">URL-адрес сайта группы по умолчанию выглядит так: `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="57445-123">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="57445-124">Введите **URL-адрес изображения** для плитки.</span><span class="sxs-lookup"><span data-stu-id="57445-124">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="57445-125">Изображение будет отображаться на странице "Мои приложения" и в средстве запуска приложений.</span><span class="sxs-lookup"><span data-stu-id="57445-125">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="57445-126">Совет. Изображение должно иметь размер 60x60 пикселей и быть доступным всем в организации без необходимости проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="57445-126">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="57445-127">Введите **описание** плитки.</span><span class="sxs-lookup"><span data-stu-id="57445-127">Enter a **Description** for the tile.</span></span> <span data-ttu-id="57445-128">Вы увидите это при выборе плитки на странице "Мои приложения" и выборе **сведений о приложении.**</span><span class="sxs-lookup"><span data-stu-id="57445-128">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="57445-129">Выберите **"Сохранить изменения",** чтобы создать настраиваемую плитку.</span><span class="sxs-lookup"><span data-stu-id="57445-129">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="57445-130">Ваша настраиваемая плитка теперь доступна вам и вашим пользователям в средстве запуска приложений на вкладке **Все**.</span><span class="sxs-lookup"><span data-stu-id="57445-130">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="57445-131">Продвижение плитки в app Launcher</span><span class="sxs-lookup"><span data-stu-id="57445-131">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="57445-132">Выберите значок запуска приложений и выберите все **приложения.**</span><span class="sxs-lookup"><span data-stu-id="57445-132">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="57445-133">Найдите новую плитку для вашего приложения, выберите многолипку и выберите "Закрепить **для запуска".**</span><span class="sxs-lookup"><span data-stu-id="57445-133">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="57445-134">Если настраиваемая плитка, созданная в предыдущих шагах, отсутствует, убедитесь, что вам назначен почтовый ящик Exchange Online и что вы входили в него по крайней мере один раз.</span><span class="sxs-lookup"><span data-stu-id="57445-134">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="57445-135">Эти действия необходимы для пользовательских плиток в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="57445-135">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="57445-136">Вам и вашим пользователям нужно выполнить эти действия, чтобы добавить настраиваемые плитки элементы со страницы "Мои приложения" в средство запуска приложений.</span><span class="sxs-lookup"><span data-stu-id="57445-136">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="57445-137">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="57445-137">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="57445-138">В Центре администрирования перейдите на **вкладку** профиля организации  >  **"Параметры**  >  **организации".** </a></span><span class="sxs-lookup"><span data-stu-id="57445-138">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile**</a> tab.</span></span>
    
2. <span data-ttu-id="57445-139">На странице **профиля организации рядом** с добавлением **пользовательских плиток** для организации выберите "Изменить". </span><span class="sxs-lookup"><span data-stu-id="57445-139">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="57445-140">Измените для настраиваемой плитки параметры **Имя плитки**, **URL-адрес**, **Описание** или **URL-адрес изображения** (см. [Добавление настраиваемой плитки в средство запуска приложений](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="57445-140">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="57445-141">Выберите **"Закрыть** \> **обновление"**.</span><span class="sxs-lookup"><span data-stu-id="57445-141">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="57445-142">Чтобы удалить пользовательскую плитку, в окне "Пользовательские **плитки"** выберите плитку и выберите "Удалить   >  **плитку".**</span><span class="sxs-lookup"><span data-stu-id="57445-142">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="57445-143">Что дальше?</span><span class="sxs-lookup"><span data-stu-id="57445-143">What's next?</span></span>

<span data-ttu-id="57445-144">Помимо добавления плиток в систему запуска приложений, на панели навигации можно добавлять плитки запуска приложений ([дополнительные).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)</span><span class="sxs-lookup"><span data-stu-id="57445-144">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="57445-145">Чтобы настроить внешний вид Microsoft 365 в соответствие с фирменным названием вашей организации, см. тему ["Настройка Microsoft 365".](../setup/customize-your-organization-theme.md)</span><span class="sxs-lookup"><span data-stu-id="57445-145">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  
