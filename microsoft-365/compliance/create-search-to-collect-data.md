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
description: ''
ms.openlocfilehash: 47d30cb2da91eff1260ffcf07838bd066917b4a1
ms.sourcegitcommit: dcea75af89f5f80ec6670346ee176407e043de54
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "42610646"
---
# <a name="create-a-search"></a><span data-ttu-id="d7a06-102">Создание поискового запроса</span><span class="sxs-lookup"><span data-stu-id="d7a06-102">Create a search</span></span>

<span data-ttu-id="d7a06-103">На вкладке **поиски** можно создать новый поиск, нажав кнопку **Новый поиск** и следуя инструкциям мастера.</span><span class="sxs-lookup"><span data-stu-id="d7a06-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

![Мастер поиска в расширенном случае обнаружения электронных данных](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a><span data-ttu-id="d7a06-105">Назовите Поиск и присвойте ему описание</span><span class="sxs-lookup"><span data-stu-id="d7a06-105">Name the search and give it a description</span></span>

<span data-ttu-id="d7a06-106">Каждый Поиск с обращением должен иметь уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="d7a06-106">Each search with a case should have a unique name.</span></span> <span data-ttu-id="d7a06-107">При необходимости можно ввести описание поиска.</span><span class="sxs-lookup"><span data-stu-id="d7a06-107">You can optionally provide a description for your search.</span></span> 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a><span data-ttu-id="d7a06-108">Выбор расположений custodians и кустодиал для поиска</span><span class="sxs-lookup"><span data-stu-id="d7a06-108">Choose the custodians and custodial locations to search</span></span>

<span data-ttu-id="d7a06-109">Выберите хранитель расположения контента для поиска, указав, что к этому случаю добавляется custodians.</span><span class="sxs-lookup"><span data-stu-id="d7a06-109">Choose custodian content locations to search by specifying that custodians you have added to the case.</span></span> <span data-ttu-id="d7a06-110">Выбрав хранитель, вы будете выполнять поиск по всем источникам данных, сопоставленным с хранитель.</span><span class="sxs-lookup"><span data-stu-id="d7a06-110">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="d7a06-111">Кроме того, существует возможность сужения поиска до выбранных источников данных для каждого хранитель.</span><span class="sxs-lookup"><span data-stu-id="d7a06-111">You also have the option to narrow the search to selected data sources for each custodian.</span></span> <span data-ttu-id="d7a06-112">Дополнительные сведения о том, как добавлять custodians и управлять их источниками данных, приведены [в статье работа с custodians](managing-custodians.md).</span><span class="sxs-lookup"><span data-stu-id="d7a06-112">For more information about how to add custodians and manage their data sources, see [Work with custodians](managing-custodians.md).</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="d7a06-113">Выбор расположений, не являющихся кустодиалми</span><span class="sxs-lookup"><span data-stu-id="d7a06-113">Choose non-custodial locations</span></span>

<span data-ttu-id="d7a06-114">В некоторых случаях может потребоваться поиск в источниках данных, не связанных с хранитель.</span><span class="sxs-lookup"><span data-stu-id="d7a06-114">In some cases, you may want to search data sources that are not associated with a custodian.</span></span> <span data-ttu-id="d7a06-115">В этом случае можно указать расположения для поиска или выбрать поиск по всем расположениям для определенной службы Office 365 (например, поиск по всем почтовым ящикам Exchange или всем сайтам SharePoint и учетным записям OneDrive).</span><span class="sxs-lookup"><span data-stu-id="d7a06-115">In this case, you can specify the locations you want to search, or choose to search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or all SharePoint sites and OneDrive accounts).</span></span>

## <a name="define-the-search-query-and-conditions"></a><span data-ttu-id="d7a06-116">Определение запроса и условий поиска</span><span class="sxs-lookup"><span data-stu-id="d7a06-116">Define the search query and conditions</span></span>

<span data-ttu-id="d7a06-117">Вы можете определить запрос ключевых слов и условия поиска с помощью встроенных карточек условий или с помощью языка запросов по ключевым словам (KQL).</span><span class="sxs-lookup"><span data-stu-id="d7a06-117">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="d7a06-118">Более подробную информацию можно узнать в статье [Создание поисковых запросов](building-search-queries.md).</span><span class="sxs-lookup"><span data-stu-id="d7a06-118">For more information, see [Build search queries](building-search-queries.md).</span></span>
