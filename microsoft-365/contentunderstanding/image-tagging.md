---
title: Расстановка тегов для изображений в SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Сведения о расстановке тегов для изображений в SharePoint Syntex
ms.openlocfilehash: 0fba54db6a16a9a8571c7e1ced61b7620cf5113e
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975869"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="36aa6-103">Расстановка тегов для изображений в SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="36aa6-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="36aa6-104">(ожидается в ближайшее время).</span><span class="sxs-lookup"><span data-stu-id="36aa6-104">(Coming soon)</span></span>

<span data-ttu-id="36aa6-105">Расстановка тегов для изображений в SharePoint Syntex помогает пользователям находить нужные изображения и создавать процессы на базе тегов.</span><span class="sxs-lookup"><span data-stu-id="36aa6-105">With image tagging in SharePoint Syntex, users can find images through search by searching on image tags, and create workflows based on image tags.</span></span> <span data-ttu-id="36aa6-106">По умолчанию для SharePoint и OneDrive включена базовая расстановка тегов для изображений.</span><span class="sxs-lookup"><span data-stu-id="36aa6-106">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="36aa6-107">Изображения, отправленные в какое-либо расположение, автоматически сканируются и к ним применяются применимые теги (при наличии) из списка 37 основных тегов.</span><span class="sxs-lookup"><span data-stu-id="36aa6-107">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="36aa6-108">Пользователи могут находить изображения с помощью поиска, выполняя поиск по тегам изображения.</span><span class="sxs-lookup"><span data-stu-id="36aa6-108">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="36aa6-109">Процесс расстановки тегов запускается автоматически при отправке изображения.</span><span class="sxs-lookup"><span data-stu-id="36aa6-109">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="36aa6-110">Если изображение будет изменено, процесс расстановки тегов запустится снова, чтобы обновить теги.</span><span class="sxs-lookup"><span data-stu-id="36aa6-110">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="36aa6-111">Пользователи с разрешениями на доступ к файлу изображения могут просматривать и редактировать теги на панели сведений о файле или на странице результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="36aa6-111">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="36aa6-112">Если пользователь изменит теги изображения, система больше не будет автоматически расставлять теги для этого изображения, даже если оно будет изменено.</span><span class="sxs-lookup"><span data-stu-id="36aa6-112">Once a user edits an image's tags, the system no longer auto-tags that image, even if it's edited.</span></span>

<span data-ttu-id="36aa6-113">Если вы отключите расстановку тегов, изображения больше не будут автоматически ими помечаться.</span><span class="sxs-lookup"><span data-stu-id="36aa6-113">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="36aa6-114">Существующие теги не будут удалены.</span><span class="sxs-lookup"><span data-stu-id="36aa6-114">Existing tags won't be removed.</span></span>

> [!NOTE]
> <span data-ttu-id="36aa6-115">Теги, созданные системой, могут измениться в связи с изменением изображения или нашей технологии тегов.</span><span class="sxs-lookup"><span data-stu-id="36aa6-115">System generated tags may change with updates to the image or our tag technology.</span></span>


## <a name="configure-image-tagging"></a><span data-ttu-id="36aa6-116">Настройка расстановки тегов для изображений</span><span class="sxs-lookup"><span data-stu-id="36aa6-116">Configure image tagging</span></span>

<span data-ttu-id="36aa6-117">После [настройки SharePoint Syntex](set-up-content-understanding.md) вы можете настроить расстановку тегов для изображений в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36aa6-117">After you [set up SharePoint Syntex](set-up-content-understanding.md), you can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="36aa6-118">Включение и отключение расстановки тегов для изображений</span><span class="sxs-lookup"><span data-stu-id="36aa6-118">To turn image tagging on or off</span></span>

1. <span data-ttu-id="36aa6-119">В Центре администрирования Microsoft 365 щелкните **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="36aa6-119">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="36aa6-120">В разделе **Знания организации** выберите **Автоматическое осмысление контента**.</span><span class="sxs-lookup"><span data-stu-id="36aa6-120">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="36aa6-121">Нажмите кнопку **Управление**.</span><span class="sxs-lookup"><span data-stu-id="36aa6-121">Click **Manage**.</span></span>

4. <span data-ttu-id="36aa6-122">На вкладке **Расстановка тегов для изображений** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="36aa6-122">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="36aa6-123">Выберите разрешить **Базовую расстановку тегов** или **Отключить** расстановку тегов.</span><span class="sxs-lookup"><span data-stu-id="36aa6-123">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="36aa6-124">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="36aa6-124">Click **Save**.</span></span>

    ![Снимок экрана элемента управления расстановкой тегов для изображений](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
