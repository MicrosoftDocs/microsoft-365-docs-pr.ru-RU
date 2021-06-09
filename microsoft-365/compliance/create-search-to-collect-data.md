---
title: Создание поискового запроса
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Узнайте, как создать, определить и выбрать хранители и места для поиска в Advanced eDiscovery случае.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1d9051824ff3f28484d0750b982edd70334a9b88
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035771"
---
# <a name="create-a-search"></a><span data-ttu-id="9024b-103">Создание поискового запроса</span><span class="sxs-lookup"><span data-stu-id="9024b-103">Create a search</span></span>

<span data-ttu-id="9024b-104">На **вкладке Поиск** в вашем случае можно создать новый поиск, щелкнув **новый** поиск и следуя за мастером.</span><span class="sxs-lookup"><span data-stu-id="9024b-104">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

![Мастер поиска в Advanced eDiscovery случае](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a><span data-ttu-id="9024b-106">Назови поиск и дайте ему описание</span><span class="sxs-lookup"><span data-stu-id="9024b-106">Name the search and give it a description</span></span>

<span data-ttu-id="9024b-107">Каждый поиск с случаем должен иметь уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="9024b-107">Each search with a case should have a unique name.</span></span> <span data-ttu-id="9024b-108">Вы можете дополнительно предоставить описание для поиска.</span><span class="sxs-lookup"><span data-stu-id="9024b-108">You can optionally provide a description for your search.</span></span> 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a><span data-ttu-id="9024b-109">Выбор хранителей и местоположений для поиска</span><span class="sxs-lookup"><span data-stu-id="9024b-109">Choose the custodians and custodial locations to search</span></span>

<span data-ttu-id="9024b-110">Выберите расположения контента хранителя для поиска, указав, что хранители, добавленные в дело.</span><span class="sxs-lookup"><span data-stu-id="9024b-110">Choose custodian content locations to search by specifying that custodians you have added to the case.</span></span> <span data-ttu-id="9024b-111">Выбрав хранителя, вы запустите поиск по всем источникам данных, отображымся к хранителям.</span><span class="sxs-lookup"><span data-stu-id="9024b-111">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="9024b-112">У вас также есть возможность сузить поиск до выбранных источников данных для каждого хранителя.</span><span class="sxs-lookup"><span data-stu-id="9024b-112">You also have the option to narrow the search to selected data sources for each custodian.</span></span> <span data-ttu-id="9024b-113">Дополнительные сведения о том, как добавлять хранителей и управлять их источниками данных, см. в этой ссылке [Работа с хранителями.](managing-custodians.md)</span><span class="sxs-lookup"><span data-stu-id="9024b-113">For more information about how to add custodians and manage their data sources, see [Work with custodians](managing-custodians.md).</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="9024b-114">Выбор местоположений, не отбираемых для содержания под стражей</span><span class="sxs-lookup"><span data-stu-id="9024b-114">Choose non-custodial locations</span></span>

<span data-ttu-id="9024b-115">В некоторых случаях может потребоваться поиск источников данных, не связанных с хранителями.</span><span class="sxs-lookup"><span data-stu-id="9024b-115">In some cases, you may want to search data sources that are not associated with a custodian.</span></span> <span data-ttu-id="9024b-116">В этом случае можно указать расположения, которые необходимо искать, или выбрать для поиска все расположения контента для определенной службы Майкрософт (например, поиска всех Exchange почтовых ящиков или всех SharePoint сайтов и OneDrive учетных записей).</span><span class="sxs-lookup"><span data-stu-id="9024b-116">In this case, you can specify the locations you want to search, or choose to search all content locations for a specific Microsoft service (such as searching all Exchange mailboxes or all SharePoint sites and OneDrive accounts).</span></span>

## <a name="define-the-search-query-and-conditions"></a><span data-ttu-id="9024b-117">Определение запроса и условий поиска</span><span class="sxs-lookup"><span data-stu-id="9024b-117">Define the search query and conditions</span></span>

<span data-ttu-id="9024b-118">Вы можете определить запрос по ключевым словам и любые условия для поиска с помощью предварительно построенных карт условий или с помощью языка запросов ключевых слов (KQL).</span><span class="sxs-lookup"><span data-stu-id="9024b-118">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="9024b-119">Дополнительные сведения см. в [см. в руб. Сборка поисковых запросов.](building-search-queries.md)</span><span class="sxs-lookup"><span data-stu-id="9024b-119">For more information, see [Build search queries](building-search-queries.md).</span></span>
