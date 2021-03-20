---
title: 'Перенос файлов Google в Microsoft 365 для бизнеса '
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как перенести файлы Google в Microsoft 365 для бизнеса с помощью Mover.
ms.openlocfilehash: 6feabff7e36e84f7dba56e74333648325cf43920
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913578"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="c8bec-103">Перенос файлов Google в Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c8bec-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="c8bec-104">При переходе в Microsoft 365 для бизнеса необходимо перенести файлы из Google Drive.</span><span class="sxs-lookup"><span data-stu-id="c8bec-104">When you move to Microsoft 365 for business, you'll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="c8bec-105">Приложение Mover можно использовать для перемещения файлов с персональных и общих дисков.</span><span class="sxs-lookup"><span data-stu-id="c8bec-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="c8bec-106">Дополнительные сведения см. в [дополнительных сведениях в Mover Cloud Migration.](/sharepointmigration/mover-plan-migration)</span><span class="sxs-lookup"><span data-stu-id="c8bec-106">For more information, see [Mover Cloud Migration](/sharepointmigration/mover-plan-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="c8bec-107">Mover сделает копию файлов и переместит их в Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c8bec-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="c8bec-108">Исходные файлы также останутся в Google Drives.</span><span class="sxs-lookup"><span data-stu-id="c8bec-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="c8bec-109">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="c8bec-109">Before you start</span></span>

<span data-ttu-id="c8bec-110">Все пользователи должны были войтись в Microsoft 365 для бизнеса и настроить oneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c8bec-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="c8bec-111">Для этого перейдите в [office.com,](https://office.com)войдите в microsoft 365 для бизнес-учетных данных, а затем выберите OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c8bec-111">To do this, go to [office.com](https://office.com), sign in with your Microsoft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="c8bec-112">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="c8bec-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="c8bec-113">Установка Mover</span><span class="sxs-lookup"><span data-stu-id="c8bec-113">Install Mover</span></span>

1. <span data-ttu-id="c8bec-114">Во входе на консоль администрирования Google Workspace в [admin.google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="c8bec-114">Sign in to your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="c8bec-115">Выберите **приложения**  >  **Google Workspace Marketplace apps** Add app to Domain Install  >  **list.**</span><span class="sxs-lookup"><span data-stu-id="c8bec-115">Choose **Apps** > **Google Workspace Marketplace apps** > **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="c8bec-116">Поиск Mover и выберите его.</span><span class="sxs-lookup"><span data-stu-id="c8bec-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="c8bec-117">Выберите **установку домена,** а затем **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="c8bec-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="c8bec-118">Просмотрите разрешения, выберите почтовый ящик, чтобы согласиться на условия, а затем выберите **Разрешить**, выберите **Далее**, а затем **Сделано**.</span><span class="sxs-lookup"><span data-stu-id="c8bec-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="c8bec-119">Создание соединители и запуск миграции</span><span class="sxs-lookup"><span data-stu-id="c8bec-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="c8bec-120">**Возвращайся к приложениям Google Workspace Marketplace.**</span><span class="sxs-lookup"><span data-stu-id="c8bec-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="c8bec-121">Обновите браузер и выберите **приложение Mover.**</span><span class="sxs-lookup"><span data-stu-id="c8bec-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="c8bec-122">Прокрутите вниз и выберите универсальную ссылку навигации.</span><span class="sxs-lookup"><span data-stu-id="c8bec-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="c8bec-123">Выберите **Авторизовать новый соединителя,** найти **G Suite (Admin)** и выбрать **Авторизации**.</span><span class="sxs-lookup"><span data-stu-id="c8bec-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="c8bec-124">Измените **имя отображения,** если хотите, выберите **Авториз.**</span><span class="sxs-lookup"><span data-stu-id="c8bec-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="c8bec-125">Выберите учетную запись администратора Google, просмотрите разрешения, а затем выберите **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="c8bec-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="c8bec-126">Mover отображает количество обнаруженных командных дисков и пользовательских дисков.</span><span class="sxs-lookup"><span data-stu-id="c8bec-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="c8bec-127">В **пункте Выбор назначения** выберите **Авторизовать новый соединители,** найдите **Office 365** и выберите **Авторизовать**.</span><span class="sxs-lookup"><span data-stu-id="c8bec-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="c8bec-128">Чтобы предоставить разрешения приложению Mover в Azure Active Directory, перейдите aka.ms/Office365MoverAuth [.](https://aka.ms/Office365MoverAuth)</span><span class="sxs-lookup"><span data-stu-id="c8bec-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="c8bec-129">Выберите **Office 365 Mover**, **Разрешения**, Предоставление **согласия администратора для вашей компании**.</span><span class="sxs-lookup"><span data-stu-id="c8bec-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="c8bec-130">Выберите учетную запись, просмотрите разрешения и выберите **Accept**.</span><span class="sxs-lookup"><span data-stu-id="c8bec-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="c8bec-131">Выберите **свойства и** убедитесь, что требуется назначение **пользователя?**</span><span class="sxs-lookup"><span data-stu-id="c8bec-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="c8bec-132">Вернись к приложению Mover, измените **имя отображения,** если хотите, выберите **Авториз,** а затем выберите учетную запись администратора Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c8bec-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="c8bec-133">Mover сообщит вам о количестве обнаруженных сайтов SharePoint Online (или SPO).</span><span class="sxs-lookup"><span data-stu-id="c8bec-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="c8bec-134">Выберите **продолжить настройку миграции,** **выберите Добавить пользователей,** а затем автоматически открыть и добавить **пользователей**.</span><span class="sxs-lookup"><span data-stu-id="c8bec-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="c8bec-135">Приложение Mover будет пытаться соединять диски с исходным путем в Google до пути назначения в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c8bec-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="c8bec-136">Если диск не имеет автоматической карты, добавьте его путь назначения к CSV-файлу, который мы будем использовать позже для переноса общего диска в библиотеку документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c8bec-136">If a drive doesn't map automatically, add its destination path to a CSV file, which we'll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="c8bec-137">В этом случае мы добавили сайт SharePoint под названием Перенесенные файлы и приняли к сведению URL-адрес страницы документов.</span><span class="sxs-lookup"><span data-stu-id="c8bec-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="c8bec-138">Затем мы создали CSV-файл в формате Source Path, Destination Path и Tags.</span><span class="sxs-lookup"><span data-stu-id="c8bec-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="c8bec-139">Подробные сведения [см. в aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv).</span><span class="sxs-lookup"><span data-stu-id="c8bec-139">For details see [aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="c8bec-140">При добавлении URL-адреса назначения удалите все после общих документов.</span><span class="sxs-lookup"><span data-stu-id="c8bec-140">When adding the Destination Path URL, remove everything after Shared Documents.</span></span> <span data-ttu-id="c8bec-141">Например, полный URL-адрес не будет работать: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="c8bec-141">For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="c8bec-142">Замените его значением `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`.</span><span class="sxs-lookup"><span data-stu-id="c8bec-142">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="c8bec-143">После того как ваш CSV-файл будет готов, выберите **Действия миграции,** Добавьте к **миграции**, **Выберите файл для загрузки**.</span><span class="sxs-lookup"><span data-stu-id="c8bec-143">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="c8bec-144">Перейдите к CSV-файлу, выберите его, а затем выберите **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="c8bec-144">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="c8bec-145">Выберите диски пользователя, файлы которых необходимо перенести, а затем выберите **Начните миграцию пользователей.**</span><span class="sxs-lookup"><span data-stu-id="c8bec-145">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="c8bec-146">Просмотрите сведения о миграции, выберите, когда приступить к миграции, согласитесь на условия и **условия,** а затем выберите **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="c8bec-146">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="c8bec-147">Приложение Mover сообщит вам, когда процесс миграции будет завершен.</span><span class="sxs-lookup"><span data-stu-id="c8bec-147">The Mover app will inform you when the migration process is complete.</span></span>