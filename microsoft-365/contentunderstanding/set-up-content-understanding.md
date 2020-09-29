---
title: Настройка SharePoint Синтекс
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Настройка контента в Project Кортекс
ms.openlocfilehash: 31c6b6dd31b3f1bc47deb8424dd847cc0af6d429
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304784"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="b742a-103">Настройка SharePoint Синтекс</span><span class="sxs-lookup"><span data-stu-id="b742a-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="b742a-104">Администраторы могут использовать центр администрирования Microsoft 365 для настройки и Microsoft SharePoint Синтекс.</span><span class="sxs-lookup"><span data-stu-id="b742a-104">Admins can use the Microsoft 365 admin center to set up and Microsoft SharePoint Syntex.</span></span> 

<span data-ttu-id="b742a-105">Прежде чем начать, примите во внимание следующее:</span><span class="sxs-lookup"><span data-stu-id="b742a-105">Consider the following before you start:</span></span>

- <span data-ttu-id="b742a-106">Какие сайты SharePoint будут включать обработку формы?</span><span class="sxs-lookup"><span data-stu-id="b742a-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="b742a-107">Все они, некоторые или выбранные сайты?</span><span class="sxs-lookup"><span data-stu-id="b742a-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="b742a-108">Укажите имя центра контента и пользователя, который является основным администратором сайта.</span><span class="sxs-lookup"><span data-stu-id="b742a-108">What will you name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="b742a-109">Вы можете изменить параметры после начальной установки в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b742a-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="b742a-110">Содержимое этой статьи предназначено для проекта Кортекс Private Preview.</span><span class="sxs-lookup"><span data-stu-id="b742a-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="b742a-111">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="b742a-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="b742a-112">Прежде чем приступать к настройке, запланируйте оптимальный способ установки и настройки контента в среде.</span><span class="sxs-lookup"><span data-stu-id="b742a-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="b742a-113">Например, необходимо принять во внимание следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="b742a-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="b742a-114">Сайты SharePoint, для которых необходимо включить обработку форм, все они, некоторые или выбранные сайты</span><span class="sxs-lookup"><span data-stu-id="b742a-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="b742a-115">Ваш центр управления контентом и имя главного администратора сайта</span><span class="sxs-lookup"><span data-stu-id="b742a-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="b742a-116">Требования</span><span class="sxs-lookup"><span data-stu-id="b742a-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="b742a-117">Чтобы получить доступ к центру администрирования Microsoft 365 и настроить общие сведения о контенте, необходимо иметь разрешения глобального администратора или администратора SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b742a-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="b742a-118">Как администратор, вы также можете вносить изменения в выбранные параметры в любое время после установки, а также во всем содержимом параметров управления в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b742a-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="b742a-119">Настройка SharePoint Синтекс</span><span class="sxs-lookup"><span data-stu-id="b742a-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="b742a-120">В центре администрирования Microsoft 365 выберите пункт **Настройка**, а затем просмотрите раздел **сведения о организации** .</span><span class="sxs-lookup"><span data-stu-id="b742a-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>

2. <span data-ttu-id="b742a-121">В разделе " **сведения о организации** " выберите элемент **Автоматизация контента**.</span><span class="sxs-lookup"><span data-stu-id="b742a-121">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![Страница "Настройка знаний организации"](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="b742a-123">На странице " **Автоматизация SharePoint Синтекс** " нажмите кнопку **начать работу** , чтобы пройти процесс установки.</span><span class="sxs-lookup"><span data-stu-id="b742a-123">On the **Automate SharePoint Syntex** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![Запуск программы установки](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="b742a-125">На странице Включение тегов изображений выберите, следует ли разрешить [маркировку изображений](image-tagging.md).</span><span class="sxs-lookup"><span data-stu-id="b742a-125">On the Turn on image tagging page, choose if you want to allow [image tagging](image-tagging.md).</span></span>

    ![Снимок экрана: параметры разметки изображений](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. <span data-ttu-id="b742a-127">На странице **Настройка обработки формы** можно выбрать, следует ли разрешить пользователям использовать построитель AI для создания моделей обработки форм в определенных библиотеках документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b742a-127">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="b742a-128">Команда меню будет доступна на ленте "Библиотека документов", чтобы **создать модель обработки форм** в библиотеках документов SharePoint, в которых она включена.</span><span class="sxs-lookup"><span data-stu-id="b742a-128">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="b742a-129">**Чтобы в библиотеках SharePoint отображался параметр для создания модели обработки форм**, можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="b742a-129">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="b742a-130">**Все библиотеки SharePoint** , чтобы сделать их доступными для всех библиотек SharePoint в Организации.</span><span class="sxs-lookup"><span data-stu-id="b742a-130">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="b742a-131">**Только библиотеки на выбранных сайтах**, а затем выберите сайты, в которых вы хотите сделать их доступными.</span><span class="sxs-lookup"><span data-stu-id="b742a-131">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>

   ![Настройка обработки форм](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="b742a-133">Включение этого параметра в библиотеке документов SharePoint не влияет на существующие модели, примененные к библиотеке, или на возможность применения моделей к библиотеке.</span><span class="sxs-lookup"><span data-stu-id="b742a-133">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 
    
6. <span data-ttu-id="b742a-134">На странице " **Создание центра содержимого** " можно создать сайт центра контента SharePoint, на котором пользователи могут создавать и управлять моделями документов.</span><span class="sxs-lookup"><span data-stu-id="b742a-134">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="b742a-135">а.</span><span class="sxs-lookup"><span data-stu-id="b742a-135">a.</span></span> <span data-ttu-id="b742a-136">В поле **имя сайта**введите имя, которое вы хотите присвоить сайту центра контента.</span><span class="sxs-lookup"><span data-stu-id="b742a-136">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="b742a-137">б.</span><span class="sxs-lookup"><span data-stu-id="b742a-137">b.</span></span> <span data-ttu-id="b742a-138">В поле **адрес сайта** отобразится URL-адрес вашего сайта в зависимости от того, что выбрано для имени сайта.</span><span class="sxs-lookup"><span data-stu-id="b742a-138">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="b742a-139">Если вы хотите изменить его, нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="b742a-139">If you want to change it, click **Edit**.</span></span></br>

      ![Создание центра контента](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="b742a-141">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b742a-141">Select **Next**.</span></span>

7. <span data-ttu-id="b742a-142">На странице **"Проверка и завершение"** можно просмотреть выбранный параметр и внести изменения.</span><span class="sxs-lookup"><span data-stu-id="b742a-142">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="b742a-143">Если вы удовлетворены выбранными параметрами, нажмите кнопку **активировать**.</span><span class="sxs-lookup"><span data-stu-id="b742a-143">If you are satisfied with your selections, select **Activate**.</span></span>

8. <span data-ttu-id="b742a-144">На странице подтверждения нажмите кнопку **done (Готово**).</span><span class="sxs-lookup"><span data-stu-id="b742a-144">On the confirmation page, click **Done**.</span></span>

9. <span data-ttu-id="b742a-145">Вы вернетесь на страницу **автоматизированного понимания контента** .</span><span class="sxs-lookup"><span data-stu-id="b742a-145">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="b742a-146">На этой странице можно выбрать пункт **Управление** , чтобы внести изменения в параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b742a-146">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="b742a-147">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="b742a-147">Assign licenses</span></span>

<span data-ttu-id="b742a-148">После настройки SharePoint Синтекс необходимо назначить лицензии для пользователей, которые будут использовать обработку форм, и ознакомиться с функциями.</span><span class="sxs-lookup"><span data-stu-id="b742a-148">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using form processing and document understanding features.</span></span>

<span data-ttu-id="b742a-149">Назначение лицензий:</span><span class="sxs-lookup"><span data-stu-id="b742a-149">To assign licenses:</span></span>

1. <span data-ttu-id="b742a-150">В центре администрирования Microsoft 365 в разделе **Пользователи**щелкните **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="b742a-150">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="b742a-151">Выберите пользователей, которым вы хотите лицензировать, и щелкните **Управление лицензиями продуктов**.</span><span class="sxs-lookup"><span data-stu-id="b742a-151">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="b742a-152">Выберите команду **назначить больше**.</span><span class="sxs-lookup"><span data-stu-id="b742a-152">Select **Assign more**.</span></span>

4. <span data-ttu-id="b742a-153">Выберите **интеллектуальные службы контента**.</span><span class="sxs-lookup"><span data-stu-id="b742a-153">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="b742a-154">В разделе **приложения**убедитесь, что выбраны все **Общие службы данных для интеллектуального** и **интеллектуального служб** контента.</span><span class="sxs-lookup"><span data-stu-id="b742a-154">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![Лицензии на SharePoint Синтекс в центре администрирования Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="b742a-156">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="b742a-156">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="b742a-157">Кредиты в построителе AI</span><span class="sxs-lookup"><span data-stu-id="b742a-157">AI Builder credits</span></span>

<span data-ttu-id="b742a-158">Если у вас 300 или более лицензий SharePoint Синтекс для SharePoint Синтекс в Организации, будет выделено 1 000 000.</span><span class="sxs-lookup"><span data-stu-id="b742a-158">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="b742a-159">Если у вас менее 300 лицензий, вы должны приобрести кредиты в построителе AI, чтобы использовать обработку форм.</span><span class="sxs-lookup"><span data-stu-id="b742a-159">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="b742a-160">Вы можете оценить мощность AI-построителя, которая подходит для вас с помощью [калькулятора AI Builder](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="b742a-160">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="b742a-161">Перейдите в [центр администрирования Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) , чтобы проверить свои кредиты и использование.</span><span class="sxs-lookup"><span data-stu-id="b742a-161">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="b742a-162">См. также</span><span class="sxs-lookup"><span data-stu-id="b742a-162">See also</span></span>

[<span data-ttu-id="b742a-163">Общие сведения о модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="b742a-163">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="b742a-164">Пошаговое руководство: создание модели документа "Общие сведения" (видео)</span><span class="sxs-lookup"><span data-stu-id="b742a-164">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

