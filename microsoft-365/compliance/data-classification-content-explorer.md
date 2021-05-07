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
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Обозреватель содержимого позволяет легко просматривать элементы с присвоенными метками.
ms.openlocfilehash: b39dd09012e7cde6c19ea88a0915154da84c712a
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114219"
---
# <a name="get-started-with-content-explorer"></a><span data-ttu-id="7dd54-103">Начало работы с обозревателем контента</span><span class="sxs-lookup"><span data-stu-id="7dd54-103">Get started with content explorer</span></span>

<span data-ttu-id="7dd54-104">Обозреватель содержимого с классификацией данных позволяет легко просматривать элементы, обобщенные на странице обзора.</span><span class="sxs-lookup"><span data-stu-id="7dd54-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

![снимок экрана: свернутый обозреватель контента](../media/data-classification-content-explorer-1.png)

## <a name="prerequisites"></a><span data-ttu-id="7dd54-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7dd54-106">Prerequisites</span></span>

<span data-ttu-id="7dd54-107">Каждой учетной записи, которая осуществляет доступ и использует классификацию данных, необходимо назначить лицензию из одной из следующих подписок:</span><span class="sxs-lookup"><span data-stu-id="7dd54-107">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="7dd54-108">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="7dd54-108">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="7dd54-109">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="7dd54-109">Office 365 (E5)</span></span>
- <span data-ttu-id="7dd54-110">Дополнение Advanced Compliance (E5)</span><span class="sxs-lookup"><span data-stu-id="7dd54-110">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="7dd54-111">Дополнение Advanced Threat Intelligence (E5)</span><span class="sxs-lookup"><span data-stu-id="7dd54-111">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="7dd54-112">Защита информации и управление данными в Microsoft 365 E5 или A5</span><span class="sxs-lookup"><span data-stu-id="7dd54-112">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="7dd54-113">Соответствие требованиям Microsoft 365 E5 или A5</span><span class="sxs-lookup"><span data-stu-id="7dd54-113">Microsoft 365 E5/A5 Compliance</span></span>


### <a name="permissions"></a><span data-ttu-id="7dd54-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="7dd54-114">Permissions</span></span>

<span data-ttu-id="7dd54-115">Чтобы получить доступ к вкладке обозревателя контента, учетной записи необходимо назначить участие в одной из следующих ролей или групп ролей.</span><span class="sxs-lookup"><span data-stu-id="7dd54-115">In order to get access to the content explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span> 

<span data-ttu-id="7dd54-116">**Группы ролей Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="7dd54-116">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="7dd54-117">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="7dd54-117">Global administrator</span></span>
- <span data-ttu-id="7dd54-118">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="7dd54-118">Compliance administrator</span></span>
- <span data-ttu-id="7dd54-119">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="7dd54-119">Security administrator</span></span>
- <span data-ttu-id="7dd54-120">Администратор данных о соответствии требованиям</span><span class="sxs-lookup"><span data-stu-id="7dd54-120">Compliance data administrator</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7dd54-121">Членство в этих группах ролей не позволяет просматривать список элементов в обозревателе контента и просматривать содержимое элементов в обозревателе контента.</span><span class="sxs-lookup"><span data-stu-id="7dd54-121">Membership in these role groups does not allow you to view the list of items in content explorer or to view the contents of the items in content explorer.</span></span>

### <a name="required-permissions-to-access-items-in-content-explorer"></a><span data-ttu-id="7dd54-122">Разрешения, необходимые для доступа к элементам в обозревателе контента</span><span class="sxs-lookup"><span data-stu-id="7dd54-122">Required permissions to access items in content explorer</span></span>

<span data-ttu-id="7dd54-123">Доступ к обозревателю контента чрезвычайно ограничен, так как он позволяет читать содержимое отсканированных файлов.</span><span class="sxs-lookup"><span data-stu-id="7dd54-123">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7dd54-124">Эти разрешения обладают приоритетом по отношению к разрешениям, заданным локально, что позволяет просматривать контент.</span><span class="sxs-lookup"><span data-stu-id="7dd54-124">These permissions supercede permissions that are locally assigned to the items, which allows viewing of the content.</span></span> 

<span data-ttu-id="7dd54-125">Существуют две роли, разрешающие доступ к обозревателю содержимого. Доступ предоставляется через [Центр безопасности и соответствия требованиям Майкрософт](https://protection.office.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="7dd54-125">There are two roles that grant access to content explorer and it is granted using the [Microsoft Security & Compliance Center](https://protection.office.com/permissions):</span></span>

- <span data-ttu-id="7dd54-126">**Роль просматривающего список обозревателя контента**. Участие в этой группе ролей позволяет просматривать каждый элемент и его расположение.</span><span class="sxs-lookup"><span data-stu-id="7dd54-126">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location in list view.</span></span> <span data-ttu-id="7dd54-127">`data classification list viewer` Роль заранее добавлена в эту группу ролей.</span><span class="sxs-lookup"><span data-stu-id="7dd54-127">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="7dd54-128">**Роль просматривающего контент обозревателя содержимого**. Участие в этой группе ролей позволяет просматривать содержимое каждого элемента в списке.</span><span class="sxs-lookup"><span data-stu-id="7dd54-128">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="7dd54-129">`data classification content viewer` Роль добавлена в эту группу ролей.</span><span class="sxs-lookup"><span data-stu-id="7dd54-129">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="7dd54-130">Учетной записи, используемой для доступа к обозревателю содержимого, должна быть присвоена одна или обе этих группы ролей.</span><span class="sxs-lookup"><span data-stu-id="7dd54-130">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="7dd54-131">Это независимые группы ролей, не включающие в себя друг друга.</span><span class="sxs-lookup"><span data-stu-id="7dd54-131">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="7dd54-132">Например, если вы хотите предоставить учетной записи возможность просматривать только элементы и их расположения, предоставьте права на просмотр списка обозревателя содержимого.</span><span class="sxs-lookup"><span data-stu-id="7dd54-132">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="7dd54-133">Если вы хотите, чтобы эта учетная запись также смогла просматривать содержимое элементов списка, дополнительно предоставьте права на просмотр контента обозревателя содержимого.</span><span class="sxs-lookup"><span data-stu-id="7dd54-133">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="7dd54-134">Вы также можете назначить одну или обе роли пользовательской группе ролей, чтобы настроить доступ к проводнику контента.</span><span class="sxs-lookup"><span data-stu-id="7dd54-134">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="7dd54-135">Глобальный администратор, администратор соответствия или администратор данных может назначить необходимую роль в группе Читатель списка в обозревателе содержимого и Читатель содержимого в обозревателе содержимого.</span><span class="sxs-lookup"><span data-stu-id="7dd54-135">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="7dd54-136">Обозреватель содержимого</span><span class="sxs-lookup"><span data-stu-id="7dd54-136">Content explorer</span></span>

<span data-ttu-id="7dd54-137">Обозреватель содержимого отображает текущий снимок элементов с присвоенными метками конфиденциальности или метками хранения, а также отнесенных к конфиденциальным сведениям в организации.</span><span class="sxs-lookup"><span data-stu-id="7dd54-137">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="7dd54-138">Типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="7dd54-138">Sensitive information types</span></span>

<span data-ttu-id="7dd54-139">[Политика защиты от потери данных](dlp-learn-about-dlp.md) помогает защитить сведения, относящиеся к одному из **типов конфиденциальной информации**.</span><span class="sxs-lookup"><span data-stu-id="7dd54-139">A [DLP policy](dlp-learn-about-dlp.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="7dd54-140">Microsoft 365 содержит готовые к использованию [определения для многих распространенных типов конфиденциальной информации](sensitive-information-type-entity-definitions.md) из различных регионов. </span><span class="sxs-lookup"><span data-stu-id="7dd54-140">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) from across many different regions that are ready for you to use.</span></span> <span data-ttu-id="7dd54-141">Например, номера кредитных карт, номера банковских счетов, национальные идентификационные номера и номера службы Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="7dd54-141">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

> [!NOTE]
> <span data-ttu-id="7dd54-142">В настоящий момент браузер контента не проверяет типы конфиденциальной информации в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7dd54-142">Content explorer doesn't currently scan for sensitive information types in Exchange Online.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="7dd54-143">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="7dd54-143">Sensitivity labels</span></span>

<span data-ttu-id="7dd54-144">[Метка конфиденциальности](sensitivity-labels.md) — это просто тег, обозначающий значение элемента для организации.</span><span class="sxs-lookup"><span data-stu-id="7dd54-144">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="7dd54-145">Ее можно применять вручную или автоматически.</span><span class="sxs-lookup"><span data-stu-id="7dd54-145">It can be applied manually, or automatically.</span></span> <span data-ttu-id="7dd54-146">После применения она внедряется в документ и повсюду следует за ним.</span><span class="sxs-lookup"><span data-stu-id="7dd54-146">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="7dd54-147">Метка конфиденциальности включает различные защитные действия, такие как обязательные водяные знаки или шифрование.</span><span class="sxs-lookup"><span data-stu-id="7dd54-147">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span>

<span data-ttu-id="7dd54-148">Для файлов SharePoint и OneDrive должны быть включены метки конфиденциальности, чтобы соответствующие данные отображались на странице классификации данных.</span><span class="sxs-lookup"><span data-stu-id="7dd54-148">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="7dd54-149">Дополнительные сведения см. в статье [Включение меток конфиденциальности для файлов Office в SharePoint и OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="7dd54-149">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="7dd54-150">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="7dd54-150">Retention labels</span></span>

<span data-ttu-id="7dd54-151">[Метка хранения](retention.md) позволяет определить срок хранения элемента с меткой и действия, которые необходимо выполнить перед его удалением.</span><span class="sxs-lookup"><span data-stu-id="7dd54-151">A [retention label](retention.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="7dd54-152">Они применяются вручную или автоматически с помощью политик.</span><span class="sxs-lookup"><span data-stu-id="7dd54-152">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="7dd54-153">С их помощью можно обеспечивать соблюдение организацией юридических и нормативных требований.</span><span class="sxs-lookup"><span data-stu-id="7dd54-153">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="7dd54-154">Использование обозревателя содержимого</span><span class="sxs-lookup"><span data-stu-id="7dd54-154">How to use content explorer</span></span>

1. <span data-ttu-id="7dd54-155">Откройте **Центр соответствия требованиям Microsoft 365**  > **Классификация данных** > **Обозреватель содержимого**.</span><span class="sxs-lookup"><span data-stu-id="7dd54-155">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="7dd54-156">Если вы знаете название метки или тип конфиденциальной информации, можно ввести их в поле фильтра.</span><span class="sxs-lookup"><span data-stu-id="7dd54-156">If you know the name of the label, or the sensitive information type, you can type that into the filter box.</span></span>
3. <span data-ttu-id="7dd54-157">Или можно выполнить поиск элемента, развернув список типов метки и выбрав метку из этого списка.</span><span class="sxs-lookup"><span data-stu-id="7dd54-157">Alternately, you can browse for the item by expanding the label type and selecting the label from the list.</span></span>
4. <span data-ttu-id="7dd54-158">Выберите расположение в разделе **Все расположения** и разверните структуру папок до элемента.</span><span class="sxs-lookup"><span data-stu-id="7dd54-158">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="7dd54-159">Дважды щелкните, чтобы открыть элемент в обозревателе содержимого.</span><span class="sxs-lookup"><span data-stu-id="7dd54-159">Double-click to open the item natively in content explorer.</span></span>

### <a name="export"></a><span data-ttu-id="7dd54-160">Экспорт</span><span class="sxs-lookup"><span data-stu-id="7dd54-160">Export</span></span>
<span data-ttu-id="7dd54-161">Элемент управления **Экспорт** создаст CSV-файл, содержащий список всех элементов, которые отображаются в области **Все расположения**.</span><span class="sxs-lookup"><span data-stu-id="7dd54-161">The **export** control will create a .csv file that contains a listing of whatever is showing in the **All locations** pane.</span></span>

![Элемент управления "Экспорт классификации данных"](../media/data_classification_export_control.png)


### <a name="search"></a><span data-ttu-id="7dd54-163">Поиск</span><span class="sxs-lookup"><span data-stu-id="7dd54-163">Search</span></span>

<span data-ttu-id="7dd54-164">При детализации расположения, например папки Exchange или сайта SharePoint или OneDrive, появляется средство **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="7dd54-164">When you drill down into a location, such as an Exchange folder, or a SharePoint or OneDrive site, the **search** tool appears.</span></span>

![средство поиска в проводнике контента](../media/data_classification_search_tool.png)


<span data-ttu-id="7dd54-166">Областью действия средства поиска является то, что отображается в панели **Все расположения**, а возможное место поиска зависит от выбранного расположения.</span><span class="sxs-lookup"><span data-stu-id="7dd54-166">The scope of the search tool is what is displaying in the **All locations** pane and what you can search on varies depending on the selected location.</span></span> 

<span data-ttu-id="7dd54-167">Если выбрано расположение **Exchange**, то поиск можно выполнить по полному адресу электронной почты в почтовом ящике, например `user@domainname.com`.</span><span class="sxs-lookup"><span data-stu-id="7dd54-167">When **Exchange** is the selected location, you can search on the full email address of the mailbox, for example `user@domainname.com`.</span></span>

<span data-ttu-id="7dd54-168">Если выбрано расположение **SharePoint** или **OneDrive**, то при детализации имен сайтов, папок и файлов будет выводиться средство "Поиск".</span><span class="sxs-lookup"><span data-stu-id="7dd54-168">When either **SharePoint** or **OneDrive** are selected location, the search tool will appear when you drill down to site names, folders and files.</span></span> 

> [!NOTE]
> <span data-ttu-id="7dd54-169">**OneDrive** В рамках программы предварительного просмотра мы получили от вас ценные отзывы относительно интеграции OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7dd54-169">**OneDrive** We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="7dd54-170">С учетом этого отзыва функции OneDrive останутся в предварительной версии до тех пор, пока не будут сделаны все исправления.</span><span class="sxs-lookup"><span data-stu-id="7dd54-170">Based on that feedback, the OneDrive functionality will remain in preview till all fixes are in place.</span></span> <span data-ttu-id="7dd54-171">В зависимости от клиента, некоторые пользователи могут не видеть OneDrive в качестве расположения.</span><span class="sxs-lookup"><span data-stu-id="7dd54-171">Depending on your tenant, some customers may not see OneDrive as a location.</span></span> <span data-ttu-id="7dd54-172">Благодарим вас за поддержку.</span><span class="sxs-lookup"><span data-stu-id="7dd54-172">We appreciate your continued support on this.</span></span>

<span data-ttu-id="7dd54-173">Вы можете выполнять поиск по следующим критериям:</span><span class="sxs-lookup"><span data-stu-id="7dd54-173">You can search on:</span></span>


|<span data-ttu-id="7dd54-174">значение</span><span class="sxs-lookup"><span data-stu-id="7dd54-174">value</span></span>|<span data-ttu-id="7dd54-175">пример</span><span class="sxs-lookup"><span data-stu-id="7dd54-175">example</span></span>  |
|---------|---------|
|<span data-ttu-id="7dd54-176">полное имя сайта</span><span class="sxs-lookup"><span data-stu-id="7dd54-176">full site name</span></span>    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|<span data-ttu-id="7dd54-177">имя корневой папки — получает все вложенные папки.</span><span class="sxs-lookup"><span data-stu-id="7dd54-177">root folder name - gets all subfolders</span></span>    | `/sites`        |
|<span data-ttu-id="7dd54-178">имя файла</span><span class="sxs-lookup"><span data-stu-id="7dd54-178">file name</span></span>    |    `RES_Resume_1234.txt`     |
|<span data-ttu-id="7dd54-179">текст в начале имени файла</span><span class="sxs-lookup"><span data-stu-id="7dd54-179">text at the beginning of file name</span></span>| `RES`|
|<span data-ttu-id="7dd54-180">текст после символа подчеркивания (_) в имени файла</span><span class="sxs-lookup"><span data-stu-id="7dd54-180">text after an underscore character ( _ ) in file name</span></span>|<span data-ttu-id="7dd54-181">`Resume` или `1234`</span><span class="sxs-lookup"><span data-stu-id="7dd54-181">`Resume` or `1234`</span></span>| 
|<span data-ttu-id="7dd54-182">расширение файла</span><span class="sxs-lookup"><span data-stu-id="7dd54-182">file extension</span></span>|`txt`|


## <a name="see-also"></a><span data-ttu-id="7dd54-183">См. также</span><span class="sxs-lookup"><span data-stu-id="7dd54-183">See also</span></span>

- [<span data-ttu-id="7dd54-184">Сведения о метках конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="7dd54-184">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="7dd54-185">Сведения о политиках и метках хранения</span><span class="sxs-lookup"><span data-stu-id="7dd54-185">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="7dd54-186">Sensitive information type entity definitions.md</span><span class="sxs-lookup"><span data-stu-id="7dd54-186">Sensitive information type entity definitions.md</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="7dd54-187">Сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="7dd54-187">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)