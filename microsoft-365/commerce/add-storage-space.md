---
title: Добавление пространства для хранения для подписки
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: drjones, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
- commerce_purchase
search.appverid: MET150
description: Добавьте хранилище файлов в Microsoft 365 подписку. С помощью дополнительного хранилища файлов можно хранить больше контента в SharePoint и OneDrive.
ms.date: 04/02/2021
ms.openlocfilehash: 14b688e850f62a06c39e4a315d871202e57d70d6
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635862"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="a2d01-104">Добавление пространства для хранения для подписки</span><span class="sxs-lookup"><span data-stu-id="a2d01-104">Add storage space for your subscription</span></span>

<span data-ttu-id="a2d01-105">Если у вас заканчивается нехватка хранилища для ваших семейств сайтов SharePoint Online, вы можете добавить хранилище к своей подписке, если ваш план соответствует критериям.</span><span class="sxs-lookup"><span data-stu-id="a2d01-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="a2d01-106">Если вы не видите  Office 365 с дополнительным хранилищем в списке доступных надстройок, это означает, что ваш план не имеет права.</span><span class="sxs-lookup"><span data-stu-id="a2d01-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="a2d01-107">Дополнительные сведения см. в [статью Имеет ли право мой план?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="a2d01-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="a2d01-108">Если вы приобрели подписку через корпоративное лицензирование или  CSP, вы не можете купить Office 365 с дополнительным хранилищем вашей организации непосредственно у Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a2d01-108">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="a2d01-109">Обратитесь за помощью к представителю или партнеру.</span><span class="sxs-lookup"><span data-stu-id="a2d01-109">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a2d01-110">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="a2d01-110">Before you begin</span></span>

<span data-ttu-id="a2d01-111">Вы должны быть глобальным или администратором SharePoint для выполнения задач в этой статье.</span><span class="sxs-lookup"><span data-stu-id="a2d01-111">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="a2d01-112">Дополнительные сведения см. в статье [О ролях администраторов](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a2d01-112">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="a2d01-113">Просмотр доступного хранилища</span><span class="sxs-lookup"><span data-stu-id="a2d01-113">View available storage</span></span>

1. <span data-ttu-id="a2d01-114">В центре SharePoint перейдите на страницу <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Активные</a> сайты и войдите в учетную запись с разрешениями администратора [для](/sharepoint/sharepoint-admin-role) вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a2d01-114">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="a2d01-115">В правом верхнем углу страницы отображается объем места в хранилище, используемый всеми сайтами, и общий объем хранилища, доступный для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="a2d01-115">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="a2d01-116">Если ваша организация настроил multi-Geo в Office 365, в панели также указывается объем хранилища, используемого во всех географических расположениях.</span><span class="sxs-lookup"><span data-stu-id="a2d01-116">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Панель "Хранилище" на странице "Активные сайты"](/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="a2d01-118">Значение используемого объема хранилища не учитывает изменения, сделанные за последние 24–48 часов.</span><span class="sxs-lookup"><span data-stu-id="a2d01-118">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="a2d01-119">После определения объемов используемого хранилища можно добавить или удалить место для хранения для подписки.</span><span class="sxs-lookup"><span data-stu-id="a2d01-119">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="a2d01-120">Чтобы узнать, сколько будет стоить добавление пространства для хранения, выполните действия в этой статье и просмотрите сведения о ценах, прежде чем покупать больше.</span><span class="sxs-lookup"><span data-stu-id="a2d01-120">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="a2d01-121">Сведения об установлении ограничений для хранения коллекций сайтов см. в руб. Управление ограничениями для хранения [коллекций сайтов.](/sharepoint/manage-site-collection-storage-limits)</span><span class="sxs-lookup"><span data-stu-id="a2d01-121">For information about setting site collection storage limits, see [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="a2d01-122">Добавление хранилища в подписку</span><span class="sxs-lookup"><span data-stu-id="a2d01-122">Add storage to your subscription</span></span>

<span data-ttu-id="a2d01-123">Если вы еще не приобрели дополнительное хранилище для подписки, вы можете это сделать.</span><span class="sxs-lookup"><span data-stu-id="a2d01-123">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="a2d01-124">В центре администрирования перейдите на страницу **Службы** покупки \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">биллинга.</a></span><span class="sxs-lookup"><span data-stu-id="a2d01-124">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="a2d01-125">В нижней части страницы **Службы**  покупки в разделе Надстройки **найдите** Office 365 с дополнительным хранилищем и выберите **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="a2d01-125">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="a2d01-126">На странице сведения о продукте выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a2d01-126">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="a2d01-127">При необходимости выберите базовую подписку, а затем введите необходимое количество гигабайт хранилища.</span><span class="sxs-lookup"><span data-stu-id="a2d01-127">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="a2d01-128">Выберите **Проверьте сейчас**.</span><span class="sxs-lookup"><span data-stu-id="a2d01-128">Select **Check out now**.</span></span>
6. <span data-ttu-id="a2d01-129">На странице **Как это выглядит?** проверьте количество выбранных гигабайт хранилища, просмотрите сведения о ценах и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a2d01-129">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="a2d01-130">На странице **Полный порядок** убедитесь в общем.</span><span class="sxs-lookup"><span data-stu-id="a2d01-130">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="a2d01-131">Если необходимо внести какие-либо изменения, выберите **порядок редактирования**.</span><span class="sxs-lookup"><span data-stu-id="a2d01-131">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="a2d01-132">Если заказ требует проверки, выберите чек.</span><span class="sxs-lookup"><span data-stu-id="a2d01-132">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="a2d01-133">По завершению выберите **порядок "Место"** \> **Перейти к домашнему администратору.**</span><span class="sxs-lookup"><span data-stu-id="a2d01-133">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="a2d01-134">Увеличение или уменьшение хранилища</span><span class="sxs-lookup"><span data-stu-id="a2d01-134">Increase or decrease storage</span></span>

<span data-ttu-id="a2d01-135">Если вы уже приобрели дополнительное  хранилище файлов через надстройку Office 365 с дополнительным хранилищем, вы можете использовать эти действия для увеличения или уменьшения дополнительного пространства для хранения для подписки.</span><span class="sxs-lookup"><span data-stu-id="a2d01-135">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="a2d01-136">Вы можете уменьшить объем хранилища до 1 гигабайта.</span><span class="sxs-lookup"><span data-stu-id="a2d01-136">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="a2d01-137">Чтобы удалить все дополнительное пространство для хранения, [обратитесь в службу поддержки.](../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="a2d01-137">To remove all of the extra storage space, [contact support](../business-video/get-help-support.md).</span></span>

1. <span data-ttu-id="a2d01-138">В Центре администрирования перейдите на страницу **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="a2d01-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="a2d01-139">На **вкладке Продукты** выберите подписку, которая содержит Office 365 с дополнительным хранилищем надстройку. </span><span class="sxs-lookup"><span data-stu-id="a2d01-139">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="a2d01-140">На странице сведения о продукте в разделе **Надстройки** выберите **Управление надстройки**.</span><span class="sxs-lookup"><span data-stu-id="a2d01-140">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="a2d01-141">В области **Управление надстройки** из списка **надстройки** выберите **Office 365 с дополнительным хранилищем**.</span><span class="sxs-lookup"><span data-stu-id="a2d01-141">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="a2d01-142">В **текстовом окне** Количество введите количество ГБ пространства хранения, которое необходимо для подписки.</span><span class="sxs-lookup"><span data-stu-id="a2d01-142">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="a2d01-143">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a2d01-143">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="a2d01-144">Доступна ли в моем плане надстройка "Office 365 с дополнительным хранилищем"?</span><span class="sxs-lookup"><span data-stu-id="a2d01-144">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="a2d01-145">Надстройка "Office 365 с дополнительным хранилищем" доступна для таких подписок:</span><span class="sxs-lookup"><span data-stu-id="a2d01-145">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="a2d01-146">Office 365 для предприятий E1</span><span class="sxs-lookup"><span data-stu-id="a2d01-146">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="a2d01-147">Office 365 для предприятий E2</span><span class="sxs-lookup"><span data-stu-id="a2d01-147">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="a2d01-148">Office 365 для предприятий E3</span><span class="sxs-lookup"><span data-stu-id="a2d01-148">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="a2d01-149">Office 365 корпоративный E4</span><span class="sxs-lookup"><span data-stu-id="a2d01-149">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="a2d01-150">Office 365 корпоративный E5</span><span class="sxs-lookup"><span data-stu-id="a2d01-150">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="a2d01-151">Office веб-страницы с SharePoint 1</span><span class="sxs-lookup"><span data-stu-id="a2d01-151">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="a2d01-152">Office веб-страницы с SharePoint Plan 2</span><span class="sxs-lookup"><span data-stu-id="a2d01-152">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="a2d01-153">SharePoint Online (план 1)</span><span class="sxs-lookup"><span data-stu-id="a2d01-153">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="a2d01-154">SharePoint Online (план 2)</span><span class="sxs-lookup"><span data-stu-id="a2d01-154">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="a2d01-155">Microsoft 365 бизнес базовый</span><span class="sxs-lookup"><span data-stu-id="a2d01-155">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="a2d01-156">Microsoft 365 бизнес стандарт</span><span class="sxs-lookup"><span data-stu-id="a2d01-156">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="a2d01-157">Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="a2d01-157">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="a2d01-158">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="a2d01-158">Microsoft 365 E3</span></span>
- <span data-ttu-id="a2d01-159">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="a2d01-159">Microsoft 365 E5</span></span>
- <span data-ttu-id="a2d01-160">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="a2d01-160">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="a2d01-161">Office 365 с дополнительным хранилищем также доступен для GCC, GCC и doD-планов.</span><span class="sxs-lookup"><span data-stu-id="a2d01-161">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="a2d01-162">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2d01-162">Related content</span></span>

<span data-ttu-id="a2d01-163">[Управление ограничениями хранения сайтов](/sharepoint/manage-site-collection-storage-limits) (статья)</span><span class="sxs-lookup"><span data-stu-id="a2d01-163">[Manage site storage limits](/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="a2d01-164">[Установите пространство хранения по умолчанию для OneDrive пользователей](/onedrive/set-default-storage-space) (статья)</span><span class="sxs-lookup"><span data-stu-id="a2d01-164">[Set the default storage space for OneDrive users](/onedrive/set-default-storage-space) (article)</span></span>
