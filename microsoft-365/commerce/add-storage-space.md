---
title: Добавление дискового пространства для подписки
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
description: Сведения о добавлении и уменьшении размера файлов в вашей подписке на Microsoft 365. С помощью дополнительного хранилища файлов вы можете хранить дополнительные материалы в SharePoint Online и OneDrive.
ms.date: ''
ms.openlocfilehash: 7f9973054bfe97beae36e28b73a3eb2025a13e73
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324472"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="84e3e-104">Добавление дискового пространства для подписки</span><span class="sxs-lookup"><span data-stu-id="84e3e-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="84e3e-105">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="84e3e-105">The admin center is changing.</span></span> <span data-ttu-id="84e3e-106">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="84e3e-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="84e3e-107">Если у вас заканчивается нехватка хранилища для ваших семейств сайтов SharePoint Online, вы можете добавить хранилище к своей подписке, если ваш план соответствует критериям.</span><span class="sxs-lookup"><span data-stu-id="84e3e-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="84e3e-108">Если вы не видите **дополнительное хранилище файлов Office 365** в списке доступных надстроек, это означает, что ваш план не подходит.</span><span class="sxs-lookup"><span data-stu-id="84e3e-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="84e3e-109">Чтобы получить дополнительные сведения, ознакомьтесь с [различной схемой.](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="84e3e-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="84e3e-110">Если вы приобрели подписку по программе корпоративного лицензирования или поставщику служб шифрования, вы не сможете приобрести **дополнительное хранилище файлов Office 365** для вашей организации непосредственно у корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="84e3e-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="84e3e-111">Обратитесь за помощью к своему представителю или партнеру.</span><span class="sxs-lookup"><span data-stu-id="84e3e-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="84e3e-112">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="84e3e-112">Before you begin</span></span>

<span data-ttu-id="84e3e-113">Для выполнения задач, описанных в этой статье, необходимо быть глобальным администратором или администратором SharePoint.</span><span class="sxs-lookup"><span data-stu-id="84e3e-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="84e3e-114">Дополнительные сведения см. в статье [О ролях администраторов](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="84e3e-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="84e3e-115">Просмотр доступного хранилища</span><span class="sxs-lookup"><span data-stu-id="84e3e-115">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="84e3e-116">В центре администрирования SharePoint перейдите на страницу <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">активные сайты</a> и войдите с помощью учетной записи, имеющей [разрешения администратора](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="84e3e-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="84e3e-117">В правом верхнем углу страницы отображается объем хранилища, используемого для всех сайтов, и общий объем хранилища для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="84e3e-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="84e3e-118">Если в вашей организации настроена поддержка нескольких регионов в Office 365, на панели также показывается объем хранилища, используемого для всех географических расположений.</span><span class="sxs-lookup"><span data-stu-id="84e3e-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Панель хранения на странице активных сайтов](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="84e3e-120">Используемое хранилище не включает изменения, внесенные в течение последних 24-48 часов.</span><span class="sxs-lookup"><span data-stu-id="84e3e-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="84e3e-121">Войдите в https://portal.office.de систему как глобальный администратор или администратор SharePoint, а затем выберите плитку администратор, чтобы открыть центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="84e3e-121">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="84e3e-122">Если вы видите сообщение о том, что у вас нет разрешения на доступ к странице, это означает, что у вас нет прав администратора Microsoft 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="84e3e-122">If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="84e3e-123">В панели слева в разделе **Центры администрирования** выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="84e3e-124">Если откроется классическая версия Центра администрирования SharePoint, нажмите кнопку **Открыть** в верхней части страницы, чтобы открыть новый Центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="84e3e-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="84e3e-125">На левой панели нового Центра администрирования SharePoint выберите пункт **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="84e3e-126">В правом верхнем углу страницы отображается объем хранилища, используемого для всех сайтов, и общий объем хранилища для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="84e3e-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

   ![Панель хранения на странице активных сайтов](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="84e3e-128">Используемое хранилище не включает изменения, внесенные в течение последних 24-48 часов.</span><span class="sxs-lookup"><span data-stu-id="84e3e-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="84e3e-129">Войдите в https://login.partner.microsoftonline.cn/ систему как глобальный администратор или администратор SharePoint, а затем выберите плитку администратор, чтобы открыть центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="84e3e-129">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="84e3e-130">(Если отображается сообщение о том, что у вас нет разрешения на доступ к странице, это означает, что у вас нет прав администратора Microsoft 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="84e3e-130">(If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="84e3e-131">В панели слева в разделе **Центры администрирования** выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-131">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="84e3e-132">Если откроется классическая версия Центра администрирования SharePoint, нажмите кнопку **Открыть** в верхней части страницы, чтобы открыть новый Центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="84e3e-132">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="84e3e-133">На левой панели нового Центра администрирования SharePoint выберите пункт **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-133">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="84e3e-134">В правом верхнем углу страницы отображается объем хранилища, используемого для всех сайтов, и общий объем хранилища для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="84e3e-134">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

   ![Панель хранения на странице активных сайтов](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="84e3e-136">Используемое хранилище не включает изменения, внесенные в течение последних 24-48 часов.</span><span class="sxs-lookup"><span data-stu-id="84e3e-136">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

<span data-ttu-id="84e3e-137">Определив объем используемого хранилища, вы можете добавить или удалить дисковое пространство для своей подписки.</span><span class="sxs-lookup"><span data-stu-id="84e3e-137">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="84e3e-138">Чтобы узнать, сколько затрат будет стоить при добавлении дискового пространства, выполните действия, описанные в этой статье, и ознакомьтесь со сведениями о ценах перед покупкой.</span><span class="sxs-lookup"><span data-stu-id="84e3e-138">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="84e3e-139">Сведения о том, как задать пределы хранения для семейства веб-сайтов, можно найти в разделе [Manage site Limit Storage Limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span><span class="sxs-lookup"><span data-stu-id="84e3e-139">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="84e3e-140">Добавление хранилища к подписке</span><span class="sxs-lookup"><span data-stu-id="84e3e-140">Add storage to your subscription</span></span>

<span data-ttu-id="84e3e-141">Если вы еще не приобрели дополнительное хранилище для своей подписки, это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="84e3e-141">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="84e3e-142">В центре администрирования перейдите на страницу Услуги по **выставлению счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">покупки</a> .</span><span class="sxs-lookup"><span data-stu-id="84e3e-142">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="84e3e-143">В нижней части страницы **услуги покупки** выберите **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>
3. <span data-ttu-id="84e3e-144">Выберите **Office 365 Extra Storage File**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-144">Select **Office 365 Extra File Storage**.</span></span>
4. <span data-ttu-id="84e3e-145">На странице **Office 365 Extra Storage File** , если она отображается, выберите базовую подписку, а затем введите количество гигабайтов хранилища, которое вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="84e3e-145">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="84e3e-146">Нажмите **кнопку извлечь.**</span><span class="sxs-lookup"><span data-stu-id="84e3e-146">Select **Check out now**.</span></span>
6. <span data-ttu-id="84e3e-147">На странице **как это выглядит?** проверьте выбранное количество гигабайтов хранилища, просмотрите сведения о ценах, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="84e3e-148">На странице **полный заказ** проверьте итоговое значение.</span><span class="sxs-lookup"><span data-stu-id="84e3e-148">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="84e3e-149">Если требуется внести изменения, выберите пункт **изменить заказ**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-149">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="84e3e-150">Если для заказа требуется проверка кредита, установите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="84e3e-150">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="84e3e-151">Когда все будет готово, нажмите кнопку **поместить заказ** \> **перейдите на домашнюю страницу администратора**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-151">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="84e3e-152">В центре администрирования перейдите на страницу подписки на **выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> .  </span><span class="sxs-lookup"><span data-stu-id="84e3e-152">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="84e3e-153">На странице " **подписки** " выберите подписку, в которую вы хотите добавить дисковое пространство, а затем выберите **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="84e3e-155">Если вы не видите **надстройки**, а ваша подписка была приобретена в партнере, выберите **центр обслуживания корпоративного лицензирования (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="84e3e-156">Выберите **купить надстройки**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-156">Select **Buy add-ons**.</span></span>

    !["Приобрести надстройки" на странице "подписки" центра администрирования.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="84e3e-158">На странице **приобретение служб** наведите указатель мыши на **дополнительное хранилище файлов Office 365**или нажмите кнопку **купить**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="84e3e-159">Введите необходимое количество пользовательских лицензий и, если это отображается, выберите базовую подписку.</span><span class="sxs-lookup"><span data-stu-id="84e3e-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="84e3e-160">Нажмите **кнопку извлечь.**</span><span class="sxs-lookup"><span data-stu-id="84e3e-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="84e3e-161">На странице **как это выглядит?** проверьте выбранное количество гигабайтов хранилища, просмотрите сведения о ценах, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="84e3e-162">На странице **полный заказ** выберите пункт **разместить заказ**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="84e3e-163">В Центре администрирования перейдите на страницу **Выставление счетов** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Подписки</a>.</span><span class="sxs-lookup"><span data-stu-id="84e3e-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="84e3e-164">На странице " **подписки** " выберите подписку, в которую вы хотите добавить дисковое пространство, а затем выберите **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-164">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="84e3e-166">Если вы не видите **надстройки**, а ваша подписка была приобретена в партнере, выберите **центр обслуживания корпоративного лицензирования (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-166">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="84e3e-167">Выберите **купить надстройки**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-167">Select **Buy add-ons**.</span></span>

    !["Приобрести надстройки" на странице "подписки" центра администрирования.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="84e3e-169">На странице **приобретение служб** наведите указатель мыши на **дополнительное хранилище файлов Office 365**или нажмите кнопку **купить**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="84e3e-170">Введите необходимое количество пользовательских лицензий и, если это отображается, выберите базовую подписку.</span><span class="sxs-lookup"><span data-stu-id="84e3e-170">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="84e3e-171">Нажмите **кнопку извлечь.**</span><span class="sxs-lookup"><span data-stu-id="84e3e-171">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="84e3e-172">На странице **как это выглядит?** проверьте выбранное количество гигабайтов хранилища, просмотрите сведения о ценах, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="84e3e-173">На странице **полный заказ** выберите пункт **разместить заказ**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-173">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="84e3e-174">Увеличение или уменьшение хранилища</span><span class="sxs-lookup"><span data-stu-id="84e3e-174">Increase or decrease storage</span></span>

<span data-ttu-id="84e3e-175">Если вы уже приобрели дополнительное хранилище файлов с помощью надстройки **Office 365 Extra Storage** , вы можете использовать эти действия, чтобы увеличить или уменьшить дополнительное место для подписки.</span><span class="sxs-lookup"><span data-stu-id="84e3e-175">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="84e3e-176">Вы можете уменьшить объем дискового пространства, как минимум 1 ГБ.</span><span class="sxs-lookup"><span data-stu-id="84e3e-176">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="84e3e-177">Чтобы удалить все лишнее дисковое пространство, [обратитесь в службу поддержки](../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="84e3e-177">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="84e3e-178">В Центре администрирования перейдите на страницу **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.</span><span class="sxs-lookup"><span data-stu-id="84e3e-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="84e3e-179">На вкладке **продукты** выберите подписку, содержащую надстройку **Office 365 Extra Storage** .</span><span class="sxs-lookup"><span data-stu-id="84e3e-179">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="84e3e-180">На странице "сведения о продукте" в разделе **надстройки** выберите пункт **Управление надстройками**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-180">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="84e3e-181">В области **Управление** надстройками выберите в списке **надстройка** **Office 365 дополнительное хранилище файлов**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-181">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="84e3e-182">В текстовом поле **количество** введите количество ГБ дискового пространства, которое требуется для подписки.</span><span class="sxs-lookup"><span data-stu-id="84e3e-182">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="84e3e-183">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-183">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="84e3e-184">В Центре администрирования перейдите на страницу **Выставление счетов** \><a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Подписки</a>.</span><span class="sxs-lookup"><span data-stu-id="84e3e-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="84e3e-185">На странице **подписки** выберите **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-185">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="84e3e-187">Если вы не видите **надстройки**, а ваша подписка была приобретена в партнере, выберите **центр обслуживания корпоративного лицензирования (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-187">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="84e3e-188">В разделе **Office 365 дополнительное хранилище файлов**выберите **изменить количество**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-188">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Ссылка "Изменить количество".](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="84e3e-190">В правой области введите общее количество гигабайтов, которое вам нужно, а затем нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-190">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="84e3e-191">Например, если у вас есть 200 ГБ дополнительного места, а вам нужно только 100 ГБ, в поле следует ввести **100**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-191">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="84e3e-192">Нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-192">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="84e3e-193">В Центре администрирования перейдите на страницу **Выставление счетов** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Подписки</a>.</span><span class="sxs-lookup"><span data-stu-id="84e3e-193">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="84e3e-194">На странице **подписки** выберите **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-194">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="84e3e-196">Если вы не видите **надстройки**, а ваша подписка была приобретена в партнере, выберите **центр обслуживания корпоративного лицензирования (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-196">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="84e3e-197">В разделе **Office 365 дополнительное хранилище файлов**выберите **изменить количество**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-197">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Ссылка "Изменить количество".](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="84e3e-199">В правой области введите общее количество гигабайтов, которое вам нужно, а затем нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-199">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="84e3e-200">Например, если у вас есть 200 ГБ дополнительного места, а вам нужно только 100 ГБ, в поле следует ввести **100**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-200">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="84e3e-201">Нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-201">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="84e3e-202">Доступна ли в моем плане надстройка "Office 365 с дополнительным хранилищем"?</span><span class="sxs-lookup"><span data-stu-id="84e3e-202">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="84e3e-203">Надстройка "Office 365 с дополнительным хранилищем" доступна для таких подписок:</span><span class="sxs-lookup"><span data-stu-id="84e3e-203">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="84e3e-204">Office 365 для предприятий E1</span><span class="sxs-lookup"><span data-stu-id="84e3e-204">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="84e3e-205">Office 365 для предприятий E2</span><span class="sxs-lookup"><span data-stu-id="84e3e-205">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="84e3e-206">Office 365 для предприятий E3</span><span class="sxs-lookup"><span data-stu-id="84e3e-206">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="84e3e-207">Office 365 корпоративный E4</span><span class="sxs-lookup"><span data-stu-id="84e3e-207">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="84e3e-208">Office 365 корпоративный E5</span><span class="sxs-lookup"><span data-stu-id="84e3e-208">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="84e3e-209">Office для Интернета с SharePoint (план 1)</span><span class="sxs-lookup"><span data-stu-id="84e3e-209">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="84e3e-210">Office для Интернета с SharePoint (план 2)</span><span class="sxs-lookup"><span data-stu-id="84e3e-210">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="84e3e-211">SharePoint Online (план 1)</span><span class="sxs-lookup"><span data-stu-id="84e3e-211">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="84e3e-212">SharePoint Online (план 2)</span><span class="sxs-lookup"><span data-stu-id="84e3e-212">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="84e3e-213">Microsoft 365 бизнес базовый</span><span class="sxs-lookup"><span data-stu-id="84e3e-213">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="84e3e-214">Microsoft 365 бизнес стандарт</span><span class="sxs-lookup"><span data-stu-id="84e3e-214">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="84e3e-215">Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="84e3e-215">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="84e3e-216">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="84e3e-216">Microsoft 365 E3</span></span>

- <span data-ttu-id="84e3e-217">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="84e3e-217">Microsoft 365 E5</span></span>

- <span data-ttu-id="84e3e-218">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="84e3e-218">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="84e3e-219">Office 365 дополнительное хранилище файлов также доступно для планов GCC, GCC High и DOD.</span><span class="sxs-lookup"><span data-stu-id="84e3e-219">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="84e3e-220">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="84e3e-220">Related content</span></span>

<span data-ttu-id="84e3e-221">[Управление пределами хранилища сайта](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (статья) </span><span class="sxs-lookup"><span data-stu-id="84e3e-221">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="84e3e-222">[Задание пространства для хранения по умолчанию для пользователей OneDrive](https://docs.microsoft.com/onedrive/set-default-storage-space)(статья)</span><span class="sxs-lookup"><span data-stu-id="84e3e-222">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>
