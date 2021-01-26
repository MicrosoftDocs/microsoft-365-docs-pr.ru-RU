---
title: Отправка типов контента на центральный сайт
description: Узнайте, как отправлять типы контента на центральный сайт
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
localization_priority: Priority
ms.openlocfilehash: 89c03a70da364bd4b945debc64de02255dec15e1
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975719"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="19727-103">Отправка типов контента на центральный сайт</span><span class="sxs-lookup"><span data-stu-id="19727-103">Push content types to a hub</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


<span data-ttu-id="19727-104">Чтобы обеспечить доступность важных типов контента в библиотеках и списках SharePoint, вы можете отправить их на один из центральных сайтов.</span><span class="sxs-lookup"><span data-stu-id="19727-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="19727-105">Отправка типов контента обеспечивает их автоматическое добавление в новые списки и библиотеки, созданные на сайтах, связанных с центральным сайтом, и на любые новые сайты, добавляемые в этот центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="19727-105">Pushing the content types automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="19727-106">Чтобы эта функция работала, типы контента, которые нужно отправить, должны быть уже опубликованы.</span><span class="sxs-lookup"><span data-stu-id="19727-106">For this feature to work, the content types being pushed must already be published.</span></span>

<span data-ttu-id="19727-107">Отправка типов контента на центральный сайт</span><span class="sxs-lookup"><span data-stu-id="19727-107">To push content types to hubs</span></span>

1. <span data-ttu-id="19727-108">В Центре администрирования SharePoint разверните раздел **Службы контента** и выберите **Коллекция типов контента**.</span><span class="sxs-lookup"><span data-stu-id="19727-108">In the SharePoint admin center, expand **Content services**, and then select **Content type gallery**.</span></span>
2. <span data-ttu-id="19727-109">Выберите тип контента, который нужно отправить на центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="19727-109">Select the content type that you want to push to hubs.</span></span>
3. <span data-ttu-id="19727-110">На панели команд нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="19727-110">Select **Edit** in the command bar.</span></span>
4. <span data-ttu-id="19727-111">Нажмите **Выбрать центральный сайт**.</span><span class="sxs-lookup"><span data-stu-id="19727-111">Select **Choose hub sites**.</span></span>
5. <span data-ttu-id="19727-112">Выберите нужные центральные сайты и нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="19727-112">Select the hub sites you want and then choose **OK**.</span></span>
6. <span data-ttu-id="19727-113">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="19727-113">Choose **Save**.</span></span>

<span data-ttu-id="19727-114">При первой отправке типа контента на существующий центральный сайт и его связанные сайты может потребоваться до часа, чтобы обновить параметры на сайте.</span><span class="sxs-lookup"><span data-stu-id="19727-114">When you push a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="19727-115">Для всех новых связей с центральным сайтом не потребуется такое ожидание. Параметры вступят в силу в течение нескольких минут.</span><span class="sxs-lookup"><span data-stu-id="19727-115">Any new associations to the hub won't require this wait and will have the settings reflected in a few minutes.</span></span>

<span data-ttu-id="19727-116">После обновления параметров тип контента с этими параметрами будет доступен через несколько минут на всех сайтах, связанных с центральным сайтом.</span><span class="sxs-lookup"><span data-stu-id="19727-116">After the settings are updated, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="19727-117">После этого в любой новый список или созданную библиотеку тип контента будет автоматически добавляться в течение нескольких минут после создания.</span><span class="sxs-lookup"><span data-stu-id="19727-117">Then, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="19727-118">Добавленный тип контента будет добавлен в библиотеку документов только в том случае, если он прямо или косвенно наследуется из типа "Документ". Тип контента будет добавлен в список только в том случае, если он не наследуется прямо или косвенно из типа "Документ".</span><span class="sxs-lookup"><span data-stu-id="19727-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="19727-119">См. также</span><span class="sxs-lookup"><span data-stu-id="19727-119">See also</span></span>
