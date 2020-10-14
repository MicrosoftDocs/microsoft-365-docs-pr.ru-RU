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
ms.openlocfilehash: 43ce7809237d32fb9d2da73e9e00bed9b9a8193e
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464066"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="5c914-103">Настройка SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="5c914-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="5c914-104">Администраторы могут использовать Центр администрирования Microsoft 365 для настройки [Microsoft SharePoint Syntex](index.md).</span><span class="sxs-lookup"><span data-stu-id="5c914-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="5c914-105">Прежде чем начать, примите во внимание следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="5c914-105">Consider the following before you start:</span></span>

- <span data-ttu-id="5c914-106">На каких сайтах SharePoint будет включена обработка форм?</span><span class="sxs-lookup"><span data-stu-id="5c914-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="5c914-107">На всех, некоторых из них или выбранных сайтах?</span><span class="sxs-lookup"><span data-stu-id="5c914-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="5c914-108">Как вы назовете свой центр содержимого по умолчанию?</span><span class="sxs-lookup"><span data-stu-id="5c914-108">What will you name of your default content center?</span></span>

<span data-ttu-id="5c914-109">Вы можете изменить параметры после начальной настройки в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5c914-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="5c914-110">Перед установкой убедитесь, что вы спланировали наилучший способ настройки понимания содержимого в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="5c914-110">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="5c914-111">Например, вам необходимо принять во внимание следующие названия:</span><span class="sxs-lookup"><span data-stu-id="5c914-111">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="5c914-112">Сайтов SharePoint, на которых вы хотите включить обработку форм — всех из них, некоторых или выбранных сайтах</span><span class="sxs-lookup"><span data-stu-id="5c914-112">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="5c914-113">Центра содержимого и имени главного администратора сайта</span><span class="sxs-lookup"><span data-stu-id="5c914-113">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="5c914-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5c914-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="5c914-115">У вас должны быть разрешения глобального администратора или администратора SharePoint, чтобы получить доступ к Центру администрирования Microsoft 365 и настраивать понимание содержимого.</span><span class="sxs-lookup"><span data-stu-id="5c914-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="5c914-116">Как администратор, вы также можете вносить изменения в выбранные параметры в любое время после завершения их настройки, а также во все параметры управления содержимым в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5c914-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="5c914-117">Чтобы настроить SharePoint Syntex, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5c914-117">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="5c914-118">В Центре администрирования Microsoft 365 выберите **Настройка**, а затем просмотрите раздел **Знания организации**.</span><span class="sxs-lookup"><span data-stu-id="5c914-118">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>

2. <span data-ttu-id="5c914-119">В разделе **Файлы и содержимое** выберите **Автоматизировать понимание содержимого**.</span><span class="sxs-lookup"><span data-stu-id="5c914-119">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="5c914-120">На странице **Автоматизировать понимание содержимого**, нажмите **Начать** , чтобы начать процесс настройки.</span><span class="sxs-lookup"><span data-stu-id="5c914-120">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![Начать настройку](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="5c914-122">На странице **Настройка обработки форм** можно выбрать, хотите ли вы, чтобы пользователи могли создавать модели обработки форм в определенных библиотеках документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5c914-122">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="5c914-123">На ленте библиотеки документов будет доступен параметр меню **Создать модель обработки форм** в библиотеках документов SharePoint, в которых он включен.</span><span class="sxs-lookup"><span data-stu-id="5c914-123">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="5c914-124">Для **каких библиотек SharePoint должен отображаться параметр создания модели обработки форм**, вы можете выбрать:</span><span class="sxs-lookup"><span data-stu-id="5c914-124">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="5c914-125">**Все библиотеки SharePoint**, чтобы сделать его доступным для всех библиотек SharePoint в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5c914-125">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="5c914-126">**Только библиотеки на выбранных сайтах**, а затем выберите сайты, в которых вы хотите сделать его доступным, или загрузите список, содержащий до 50 сайтов.</span><span class="sxs-lookup"><span data-stu-id="5c914-126">**Only libraries in selected sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="5c914-127">**Не в библиотеках SharePoint**, если вы не хотите, чтобы он был доступен для всех сайтов (после настройки вы можете изменить эту настройку).</span><span class="sxs-lookup"><span data-stu-id="5c914-127">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   ![Настройка обработки форм](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="5c914-129">Удаление сайта после его включения, не влияет на существующие модели, применяемые к библиотекам на этом сайте, или на возможность применять модели понимания документов к библиотеке.</span><span class="sxs-lookup"><span data-stu-id="5c914-129">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
5. <span data-ttu-id="5c914-p104">На странице **Создание Центра содержимого** можно создать сайт Центра содержимого SharePoint, на котором пользователи смогут создавать и управлять моделями понимания документов. </span><span class="sxs-lookup"><span data-stu-id="5c914-p104">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models. </span></span></br>
    <span data-ttu-id="5c914-131">а.</span><span class="sxs-lookup"><span data-stu-id="5c914-131">a.</span></span> <span data-ttu-id="5c914-132">В поле **Имя сайта** введите имя, которое вы хотите дать сайту Центра содержимого.</span><span class="sxs-lookup"><span data-stu-id="5c914-132">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="5c914-133">б.</span><span class="sxs-lookup"><span data-stu-id="5c914-133">b.</span></span> <span data-ttu-id="5c914-134">В **адресе сайта** будет отображаться URL-адрес вашего сайта в зависимости от выбранного имени сайта.</span><span class="sxs-lookup"><span data-stu-id="5c914-134">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="5c914-135">Если вы хотите его изменить, нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5c914-135">If you want to change it, click **Edit**.</span></span></br>

      ![Создание Центра содержимого](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="5c914-137">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5c914-137">Select **Next**.</span></span>

6. <span data-ttu-id="5c914-138">На странице **Проверка и завершение** можно просмотреть выбранный параметр и внести в него изменения.</span><span class="sxs-lookup"><span data-stu-id="5c914-138">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="5c914-139">Если выбор вас устраивает, нажмите кнопку **Активировать**.</span><span class="sxs-lookup"><span data-stu-id="5c914-139">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="5c914-140">На странице подтверждения нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5c914-140">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="5c914-141">Вы вернетесь к странице **Автоматизировать понимание содержимого**.</span><span class="sxs-lookup"><span data-stu-id="5c914-141">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="5c914-142">На этой странице можно выбрать **Управлять**, чтобы внести изменения в параметры настройки.</span><span class="sxs-lookup"><span data-stu-id="5c914-142">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="5c914-143">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="5c914-143">Assign licenses</span></span>

<span data-ttu-id="5c914-144">После настройки SharePoint Syntex необходимо назначить лицензии пользователям, которые будут использовать возможности SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="5c914-144">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="5c914-145">Чтобы назначить лицензии, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5c914-145">To assign licenses:</span></span>

1. <span data-ttu-id="5c914-146">В Центре администрирования Microsoft 365 в разделе **Пользователи**, щелкните **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="5c914-146">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="5c914-147">Выберите пользователей, которых вы хотите лицензировать, и щелкните **Управление лицензиями продуктов**.</span><span class="sxs-lookup"><span data-stu-id="5c914-147">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="5c914-148">Щелкните **Назначить еще**.</span><span class="sxs-lookup"><span data-stu-id="5c914-148">Select **Assign more**.</span></span>

4. <span data-ttu-id="5c914-149">Выберите **Интеллектуальные службы содержимого**.</span><span class="sxs-lookup"><span data-stu-id="5c914-149">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="5c914-150">Убедитесь в том, что в разделе **Приложения** выбраны параметры **Common Data Service для интеллектуальных служб содержимого** и **Интеллектуальные службы содержимого**.</span><span class="sxs-lookup"><span data-stu-id="5c914-150">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![Лицензии SharePoint Syntex в Центре администрирования Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="5c914-152">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="5c914-152">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="5c914-153">Титры AI Builder</span><span class="sxs-lookup"><span data-stu-id="5c914-153">AI Builder credits</span></span>

<span data-ttu-id="5c914-154">Если у вас есть 300 или более лицензий SharePoint Syntex в вашей организации, вам будет выделен миллион титров AI Builder.</span><span class="sxs-lookup"><span data-stu-id="5c914-154">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="5c914-155">Если у вас менее 300 лицензий, необходимо купить титры AI Builder, чтобы использовать обработку форм.</span><span class="sxs-lookup"><span data-stu-id="5c914-155">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="5c914-156">Вы можете оценить мощность AI Builder, которая подходит именно вам, с помощью [калькулятора AI Builder](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="5c914-156">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="5c914-157">Чтобы проверить титры и использование, перейдите в [Центр администрирования Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity).</span><span class="sxs-lookup"><span data-stu-id="5c914-157">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c914-158">См. также</span><span class="sxs-lookup"><span data-stu-id="5c914-158">See also</span></span>

[<span data-ttu-id="5c914-159">Обзор модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="5c914-159">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="5c914-160">Пошаговые инструкции: Создание модели понимания документа (видео)</span><span class="sxs-lookup"><span data-stu-id="5c914-160">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

