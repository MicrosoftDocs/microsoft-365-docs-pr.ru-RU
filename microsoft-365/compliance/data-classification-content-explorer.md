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
ms.openlocfilehash: 205ec6b4f2049e18ee95f25505d8a58d7eb7ac77
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "42409694"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="2f1b7-103">Использование обозревателя содержимого с классификацией данных (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="2f1b7-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="2f1b7-104">Обозреватель содержимого с классификацией данных позволяет легко просматривать элементы, обобщенные на странице обзора.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2f1b7-105">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="2f1b7-105">Prerequisites</span></span>

<span data-ttu-id="2f1b7-106">Каждой учетной записи, которая обращается к обозревателю действий и использует его, должна быть назначена лицензия одной из следующих подписок:</span><span class="sxs-lookup"><span data-stu-id="2f1b7-106">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="2f1b7-107">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="2f1b7-107">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="2f1b7-108">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="2f1b7-108">Office 365 (E5)</span></span>
- <span data-ttu-id="2f1b7-109">Дополнение Advanced Compliance (E5)</span><span class="sxs-lookup"><span data-stu-id="2f1b7-109">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="2f1b7-110">Дополнение Advanced Threat Intelligence (E5)</span><span class="sxs-lookup"><span data-stu-id="2f1b7-110">Advanced Threat Intelligence (E5) add-on</span></span>

## <a name="content-explorer"></a><span data-ttu-id="2f1b7-111">Обозреватель содержимого</span><span class="sxs-lookup"><span data-stu-id="2f1b7-111">Content explorer</span></span>

<span data-ttu-id="2f1b7-112">Обозреватель содержимого отображает текущий снимок элементов с присвоенными метками конфиденциальности или метками хранения, а также отнесенных к конфиденциальным сведениям в организации.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-112">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="2f1b7-113">Типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="2f1b7-113">Sensitive information types</span></span>

<span data-ttu-id="2f1b7-114">[Политика защиты от потери данных](data-loss-prevention-policies.md) помогает защитить сведения, относящиеся к одному из **типов конфиденциальной информации**.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-114">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="2f1b7-115">Microsoft 365 содержит готовые к использованию [определения для многих распространенных типов конфиденциальной информации](what-the-sensitive-information-types-look-for.md) из различных регионов. </span><span class="sxs-lookup"><span data-stu-id="2f1b7-115">Microsoft 365 includes [definitions for many common sensitive information types](what-the-sensitive-information-types-look-for.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="2f1b7-116">Например, номера кредитных карт, номера банковских счетов, национальные идентификационные номера и номера службы Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-116">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="2f1b7-117">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="2f1b7-117">Sensitivity labels</span></span>

<span data-ttu-id="2f1b7-118">[Метка конфиденциальности](sensitivity-labels.md) — это просто тег, обозначающий значение элемента для организации.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-118">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="2f1b7-119">Ее можно применять вручную или автоматически.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-119">It can be applied manually, or automatically.</span></span> <span data-ttu-id="2f1b7-120">После применения она внедряется в документ и повсюду следует за ним.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-120">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="2f1b7-121">Метка конфиденциальности включает различные защитные действия, такие как обязательные водяные знаки или шифрование.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-121">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="2f1b7-122">С включенной защитой конечной точки можно даже запретить элементу покидать организацию.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-122">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="2f1b7-123">Для файлов SharePoint и OneDrive должны быть включены метки конфиденциальности, чтобы соответствующие данные отображались на странице классификации данных.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-123">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="2f1b7-124">Дополнительные сведения см. в статье [Включение меток конфиденциальности для файлов Office в SharePoint и OneDrive (общедоступная предварительная версия)](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="2f1b7-124">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="2f1b7-125">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="2f1b7-125">Retention labels</span></span>

<span data-ttu-id="2f1b7-126">[Метка хранения](labels.md) позволяет определить срок хранения элемента с меткой и действия, которые необходимо выполнить перед его удалением.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-126">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="2f1b7-127">Они применяются вручную или автоматически с помощью политик.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-127">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="2f1b7-128">С их помощью можно обеспечивать соблюдение организацией юридических и нормативных требований.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-128">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![снимок экрана: свернутый обозреватель содержимого](../media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="2f1b7-130">Разрешения</span><span class="sxs-lookup"><span data-stu-id="2f1b7-130">Permissions</span></span>

<span data-ttu-id="2f1b7-131">Доступ к обозревателю содержимого предоставляется двумя ролями:</span><span class="sxs-lookup"><span data-stu-id="2f1b7-131">There are two roles that grant access to content explorer:</span></span>

- <span data-ttu-id="2f1b7-132">**Роль просматривающего список обозревателя содержимого**. Участие в этой группе ролей позволяет просматривать каждый элемент и его расположение.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-132">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location.</span></span> <span data-ttu-id="2f1b7-133">`data classification list viewer` Роль добавлена в эту группу ролей.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-133">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="2f1b7-134">**Роль просматривающего контент обозревателя содержимого**. Участие в этой группе ролей позволяет просматривать содержимое каждого элемента в списке.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-134">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="2f1b7-135">`data classification content viewer` Роль добавлена в эту группу ролей.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-135">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="2f1b7-136">Учетной записи, используемой для доступа к обозревателю содержимого, должна быть присвоена одна или обе этих группы ролей.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-136">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="2f1b7-137">Это независимые группы ролей, не включающие в себя друг друга.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-137">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="2f1b7-138">Например, если вы хотите предоставить учетной записи возможность просматривать только элементы и их расположения, предоставьте права на просмотр списка обозревателя содержимого.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-138">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="2f1b7-139">Если вы хотите, чтобы эта учетная запись также смогла просматривать содержимое элементов списка, дополнительно предоставьте права на просмотр контента обозревателя содержимого.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-139">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="2f1b7-140">Вы также можете назначить одну или обе роли пользовательской группе ролей, чтобы настроить доступ к проводнику контента.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-140">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="2f1b7-141">Глобальный администратор, администратор соответствия или администратор данных может назначить необходимую роль в группе Читатель списка в обозревателе содержимого и Читатель содержимого в обозревателе содержимого.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-141">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="2f1b7-142">Использование обозревателя содержимого</span><span class="sxs-lookup"><span data-stu-id="2f1b7-142">How to use content explorer</span></span>

1. <span data-ttu-id="2f1b7-143">Откройте **Центр соответствия требованиям Microsoft 365**  > **Классификация данных** > **Обозреватель содержимого**.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-143">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="2f1b7-144">Если вы знаете имя метки или тип конфиденциальной информации, можно ввести их в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-144">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="2f1b7-145">Или можно выполнить поиск элемента, развернув тип метки и выбрав метку из списка. Элемент из раздела списка с метками хранения отображается ниже.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-145">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="2f1b7-146">Выберите расположение в разделе **Все расположения** и разверните структуру папок до элемента.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-146">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="2f1b7-147">Дважды щелкните, чтобы открыть элемент в обозревателе содержимого.</span><span class="sxs-lookup"><span data-stu-id="2f1b7-147">Double-click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f1b7-148">См. также</span><span class="sxs-lookup"><span data-stu-id="2f1b7-148">See also</span></span>

- [<span data-ttu-id="2f1b7-149">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="2f1b7-149">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="2f1b7-150">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="2f1b7-150">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="2f1b7-151">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="2f1b7-151">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="2f1b7-152">Обзор политик хранения</span><span class="sxs-lookup"><span data-stu-id="2f1b7-152">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="2f1b7-153">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="2f1b7-153">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
