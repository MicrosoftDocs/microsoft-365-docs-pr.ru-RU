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
ms.openlocfilehash: ab57bcd3cd21d691e8c2dc669a55588dbcaa886b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595556"
---
# <a name="create-a-search"></a><span data-ttu-id="45cb6-102">Создание поискового запроса</span><span class="sxs-lookup"><span data-stu-id="45cb6-102">Create a search</span></span>

<span data-ttu-id="45cb6-103">На вкладке **поиски** можно создать новый поиск, нажав кнопку **Новый поиск** и следуя инструкциям мастера.</span><span class="sxs-lookup"><span data-stu-id="45cb6-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

## <a name="name-your-search-and-give-it-a-description"></a><span data-ttu-id="45cb6-104">Назовите Поиск и присвойте ему описание</span><span class="sxs-lookup"><span data-stu-id="45cb6-104">Name your search and give it a description</span></span>

<span data-ttu-id="45cb6-105">Каждый Поиск с обращением должен иметь уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="45cb6-105">Each search with a case should have a unique name.</span></span> <span data-ttu-id="45cb6-106">При необходимости можно ввести описание поиска.</span><span class="sxs-lookup"><span data-stu-id="45cb6-106">You can optionally provide a description for your search.</span></span> 

## <a name="define-your-search-query-and-conditions"></a><span data-ttu-id="45cb6-107">Определение запросов и условий поиска</span><span class="sxs-lookup"><span data-stu-id="45cb6-107">Define your search query and conditions</span></span>

<span data-ttu-id="45cb6-108">Вы можете определить запрос ключевых слов и условия поиска с помощью встроенных карточек условий или с помощью языка запросов по ключевым словам (KQL).</span><span class="sxs-lookup"><span data-stu-id="45cb6-108">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="45cb6-109">Более подробную информацию можно узнать в статье [Создание поисковых запросов](building-search-queries.md).</span><span class="sxs-lookup"><span data-stu-id="45cb6-109">For more information, see [Build search queries](building-search-queries.md).</span></span>

## <a name="choose-the-custodians-to-search-from"></a><span data-ttu-id="45cb6-110">Выбор custodians для поиска</span><span class="sxs-lookup"><span data-stu-id="45cb6-110">Choose the custodians to search from</span></span>

<span data-ttu-id="45cb6-111">Определив условия, необходимо выбрать расположения, в которых будет выполняться поиск.</span><span class="sxs-lookup"><span data-stu-id="45cb6-111">Once you have defined your conditions, you need to choose which locations you want to search.</span></span> <span data-ttu-id="45cb6-112">Один из способов сделать это — указать, какие custodians вы уже добавили в тот случай, когда вы хотите выполнить поиск.</span><span class="sxs-lookup"><span data-stu-id="45cb6-112">One way to do it is by specifying which custodians you have already added to the case you want to search.</span></span> <span data-ttu-id="45cb6-113">Выбрав хранитель, вы будете выполнять поиск по всем источникам данных, сопоставленным с хранитель.</span><span class="sxs-lookup"><span data-stu-id="45cb6-113">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="45cb6-114">Для получения дополнительных сведений о том, как добавить custodians к своему случаю и управлять их источниками данных, ознакомьтесь со статьей [Working with custodians](managing-custodians.md) .</span><span class="sxs-lookup"><span data-stu-id="45cb6-114">See [Work with custodians](managing-custodians.md) for more information on how to add custodians to your case and manage their data sources.</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="45cb6-115">Выбор расположений, не являющихся кустодиалми</span><span class="sxs-lookup"><span data-stu-id="45cb6-115">Choose non-custodial locations</span></span>

<span data-ttu-id="45cb6-116">В некоторых случаях может потребоваться поиск в источниках данных, которые не сопоставлены с хранитель.</span><span class="sxs-lookup"><span data-stu-id="45cb6-116">In some cases, you may wish to search data sources that are not mapped to a custodian.</span></span> <span data-ttu-id="45cb6-117">В этом случае можно указать расположения, в которых требуется выполнить поиск, или выбрать поиск по всем расположениям для определенной службы Office 365 (например, поиск по всем почтовым ящикам Exchange или всем сайтам SharePoint и OneDrive для бизнеса).</span><span class="sxs-lookup"><span data-stu-id="45cb6-117">In this case, you can specify the locations you would like to search, or choose to search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or all SharePoint and OneDrive for Business sites).</span></span>