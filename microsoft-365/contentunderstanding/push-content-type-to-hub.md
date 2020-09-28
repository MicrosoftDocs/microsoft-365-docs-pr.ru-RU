---
title: Передача типов контента концентратору
description: Сведения о том, как отправлять типы контента в концентратор
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a852207bfd1a2a7643ce8895a533371d194954cf
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296100"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="6e4e6-103">Передача типов контента концентратору</span><span class="sxs-lookup"><span data-stu-id="6e4e6-103">Push content types to a hub</span></span>

<span data-ttu-id="6e4e6-104">Чтобы важные типы контента были более согласованно доступны в библиотеках и списках SharePoint, их можно переместить на выбранные вами концентраторы.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="6e4e6-105">Это автоматически добавляет их в любые новые списки и библиотеки, созданные на сайтах, связанных с концентратором, а также на все новые сайты, добавленные в концентратор.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-105">This automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="6e4e6-106">Чтобы эта функция работала, отправляемые типы контента уже должны быть опубликованы.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-106">For this feature to work, The content types being pushed must already be published.</span></span>

<span data-ttu-id="6e4e6-107">Передача типов контента в концентраторы</span><span class="sxs-lookup"><span data-stu-id="6e4e6-107">To push content types to hubs</span></span>

1. <span data-ttu-id="6e4e6-108">В центре администрирования SharePoint разверните узел **службы содержимого**и выберите **Коллекция типов контента**.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-108">In the SharePoint admin center, expand **Content services**, and then click **Content type gallery**.</span></span>

2. <span data-ttu-id="6e4e6-109">Щелкните тип контента, который нужно передать в концентраторы.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-109">Click the content type that you want to push to hubs.</span></span>

3. <span data-ttu-id="6e4e6-110">Нажмите кнопку **изменить** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-110">Click **Edit** in the command bar.</span></span>
 
4. <span data-ttu-id="6e4e6-111">Нажмите кнопку **выбрать центральные сайты**.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-111">Click **Choose hub sites**.</span></span>
 
5. <span data-ttu-id="6e4e6-112">Выберите нужные центральные сайты и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-112">Select the desired hub sites and then click **OK**.</span></span>
 
6. <span data-ttu-id="6e4e6-113">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-113">Click **Save**.</span></span>

<span data-ttu-id="6e4e6-114">При повторной отправке типа контента существующему концентратору & его существующие связанные сайты, он может занять до часа после посещения концентратора или связанных сайтов, чтобы обновить параметры на сайте.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-114">When pushing a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="6e4e6-115">Все новые связи с концентратором не требуют этого ожидания, и параметры будут отражены в течение нескольких минут.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-115">Any new associations to the hub will not require this wait and will have the settings reflected in a few minutes.</span></span> 

<span data-ttu-id="6e4e6-116">После настройки этот тип контента с этими параметрами будет доступен всем новым связанным сайтам с концентратором через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-116">Once this is configured, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="6e4e6-117">После этого любой новый список или созданная библиотека автоматически добавит тип контента в течение нескольких минут создания.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-117">Once available, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="6e4e6-118">Переданный тип контента будет добавлен в библиотеку документов только в том случае, если он прямо или косвенно является производным от типа контента документа, а тип контента будет добавлен в список только в том случае, если он не является напрямую или косвенно производным от типа контента документа.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e4e6-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6e4e6-119">See also</span></span>



  






