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
- AdminSurgePortfolio
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
ms.openlocfilehash: f31495127feb345cccdc792c60333f5fc0c7cc6f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402682"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="79943-104">Добавление дискового пространства для подписки</span><span class="sxs-lookup"><span data-stu-id="79943-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="79943-105">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="79943-105">The admin center is changing.</span></span> <span data-ttu-id="79943-106">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="79943-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="79943-107">Если у вас заканчивается нехватка хранилища для ваших семейств сайтов SharePoint Online, вы можете добавить хранилище к своей подписке, если ваш план соответствует критериям.</span><span class="sxs-lookup"><span data-stu-id="79943-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="79943-108">Если вы не видите **дополнительное хранилище файлов Office 365** в списке доступных надстроек, это означает, что ваш план не подходит.</span><span class="sxs-lookup"><span data-stu-id="79943-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="79943-109">Чтобы получить дополнительные сведения, ознакомьтесь с [различной схемой.](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="79943-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="79943-110">Просмотр доступного хранилища</span><span class="sxs-lookup"><span data-stu-id="79943-110">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="79943-111">Перейдите на страницу ["Активные сайты" в новом Центре администрирования SharePoint](https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true) и войдите, используя учетную запись с [правами администратора](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="79943-111">Go to the [Active sites page of the new SharePoint admin center](https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true), and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="79943-112">В правом верхнем углу страницы отображается объем хранилища, используемого для всех сайтов, и общий объем хранилища для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="79943-112">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="79943-113">(Если в организации настроена поддержка нескольких регионов в Office 365, на панели также показывается объем хранилища, используемого для всех географических расположений.)</span><span class="sxs-lookup"><span data-stu-id="79943-113">(If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.)</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="79943-114">Войдите в https://portal.office.de систему как глобальный администратор или администратор SharePoint, а затем выберите плитку администратор, чтобы открыть центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="79943-114">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="79943-115">(Если отображается сообщение о том, что у вас нет разрешения на доступ к странице, у вас нет прав администратора Microsoft 365 в вашей организации.)</span><span class="sxs-lookup"><span data-stu-id="79943-115">(If you see a message that you don't have permission to access the page, you don't have Microsoft 365 administrator permissions in your organization.)</span></span>

2. <span data-ttu-id="79943-116">В панели слева в разделе **Центры администрирования** выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="79943-116">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="79943-117">Если откроется классическая версия Центра администрирования SharePoint, нажмите кнопку **Открыть** в верхней части страницы, чтобы открыть новый Центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="79943-117">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="79943-118">На левой панели нового Центра администрирования SharePoint выберите пункт **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="79943-118">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="79943-119">В правом верхнем углу страницы отображается объем хранилища, используемого для всех сайтов, и общий объем хранилища для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="79943-119">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="79943-120">Войдите в https://login.partner.microsoftonline.cn/ систему как глобальный администратор или администратор SharePoint, а затем выберите плитку администратор, чтобы открыть центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="79943-120">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="79943-121">(Если отображается сообщение о том, что у вас нет разрешения на доступ к странице, у вас нет прав администратора Microsoft 365 в вашей организации.)</span><span class="sxs-lookup"><span data-stu-id="79943-121">(If you see a message that you don't have permission to access the page, you don't have Microsoft 365 administrator permissions in your organization.)</span></span>

2. <span data-ttu-id="79943-122">В панели слева в разделе **Центры администрирования** выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="79943-122">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="79943-123">Если откроется классическая версия Центра администрирования SharePoint, нажмите кнопку **Открыть** в верхней части страницы, чтобы открыть новый Центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="79943-123">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="79943-124">На левой панели нового Центра администрирования SharePoint выберите пункт **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="79943-124">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="79943-125">В правом верхнем углу страницы отображается объем хранилища, используемого для всех сайтов, и общий объем хранилища для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="79943-125">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

::: moniker-end

![Панель хранения на странице активных сайтов](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

> [!NOTE]
> <span data-ttu-id="79943-127">Используемое хранилище не включает изменения, внесенные в течение последних 24-48 часов.</span><span class="sxs-lookup"><span data-stu-id="79943-127">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="79943-128">Определив объем используемого хранилища, вы можете добавить или удалить дисковое пространство для своей подписки.</span><span class="sxs-lookup"><span data-stu-id="79943-128">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="79943-129">Чтобы узнать, сколько затрат будет стоить при добавлении дискового пространства, выполните действия, описанные в этой статье, и ознакомьтесь со сведениями о ценах перед покупкой.</span><span class="sxs-lookup"><span data-stu-id="79943-129">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="79943-130">Сведения о том, как задать пределы хранения для семейства веб-сайтов, можно найти в разделе [Manage site Limit Storage Limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span><span class="sxs-lookup"><span data-stu-id="79943-130">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="79943-131">Добавление хранилища к подписке</span><span class="sxs-lookup"><span data-stu-id="79943-131">Add storage to your subscription</span></span>

<span data-ttu-id="79943-132">Если вы еще не приобрели дополнительное хранилище для своей подписки, это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="79943-132">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="79943-133">В центре администрирования перейдите на страницу Услуги по **выставлению счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">покупки</a> .</span><span class="sxs-lookup"><span data-stu-id="79943-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

2. <span data-ttu-id="79943-134">В нижней части страницы **услуги покупки** выберите **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="79943-134">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>

3. <span data-ttu-id="79943-135">Выберите **Office 365 Extra Storage File**.</span><span class="sxs-lookup"><span data-stu-id="79943-135">Select **Office 365 Extra File Storage**.</span></span>

4. <span data-ttu-id="79943-136">На странице **Office 365 Extra Storage File** , если она отображается, выберите базовую подписку, а затем введите количество гигабайтов хранилища, которое вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="79943-136">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>

5. <span data-ttu-id="79943-137">Нажмите **кнопку извлечь.**</span><span class="sxs-lookup"><span data-stu-id="79943-137">Select **Check out now**.</span></span>

6. <span data-ttu-id="79943-138">На странице **как это выглядит?** проверьте выбранное количество гигабайтов хранилища, просмотрите сведения о ценах, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="79943-138">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="79943-139">На странице **полный заказ** проверьте итоговое значение.</span><span class="sxs-lookup"><span data-stu-id="79943-139">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="79943-140">Если требуется внести изменения, выберите пункт **изменить заказ**.</span><span class="sxs-lookup"><span data-stu-id="79943-140">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="79943-141">Если для заказа требуется проверка кредита, установите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="79943-141">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="79943-142">Когда все будет готово, нажмите кнопку **поместить заказ** \> **перейдите на домашнюю страницу администратора**.</span><span class="sxs-lookup"><span data-stu-id="79943-142">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="79943-143">В центре администрирования перейдите на страницу подписки на **выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> .  </span><span class="sxs-lookup"><span data-stu-id="79943-143">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="79943-144">На странице " **подписки** " выберите подписку, в которую вы хотите добавить дисковое пространство, а затем выберите **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="79943-144">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="79943-146">Если вы не видите **надстройки**, а ваша подписка была приобретена в партнере, выберите **центр обслуживания корпоративного лицензирования (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="79943-146">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="79943-147">Выберите **купить надстройки**.</span><span class="sxs-lookup"><span data-stu-id="79943-147">Select **Buy add-ons**.</span></span>

    !["Приобрести надстройки" на странице "подписки" центра администрирования.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="79943-149">На странице **приобретение служб** наведите указатель мыши на **дополнительное хранилище файлов Office 365**или нажмите кнопку **купить**.</span><span class="sxs-lookup"><span data-stu-id="79943-149">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="79943-150">Введите необходимое количество пользовательских лицензий и, если это отображается, выберите базовую подписку.</span><span class="sxs-lookup"><span data-stu-id="79943-150">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="79943-151">Нажмите **кнопку извлечь.**</span><span class="sxs-lookup"><span data-stu-id="79943-151">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="79943-152">На странице **как это выглядит?** проверьте выбранное количество гигабайтов хранилища, просмотрите сведения о ценах, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="79943-152">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="79943-153">На странице **полный заказ** выберите пункт **разместить заказ**.</span><span class="sxs-lookup"><span data-stu-id="79943-153">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="79943-154">В Центре администрирования перейдите на страницу **Выставление счетов** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Подписки</a>.</span><span class="sxs-lookup"><span data-stu-id="79943-154">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="79943-155">На странице " **подписки** " выберите подписку, в которую вы хотите добавить дисковое пространство, а затем выберите **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="79943-155">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="79943-157">Если вы не видите **надстройки**, а ваша подписка была приобретена в партнере, выберите **центр обслуживания корпоративного лицензирования (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="79943-157">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="79943-158">Выберите **купить надстройки**.</span><span class="sxs-lookup"><span data-stu-id="79943-158">Select **Buy add-ons**.</span></span>

    !["Приобрести надстройки" на странице "подписки" центра администрирования.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="79943-160">На странице **приобретение служб** наведите указатель мыши на **дополнительное хранилище файлов Office 365**или нажмите кнопку **купить**.</span><span class="sxs-lookup"><span data-stu-id="79943-160">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="79943-161">Введите необходимое количество пользовательских лицензий и, если это отображается, выберите базовую подписку.</span><span class="sxs-lookup"><span data-stu-id="79943-161">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="79943-162">Нажмите **кнопку извлечь.**</span><span class="sxs-lookup"><span data-stu-id="79943-162">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="79943-163">На странице **как это выглядит?** проверьте выбранное количество гигабайтов хранилища, просмотрите сведения о ценах, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="79943-163">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="79943-164">На странице **полный заказ** выберите пункт **разместить заказ**.</span><span class="sxs-lookup"><span data-stu-id="79943-164">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="79943-165">Увеличение или уменьшение хранилища</span><span class="sxs-lookup"><span data-stu-id="79943-165">Increase or decrease storage</span></span>

<span data-ttu-id="79943-166">Если вы уже приобрели дополнительное хранилище файлов с помощью надстройки **Office 365 Extra Storage** , вы можете использовать эти действия, чтобы увеличить или уменьшить дополнительное место для подписки.</span><span class="sxs-lookup"><span data-stu-id="79943-166">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="79943-167">Вы можете уменьшить объем дискового пространства, как минимум 1 ГБ.</span><span class="sxs-lookup"><span data-stu-id="79943-167">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="79943-168">Чтобы удалить все лишнее дисковое пространство, необходимо обратиться в [службу поддержки](../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="79943-168">To remove all of the extra storage space, you need to [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="79943-169">В Центре администрирования перейдите на страницу **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="79943-169">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="79943-170">Выберите подписку, которая содержит надстройку **Office 365 Extra Storage** .</span><span class="sxs-lookup"><span data-stu-id="79943-170">Choose the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>

3. <span data-ttu-id="79943-171">Выберите **надстройки**, а затем нажмите **изменить количество**.</span><span class="sxs-lookup"><span data-stu-id="79943-171">Select **Add-ons**, then choose **Change quantity**.</span></span>

4. <span data-ttu-id="79943-172">В области **Добавить/удалить гигабайты** введите общее количество гигабайтов, которое требуется для подписки, а затем нажмите кнопку **послать изменение**.</span><span class="sxs-lookup"><span data-stu-id="79943-172">In the **Add/Remove gigabytes** pane, enter the total gigabytes you want for the subscription, then select **Submit change**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="79943-173">В Центре администрирования перейдите на страницу **Выставление счетов** \><a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Подписки</a>.</span><span class="sxs-lookup"><span data-stu-id="79943-173">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="79943-174">На странице **подписки** выберите **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="79943-174">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="79943-176">Если вы не видите **надстройки**, а ваша подписка была приобретена в партнере, выберите **центр обслуживания корпоративного лицензирования (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="79943-176">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="79943-177">В разделе **Office 365 дополнительное хранилище файлов**выберите **изменить количество**.</span><span class="sxs-lookup"><span data-stu-id="79943-177">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Ссылка "Изменить количество".](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="79943-179">В правой области введите общее количество гигабайтов, которое вам нужно, а затем нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="79943-179">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="79943-180">Например, если у вас есть 200 ГБ дополнительного места, а вам нужно только 100 ГБ, в поле следует ввести **100**.</span><span class="sxs-lookup"><span data-stu-id="79943-180">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="79943-181">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="79943-181">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="79943-182">В Центре администрирования перейдите на страницу **Выставление счетов** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Подписки</a>.</span><span class="sxs-lookup"><span data-stu-id="79943-182">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="79943-183">На странице **подписки** выберите **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="79943-183">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="79943-185">Если вы не видите **надстройки**, а ваша подписка была приобретена в партнере, выберите **центр обслуживания корпоративного лицензирования (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="79943-185">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="79943-186">В разделе **Office 365 дополнительное хранилище файлов**выберите **изменить количество**.</span><span class="sxs-lookup"><span data-stu-id="79943-186">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Ссылка "Изменить количество".](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="79943-188">В правой области введите общее количество гигабайтов, которое вам нужно, а затем нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="79943-188">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="79943-189">Например, если у вас есть 200 ГБ дополнительного места, а вам нужно только 100 ГБ, в поле следует ввести **100**.</span><span class="sxs-lookup"><span data-stu-id="79943-189">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="79943-190">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="79943-190">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="79943-191">Доступна ли в моем плане надстройка "Office 365 с дополнительным хранилищем"?</span><span class="sxs-lookup"><span data-stu-id="79943-191">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="79943-192">Надстройка "Office 365 с дополнительным хранилищем" доступна для таких подписок:</span><span class="sxs-lookup"><span data-stu-id="79943-192">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="79943-193">Office 365 для предприятий E1</span><span class="sxs-lookup"><span data-stu-id="79943-193">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="79943-194">Office 365 для предприятий E2</span><span class="sxs-lookup"><span data-stu-id="79943-194">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="79943-195">Office 365 для предприятий E3</span><span class="sxs-lookup"><span data-stu-id="79943-195">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="79943-196">Office 365 корпоративный E4</span><span class="sxs-lookup"><span data-stu-id="79943-196">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="79943-197">Office 365 корпоративный E5</span><span class="sxs-lookup"><span data-stu-id="79943-197">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="79943-198">Office для Интернета с SharePoint (план 1)</span><span class="sxs-lookup"><span data-stu-id="79943-198">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="79943-199">Office для Интернета с SharePoint (план 2)</span><span class="sxs-lookup"><span data-stu-id="79943-199">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="79943-200">SharePoint Online (план 1)</span><span class="sxs-lookup"><span data-stu-id="79943-200">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="79943-201">SharePoint Online (план 2)</span><span class="sxs-lookup"><span data-stu-id="79943-201">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="79943-202">Microsoft 365 бизнес базовый</span><span class="sxs-lookup"><span data-stu-id="79943-202">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="79943-203">Microsoft 365 бизнес стандарт</span><span class="sxs-lookup"><span data-stu-id="79943-203">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="79943-204">Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="79943-204">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="79943-205">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="79943-205">Microsoft 365 E3</span></span>

- <span data-ttu-id="79943-206">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="79943-206">Microsoft 365 E5</span></span>

- <span data-ttu-id="79943-207">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="79943-207">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="79943-208">Office 365 дополнительное хранилище файлов также доступно для планов GCC, GCC High и DOD.</span><span class="sxs-lookup"><span data-stu-id="79943-208">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>
