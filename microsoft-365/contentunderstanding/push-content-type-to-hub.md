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
localization_priority: Priority
ms.openlocfilehash: 03e1be51b35447376be5adfc2f2cd3c944cf89fa
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321341"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="9bd4b-103">Отправка типов контента на центральный сайт</span><span class="sxs-lookup"><span data-stu-id="9bd4b-103">Push content types to a hub</span></span>

<span data-ttu-id="9bd4b-104">Чтобы обеспечить доступность важных типов контента в библиотеках и списках SharePoint, вы можете отправить их на один из центральных сайтов.</span><span class="sxs-lookup"><span data-stu-id="9bd4b-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="9bd4b-105">Они будут автоматически добавлены в новые списки и библиотеки, созданные на сайтах, связанных с центральным сайтом, и на любые новые сайты, добавляемые в этот центр.</span><span class="sxs-lookup"><span data-stu-id="9bd4b-105">This automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="9bd4b-106">Чтобы эта функция работала, типы контента, которые нужно отправить, должны быть уже опубликованы.</span><span class="sxs-lookup"><span data-stu-id="9bd4b-106">For this feature to work, The content types being pushed must already be published.</span></span>

<span data-ttu-id="9bd4b-107">Отправка типов контента на центральный сайт</span><span class="sxs-lookup"><span data-stu-id="9bd4b-107">To push content types to hubs</span></span>

1. <span data-ttu-id="9bd4b-108">В центре администрирования SharePoint разверните раздел **Службы контента**, а затем выберите пункт **Коллекция типов контента**.</span><span class="sxs-lookup"><span data-stu-id="9bd4b-108">In the SharePoint admin center, expand **Content services**, and then click **Content type gallery**.</span></span>

2. <span data-ttu-id="9bd4b-109">Выберите тип контента, который нужно отправить на центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="9bd4b-109">Click the content type that you want to push to hubs.</span></span>

3. <span data-ttu-id="9bd4b-110">На панели команд нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9bd4b-110">Click **Edit** in the command bar.</span></span>
 
4. <span data-ttu-id="9bd4b-111">Нажмите кнопку **Выбрать центральный сайт**.</span><span class="sxs-lookup"><span data-stu-id="9bd4b-111">Click **Choose hub sites**.</span></span>
 
5. <span data-ttu-id="9bd4b-112">Выберите нужные центры, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9bd4b-112">Select the desired hub sites and then click **OK**.</span></span>
 
6. <span data-ttu-id="9bd4b-113">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9bd4b-113">Click **Save**.</span></span>

<span data-ttu-id="9bd4b-114">При отправлении типа контента на существующий центр и его связанные сайты в первый раз может потребоваться до часа, чтобы обновить параметры на сайте.</span><span class="sxs-lookup"><span data-stu-id="9bd4b-114">When pushing a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="9bd4b-115">Для всех новых связей с центральным сайтом не потребуется такое ожидание. Параметры вступят в силу в течение нескольких минут.</span><span class="sxs-lookup"><span data-stu-id="9bd4b-115">Any new associations to the hub will not require this wait and will have the settings reflected in a few minutes.</span></span> 

<span data-ttu-id="9bd4b-116">После настройки тип контента с такими параметрами будет доступен на всех сайтах, связанных с центром через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="9bd4b-116">Once this is configured, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="9bd4b-117">Тип контента любого нового списка или библиотеки будет автоматически добавлен в течение нескольких минут после создания.</span><span class="sxs-lookup"><span data-stu-id="9bd4b-117">Once available, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="9bd4b-118">Добавленный тип контента будет добавлен в библиотеку документов только в том случае, если он прямо или косвенно наследуется из типа "Документ". Тип контента будет добавлен в список только в том случае, если он не наследуется прямо или косвенно из типа "Документ".</span><span class="sxs-lookup"><span data-stu-id="9bd4b-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="9bd4b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9bd4b-119">See also</span></span>



  






