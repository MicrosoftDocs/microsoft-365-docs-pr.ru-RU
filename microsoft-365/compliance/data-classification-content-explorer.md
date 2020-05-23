---
title: Начало работы с обозревателем контента
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
ms.openlocfilehash: 731ae51a02e4a6fbd35b5be7c0bf083c814ddfd3
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327855"
---
# <a name="get-started-with-content-explorer"></a><span data-ttu-id="a8b99-103">Начало работы с обозревателем контента</span><span class="sxs-lookup"><span data-stu-id="a8b99-103">Get started with content explorer</span></span>

<span data-ttu-id="a8b99-104">Обозреватель содержимого с классификацией данных позволяет легко просматривать элементы, обобщенные на странице обзора.</span><span class="sxs-lookup"><span data-stu-id="a8b99-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

![снимок экрана: свернутый обозреватель контента](../media/data-classification-content-explorer-1.png)

## <a name="prerequisites"></a><span data-ttu-id="a8b99-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="a8b99-106">Prerequisites</span></span>

<span data-ttu-id="a8b99-107">Каждой учетной записи, которая осуществляет доступ и использует классификацию данных, необходимо назначить лицензию из одной из следующих подписок:</span><span class="sxs-lookup"><span data-stu-id="a8b99-107">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="a8b99-108">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="a8b99-108">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="a8b99-109">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="a8b99-109">Office 365 (E5)</span></span>
- <span data-ttu-id="a8b99-110">Дополнение Advanced Compliance (E5)</span><span class="sxs-lookup"><span data-stu-id="a8b99-110">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="a8b99-111">Дополнение Advanced Threat Intelligence (E5)</span><span class="sxs-lookup"><span data-stu-id="a8b99-111">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="a8b99-112">Разрешения</span><span class="sxs-lookup"><span data-stu-id="a8b99-112">Permissions</span></span>

<span data-ttu-id="a8b99-113">Чтобы получить доступ к вкладке обозревателя контента, учетной записи необходимо назначить участие в одной из следующих ролей или групп ролей.</span><span class="sxs-lookup"><span data-stu-id="a8b99-113">In order to get access to the content explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span> 

<span data-ttu-id="a8b99-114">[Политика защиты от потери данных](data-loss-prevention-policies.md) помогает защитить сведения, относящиеся к одному из **типов конфиденциальной информации**.</span><span class="sxs-lookup"><span data-stu-id="a8b99-114">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="a8b99-115">Microsoft 365 содержит готовые к использованию [определения для многих распространенных типов конфиденциальной информации](sensitive-information-type-entity-definitions.md) из различных регионов. </span><span class="sxs-lookup"><span data-stu-id="a8b99-115">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="a8b99-116">Например, номера кредитных карт, номера банковских счетов, национальные идентификационные номера и номера службы Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="a8b99-116">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

<span data-ttu-id="a8b99-117">**Группы ролей Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="a8b99-117">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="a8b99-118">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="a8b99-118">Global administrator</span></span>
- <span data-ttu-id="a8b99-119">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a8b99-119">Compliance administrator</span></span>
- <span data-ttu-id="a8b99-120">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="a8b99-120">Security administrator</span></span>
- <span data-ttu-id="a8b99-121">Администратор данных о соответствии требованиям</span><span class="sxs-lookup"><span data-stu-id="a8b99-121">Compliance data administrator</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8b99-122">Членство в этих группах ролей не позволяет просматривать список элементов в обозревателе контента и просматривать содержимое элементов в обозревателе контента.</span><span class="sxs-lookup"><span data-stu-id="a8b99-122">Membership in these role groups does not allow you to view the list of items in content explorer or to view the contents of the items in content explorer.</span></span>

### <a name="required-permissions-to-access-items-in-content-explorer"></a><span data-ttu-id="a8b99-123">Разрешения, необходимые для доступа к элементам в обозревателе контента</span><span class="sxs-lookup"><span data-stu-id="a8b99-123">Required permissions to access items in content explorer</span></span>

<span data-ttu-id="a8b99-124">Доступ к обозревателю контента чрезвычайно ограничен, так как он позволяет читать содержимое отсканированных файлов.</span><span class="sxs-lookup"><span data-stu-id="a8b99-124">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8b99-125">Эти разрешения обладают приоритетом по отношению к разрешениям, заданным локально, что позволяет просматривать контент.</span><span class="sxs-lookup"><span data-stu-id="a8b99-125">These permissions supercede permissions that are locally assigned to the items, which allows viewing of the content.</span></span> 

<span data-ttu-id="a8b99-126">Доступ к обозревателю контента предоставляется двумя ролями:</span><span class="sxs-lookup"><span data-stu-id="a8b99-126">There are two roles that grant access to content explorer:</span></span>

- <span data-ttu-id="a8b99-127">**Роль просматривающего список обозревателя контента**. Участие в этой группе ролей позволяет просматривать каждый элемент и его расположение.</span><span class="sxs-lookup"><span data-stu-id="a8b99-127">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location in list view.</span></span> <span data-ttu-id="a8b99-128">`data classification list viewer` Роль заранее добавлена в эту группу ролей.</span><span class="sxs-lookup"><span data-stu-id="a8b99-128">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="a8b99-129">**Роль просматривающего контент обозревателя содержимого**. Участие в этой группе ролей позволяет просматривать содержимое каждого элемента в списке.</span><span class="sxs-lookup"><span data-stu-id="a8b99-129">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="a8b99-130">`data classification content viewer` Роль добавлена в эту группу ролей.</span><span class="sxs-lookup"><span data-stu-id="a8b99-130">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="a8b99-131">Учетной записи, используемой для доступа к обозревателю содержимого, должна быть присвоена одна или обе этих группы ролей.</span><span class="sxs-lookup"><span data-stu-id="a8b99-131">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="a8b99-132">Это независимые группы ролей, не включающие в себя друг друга.</span><span class="sxs-lookup"><span data-stu-id="a8b99-132">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="a8b99-133">Например, если вы хотите предоставить учетной записи возможность просматривать только элементы и их расположения, предоставьте права на просмотр списка обозревателя содержимого.</span><span class="sxs-lookup"><span data-stu-id="a8b99-133">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="a8b99-134">Если вы хотите, чтобы эта учетная запись также смогла просматривать содержимое элементов списка, дополнительно предоставьте права на просмотр контента обозревателя содержимого.</span><span class="sxs-lookup"><span data-stu-id="a8b99-134">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="a8b99-135">Вы также можете назначить одну или обе роли пользовательской группе ролей, чтобы настроить доступ к проводнику контента.</span><span class="sxs-lookup"><span data-stu-id="a8b99-135">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="a8b99-136">Глобальный администратор, администратор соответствия или администратор данных может назначить необходимую роль в группе Читатель списка в обозревателе содержимого и Читатель содержимого в обозревателе содержимого.</span><span class="sxs-lookup"><span data-stu-id="a8b99-136">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="a8b99-137">Обозреватель содержимого</span><span class="sxs-lookup"><span data-stu-id="a8b99-137">Content explorer</span></span>

<span data-ttu-id="a8b99-138">Обозреватель содержимого отображает текущий снимок элементов с присвоенными метками конфиденциальности или метками хранения, а также отнесенных к конфиденциальным сведениям в организации.</span><span class="sxs-lookup"><span data-stu-id="a8b99-138">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="a8b99-139">Типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="a8b99-139">Sensitive information types</span></span>

<span data-ttu-id="a8b99-140">[Политика защиты от потери данных](data-loss-prevention-policies.md) помогает защитить сведения, относящиеся к одному из **типов конфиденциальной информации**.</span><span class="sxs-lookup"><span data-stu-id="a8b99-140">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="a8b99-141">Microsoft 365 содержит готовые к использованию [определения для многих распространенных типов конфиденциальной информации](sensitive-information-type-entity-definitions.md) из различных регионов. </span><span class="sxs-lookup"><span data-stu-id="a8b99-141">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) from across many different regions that are ready for you to use.</span></span> <span data-ttu-id="a8b99-142">Например, номера кредитных карт, номера банковских счетов, национальные идентификационные номера и номера службы Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="a8b99-142">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

> [!NOTE]
> <span data-ttu-id="a8b99-143">В настоящий момент браузер контента не проверяет типы конфиденциальной информации в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a8b99-143">Content explorer doesn't currently scan for sensitive information types in Exchange Online.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="a8b99-144">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="a8b99-144">Sensitivity labels</span></span>

<span data-ttu-id="a8b99-145">[Метка конфиденциальности](sensitivity-labels.md) — это просто тег, обозначающий значение элемента для организации.</span><span class="sxs-lookup"><span data-stu-id="a8b99-145">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="a8b99-146">Ее можно применять вручную или автоматически.</span><span class="sxs-lookup"><span data-stu-id="a8b99-146">It can be applied manually, or automatically.</span></span> <span data-ttu-id="a8b99-147">После применения она внедряется в документ и повсюду следует за ним.</span><span class="sxs-lookup"><span data-stu-id="a8b99-147">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="a8b99-148">Метка конфиденциальности включает различные защитные действия, такие как обязательные водяные знаки или шифрование.</span><span class="sxs-lookup"><span data-stu-id="a8b99-148">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span>

<span data-ttu-id="a8b99-149">Для файлов SharePoint и OneDrive должны быть включены метки конфиденциальности, чтобы соответствующие данные отображались на странице классификации данных.</span><span class="sxs-lookup"><span data-stu-id="a8b99-149">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="a8b99-150">Дополнительные сведения см. в статье [Включение меток конфиденциальности для файлов Office в SharePoint и OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="a8b99-150">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="a8b99-151">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="a8b99-151">Retention labels</span></span>

<span data-ttu-id="a8b99-152">[Метка хранения](labels.md) позволяет определить срок хранения элемента с меткой и действия, которые необходимо выполнить перед его удалением.</span><span class="sxs-lookup"><span data-stu-id="a8b99-152">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="a8b99-153">Они применяются вручную или автоматически с помощью политик.</span><span class="sxs-lookup"><span data-stu-id="a8b99-153">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="a8b99-154">С их помощью можно обеспечивать соблюдение организацией юридических и нормативных требований.</span><span class="sxs-lookup"><span data-stu-id="a8b99-154">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="a8b99-155">Использование обозревателя содержимого</span><span class="sxs-lookup"><span data-stu-id="a8b99-155">How to use content explorer</span></span>

1. <span data-ttu-id="a8b99-156">Откройте **Центр соответствия требованиям Microsoft 365**  > **Классификация данных** > **Обозреватель содержимого**.</span><span class="sxs-lookup"><span data-stu-id="a8b99-156">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="a8b99-157">Если вы знаете название метки или тип конфиденциальной информации, можно ввести их в поле фильтра.</span><span class="sxs-lookup"><span data-stu-id="a8b99-157">If you know the name of the label, or the sensitive information type, you can type that into the filter box.</span></span>
3. <span data-ttu-id="a8b99-158">Или можно выполнить поиск элемента, развернув список типов метки и выбрав метку из этого списка.</span><span class="sxs-lookup"><span data-stu-id="a8b99-158">Alternately, you can browse for the item by expanding the label type and selecting the label from the list.</span></span>
4. <span data-ttu-id="a8b99-159">Выберите расположение в разделе **Все расположения** и разверните структуру папок до элемента.</span><span class="sxs-lookup"><span data-stu-id="a8b99-159">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="a8b99-160">Дважды щелкните, чтобы открыть элемент в обозревателе содержимого.</span><span class="sxs-lookup"><span data-stu-id="a8b99-160">Double-click to open the item natively in content explorer.</span></span>

### <a name="export"></a><span data-ttu-id="a8b99-161">Экспорт</span><span class="sxs-lookup"><span data-stu-id="a8b99-161">Export</span></span>
<span data-ttu-id="a8b99-162">Элемент управления **Экспорт** создаст CSV-файл, содержащий список всех элементов, которые отображаются в области **Все расположения**.</span><span class="sxs-lookup"><span data-stu-id="a8b99-162">The **export** control will create a .csv file that contains a listing of whatever is showing in the **All locations** pane.</span></span>

![Элемент управления "Экспорт классификации данных"](../media/data_classification_export_control.png)


### <a name="search"></a><span data-ttu-id="a8b99-164">Поиск</span><span class="sxs-lookup"><span data-stu-id="a8b99-164">Search</span></span>

<span data-ttu-id="a8b99-165">При детализации расположения, например папки Exchange или сайта SharePoint или OneDrive, появляется средство **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="a8b99-165">When you drill down into a location, such as an Exchange folder, or a SharePoint or OneDrive site, the **search** tool appears.</span></span>

![средство поиска в проводнике контента](../media/data_classification_search_tool.png)


<span data-ttu-id="a8b99-167">Областью действия средства поиска является то, что отображается в панели **Все расположения**, а возможное место поиска зависит от выбранного расположения.</span><span class="sxs-lookup"><span data-stu-id="a8b99-167">The scope of the search tool is what is displaying in the **All locations** pane and what you can search on varies depending on the selected location.</span></span> 

<span data-ttu-id="a8b99-168">Если выбрано расположение \*\* Exchange\*\*, то поиск можно выполнить по полному адресу электронной почты в почтовом ящике, например `user@domainname.com`.</span><span class="sxs-lookup"><span data-stu-id="a8b99-168">When **Exchange** is the selected location, you can search on the full email address of the mailbox, for example `user@domainname.com`.</span></span>

<span data-ttu-id="a8b99-169">Если выбрано расположение **SharePoint** или **OneDrive**, то при детализации имен сайтов, папок и файлов будет выводиться средство "Поиск".</span><span class="sxs-lookup"><span data-stu-id="a8b99-169">When either **SharePoint** or **OneDrive** are selected location, the search tool will appear when you drill down to site names, folders and files.</span></span> 

> [!NOTE]
> <span data-ttu-id="a8b99-170">**OneDrive** В рамках программы предварительного просмотра мы получили от вас ценные отзывы относительно интеграции OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a8b99-170">**OneDrive** We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="a8b99-171">С учетом этого отзыва функции OneDrive останутся в предварительной версии до тех пор, пока не будут сделаны все исправления.</span><span class="sxs-lookup"><span data-stu-id="a8b99-171">Based on that feedback, the OneDrive functionality will remain in preview till all fixes are in place.</span></span> <span data-ttu-id="a8b99-172">В зависимости от клиента, некоторые пользователи могут не видеть OneDrive в качестве расположения.</span><span class="sxs-lookup"><span data-stu-id="a8b99-172">Depending on your tenant, some customers may not see OneDrive as a location.</span></span> <span data-ttu-id="a8b99-173">Благодарим вас за поддержку.</span><span class="sxs-lookup"><span data-stu-id="a8b99-173">We appreciate your continued support on this.</span></span>

<span data-ttu-id="a8b99-174">Вы можете выполнять поиск по следующим критериям:</span><span class="sxs-lookup"><span data-stu-id="a8b99-174">You can search on:</span></span>


|<span data-ttu-id="a8b99-175">значение</span><span class="sxs-lookup"><span data-stu-id="a8b99-175">value</span></span>|<span data-ttu-id="a8b99-176">пример</span><span class="sxs-lookup"><span data-stu-id="a8b99-176">example</span></span>  |
|---------|---------|
|<span data-ttu-id="a8b99-177">полное имя сайта</span><span class="sxs-lookup"><span data-stu-id="a8b99-177">full site name</span></span>    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|<span data-ttu-id="a8b99-178">имя корневой папки — получает все вложенные папки.</span><span class="sxs-lookup"><span data-stu-id="a8b99-178">root folder name - gets all subfolders</span></span>    | `/sites`        |
|<span data-ttu-id="a8b99-179">имя файла</span><span class="sxs-lookup"><span data-stu-id="a8b99-179">file name</span></span>    |    `RES_Resume_1234.txt`     |
|<span data-ttu-id="a8b99-180">текст в начале имени файла</span><span class="sxs-lookup"><span data-stu-id="a8b99-180">text at the beginning of file name</span></span>| `RES`|
|<span data-ttu-id="a8b99-181">текст после символа подчеркивания (_) в имени файла</span><span class="sxs-lookup"><span data-stu-id="a8b99-181">text after an underscore character ( _ ) in file name</span></span>|<span data-ttu-id="a8b99-182">`Resume` или `1234`</span><span class="sxs-lookup"><span data-stu-id="a8b99-182">`Resume` or `1234`</span></span>| 
|<span data-ttu-id="a8b99-183">расширение файла</span><span class="sxs-lookup"><span data-stu-id="a8b99-183">file extension</span></span>|`txt`|


## <a name="see-also"></a><span data-ttu-id="a8b99-184">См. также</span><span class="sxs-lookup"><span data-stu-id="a8b99-184">See also</span></span>

- [<span data-ttu-id="a8b99-185">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="a8b99-185">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="a8b99-186">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="a8b99-186">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="a8b99-187">Sensitive information type entity definitions.md</span><span class="sxs-lookup"><span data-stu-id="a8b99-187">Sensitive information type entity definitions.md</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="a8b99-188">Обзор политик хранения</span><span class="sxs-lookup"><span data-stu-id="a8b99-188">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="a8b99-189">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="a8b99-189">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
