---
title: Расстановка тегов для изображений в SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Сведения о расстановке тегов для изображений в SharePoint Syntex
ms.openlocfilehash: 38b9ad6823aa5f63a4ddec87bab7fec52a37f163
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296095"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="4d64a-103">Расстановка тегов для изображений в SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="4d64a-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="4d64a-104">По умолчанию для SharePoint и OneDrive включена базовая расстановка тегов для изображений.</span><span class="sxs-lookup"><span data-stu-id="4d64a-104">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="4d64a-105">Изображения, отправленные в какое-либо расположение, автоматически сканируются и к ним применяются применимые теги (при наличии) из списка 37 основных тегов.</span><span class="sxs-lookup"><span data-stu-id="4d64a-105">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="4d64a-106">Пользователи могут находить изображения с помощью поиска, выполняя поиск по тегам изображения.</span><span class="sxs-lookup"><span data-stu-id="4d64a-106">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="4d64a-107">Процесс расстановки тегов запускается автоматически при отправке изображения.</span><span class="sxs-lookup"><span data-stu-id="4d64a-107">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="4d64a-108">Если изображение будет изменено, процесс расстановки тегов запустится снова, чтобы обновить теги.</span><span class="sxs-lookup"><span data-stu-id="4d64a-108">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="4d64a-109">Пользователи с разрешениями на доступ к файлу изображения могут просматривать и редактировать теги на панели сведений о файле или на странице результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="4d64a-109">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="4d64a-110">Если пользователь изменит теги изображения, система больше не будет выполнять автоматическую расстановку тегов для этого изображения, даже если оно будет изменено.</span><span class="sxs-lookup"><span data-stu-id="4d64a-110">Once a user edits an image's tags, the system no longer performs auto-tagging on that image, even if it is edited.</span></span>

<span data-ttu-id="4d64a-111">Если вы отключите расстановку тегов, изображения больше не будут автоматически ими помечаться.</span><span class="sxs-lookup"><span data-stu-id="4d64a-111">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="4d64a-112">Существующие теги не будут удалены.</span><span class="sxs-lookup"><span data-stu-id="4d64a-112">Existing tags will not be removed.</span></span>

## <a name="configure-image-tagging"></a><span data-ttu-id="4d64a-113">Настройка расстановки тегов для изображений</span><span class="sxs-lookup"><span data-stu-id="4d64a-113">Configure image tagging</span></span>

<span data-ttu-id="4d64a-114">Расстановку тегов для изображений можно настроить в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4d64a-114">You can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="4d64a-115">Включение и отключение расстановки тегов для изображений</span><span class="sxs-lookup"><span data-stu-id="4d64a-115">To turn image tagging on or off</span></span>

1. <span data-ttu-id="4d64a-116">В Центре администрирования Microsoft 365 щелкните **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="4d64a-116">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="4d64a-117">В разделе **Знания организации** выберите **Автоматическое осмысление контента**.</span><span class="sxs-lookup"><span data-stu-id="4d64a-117">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="4d64a-118">Нажмите кнопку **Управление**.</span><span class="sxs-lookup"><span data-stu-id="4d64a-118">Click **Manage**.</span></span>

4. <span data-ttu-id="4d64a-119">На вкладке **Расстановка тегов для изображений** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="4d64a-119">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="4d64a-120">Выберите разрешить **Базовую расстановку тегов** или **Отключить** расстановку тегов.</span><span class="sxs-lookup"><span data-stu-id="4d64a-120">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="4d64a-121">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4d64a-121">Click **Save**.</span></span>

    ![Снимок экрана элемента управления расстановкой тегов для изображений](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)

## <a name="see-also"></a><span data-ttu-id="4d64a-123">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="4d64a-123">See also</span></span>

[<span data-ttu-id="4d64a-124">Настройка осмысления контента</span><span class="sxs-lookup"><span data-stu-id="4d64a-124">Set up content understanding</span></span>](set-up-content-understanding.md)