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
ms.openlocfilehash: 72ea81ad86a20e01b4650915fef96a713b207c3b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166163"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="cd0e8-103">Перенос файлов Google в Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cd0e8-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="cd0e8-104">При переходе на Microsoft 365 для бизнеса вам необходимо перенести файлы с Google Drive.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-104">When you move to Microsoft 365 for business, you'll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="cd0e8-105">Вы можете использовать приложение Mover для перемещения файлов с персональных и общих дисков.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="cd0e8-106">Дополнительные сведения см. в [сведениях о миграции Mover Cloud.](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span><span class="sxs-lookup"><span data-stu-id="cd0e8-106">For more information, see [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="cd0e8-107">Mover сделает копию файлов и переместит их в Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="cd0e8-108">Исходные файлы также останутся на дисках Google.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="cd0e8-109">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="cd0e8-109">Before you start</span></span>

<span data-ttu-id="cd0e8-110">Все пользователи должны были в свои учетные записи в Microsoft 365 для бизнеса настроить OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="cd0e8-111">Для этого перейдите в [office.com,](https://office.com)войдите с помощью учетных данных Microsoft 365 для бизнеса и выберите OneDrive.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-111">To do this, go to [office.com](https://office.com), sign in with your Microsoft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="cd0e8-112">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="cd0e8-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="cd0e8-113">Установка Mover</span><span class="sxs-lookup"><span data-stu-id="cd0e8-113">Install Mover</span></span>

1. <span data-ttu-id="cd0e8-114">Во sign in to your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="cd0e8-114">Sign in to your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="cd0e8-115">Choose **Apps**  >  **Google Workspace Marketplace apps** Add app to Domain Install  >  **list.**</span><span class="sxs-lookup"><span data-stu-id="cd0e8-115">Choose **Apps** > **Google Workspace Marketplace apps** > **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="cd0e8-116">Найщите Mover и выберите его.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="cd0e8-117">Choose **Domain Install**, then **Continue**.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="cd0e8-118">Просмотрите разрешения, выберите этот контрольный ящик, чтобы согласиться с условиями, а затем выберите "Разрешить", **"Далее"** и **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="cd0e8-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="cd0e8-119">Создание соединитеителей и запуск миграции</span><span class="sxs-lookup"><span data-stu-id="cd0e8-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="cd0e8-120">Вернись в **приложения Google Workspace Marketplace.**</span><span class="sxs-lookup"><span data-stu-id="cd0e8-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="cd0e8-121">Обновите браузер и выберите **приложение Mover.**</span><span class="sxs-lookup"><span data-stu-id="cd0e8-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="cd0e8-122">Прокрутите вниз и выберите ссылку универсальной навигации.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="cd0e8-123">Select **Authorize New Connector,** locate **G Suite (Admin)**, and choose **Authorize**.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="cd0e8-124">Измените **отображаемую именем,** если хотите, затем выберите **"Авторизировать".**</span><span class="sxs-lookup"><span data-stu-id="cd0e8-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="cd0e8-125">Выберите учетную запись администратора Google, просмотрите разрешения, а затем выберите **"Разрешить".**</span><span class="sxs-lookup"><span data-stu-id="cd0e8-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="cd0e8-126">Mover отображает количество обнаруженных дисков группы и пользовательских дисков.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="cd0e8-127">В **области "Выбор назначения"** выберите **"Авторизовать новый соединители",**"Найти **Office 365"** и **"Авторизовать".**</span><span class="sxs-lookup"><span data-stu-id="cd0e8-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="cd0e8-128">Чтобы предоставить разрешения для приложения Mover в Azure Active Directory, перейдите [к](https://aka.ms/Office365MoverAuth)aka.ms/Office365MoverAuth.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="cd0e8-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="cd0e8-130">Выберите свою учетную запись, просмотрите разрешения и выберите **"Принять".**</span><span class="sxs-lookup"><span data-stu-id="cd0e8-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="cd0e8-131">Выберите **"Свойства"** и убедитесь, что назначение пользователя **обязательно?** Включено.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="cd0e8-132">Вернись в приложение Mover, измените **отображаемую** именем , если вы хотите, выберите **Авторизировать,** а затем выберите учетную запись администратора Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="cd0e8-133">Mover сообщит вам о количестве обнаруженных сайтов SharePoint Online (или SPO) и пользователей.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="cd0e8-134">Choose **Continue Migration Setup,** select **Add Users**, then **Automatically Discover and Add Users**.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="cd0e8-135">Приложение Mover попытается соединять диски из пути к источнику в Google с пунктом назначения в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="cd0e8-136">Если диск не сопоает автоматически, добавьте его конечный путь в CSV-файл, который мы позже будем использовать для переноса общего диска в библиотеку документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-136">If a drive doesn't map automatically, add its destination path to a CSV file, which we'll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="cd0e8-137">В этом случае мы добавили сайт SharePoint Под названием "Перенесенные файлы" и занося URL-адрес страницы документов.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="cd0e8-138">Затем мы создали CSV-файл в формате "Исходный путь", "Путь назначения" и "Теги".</span><span class="sxs-lookup"><span data-stu-id="cd0e8-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="cd0e8-139">Подробные сведения [см. в aka.ms/movercsv.](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv)</span><span class="sxs-lookup"><span data-stu-id="cd0e8-139">For details see [aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="cd0e8-140">При добавлении URL-адреса пути назначения удалите все после общих документов.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-140">When adding the Destination Path URL, remove everything after Shared Documents.</span></span> <span data-ttu-id="cd0e8-141">Например, полный URL-адрес не будет работать: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="cd0e8-141">For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="cd0e8-142">Замените его значением `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-142">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="cd0e8-143">Когда CSV-файл будет готов, выберите **"Действия** миграции", **"Добавить в миграцию"** и **"Выберите файл для отправки".**</span><span class="sxs-lookup"><span data-stu-id="cd0e8-143">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="cd0e8-144">Перейдите к CSV-файлу, выберите его, а затем выберите **"Открыть".**</span><span class="sxs-lookup"><span data-stu-id="cd0e8-144">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="cd0e8-145">Выберите диски пользователей, файлы которых нужно перенести, а затем выберите **"Начать миграцию пользователей".**</span><span class="sxs-lookup"><span data-stu-id="cd0e8-145">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="cd0e8-146">Просмотрите сведения о миграции, выберите время начала миграции, согласитесь с условиями и выберите **"Продолжить".**</span><span class="sxs-lookup"><span data-stu-id="cd0e8-146">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="cd0e8-147">Приложение Mover сообщит вам о том, что процесс миграции завершен.</span><span class="sxs-lookup"><span data-stu-id="cd0e8-147">The Mover app will inform you when the migration process is complete.</span></span>
