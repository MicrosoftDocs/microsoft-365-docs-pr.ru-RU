---
title: Удаление данных Microsoft 365 SharePoint Online
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: Сведения о том, как удаление данных работает в SharePoint Online, например, место хранения удаленного контента и продолжительность.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e914e84f3679483e5030b7f2a06913cb052e5411
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332728"
---
# <a name="sharepoint-online-data-deletion-in-microsoft-365"></a><span data-ttu-id="0c762-103">Удаление данных SharePoint Online в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c762-103">SharePoint Online Data Deletion in Microsoft 365</span></span>

<span data-ttu-id="0c762-104">SharePoint Online хранит объекты в виде абстрактного кода в базах данных приложений.</span><span class="sxs-lookup"><span data-stu-id="0c762-104">SharePoint Online stores objects as abstracted code within application databases.</span></span> <span data-ttu-id="0c762-105">Когда пользователь отправляет файл в SharePoint Online, этот файл разбивается и преобразуется в код приложения и хранится в нескольких таблицах нескольких баз данных.</span><span class="sxs-lookup"><span data-stu-id="0c762-105">When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases.</span></span> <span data-ttu-id="0c762-106">В SharePoint Online весь контент, который отправляет клиент, разбивается на блоки, шифруются (потенциально с несколькими ключами AES 256-bit) и распределяются в центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="0c762-106">In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter.</span></span> <span data-ttu-id="0c762-107">Конкретные сведения о процессе фрагментирования и шифровании приведены в разделе [Шифрование в Microsoft Cloud](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).</span><span class="sxs-lookup"><span data-stu-id="0c762-107">For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).</span></span> 

<span data-ttu-id="0c762-108">В SharePoint Online элементы сохраняются в течение 93 дней с момента их удаления из исходного расположения.</span><span class="sxs-lookup"><span data-stu-id="0c762-108">In SharePoint Online, items are retained for 93 days from the time you delete them from their original location.</span></span> <span data-ttu-id="0c762-109">Они остаются в корзине сайта все время, если кто-то не удаляет их из нее или очищает корзину.</span><span class="sxs-lookup"><span data-stu-id="0c762-109">They stay in the site Recycle Bin the entire time, unless someone deletes them from there or empties that Recycle Bin.</span></span> <span data-ttu-id="0c762-110">В этом случае элементы помещаются в корзину семейства веб-сайтов, где они остаются в оставшейся части 93 дней.</span><span class="sxs-lookup"><span data-stu-id="0c762-110">In that case, the items go to the site collection Recycle Bin, where they stay for the remainder of the 93 days.</span></span> <span data-ttu-id="0c762-111">Сведения о восстановлении удаленных элементов см [в разделе Восстановление элементов в корзине сайта SharePoint](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) и [Восстановление удаленных элементов из корзины семейства веб-сайтов](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b).</span><span class="sxs-lookup"><span data-stu-id="0c762-111">For info about restoring deleted items, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) and [Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b).</span></span> <span data-ttu-id="0c762-112">Время хранения в корзине не настраивается в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0c762-112">The Recycle Bin retention time is not configurable in SharePoint Online.</span></span>

<span data-ttu-id="0c762-113">При удалении семейства веб-сайтов вы также удаляете иерархию сайтов в коллекции и весь контент в них:</span><span class="sxs-lookup"><span data-stu-id="0c762-113">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, and all content within them:</span></span>

- <span data-ttu-id="0c762-114">документы и библиотеки документов;</span><span class="sxs-lookup"><span data-stu-id="0c762-114">Documents and document libraries</span></span>
- <span data-ttu-id="0c762-115">Списки и данные списков</span><span class="sxs-lookup"><span data-stu-id="0c762-115">Lists and list data</span></span>
- <span data-ttu-id="0c762-116">Параметры конфигурации сайта</span><span class="sxs-lookup"><span data-stu-id="0c762-116">Site configuration settings</span></span>
- <span data-ttu-id="0c762-117">Сведения о ролях и безопасности, связанные с сайтом или его дочерними сайтами</span><span class="sxs-lookup"><span data-stu-id="0c762-117">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="0c762-118">Дочерние сайты веб-сайта верхнего уровня, их содержимое и сведения о пользователях</span><span class="sxs-lookup"><span data-stu-id="0c762-118">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="0c762-119">Если вы случайно удалили семейство веб-сайтов, его можно восстановить с помощью глобального администратора или администратора SharePoint с помощью центра администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0c762-119">If you accidentally delete a site collection, it can be restored by a global or SharePoint admin using the SharePoint admin center.</span></span>

<span data-ttu-id="0c762-120">Удаленные семейства веб-сайтов хранятся в течение 93 дней.</span><span class="sxs-lookup"><span data-stu-id="0c762-120">Deleted site collections are retained for 93 days.</span></span> <span data-ttu-id="0c762-121">По истечении 93 дней сайты и все их содержимое с параметрами, в том числе списки, библиотеки, страницы и любые дочерние сайты, удаляются без возможности восстановления.</span><span class="sxs-lookup"><span data-stu-id="0c762-121">After 93 days, sites and all their content and settings are permanently deleted, including lists, libraries, pages, and any subsites.</span></span>

<span data-ttu-id="0c762-122">Окончательное удаление происходит, когда пользователь удаляет удаленные элементы из корзины семейства веб-сайтов, когда истечет срок хранения и сроки резервного копирования, или когда администратор окончательно удаляет семейство сайтов с помощью [командлета Recycle-SPODeletedSite](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="0c762-122">Hard deletion occurs when a user purges deleted items from the site collection Recycle Bin, when the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps).</span></span> <span data-ttu-id="0c762-123">При окончательном удалении (окончательном удалении или очистке) контента из SharePoint Online все ключи шифрования для удаленных блоков также удаляются.</span><span class="sxs-lookup"><span data-stu-id="0c762-123">When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted.</span></span> <span data-ttu-id="0c762-124">Блоки на дисках, которые ранее сохраняли удаленные блоки, помечаются как неиспользуемые и доступны для повторного использования.</span><span class="sxs-lookup"><span data-stu-id="0c762-124">The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
