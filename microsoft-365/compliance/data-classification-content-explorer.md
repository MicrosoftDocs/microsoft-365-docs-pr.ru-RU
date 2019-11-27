---
title: Использование обозревателя содержимого с классификацией данных (предварительная версия)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Обозреватель содержимого позволяет легко просматривать элементы с присвоенными метками.
ms.openlocfilehash: 6f062901acbf149f6fc56c266d10b370ed0c1112
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "39268631"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="77bc8-103">Использование обозревателя содержимого с классификацией данных (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="77bc8-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="77bc8-104">Обозреватель содержимого с классификацией данных позволяет легко просматривать элементы, обобщенные на странице обзора.</span><span class="sxs-lookup"><span data-stu-id="77bc8-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="77bc8-105">Обозреватель содержимого</span><span class="sxs-lookup"><span data-stu-id="77bc8-105">Content explorer</span></span>

<span data-ttu-id="77bc8-106">Обозреватель содержимого — это текущий снимок элементов с присвоенными метками конфиденциальности или метками хранения, а также отнесенных к конфиденциальным сведениям в организации.</span><span class="sxs-lookup"><span data-stu-id="77bc8-106">Content explorer is a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

![снимок экрана: свернутый обозреватель содержимого](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="77bc8-108">Разрешения</span><span class="sxs-lookup"><span data-stu-id="77bc8-108">Permissions</span></span>

<span data-ttu-id="77bc8-109">Доступ к обозревателю содержимого предоставляется двумя ролями:</span><span class="sxs-lookup"><span data-stu-id="77bc8-109">There are two roles that grant access to Content explorer:</span></span>

- <span data-ttu-id="77bc8-110">**Роль просматривающего список обозревателя содержимого**. Участие в этой роли позволяет просматривать каждый элемент и его расположение.</span><span class="sxs-lookup"><span data-stu-id="77bc8-110">**Content Explorer List viewer**: Membership in this role allows you to see each item and its location.</span></span>

- <span data-ttu-id="77bc8-111">**Роль просматривающего контент обозревателя содержимого**. Участие в этой роли позволяет просматривать содержимое каждого элемента в списке.</span><span class="sxs-lookup"><span data-stu-id="77bc8-111">**Content Explorer Content viewer**: Membership in this role allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="77bc8-112">Учетной записи, используемой для доступа к обозревателю содержимого, должна быть присвоена одна или обе этих роли.</span><span class="sxs-lookup"><span data-stu-id="77bc8-112">The account you use to access Content explorer must be in one or both of the roles.</span></span> <span data-ttu-id="77bc8-113">Это независимые роли, не включающие в себя друг друга.</span><span class="sxs-lookup"><span data-stu-id="77bc8-113">These are independent roles and are not cumulative.</span></span> <span data-ttu-id="77bc8-114">Например, если вы хотите предоставить учетной записи возможность просматривать только элементы и их расположения, предоставьте права на просмотр списка обозревателя содержимого.</span><span class="sxs-lookup"><span data-stu-id="77bc8-114">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="77bc8-115">Если вы хотите, чтобы эта учетная запись также смогла просматривать содержимое элементов списка, дополнительно предоставьте права на просмотр контента обозревателя содержимого.</span><span class="sxs-lookup"><span data-stu-id="77bc8-115">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="77bc8-116">Использование обозревателя содержимого</span><span class="sxs-lookup"><span data-stu-id="77bc8-116">How to use content explorer</span></span>

1. <span data-ttu-id="77bc8-117">Откройте **Центр соответствия требованиям Microsoft 365**  > **Классификация данных** > **Обозреватель содержимого**.</span><span class="sxs-lookup"><span data-stu-id="77bc8-117">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="77bc8-118">Если вы знаете имя метки или тип конфиденциальной информации, можно ввести их в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="77bc8-118">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="77bc8-119">Или можно выполнить поиск элемента, развернув тип метки и выбрав метку из списка. Элемент из раздела списка с метками хранения отображается ниже.</span><span class="sxs-lookup"><span data-stu-id="77bc8-119">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="77bc8-120">Выберите расположение в разделе **Все расположения** и разверните структуру папок до элемента.</span><span class="sxs-lookup"><span data-stu-id="77bc8-120">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="77bc8-121">Дважды щелкните, чтобы открыть элемент в обозревателе содержимого.</span><span class="sxs-lookup"><span data-stu-id="77bc8-121">Double click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="77bc8-122">См. также</span><span class="sxs-lookup"><span data-stu-id="77bc8-122">See also</span></span>

- [<span data-ttu-id="77bc8-123">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="77bc8-123">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="77bc8-124">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="77bc8-124">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="77bc8-125">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="77bc8-125">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="77bc8-126">Обзор политик хранения</span><span class="sxs-lookup"><span data-stu-id="77bc8-126">Overview of retention policies</span></span>](retention-policies.md)
