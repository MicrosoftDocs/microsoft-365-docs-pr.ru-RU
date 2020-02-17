---
title: Использование обозревателя содержимого с классификацией данных (предварительная версия)
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 2d9be42c00940bf9d37d1fdeb9b15b071aa412ac
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076435"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="015fe-103">Использование обозревателя содержимого с классификацией данных (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="015fe-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="015fe-104">Обозреватель содержимого с классификацией данных позволяет легко просматривать элементы, обобщенные на странице обзора.</span><span class="sxs-lookup"><span data-stu-id="015fe-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="015fe-105">Обозреватель содержимого</span><span class="sxs-lookup"><span data-stu-id="015fe-105">Content explorer</span></span>

<span data-ttu-id="015fe-106">Обозреватель содержимого отображает текущий снимок элементов с присвоенными метками конфиденциальности или метками хранения, а также отнесенных к конфиденциальным сведениям в организации.</span><span class="sxs-lookup"><span data-stu-id="015fe-106">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="015fe-107">Типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="015fe-107">Sensitive information types</span></span>

<span data-ttu-id="015fe-108">[Политика защиты от потери данных](data-loss-prevention-policies.md) помогает защитить сведения, относящиеся к одному из **типов конфиденциальной информации**.</span><span class="sxs-lookup"><span data-stu-id="015fe-108">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="015fe-109">Microsoft 365 содержит готовые к использованию [определения для многих распространенных типов конфиденциальной информации](what-the-sensitive-information-types-look-for.md) из различных регионов. </span><span class="sxs-lookup"><span data-stu-id="015fe-109">Microsoft 365 includes [definitions for many common sensitive information types](what-the-sensitive-information-types-look-for.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="015fe-110">Например, номера кредитных карт, номера банковских счетов, национальные идентификационные номера и номера службы Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="015fe-110">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="015fe-111">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="015fe-111">Sensitivity labels</span></span>

<span data-ttu-id="015fe-112">[Метка конфиденциальности](sensitivity-labels.md) — это просто тег, обозначающий значение элемента для организации.</span><span class="sxs-lookup"><span data-stu-id="015fe-112">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="015fe-113">Ее можно применять вручную или автоматически.</span><span class="sxs-lookup"><span data-stu-id="015fe-113">It can be applied manually, or automatically.</span></span> <span data-ttu-id="015fe-114">После применения она внедряется в документ и повсюду следует за ним.</span><span class="sxs-lookup"><span data-stu-id="015fe-114">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="015fe-115">Метка конфиденциальности включает различные защитные действия, такие как обязательные водяные знаки или шифрование.</span><span class="sxs-lookup"><span data-stu-id="015fe-115">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="015fe-116">С включенной защитой конечной точки можно даже запретить элементу покидать организацию.</span><span class="sxs-lookup"><span data-stu-id="015fe-116">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="015fe-117">Для файлов SharePoint и OneDrive должны быть включены метки конфиденциальности, чтобы соответствующие данные отображались на странице классификации данных.</span><span class="sxs-lookup"><span data-stu-id="015fe-117">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="015fe-118">Дополнительные сведения см. в статье [Включение меток конфиденциальности для файлов Office в SharePoint и OneDrive (общедоступная предварительная версия)](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="015fe-118">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="015fe-119">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="015fe-119">Retention labels</span></span>

<span data-ttu-id="015fe-120">[Метка хранения](labels.md) позволяет определить срок хранения элемента с меткой и действия, которые необходимо выполнить перед его удалением.</span><span class="sxs-lookup"><span data-stu-id="015fe-120">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="015fe-121">Они применяются вручную или автоматически с помощью политик.</span><span class="sxs-lookup"><span data-stu-id="015fe-121">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="015fe-122">С их помощью можно обеспечивать соблюдение организацией юридических и нормативных требований.</span><span class="sxs-lookup"><span data-stu-id="015fe-122">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![снимок экрана: свернутый обозреватель содержимого](../media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="015fe-124">Разрешения</span><span class="sxs-lookup"><span data-stu-id="015fe-124">Permissions</span></span>

<span data-ttu-id="015fe-125">Доступ к обозревателю содержимого предоставляется двумя ролями:</span><span class="sxs-lookup"><span data-stu-id="015fe-125">There are two roles that grant access to content explorer:</span></span>

- <span data-ttu-id="015fe-126">**Роль просматривающего список обозревателя содержимого**. Участие в этой группе ролей позволяет просматривать каждый элемент и его расположение.</span><span class="sxs-lookup"><span data-stu-id="015fe-126">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location.</span></span> <span data-ttu-id="015fe-127">`data classification list viewer` Роль добавлена в эту группу ролей.</span><span class="sxs-lookup"><span data-stu-id="015fe-127">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="015fe-128">**Роль просматривающего контент обозревателя содержимого**. Участие в этой группе ролей позволяет просматривать содержимое каждого элемента в списке.</span><span class="sxs-lookup"><span data-stu-id="015fe-128">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="015fe-129">`data classification content viewer` Роль добавлена в эту группу ролей.</span><span class="sxs-lookup"><span data-stu-id="015fe-129">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="015fe-130">Учетной записи, используемой для доступа к обозревателю содержимого, должна быть присвоена одна или обе этих группы ролей.</span><span class="sxs-lookup"><span data-stu-id="015fe-130">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="015fe-131">Это независимые группы ролей, не включающие в себя друг друга.</span><span class="sxs-lookup"><span data-stu-id="015fe-131">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="015fe-132">Например, если вы хотите предоставить учетной записи возможность просматривать только элементы и их расположения, предоставьте права на просмотр списка обозревателя содержимого.</span><span class="sxs-lookup"><span data-stu-id="015fe-132">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="015fe-133">Если вы хотите, чтобы эта учетная запись также смогла просматривать содержимое элементов списка, дополнительно предоставьте права на просмотр контента обозревателя содержимого.</span><span class="sxs-lookup"><span data-stu-id="015fe-133">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="015fe-134">Вы также можете назначить одну или обе роли пользовательской группе ролей, чтобы настроить доступ к проводнику контента.</span><span class="sxs-lookup"><span data-stu-id="015fe-134">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="015fe-135">Использование обозревателя содержимого</span><span class="sxs-lookup"><span data-stu-id="015fe-135">How to use content explorer</span></span>

1. <span data-ttu-id="015fe-136">Откройте **Центр соответствия требованиям Microsoft 365**  > **Классификация данных** > **Обозреватель содержимого**.</span><span class="sxs-lookup"><span data-stu-id="015fe-136">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="015fe-137">Если вы знаете имя метки или тип конфиденциальной информации, можно ввести их в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="015fe-137">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="015fe-138">Или можно выполнить поиск элемента, развернув тип метки и выбрав метку из списка. Элемент из раздела списка с метками хранения отображается ниже.</span><span class="sxs-lookup"><span data-stu-id="015fe-138">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="015fe-139">Выберите расположение в разделе **Все расположения** и разверните структуру папок до элемента.</span><span class="sxs-lookup"><span data-stu-id="015fe-139">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="015fe-140">Дважды щелкните, чтобы открыть элемент в обозревателе содержимого.</span><span class="sxs-lookup"><span data-stu-id="015fe-140">Double-click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="015fe-141">См. также</span><span class="sxs-lookup"><span data-stu-id="015fe-141">See also</span></span>

- [<span data-ttu-id="015fe-142">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="015fe-142">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="015fe-143">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="015fe-143">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="015fe-144">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="015fe-144">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="015fe-145">Обзор политик хранения</span><span class="sxs-lookup"><span data-stu-id="015fe-145">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="015fe-146">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="015fe-146">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
