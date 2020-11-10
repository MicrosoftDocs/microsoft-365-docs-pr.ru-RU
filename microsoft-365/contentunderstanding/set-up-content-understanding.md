---
title: Настройка SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: MET150
localization_priority: Priority
description: Настройка понимания содержимого в Project Cortex
ms.openlocfilehash: 8f1ebd70f932bce874efc19f525b549f6717f532
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988688"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="d3572-103">Настройка SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="d3572-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="d3572-104">Администраторы могут использовать Центр администрирования Microsoft 365 для настройки [Microsoft SharePoint Syntex](index.md).</span><span class="sxs-lookup"><span data-stu-id="d3572-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="d3572-105">Прежде чем начать, примите во внимание следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="d3572-105">Consider the following before you start:</span></span>

- <span data-ttu-id="d3572-106">На каких сайтах SharePoint будет включена обработка форм?</span><span class="sxs-lookup"><span data-stu-id="d3572-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="d3572-107">На всех, некоторых из них или выбранных сайтах?</span><span class="sxs-lookup"><span data-stu-id="d3572-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="d3572-108">Как вы назовете свой центр содержимого по умолчанию?</span><span class="sxs-lookup"><span data-stu-id="d3572-108">What will you name of your default content center?</span></span>

<span data-ttu-id="d3572-109">Вы можете изменить параметры после начальной настройки в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d3572-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="d3572-110">Перед установкой убедитесь, что вы спланировали наилучший способ настройки понимания содержимого в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="d3572-110">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="d3572-111">Например, вам необходимо принять во внимание следующие названия:</span><span class="sxs-lookup"><span data-stu-id="d3572-111">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="d3572-112">Сайтов SharePoint, на которых вы хотите включить обработку форм — всех из них, некоторых или выбранных сайтах</span><span class="sxs-lookup"><span data-stu-id="d3572-112">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="d3572-113">Центра содержимого и имени главного администратора сайта</span><span class="sxs-lookup"><span data-stu-id="d3572-113">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="d3572-114">Требования</span><span class="sxs-lookup"><span data-stu-id="d3572-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="d3572-115">У вас должны быть разрешения глобального администратора или администратора SharePoint, чтобы получить доступ к Центру администрирования Microsoft 365 и настраивать понимание содержимого.</span><span class="sxs-lookup"><span data-stu-id="d3572-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="d3572-116">Как администратор, вы также можете вносить изменения в выбранные параметры в любое время после завершения их настройки, а также во все параметры управления содержимым в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d3572-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="d3572-117">Чтобы настроить SharePoint Syntex, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d3572-117">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="d3572-118">В Центре администрирования Microsoft 365 выберите **Настройка** , затем просмотрите раздел **Файлы и содержимое**.</span><span class="sxs-lookup"><span data-stu-id="d3572-118">In the Microsoft 365 admin center, select **Setup** , and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="d3572-119">В разделе **Файлы и содержимое** выберите **Автоматизировать понимание содержимого**.</span><span class="sxs-lookup"><span data-stu-id="d3572-119">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="d3572-120">На странице **Автоматизировать понимание содержимого** , нажмите **Начать** , чтобы начать процесс настройки.</span><span class="sxs-lookup"><span data-stu-id="d3572-120">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d3572-121">![Начало настройки](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="d3572-121">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="d3572-122">На странице **Настройка обработки форм** можно выбрать, хотите ли вы, чтобы пользователи могли создавать модели обработки форм в определенных библиотеках документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d3572-122">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="d3572-123">На ленте библиотеки документов будет доступен параметр меню **Создать модель обработки форм** в библиотеках документов SharePoint, в которых он включен.</span><span class="sxs-lookup"><span data-stu-id="d3572-123">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="d3572-124">Для **каких библиотек SharePoint должен отображаться параметр создания модели обработки форм** , вы можете выбрать:</span><span class="sxs-lookup"><span data-stu-id="d3572-124">For **Which SharePoint libraries should show option to create a form processing model** , you can select:</span></span></br>
      - <span data-ttu-id="d3572-125">**Все библиотеки SharePoint** , чтобы сделать его доступным для всех библиотек SharePoint в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d3572-125">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="d3572-126">**Только библиотеки на выбранных сайтах** , а затем выберите сайты, в которых вы хотите сделать его доступным, или загрузите список, содержащий до 50 сайтов.</span><span class="sxs-lookup"><span data-stu-id="d3572-126">**Only libraries in selected sites** , and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="d3572-127">**Не в библиотеках SharePoint** , если вы не хотите, чтобы он был доступен для всех сайтов (после настройки вы можете изменить эту настройку).</span><span class="sxs-lookup"><span data-stu-id="d3572-127">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d3572-128">![Настройка обработки форм](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="d3572-128">![Configure form processing](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="d3572-129">Удаление сайта после его включения, не влияет на существующие модели, применяемые к библиотекам на этом сайте, или на возможность применять модели понимания документов к библиотеке.</span><span class="sxs-lookup"><span data-stu-id="d3572-129">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
5. <span data-ttu-id="d3572-130">На странице **Создание Центра содержимого** можно создать сайт Центра содержимого SharePoint, на котором пользователи смогут создавать и управлять моделями понимания документов.</span><span class="sxs-lookup"><span data-stu-id="d3572-130">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="d3572-131">В поле **Имя сайта** введите имя, которое вы хотите дать сайту Центра содержимого.</span><span class="sxs-lookup"><span data-stu-id="d3572-131">For **Site name** , type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="d3572-132">В **адресе сайта** будет отображаться URL-адрес вашего сайта в зависимости от выбранного имени сайта.</span><span class="sxs-lookup"><span data-stu-id="d3572-132">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="d3572-133">Если вы хотите его изменить, нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="d3572-133">If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="d3572-134">![Создание Центра содержимого](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="d3572-134">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="d3572-135">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d3572-135">Select **Next**.</span></span>

6. <span data-ttu-id="d3572-136">На странице **Проверка и завершение** можно просмотреть выбранный параметр и внести в него изменения.</span><span class="sxs-lookup"><span data-stu-id="d3572-136">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="d3572-137">Если выбор вас устраивает, нажмите кнопку **Активировать**.</span><span class="sxs-lookup"><span data-stu-id="d3572-137">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="d3572-138">На странице подтверждения нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d3572-138">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="d3572-139">Вы вернетесь к странице **Автоматизировать понимание содержимого**.</span><span class="sxs-lookup"><span data-stu-id="d3572-139">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="d3572-140">На этой странице можно выбрать **Управлять** , чтобы внести изменения в параметры настройки.</span><span class="sxs-lookup"><span data-stu-id="d3572-140">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="d3572-141">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="d3572-141">Assign licenses</span></span>

<span data-ttu-id="d3572-142">После настройки SharePoint Syntex необходимо назначить лицензии пользователям, которые будут использовать возможности SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="d3572-142">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="d3572-143">Чтобы назначить лицензии, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d3572-143">To assign licenses:</span></span>

1. <span data-ttu-id="d3572-144">В Центре администрирования Microsoft 365 в разделе **Пользователи** , щелкните **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="d3572-144">In the Microsoft 365 admin center, under **Users** , click **Active users**.</span></span>

2. <span data-ttu-id="d3572-145">Выберите пользователей, которых вы хотите лицензировать, и щелкните **Управление лицензиями продуктов**.</span><span class="sxs-lookup"><span data-stu-id="d3572-145">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="d3572-146">Выберите **Назначить еще**.</span><span class="sxs-lookup"><span data-stu-id="d3572-146">Select **Assign more**.</span></span>

4. <span data-ttu-id="d3572-147">Выберите **SharePoint Syntex**.</span><span class="sxs-lookup"><span data-stu-id="d3572-147">Select **SharePoint Syntex**.</span></span> <span data-ttu-id="d3572-148">В разделе **Приложения** , убедитесь, что выбраны **Common Data Service для SharePoint Syntex** , **SharePoint Syntex** , и **SharePoint Syntex - тип SPO**.</span><span class="sxs-lookup"><span data-stu-id="d3572-148">Under **Apps** , make sure **Common Data Service for SharePoint Syntex** , **SharePoint Syntex** , and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d3572-149">![Лицензии SharePoint Syntex в Центре администрирования Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="d3572-149">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="d3572-150">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="d3572-150">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="d3572-151">Титры AI Builder</span><span class="sxs-lookup"><span data-stu-id="d3572-151">AI Builder credits</span></span>

<span data-ttu-id="d3572-152">Если у вас есть 300 или более лицензий SharePoint Syntex в вашей организации, вам будет выделен миллион титров AI Builder.</span><span class="sxs-lookup"><span data-stu-id="d3572-152">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="d3572-153">Если у вас менее 300 лицензий, необходимо купить титры AI Builder, чтобы использовать обработку форм.</span><span class="sxs-lookup"><span data-stu-id="d3572-153">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="d3572-154">Вы можете оценить мощность AI Builder, которая подходит именно вам, с помощью [калькулятора AI Builder](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="d3572-154">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="d3572-155">Чтобы проверить титры и использование, перейдите в [Центр администрирования Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity).</span><span class="sxs-lookup"><span data-stu-id="d3572-155">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3572-156">См. также</span><span class="sxs-lookup"><span data-stu-id="d3572-156">See also</span></span>

[<span data-ttu-id="d3572-157">Обзор модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="d3572-157">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="d3572-158">Пошаговые инструкции: Создание модели понимания документа (видео)</span><span class="sxs-lookup"><span data-stu-id="d3572-158">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

