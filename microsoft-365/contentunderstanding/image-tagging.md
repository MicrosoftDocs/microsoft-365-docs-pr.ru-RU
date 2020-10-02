---
title: Расстановка тегов для изображений в SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: MET150
localization_priority: Priority
description: Сведения о расстановке тегов для изображений в SharePoint Syntex
ms.openlocfilehash: 7b41422633934593de881bdb0c04f0a845a3fe5f
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321257"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="d8108-103">Расстановка тегов для изображений в SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="d8108-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="d8108-104">Расстановка тегов для изображений в SharePoint Syntex помогает пользователям находить нужные изображения и создавать процессы на базе тегов.</span><span class="sxs-lookup"><span data-stu-id="d8108-104">With image tagging in SharePoint Syntex, users can find images through search by searching on image tags, and create workflows based on image tags.</span></span> <span data-ttu-id="d8108-105">По умолчанию для SharePoint и OneDrive включена базовая расстановка тегов для изображений.</span><span class="sxs-lookup"><span data-stu-id="d8108-105">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="d8108-106">Изображения, отправленные в какое-либо расположение, автоматически сканируются и к ним применяются применимые теги (при наличии) из списка 37 основных тегов.</span><span class="sxs-lookup"><span data-stu-id="d8108-106">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="d8108-107">Пользователи могут находить изображения с помощью поиска, выполняя поиск по тегам изображения.</span><span class="sxs-lookup"><span data-stu-id="d8108-107">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="d8108-108">Процесс расстановки тегов запускается автоматически при отправке изображения.</span><span class="sxs-lookup"><span data-stu-id="d8108-108">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="d8108-109">Если изображение будет изменено, процесс расстановки тегов запустится снова, чтобы обновить теги.</span><span class="sxs-lookup"><span data-stu-id="d8108-109">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="d8108-110">Пользователи с разрешениями на доступ к файлу изображения могут просматривать и редактировать теги на панели сведений о файле или на странице результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="d8108-110">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="d8108-111">Если пользователь изменит теги изображения, система больше не будет автоматически расставлять теги для этого изображения, даже если оно будет изменено.</span><span class="sxs-lookup"><span data-stu-id="d8108-111">Once a user edits an image's tags, the system no longer auto-tags that image, even if it's edited.</span></span>

<span data-ttu-id="d8108-112">Если вы отключите расстановку тегов, изображения больше не будут автоматически ими помечаться.</span><span class="sxs-lookup"><span data-stu-id="d8108-112">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="d8108-113">Существующие теги не будут удалены.</span><span class="sxs-lookup"><span data-stu-id="d8108-113">Existing tags won't be removed.</span></span>

> [!NOTE]
> <span data-ttu-id="d8108-114">Теги, созданные системой, могут измениться в связи с изменением изображения или нашей технологии тегов.</span><span class="sxs-lookup"><span data-stu-id="d8108-114">System generated tags may change with updates to the image or our tag technology.</span></span>


## <a name="configure-image-tagging"></a><span data-ttu-id="d8108-115">Настройка расстановки тегов для изображений</span><span class="sxs-lookup"><span data-stu-id="d8108-115">Configure image tagging</span></span>

<span data-ttu-id="d8108-116">После [настройки SharePoint Syntex](set-up-content-understanding.md) вы можете настроить расстановку тегов для изображений в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8108-116">After you [set up SharePoint Syntex](set-up-content-understanding.md), you can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="d8108-117">Включение и отключение расстановки тегов для изображений</span><span class="sxs-lookup"><span data-stu-id="d8108-117">To turn image tagging on or off</span></span>

1. <span data-ttu-id="d8108-118">В Центре администрирования Microsoft 365 щелкните **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="d8108-118">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="d8108-119">В разделе **Знания организации** выберите **Автоматическое осмысление контента**.</span><span class="sxs-lookup"><span data-stu-id="d8108-119">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="d8108-120">Нажмите кнопку **Управление**.</span><span class="sxs-lookup"><span data-stu-id="d8108-120">Click **Manage**.</span></span>

4. <span data-ttu-id="d8108-121">На вкладке **Расстановка тегов для изображений** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="d8108-121">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="d8108-122">Выберите разрешить **Базовую расстановку тегов** или **Отключить** расстановку тегов.</span><span class="sxs-lookup"><span data-stu-id="d8108-122">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="d8108-123">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d8108-123">Click **Save**.</span></span>

    ![Снимок экрана элемента управления расстановкой тегов для изображений](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
