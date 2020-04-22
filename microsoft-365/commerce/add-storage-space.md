---
title: Добавление дискового пространства для подписки
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEU150
- GEA150
- GSP150
ms.assetid: 96ea3533-de64-4b01-839a-c560875a662c
description: Сведения о добавлении и уменьшении размера файлов в вашей подписке на Microsoft 365. С помощью дополнительного хранилища файлов вы можете хранить дополнительные материалы в SharePoint Online и OneDrive.
ms.openlocfilehash: b5dea51e0e8616749a820ff35827b4390390af50
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632747"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="7608b-104">Добавление дискового пространства для подписки</span><span class="sxs-lookup"><span data-stu-id="7608b-104">Add storage space for your subscription</span></span>

<span data-ttu-id="7608b-105">Если у вас заканчивается нехватка хранилища для ваших семейств сайтов SharePoint Online, вы можете добавить хранилище к своей подписке, если ваш план соответствует критериям.</span><span class="sxs-lookup"><span data-stu-id="7608b-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="7608b-106">Если вы не видите **дополнительное хранилище файлов Office 365** в списке доступных надстроек, это означает, что ваш план не подходит.</span><span class="sxs-lookup"><span data-stu-id="7608b-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="7608b-107">Чтобы получить дополнительные сведения, ознакомьтесь с [различной схемой.](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="7608b-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="7608b-108">Просмотр доступного хранилища</span><span class="sxs-lookup"><span data-stu-id="7608b-108">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7608b-109">Войдите в https://admin.microsoft.com систему как глобальный администратор или администратор SharePoint. (Если отображается сообщение о том, что у вас нет разрешения на доступ к странице, у вас нет прав администратора Microsoft 365 в вашей организации.)</span><span class="sxs-lookup"><span data-stu-id="7608b-109">Sign in to https://admin.microsoft.com as a global or SharePoint admin. (If you see a message that you don't have permission to access the page, you don't have Microsoft 365 administrator permissions in your organization.)</span></span>
    
2. <span data-ttu-id="7608b-110">В панели слева в разделе **Центры администрирования** выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7608b-110">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="7608b-111">Если откроется классическая версия Центра администрирования SharePoint, нажмите кнопку **Открыть** в верхней части страницы, чтобы открыть новый Центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7608b-111">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span> 
    
3. <span data-ttu-id="7608b-112">На левой панели нового Центра администрирования SharePoint выберите пункт **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="7608b-112">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="7608b-113">В правом верхнем углу страницы отображается объем хранилища, используемого для всех сайтов, и общий объем хранилища для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="7608b-113">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="7608b-114">(Если в организации настроена поддержка нескольких регионов в Office 365, на панели также показывается объем хранилища, используемого для всех географических расположений.)</span><span class="sxs-lookup"><span data-stu-id="7608b-114">(If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.)</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7608b-115">Войдите в https://portal.office.de систему как глобальный администратор или администратор SharePoint, а затем выберите плитку администратор, чтобы открыть центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="7608b-115">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="7608b-116">(Если отображается сообщение о том, что у вас нет разрешения на доступ к странице, у вас нет прав администратора Microsoft 365 в вашей организации.)</span><span class="sxs-lookup"><span data-stu-id="7608b-116">(If you see a message that you don't have permission to access the page, you don't have Microsoft 365 administrator permissions in your organization.)</span></span>
    
2. <span data-ttu-id="7608b-117">В панели слева в разделе **Центры администрирования** выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7608b-117">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="7608b-118">Если откроется классическая версия Центра администрирования SharePoint, нажмите кнопку **Открыть** в верхней части страницы, чтобы открыть новый Центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7608b-118">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span> 
    
3. <span data-ttu-id="7608b-119">На левой панели нового Центра администрирования SharePoint выберите пункт **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="7608b-119">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="7608b-120">В правом верхнем углу страницы отображается объем хранилища, используемого для всех сайтов, и общий объем хранилища для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="7608b-120">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7608b-121">Войдите в https://login.partner.microsoftonline.cn/ систему как глобальный администратор или администратор SharePoint, а затем выберите плитку администратор, чтобы открыть центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="7608b-121">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="7608b-122">(Если отображается сообщение о том, что у вас нет разрешения на доступ к странице, у вас нет прав администратора Microsoft 365 в вашей организации.)</span><span class="sxs-lookup"><span data-stu-id="7608b-122">(If you see a message that you don't have permission to access the page, you don't have Microsoft 365 administrator permissions in your organization.)</span></span>
     
2. <span data-ttu-id="7608b-123">В панели слева в разделе **Центры администрирования** выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7608b-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="7608b-124">Если откроется классическая версия Центра администрирования SharePoint, нажмите кнопку **Открыть** в верхней части страницы, чтобы открыть новый Центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7608b-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span> 
    
3. <span data-ttu-id="7608b-125">На левой панели нового Центра администрирования SharePoint выберите пункт **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="7608b-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="7608b-126">В правом верхнем углу страницы отображается объем хранилища, используемого для всех сайтов, и общий объем хранилища для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="7608b-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

::: moniker-end


![Панель хранения на странице активных сайтов](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

> [!NOTE]
> <span data-ttu-id="7608b-128">Используемое хранилище не включает изменения, внесенные в течение последних 24-48 часов.</span><span class="sxs-lookup"><span data-stu-id="7608b-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span> 

<span data-ttu-id="7608b-129">Определив объем используемого хранилища, вы можете добавить или удалить дисковое пространство для своей подписки.</span><span class="sxs-lookup"><span data-stu-id="7608b-129">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="7608b-130">Чтобы узнать, сколько затрат будет стоить при добавлении дискового пространства, выполните действия, описанные в этой статье, и ознакомьтесь со сведениями о ценах перед покупкой.</span><span class="sxs-lookup"><span data-stu-id="7608b-130">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="7608b-131">Сведения о том, как задать пределы хранения для семейства веб-сайтов, можно найти в разделе [Manage site Limit Storage Limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span><span class="sxs-lookup"><span data-stu-id="7608b-131">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="7608b-132">Добавление хранилища к подписке</span><span class="sxs-lookup"><span data-stu-id="7608b-132">Add storage to your subscription</span></span>

<span data-ttu-id="7608b-133">Если вы еще не приобрели дополнительное хранилище для своей подписки, это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="7608b-133">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"


1. <span data-ttu-id="7608b-134">В центре администрирования перейдите на страницу Услуги по **выставлению счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">покупки</a> .</span><span class="sxs-lookup"><span data-stu-id="7608b-134">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

2. <span data-ttu-id="7608b-135">В нижней части страницы **услуги покупки** выберите **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="7608b-135">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>

3. <span data-ttu-id="7608b-136">Выберите **Office 365 Extra Storage File**.</span><span class="sxs-lookup"><span data-stu-id="7608b-136">Select **Office 365 Extra File Storage**.</span></span>

4. <span data-ttu-id="7608b-137">На странице **Office 365 Extra Storage File** , если она отображается, выберите базовую подписку, а затем введите количество гигабайтов хранилища, которое вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="7608b-137">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>

5. <span data-ttu-id="7608b-138">Нажмите **кнопку извлечь.**</span><span class="sxs-lookup"><span data-stu-id="7608b-138">Select **Check out now**.</span></span>

6. <span data-ttu-id="7608b-139">На странице **как это выглядит?** проверьте выбранное количество гигабайтов хранилища, просмотрите сведения о ценах, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7608b-139">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="7608b-140">На странице **полный заказ** проверьте итоговое значение.</span><span class="sxs-lookup"><span data-stu-id="7608b-140">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="7608b-141">Если требуется внести изменения, выберите пункт **изменить заказ**.</span><span class="sxs-lookup"><span data-stu-id="7608b-141">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="7608b-142">Если для заказа требуется проверка кредита, установите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="7608b-142">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="7608b-143">Когда все будет готово, нажмите кнопку **поместить заказ** \> **перейдите на домашнюю страницу администратора**.</span><span class="sxs-lookup"><span data-stu-id="7608b-143">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7608b-144">В центре администрирования перейдите на страницу <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">подписки</a> на **выставление счетов** \>.  </span><span class="sxs-lookup"><span data-stu-id="7608b-144">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="7608b-145">На странице " **подписки** " выберите подписку, в которую вы хотите добавить дисковое пространство, а затем выберите **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="7608b-145">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="7608b-147">Если вы не видите **надстройки**, а ваша подписка была приобретена в партнере, выберите **центр обслуживания корпоративного лицензирования (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="7608b-147">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="7608b-148">Выберите **купить надстройки**.</span><span class="sxs-lookup"><span data-stu-id="7608b-148">Select **Buy add-ons**.</span></span>

    !["Приобрести надстройки" на странице "подписки" центра администрирования.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="7608b-150">На странице **приобретение служб** наведите указатель мыши на **дополнительное хранилище файлов Office 365**или нажмите кнопку **купить**.</span><span class="sxs-lookup"><span data-stu-id="7608b-150">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="7608b-151">Введите необходимое количество пользовательских лицензий и, если это отображается, выберите базовую подписку.</span><span class="sxs-lookup"><span data-stu-id="7608b-151">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="7608b-152">Нажмите **кнопку извлечь.**</span><span class="sxs-lookup"><span data-stu-id="7608b-152">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="7608b-153">На странице **как это выглядит?** проверьте выбранное количество гигабайтов хранилища, просмотрите сведения о ценах, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7608b-153">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="7608b-154">На странице **полный заказ** выберите пункт **разместить заказ**.</span><span class="sxs-lookup"><span data-stu-id="7608b-154">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7608b-155">В Центре администрирования выберите страницу **Выставление счетов** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Подписки</a>.</span><span class="sxs-lookup"><span data-stu-id="7608b-155">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="7608b-156">На странице " **подписки** " выберите подписку, в которую вы хотите добавить дисковое пространство, а затем выберите **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="7608b-156">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="7608b-158">Если вы не видите **надстройки**, а ваша подписка была приобретена в партнере, выберите **центр обслуживания корпоративного лицензирования (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="7608b-158">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="7608b-159">Выберите **купить надстройки**.</span><span class="sxs-lookup"><span data-stu-id="7608b-159">Select **Buy add-ons**.</span></span>

    !["Приобрести надстройки" на странице "подписки" центра администрирования.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="7608b-161">На странице **приобретение служб** наведите указатель мыши на **дополнительное хранилище файлов Office 365**или нажмите кнопку **купить**.</span><span class="sxs-lookup"><span data-stu-id="7608b-161">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="7608b-162">Введите необходимое количество пользовательских лицензий и, если это отображается, выберите базовую подписку.</span><span class="sxs-lookup"><span data-stu-id="7608b-162">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="7608b-163">Нажмите **кнопку извлечь.**</span><span class="sxs-lookup"><span data-stu-id="7608b-163">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="7608b-164">На странице **как это выглядит?** проверьте выбранное количество гигабайтов хранилища, просмотрите сведения о ценах, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7608b-164">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="7608b-165">На странице **полный заказ** выберите пункт **разместить заказ**.</span><span class="sxs-lookup"><span data-stu-id="7608b-165">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end


## <a name="increase-or-decrease-storage"></a><span data-ttu-id="7608b-166">Увеличение или уменьшение хранилища</span><span class="sxs-lookup"><span data-stu-id="7608b-166">Increase or decrease storage</span></span>

<span data-ttu-id="7608b-167">Если вы уже приобрели дополнительное хранилище файлов с помощью надстройки **Office 365 Extra Storage** , вы можете использовать эти действия, чтобы увеличить или уменьшить дополнительное место для подписки.</span><span class="sxs-lookup"><span data-stu-id="7608b-167">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="7608b-168">Вы можете уменьшить объем дискового пространства, как минимум 1 ГБ.</span><span class="sxs-lookup"><span data-stu-id="7608b-168">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="7608b-169">Чтобы удалить все лишнее дисковое пространство, необходимо обратиться в [службу поддержки](../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="7608b-169">To remove all of the extra storage space, you need to [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"


1. <span data-ttu-id="7608b-170">В Центре администрирования перейдите на страницу **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Продукты и службы</a>.</span><span class="sxs-lookup"><span data-stu-id="7608b-170">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="7608b-171">Выберите подписку, которая содержит надстройку **Office 365 Extra Storage** .</span><span class="sxs-lookup"><span data-stu-id="7608b-171">Choose the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>

3. <span data-ttu-id="7608b-172">Выберите **надстройки**, а затем нажмите **изменить количество**.</span><span class="sxs-lookup"><span data-stu-id="7608b-172">Select **Add-ons**, then choose **Change quantity**.</span></span>

4. <span data-ttu-id="7608b-173">В области **Добавить/удалить гигабайты** введите общее количество гигабайтов, которое требуется для подписки, а затем нажмите кнопку **послать изменение**.</span><span class="sxs-lookup"><span data-stu-id="7608b-173">In the **Add/Remove gigabytes** pane, enter the total gigabytes you want for the subscription, then select **Submit change**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7608b-174">В Центре администрирования выберите страницу **Выставление счетов** \><a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Подписки</a>.</span><span class="sxs-lookup"><span data-stu-id="7608b-174">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>


2. <span data-ttu-id="7608b-175">На странице **подписки** выберите **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="7608b-175">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="7608b-177">Если вы не видите **надстройки**, а ваша подписка была приобретена в партнере, выберите **центр обслуживания корпоративного лицензирования (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="7608b-177">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="7608b-178">В разделе **Office 365 дополнительное хранилище файлов**выберите **изменить количество**.</span><span class="sxs-lookup"><span data-stu-id="7608b-178">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Ссылка "Изменить количество".](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="7608b-180">В правой области введите общее количество гигабайтов, которое вам нужно, а затем нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="7608b-180">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="7608b-181">Например, если у вас есть 200 ГБ дополнительного места, а вам нужно только 100 ГБ, в поле следует ввести **100**.</span><span class="sxs-lookup"><span data-stu-id="7608b-181">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="7608b-182">Нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7608b-182">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7608b-183">В Центре администрирования выберите страницу **Выставление счетов** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Подписки</a>.</span><span class="sxs-lookup"><span data-stu-id="7608b-183">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="7608b-184">На странице **подписки** выберите **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="7608b-184">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="7608b-186">Если вы не видите **надстройки**, а ваша подписка была приобретена в партнере, выберите **центр обслуживания корпоративного лицензирования (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="7608b-186">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="7608b-187">В разделе **Office 365 дополнительное хранилище файлов**выберите **изменить количество**.</span><span class="sxs-lookup"><span data-stu-id="7608b-187">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Ссылка "Изменить количество".](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="7608b-189">В правой области введите общее количество гигабайтов, которое вам нужно, а затем нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="7608b-189">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="7608b-190">Например, если у вас есть 200 ГБ дополнительного места, а вам нужно только 100 ГБ, в поле следует ввести **100**.</span><span class="sxs-lookup"><span data-stu-id="7608b-190">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="7608b-191">Нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7608b-191">Select **Close**.</span></span>

::: moniker-end



## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="7608b-192">Доступна ли в моем плане надстройка "Office 365 с дополнительным хранилищем"?</span><span class="sxs-lookup"><span data-stu-id="7608b-192">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="7608b-193">Надстройка "Office 365 с дополнительным хранилищем" доступна для таких подписок:</span><span class="sxs-lookup"><span data-stu-id="7608b-193">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="7608b-194">Office 365 для предприятий E1</span><span class="sxs-lookup"><span data-stu-id="7608b-194">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="7608b-195">Office 365 для предприятий E2</span><span class="sxs-lookup"><span data-stu-id="7608b-195">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="7608b-196">Office 365 для предприятий E3</span><span class="sxs-lookup"><span data-stu-id="7608b-196">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="7608b-197">Office 365 корпоративный E4</span><span class="sxs-lookup"><span data-stu-id="7608b-197">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="7608b-198">Office 365 корпоративный E5</span><span class="sxs-lookup"><span data-stu-id="7608b-198">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="7608b-199">Office для Интернета с SharePoint (план 1)</span><span class="sxs-lookup"><span data-stu-id="7608b-199">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="7608b-200">Office для Интернета с SharePoint (план 2)</span><span class="sxs-lookup"><span data-stu-id="7608b-200">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="7608b-201">SharePoint Online (план 1)</span><span class="sxs-lookup"><span data-stu-id="7608b-201">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="7608b-202">SharePoint Online (план 2)</span><span class="sxs-lookup"><span data-stu-id="7608b-202">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="7608b-203">Microsoft 365 бизнес базовый</span><span class="sxs-lookup"><span data-stu-id="7608b-203">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="7608b-204">Microsoft 365 бизнес Standard</span><span class="sxs-lookup"><span data-stu-id="7608b-204">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="7608b-205">Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="7608b-205">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="7608b-206">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="7608b-206">Microsoft 365 E3</span></span>

- <span data-ttu-id="7608b-207">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="7608b-207">Microsoft 365 E5</span></span>

- <span data-ttu-id="7608b-208">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="7608b-208">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="7608b-209">Office 365 дополнительное хранилище файлов также доступно для планов GCC, GCC High и DOD.</span><span class="sxs-lookup"><span data-stu-id="7608b-209">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>