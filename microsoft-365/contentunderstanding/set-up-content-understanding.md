---
title: Настройка SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: Настройка понимания содержимого в Project Cortex
ms.openlocfilehash: a275b2ec14403e16651acb293f8598b453fd3739
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515020"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="15850-103">Настройка SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="15850-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="15850-104">Администраторы могут использовать Центр администрирования Microsoft 365 для настройки [Microsoft SharePoint Syntex](index.md).</span><span class="sxs-lookup"><span data-stu-id="15850-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="15850-105">Прежде чем начать, примите во внимание следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="15850-105">Consider the following before you start:</span></span>

- <span data-ttu-id="15850-106">На каких сайтах SharePoint будет включена обработка форм?</span><span class="sxs-lookup"><span data-stu-id="15850-106">In which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="15850-107">На всех, некоторых из них или выбранных сайтах?</span><span class="sxs-lookup"><span data-stu-id="15850-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="15850-108">Как вы назовете свой центр контента по умолчанию?</span><span class="sxs-lookup"><span data-stu-id="15850-108">What will you name your default content center?</span></span>

<span data-ttu-id="15850-109">Вы можете изменить параметры после начальной настройки в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15850-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="15850-110">Перед установкой убедитесь, что вы спланировали наилучший способ настройки понимания содержимого в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="15850-110">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="15850-111">Например, вам необходимо принять следующие решения.</span><span class="sxs-lookup"><span data-stu-id="15850-111">For example, you need to make the following decisions:</span></span>

- <span data-ttu-id="15850-112">Сайты SharePoint, на которых вы хотите включить обработку форм — все, некоторые или выбранные сайты</span><span class="sxs-lookup"><span data-stu-id="15850-112">The SharePoint sites in which you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="15850-113">Название вашего центра контента и его администраторы</span><span class="sxs-lookup"><span data-stu-id="15850-113">The name and admins for your content center</span></span>

## <a name="requirements"></a><span data-ttu-id="15850-114">Требования</span><span class="sxs-lookup"><span data-stu-id="15850-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="15850-115">У вас должны быть разрешения глобального администратора или администратора SharePoint, чтобы получить доступ к Центру администрирования Microsoft 365 и настроить SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="15850-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up SharePoint Syntex.</span></span>

<span data-ttu-id="15850-116">Как администратор, вы также можете вносить изменения в выбранные параметры в любое время после завершения их настройки, а также во все параметры управления содержимым в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15850-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

### <a name="licensing"></a><span data-ttu-id="15850-117">Лицензирование</span><span class="sxs-lookup"><span data-stu-id="15850-117">Licensing</span></span>

<span data-ttu-id="15850-118">Чтобы использовать SharePoint Syntex, у вашей организации должна быть подписка на SharePoint Syntex, а каждому пользователю должны быть назначены следующие лицензии:</span><span class="sxs-lookup"><span data-stu-id="15850-118">To use SharePoint Syntex, your organization must have a subscription to SharePoint Syntex, and each user must have the following licenses assigned:</span></span>

- <span data-ttu-id="15850-119">SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="15850-119">SharePoint Syntex</span></span>
- <span data-ttu-id="15850-120">SharePoint Syntex — тип SPO</span><span class="sxs-lookup"><span data-stu-id="15850-120">SharePoint Syntex - SPO type</span></span>
- <span data-ttu-id="15850-121">Общая служба данных для SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="15850-121">Common Data Service for SharePoint Syntex</span></span>

<span data-ttu-id="15850-122">Если вы отмените подписку на SharePoint Syntex в будущем (или истечет срок действия пробной подписки), пользователи не смогут создавать и запускать модели осмысления документации или обработки форм, а шаблон центра контента станет недоступным.</span><span class="sxs-lookup"><span data-stu-id="15850-122">If you cancel your SharePoint Syntex subscription at a future date (or your trial expires), users will no longer be able to create or run document understanding or form processing models, and the content center template will no longer be available.</span></span> <span data-ttu-id="15850-123">Кроме того, станут недоступны отчеты банка терминов, импорт таксономии SKOS и передача типа контента.</span><span class="sxs-lookup"><span data-stu-id="15850-123">Additionally, term store reports, SKOS taxonomy import, and Content type push will no longer be available.</span></span> <span data-ttu-id="15850-124">Содержимое не удаляются, а разрешения сайта не изменяются.</span><span class="sxs-lookup"><span data-stu-id="15850-124">No content will be deleted and site permissions will not be changed.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="15850-125">Чтобы настроить SharePoint Syntex, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="15850-125">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="15850-126">В Центре администрирования Microsoft 365 выберите **Настройка**, затем просмотрите раздел **Файлы и содержимое**.</span><span class="sxs-lookup"><span data-stu-id="15850-126">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="15850-127">В разделе **Файлы и содержимое** выберите **Автоматизировать понимание содержимого**.</span><span class="sxs-lookup"><span data-stu-id="15850-127">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="15850-128">На странице **Автоматизировать понимание содержимого**, нажмите **Начать** , чтобы начать процесс настройки.</span><span class="sxs-lookup"><span data-stu-id="15850-128">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="15850-129">![Начало настройки](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="15850-129">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="15850-130">На странице **Настройка обработки форм** можно выбрать, хотите ли вы, чтобы пользователи могли создавать модели обработки форм в определенных библиотеках документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="15850-130">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="15850-131">На ленте библиотеки документов будет доступен параметр меню **Создать модель обработки форм** в библиотеках документов SharePoint, в которых он включен.</span><span class="sxs-lookup"><span data-stu-id="15850-131">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="15850-132">Для **каких библиотек SharePoint должен отображаться параметр создания модели обработки форм**, вы можете выбрать:</span><span class="sxs-lookup"><span data-stu-id="15850-132">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="15850-133">**Библиотеки на всех сайтах SharePoint**, чтобы сделать его доступным для всех библиотек SharePoint в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="15850-133">**Libraries in all SharePoint sites** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="15850-134">**Библиотеки на выбранных сайтах SharePoint**, а затем выберите сайты, в которых вы хотите сделать его доступным, или отправьте список, содержащий до 50 сайтов.</span><span class="sxs-lookup"><span data-stu-id="15850-134">**Libraries in selected SharePoint sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="15850-135">**Не в библиотеках SharePoint**, если вы не хотите, чтобы он был доступен для всех сайтов (после настройки вы можете изменить эту настройку).</span><span class="sxs-lookup"><span data-stu-id="15850-135">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="15850-136">![Настройка обработки форм](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="15850-136">![Configure form processing](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="15850-137">Удаление сайта после его включения, не влияет на существующие модели, применяемые к библиотекам на этом сайте, или на возможность применять модели понимания документов к библиотеке.</span><span class="sxs-lookup"><span data-stu-id="15850-137">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
5. <span data-ttu-id="15850-138">На странице **Создание Центра содержимого** можно создать сайт Центра содержимого SharePoint, на котором пользователи смогут создавать и управлять моделями понимания документов.</span><span class="sxs-lookup"><span data-stu-id="15850-138">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="15850-139">В поле **Имя сайта** введите имя, которое вы хотите дать сайту Центра содержимого.</span><span class="sxs-lookup"><span data-stu-id="15850-139">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="15850-140">В **адресе сайта** будет отображаться URL-адрес вашего сайта в зависимости от выбранного имени сайта.</span><span class="sxs-lookup"><span data-stu-id="15850-140">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="15850-141">Если вы хотите его изменить, нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="15850-141">If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="15850-142">![Создание Центра содержимого](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="15850-142">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="15850-143">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15850-143">Select **Next**.</span></span>

6. <span data-ttu-id="15850-144">На странице **Проверка и завершение** можно просмотреть выбранный параметр и внести в него изменения.</span><span class="sxs-lookup"><span data-stu-id="15850-144">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="15850-145">Если выбор вас устраивает, нажмите кнопку **Активировать**.</span><span class="sxs-lookup"><span data-stu-id="15850-145">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="15850-146">На странице подтверждения нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="15850-146">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="15850-147">Вы вернетесь к странице **Автоматизировать понимание содержимого**.</span><span class="sxs-lookup"><span data-stu-id="15850-147">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="15850-148">На этой странице можно выбрать **Управлять**, чтобы внести изменения в параметры настройки.</span><span class="sxs-lookup"><span data-stu-id="15850-148">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="15850-149">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="15850-149">Assign licenses</span></span>

<span data-ttu-id="15850-150">После настройки SharePoint Syntex необходимо назначить лицензии пользователям, которые будут использовать возможности SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="15850-150">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="15850-151">Чтобы назначить лицензии, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="15850-151">To assign licenses:</span></span>

1. <span data-ttu-id="15850-152">В Центре администрирования Microsoft 365 в разделе **Пользователи**, щелкните **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="15850-152">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="15850-153">Выберите пользователей, которым вы хотите назначить лицензии, и нажмите **Управление лицензиями продуктов**.</span><span class="sxs-lookup"><span data-stu-id="15850-153">Select the users that you want to license, and choose **Manage product licenses**.</span></span>

3. <span data-ttu-id="15850-154">Выберите **Приложения** в раскрывающемся меню.</span><span class="sxs-lookup"><span data-stu-id="15850-154">Choose **Apps** from the drop-down menu.</span></span>

4. <span data-ttu-id="15850-155">Выберите **Показать приложения для SharePoint Syntex**.</span><span class="sxs-lookup"><span data-stu-id="15850-155">Select **Show apps for  SharePoint Syntex**.</span></span> <span data-ttu-id="15850-156">В разделе **Приложения**, убедитесь, что выбраны **Common Data Service для SharePoint Syntex**, **SharePoint Syntex**, и **SharePoint Syntex - тип SPO**.</span><span class="sxs-lookup"><span data-stu-id="15850-156">Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="15850-157">![Лицензии SharePoint Syntex в Центре администрирования Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="15850-157">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="15850-158">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="15850-158">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="15850-159">Титры AI Builder</span><span class="sxs-lookup"><span data-stu-id="15850-159">AI Builder credits</span></span>

<span data-ttu-id="15850-160">Если у вас есть 300 или более лицензий SharePoint Syntex в вашей организации, вам будет выделен миллион титров AI Builder.</span><span class="sxs-lookup"><span data-stu-id="15850-160">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="15850-161">Если у вас менее 300 лицензий, необходимо купить титры AI Builder, чтобы использовать обработку форм.</span><span class="sxs-lookup"><span data-stu-id="15850-161">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="15850-162">Вы можете оценить мощность AI Builder, которая подходит именно вам, с помощью [калькулятора AI Builder](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="15850-162">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="15850-163">Чтобы проверить титры и использование, перейдите в [Центр администрирования Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity).</span><span class="sxs-lookup"><span data-stu-id="15850-163">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="15850-164">См. также</span><span class="sxs-lookup"><span data-stu-id="15850-164">See also</span></span>

[<span data-ttu-id="15850-165">Обзор модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="15850-165">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="15850-166">Пошаговые инструкции: Создание модели понимания документа (видео)</span><span class="sxs-lookup"><span data-stu-id="15850-166">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)
