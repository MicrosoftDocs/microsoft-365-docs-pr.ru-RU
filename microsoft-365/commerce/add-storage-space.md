---
title: Добавление места в хранилище для подписки
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Узнайте, как добавлять и уменьшать объем хранилища файлов в подписке на Microsoft 365. Благодаря дополнительному хранилищу файлов вы можете хранить больше содержимого в SharePoint Online и OneDrive.
ms.date: ''
ms.openlocfilehash: fd59de31a27a1dd29800ae1d081e1f509f399124
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114911"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="91651-104">Добавление места в хранилище для подписки</span><span class="sxs-lookup"><span data-stu-id="91651-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="91651-105">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="91651-105">The admin center is changing.</span></span> <span data-ttu-id="91651-106">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="91651-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="91651-107">Если у вас заканчивается нехватка хранилища для ваших семейств сайтов SharePoint Online, вы можете добавить хранилище к своей подписке, если ваш план соответствует критериям.</span><span class="sxs-lookup"><span data-stu-id="91651-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="91651-108">Если вы не видите дополнительное хранилище файлов **Office 365** в списке доступных надстройок, это означает, что ваш план не имеет права.</span><span class="sxs-lookup"><span data-stu-id="91651-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="91651-109">Дополнительные сведения см. в [подходящем плане?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="91651-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="91651-110">Если вы приобрели подписку через корпоративное лицензирование или CSP, вы не сможете приобрести дополнительное хранилище файлов **Office 365** для своей организации непосредственно у корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="91651-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="91651-111">Обратитесь за помощью к представителю или партнеру.</span><span class="sxs-lookup"><span data-stu-id="91651-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="91651-112">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="91651-112">Before you begin</span></span>

<span data-ttu-id="91651-113">Для выполнения задач в этой статье необходимо быть глобальным администратором или администратором SharePoint.</span><span class="sxs-lookup"><span data-stu-id="91651-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="91651-114">Дополнительные сведения см. в статье [О ролях администраторов](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="91651-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="91651-115">Просмотр доступного хранилища</span><span class="sxs-lookup"><span data-stu-id="91651-115">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="91651-116">В Центре администрирования SharePoint <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank"></a> перейдите на страницу "Активные [](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) сайты" и войдите с помощью учетной записи с разрешениями администратора для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="91651-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="91651-117">В правом верхнем углу страницы отображается объем места в хранилище, используемый всеми сайтами, и общий объем хранилища, доступный для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="91651-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="91651-118">Если в вашей организации настроена служба с несколькими регионами в Office 365, на панели также указывается объем хранилища, используемого во всех географических расположениях.</span><span class="sxs-lookup"><span data-stu-id="91651-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Панель "Хранилище" на странице "Активные сайты"](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="91651-120">Значение используемого объема хранилища не учитывает изменения, сделанные за последние 24–48 часов.</span><span class="sxs-lookup"><span data-stu-id="91651-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="91651-121">Во sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span><span class="sxs-lookup"><span data-stu-id="91651-121">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="91651-122">Если вы видите сообщение о том, что у вас нет разрешения на доступ к странице, это означает, что в вашей организации нет разрешений администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="91651-122">If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="91651-123">В панели слева в разделе **Центры администрирования** выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="91651-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="91651-124">Если откроется классическая версия Центра администрирования SharePoint, нажмите кнопку **Открыть** в верхней части страницы, чтобы открыть новый Центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="91651-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="91651-125">На левой панели нового Центра администрирования SharePoint выберите пункт **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="91651-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="91651-126">В правом верхнем углу страницы отображается объем места в хранилище, используемый всеми сайтами, и общий объем хранилища, доступный для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="91651-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

   ![Панель "Хранилище" на странице "Активные сайты"](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="91651-128">Значение используемого объема хранилища не учитывает изменения, сделанные за последние 24–48 часов.</span><span class="sxs-lookup"><span data-stu-id="91651-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="91651-129">Во sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span><span class="sxs-lookup"><span data-stu-id="91651-129">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="91651-130">(Если вы видите сообщение о том, что у вас нет разрешения на доступ к странице, это означает, что у вас нет разрешений администратора Microsoft 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="91651-130">(If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="91651-131">В панели слева в разделе **Центры администрирования** выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="91651-131">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="91651-132">Если откроется классическая версия Центра администрирования SharePoint, нажмите кнопку **Открыть** в верхней части страницы, чтобы открыть новый Центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="91651-132">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="91651-133">На левой панели нового Центра администрирования SharePoint выберите пункт **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="91651-133">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="91651-134">В правом верхнем углу страницы отображается объем места в хранилище, используемый всеми сайтами, и общий объем хранилища, доступный для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="91651-134">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

   ![Панель "Хранилище" на странице "Активные сайты"](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="91651-136">Значение используемого объема хранилища не учитывает изменения, сделанные за последние 24–48 часов.</span><span class="sxs-lookup"><span data-stu-id="91651-136">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

<span data-ttu-id="91651-137">Определив объем используемого хранилища, вы можете добавить или удалить место в хранилище для подписки.</span><span class="sxs-lookup"><span data-stu-id="91651-137">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="91651-138">Чтобы узнать, сколько будет стоить добавление места в хранилище, выполните действия, которые вы выполните в этой статье, и просмотрите сведения о ценах перед покупкой.</span><span class="sxs-lookup"><span data-stu-id="91651-138">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="91651-139">Сведения о настройке ограничений на хранение в коллекции сайтов см. в под управлением ограничений на хранение в [коллекции веб-сайтов.](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)</span><span class="sxs-lookup"><span data-stu-id="91651-139">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="91651-140">Добавление хранилища в подписку</span><span class="sxs-lookup"><span data-stu-id="91651-140">Add storage to your subscription</span></span>

<span data-ttu-id="91651-141">Если вы еще не приобрели дополнительное хранилище для подписки, это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="91651-141">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="91651-142">В Центре администрирования перейдите на страницу **"Приобретение** услуг \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">вы выставления счета".</a></span><span class="sxs-lookup"><span data-stu-id="91651-142">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="91651-143">В нижней части страницы "Приобретение **служб"** выберите **"Надстройки".**</span><span class="sxs-lookup"><span data-stu-id="91651-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>
3. <span data-ttu-id="91651-144">Выберите дополнительное хранилище файлов **Office 365.**</span><span class="sxs-lookup"><span data-stu-id="91651-144">Select **Office 365 Extra File Storage**.</span></span>
4. <span data-ttu-id="91651-145">На странице "Дополнительное хранилище файлов **Office 365",** если она отображается, выберите базовую подписку, а затем введите количество гигабайт хранилища, который вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="91651-145">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="91651-146">Выберите **"Проверить" сейчас.**</span><span class="sxs-lookup"><span data-stu-id="91651-146">Select **Check out now**.</span></span>
6. <span data-ttu-id="91651-147">На странице "Как это **выглядит?"** проверьте количество выбранных гигабайт хранилища, просмотрите сведения о ценах и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="91651-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="91651-148">На странице **"Полный заказ"** проверьте итог.</span><span class="sxs-lookup"><span data-stu-id="91651-148">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="91651-149">Если необходимо внести какие-либо изменения, выберите **"Изменить порядок".**</span><span class="sxs-lookup"><span data-stu-id="91651-149">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="91651-150">Если заказ требует проверки кредитоспособности, выберите этот ящик.</span><span class="sxs-lookup"><span data-stu-id="91651-150">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="91651-151">Когда все будет готово, выберите **"Place order** \> **Go to Admin Home".**</span><span class="sxs-lookup"><span data-stu-id="91651-151">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="91651-152">В Центре администрирования перейдите на страницу **"Подписки** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">на выставление счета".</a>  </span><span class="sxs-lookup"><span data-stu-id="91651-152">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="91651-153">На странице **"Подписки"** выберите подписку, в которую нужно добавить место, а затем выберите **"Надстройки".**</span><span class="sxs-lookup"><span data-stu-id="91651-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="91651-155">Если вы не видите надстроек **и** ваша подписка приобретена у партнера, выберите Volume **Licensing Service Center (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="91651-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="91651-156">Выберите **"Купить надстройки".**</span><span class="sxs-lookup"><span data-stu-id="91651-156">Select **Buy add-ons**.</span></span>

    ![Ссылка "Купить надстройки" на странице "Подписки" в Центре администрирования.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="91651-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select Buy **now**.</span><span class="sxs-lookup"><span data-stu-id="91651-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="91651-159">Введите необходимое количество пользовательских лицензий и, если они показано, выберите базовую подписку.</span><span class="sxs-lookup"><span data-stu-id="91651-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="91651-160">Выберите **"Проверить" сейчас.**</span><span class="sxs-lookup"><span data-stu-id="91651-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="91651-161">На странице "Как это **выглядит?"** проверьте количество выбранных гигабайт хранилища, просмотрите сведения о ценах и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="91651-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="91651-162">На странице **"Полный заказ"** выберите **"Place order" (Разместить заказ).**</span><span class="sxs-lookup"><span data-stu-id="91651-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="91651-163">В Центре администрирования перейдите на страницу **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Подписки</a>.</span><span class="sxs-lookup"><span data-stu-id="91651-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="91651-164">На странице **"Подписки"** выберите подписку, в которую нужно добавить место, а затем выберите **"Надстройки".**</span><span class="sxs-lookup"><span data-stu-id="91651-164">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="91651-166">Если вы не видите надстроек **и** ваша подписка приобретена у партнера, выберите Volume **Licensing Service Center (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="91651-166">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="91651-167">Выберите **"Купить надстройки".**</span><span class="sxs-lookup"><span data-stu-id="91651-167">Select **Buy add-ons**.</span></span>

    ![Ссылка "Купить надстройки" на странице "Подписки" в Центре администрирования.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="91651-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select Buy **now**.</span><span class="sxs-lookup"><span data-stu-id="91651-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="91651-170">Введите необходимое количество пользовательских лицензий и, если они показано, выберите базовую подписку.</span><span class="sxs-lookup"><span data-stu-id="91651-170">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="91651-171">Выберите **"Проверить" сейчас.**</span><span class="sxs-lookup"><span data-stu-id="91651-171">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="91651-172">На странице "Как это **выглядит?"** проверьте количество выбранных гигабайт хранилища, просмотрите сведения о ценах и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="91651-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="91651-173">На странице **"Полный заказ"** выберите **"Place order" (Разместить заказ).**</span><span class="sxs-lookup"><span data-stu-id="91651-173">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="91651-174">Увеличение или уменьшение хранилища</span><span class="sxs-lookup"><span data-stu-id="91651-174">Increase or decrease storage</span></span>

<span data-ttu-id="91651-175">Если вы уже приобрели дополнительное хранилище файлов с помощью надстройки "Дополнительное хранилище файлов **Office 365",** с помощью этих действий можно увеличить или уменьшить дополнительное место в хранилище для подписки.</span><span class="sxs-lookup"><span data-stu-id="91651-175">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="91651-176">Вы можете уменьшить объем хранилища до 1 гигабайта.</span><span class="sxs-lookup"><span data-stu-id="91651-176">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="91651-177">Чтобы удалить все дополнительное место в хранилище, [обратитесь в службу поддержки.](../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="91651-177">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="91651-178">В Центре администрирования перейдите на страницу **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="91651-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="91651-179">На **вкладке** "Продукты" выберите подписку, которая содержит надстройку **office 365 с** дополнительным хранилищем файлов.</span><span class="sxs-lookup"><span data-stu-id="91651-179">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="91651-180">На странице сведений о продукте в **разделе** "Надстройки" выберите "Управление **надстройки".**</span><span class="sxs-lookup"><span data-stu-id="91651-180">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="91651-181">В области **"Управление надстройки"** в списке надстройки выберите "Дополнительное хранилище файлов **Office 365".** </span><span class="sxs-lookup"><span data-stu-id="91651-181">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="91651-182">В **текстовом поле** "Количество" введите количество ГБ места в хранилище, которое необходимо для подписки.</span><span class="sxs-lookup"><span data-stu-id="91651-182">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="91651-183">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="91651-183">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="91651-184">В Центре администрирования перейдите на страницу **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Подписки</a>.</span><span class="sxs-lookup"><span data-stu-id="91651-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="91651-185">На странице **"Подписки"** выберите **"Надстройки".**</span><span class="sxs-lookup"><span data-stu-id="91651-185">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="91651-187">Если вы не видите надстроек **и** ваша подписка приобретена у партнера, выберите Volume **Licensing Service Center (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="91651-187">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="91651-188">В **области "Дополнительное хранилище файлов Office 365"** выберите **"Изменить количество".**</span><span class="sxs-lookup"><span data-stu-id="91651-188">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Ссылка "Изменить количество".](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="91651-190">В правой области введите необходимое количество гигабайт, а затем выберите **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="91651-190">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="91651-191">Например, если у вас есть 200 ГБ дополнительного места, а вам нужно только 100 ГБ, в поле следует ввести **100**.</span><span class="sxs-lookup"><span data-stu-id="91651-191">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="91651-192">Нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="91651-192">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="91651-193">В Центре администрирования перейдите на страницу **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Подписки</a>.</span><span class="sxs-lookup"><span data-stu-id="91651-193">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="91651-194">На странице **"Подписки"** выберите **"Надстройки".**</span><span class="sxs-lookup"><span data-stu-id="91651-194">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="91651-196">Если вы не видите надстроек **и** ваша подписка приобретена у партнера, выберите Volume **Licensing Service Center (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="91651-196">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="91651-197">В **области "Дополнительное хранилище файлов Office 365"** выберите **"Изменить количество".**</span><span class="sxs-lookup"><span data-stu-id="91651-197">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Ссылка "Изменить количество".](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="91651-199">В правой области введите необходимое количество гигабайт, а затем выберите **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="91651-199">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="91651-200">Например, если у вас есть 200 ГБ дополнительного места, а вам нужно только 100 ГБ, в поле следует ввести **100**.</span><span class="sxs-lookup"><span data-stu-id="91651-200">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="91651-201">Нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="91651-201">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="91651-202">Доступна ли в моем плане надстройка "Office 365 с дополнительным хранилищем"?</span><span class="sxs-lookup"><span data-stu-id="91651-202">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="91651-203">Надстройка "Office 365 с дополнительным хранилищем" доступна для таких подписок:</span><span class="sxs-lookup"><span data-stu-id="91651-203">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="91651-204">Office 365 для предприятий E1</span><span class="sxs-lookup"><span data-stu-id="91651-204">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="91651-205">Office 365 для предприятий E2</span><span class="sxs-lookup"><span data-stu-id="91651-205">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="91651-206">Office 365 для предприятий E3</span><span class="sxs-lookup"><span data-stu-id="91651-206">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="91651-207">Office 365 корпоративный E4</span><span class="sxs-lookup"><span data-stu-id="91651-207">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="91651-208">Office 365 корпоративный E5</span><span class="sxs-lookup"><span data-stu-id="91651-208">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="91651-209">Office для Интернета с SharePoint (план 1)</span><span class="sxs-lookup"><span data-stu-id="91651-209">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="91651-210">Office для Интернета с SharePoint (план 2)</span><span class="sxs-lookup"><span data-stu-id="91651-210">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="91651-211">SharePoint Online (план 1)</span><span class="sxs-lookup"><span data-stu-id="91651-211">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="91651-212">SharePoint Online (план 2)</span><span class="sxs-lookup"><span data-stu-id="91651-212">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="91651-213">Microsoft 365 бизнес базовый</span><span class="sxs-lookup"><span data-stu-id="91651-213">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="91651-214">Microsoft 365 бизнес стандарт</span><span class="sxs-lookup"><span data-stu-id="91651-214">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="91651-215">Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="91651-215">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="91651-216">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="91651-216">Microsoft 365 E3</span></span>

- <span data-ttu-id="91651-217">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="91651-217">Microsoft 365 E5</span></span>

- <span data-ttu-id="91651-218">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="91651-218">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="91651-219">Дополнительное хранилище файлов Office 365 также доступно для планов GCC, GCC High и DOD.</span><span class="sxs-lookup"><span data-stu-id="91651-219">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="91651-220">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="91651-220">Related content</span></span>

<span data-ttu-id="91651-221">[Управление ограничениями хранилища сайтов](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (статья)</span><span class="sxs-lookup"><span data-stu-id="91651-221">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="91651-222">[Настройка хранилища по умолчанию для пользователей OneDrive](https://docs.microsoft.com/onedrive/set-default-storage-space)(статья)</span><span class="sxs-lookup"><span data-stu-id="91651-222">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>
