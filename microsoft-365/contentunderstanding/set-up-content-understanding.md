---
title: 'Сведения о настройке контента (Предварительная версия) '
description: Настройка проекта кортекс.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 5fcc7f78bfc12faae19ce2a3fbc77c4348da01de
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612706"
---
# <a name="set-up-content-understanding-preview"></a><span data-ttu-id="c8a2e-103">Сведения о настройке контента (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="c8a2e-103">Set up content understanding (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="c8a2e-104">Содержимое этой статьи предназначено для Кортексного предварительного просмотра Project.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="c8a2e-105">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="c8a2e-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="c8a2e-106">Администраторы могут использовать центр администрирования Microsoft 365, чтобы настроить и настроить общие сведения о содержимом.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-106">Admins can use the Microsoft 365 admin center to set up and configure content understanding.</span></span> 

<span data-ttu-id="c8a2e-107">Прежде чем приступать к настройке, запланируйте оптимальный способ установки и настройки контента в среде.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-107">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="c8a2e-108">Например, необходимо принять во внимание следующее:</span><span class="sxs-lookup"><span data-stu-id="c8a2e-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="c8a2e-109">Какие сайты SharePoint будут включать обработку формы?</span><span class="sxs-lookup"><span data-stu-id="c8a2e-109">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="c8a2e-110">Все они, некоторые или выбранные сайты?</span><span class="sxs-lookup"><span data-stu-id="c8a2e-110">All of them, some, or select sites?</span></span>
- <span data-ttu-id="c8a2e-111">Имя центра управления контентом и кого является основным администратором сайта?</span><span class="sxs-lookup"><span data-stu-id="c8a2e-111">Name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="c8a2e-112">Администратор также может вносить изменения в выбранные параметры в любое время после установки через содержание параметры управления в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-112">An admin can also make changes to your selected settings anytime after setup through the content understanding management settings in the Microsoft 365 admin center.</span></span>


## <a name="requirements"></a><span data-ttu-id="c8a2e-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c8a2e-113">Requirements</span></span> 
<span data-ttu-id="c8a2e-114">Чтобы получить доступ к центру администрирования Microsoft 365 и настроить общие сведения о контенте, необходимо иметь разрешения глобального администратора или администратора SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-114">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>


## <a name="to-set-up-content-understanding"></a><span data-ttu-id="c8a2e-115">Настройка понимания контента</span><span class="sxs-lookup"><span data-stu-id="c8a2e-115">To set up content understanding</span></span>

1. <span data-ttu-id="c8a2e-116">В центре администрирования Microsoft 365 выберите пункт **Настройка**, а затем просмотрите раздел **сведения о организации** .</span><span class="sxs-lookup"><span data-stu-id="c8a2e-116">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>
2. <span data-ttu-id="c8a2e-117">В разделе " **сведения о организации** " выберите элемент **Автоматизация контента**.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-117">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![Страница "Настройка знаний организации"](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="c8a2e-119">На странице **автоматизированное представление контента** нажмите кнопку Начало **работы** , чтобы проанализировать процесс установки.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-119">On the **Automate content understanding** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Запуск программы установки](../media/content-understanding/admin-content-understanding-get-started.png)</br>


4. <span data-ttu-id="c8a2e-121">На странице **Настройка обработки формы** можно выбрать, следует ли разрешить пользователям использовать построитель AI для создания моделей обработки форм в определенных библиотеках документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-121">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="c8a2e-122">Команда меню будет доступна на ленте "Библиотека документов", чтобы **создать модель обработки форм** в библиотеках документов SharePoint, в которых она включена.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-122">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="c8a2e-123">**Чтобы в библиотеках SharePoint отображался параметр для создания модели обработки форм**, можно выбрать:</span><span class="sxs-lookup"><span data-stu-id="c8a2e-123">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
    - <span data-ttu-id="c8a2e-124">**Все библиотеки SharePoint** , чтобы сделать их доступными для всех библиотек SharePoint в клиенте.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-124">**All SharePoint libraries** to make it available to all SharePoint libraries in your tenant.</span></span></br>
    - <span data-ttu-id="c8a2e-125">**Только библиотеки на выбранных сайтах**, а затем выберите сайты, в которых вы хотите сделать их доступными.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-125">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>
    - <span data-ttu-id="c8a2e-126">**Нет библиотек SharePoint** . Если вы не хотите, чтобы она была доступна для всех сайтов (это можно сделать после установки).</span><span class="sxs-lookup"><span data-stu-id="c8a2e-126">**No SharePoint libraries** if you currently don't want to make it available to any sites (you can change this after setup).</span></span>
</br>

   <span data-ttu-id="c8a2e-127">![Настройка обработки форм](../media/content-understanding/admin-configforms.png)
</span><span class="sxs-lookup"><span data-stu-id="c8a2e-127">![Configure form processing](../media/content-understanding/admin-configforms.png)
</span></span></br>

   > [!Note]
   > <span data-ttu-id="c8a2e-128">Включение этого параметра в библиотеке документов SharePoint не влияет на существующие модели, примененные к библиотеке, или на возможность применения моделей к библиотеке.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-128">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 

    
5. <span data-ttu-id="c8a2e-129">На странице " **Создание центра содержимого** " можно создать сайт центра контента SharePoint, на котором пользователи могут создавать и управлять моделями документов.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-129">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="c8a2e-130">а.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-130">a.</span></span> <span data-ttu-id="c8a2e-131">В поле **имя сайта**введите имя, которое вы хотите присвоить сайту центра контента.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-131">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="c8a2e-132">б.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-132">b.</span></span> <span data-ttu-id="c8a2e-133">В поле **адрес сайта** отобразится URL-адрес вашего сайта в зависимости от того, что выбрано для имени сайта.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-133">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span></br>

    > [!Note] 
    > <span data-ttu-id="c8a2e-134">Несмотря на то, что вы можете выбрать любой поддерживаемый язык, обратите внимание на то, что основные сведения о моделях можно создавать только для английского языка.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-134">While you can select any supported language, note that content understanding models can only be created for English.</span></span></br>

      ![Создание центра контента](../media/content-understanding/admin-cu-create-cc.png)</br>


    <span data-ttu-id="c8a2e-136">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-136">Select **Next**.</span></span>
6. <span data-ttu-id="c8a2e-137">На странице **"завершение и проверка"** можно просмотреть выбранный параметр и внести изменения.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-137">On the **Finish and review** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="c8a2e-138">Если вы удовлетворены выбранными параметрами, нажмите кнопку **активировать**.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-138">If you are satisfied with your selections, select **Activate**.</span></span>



7. <span data-ttu-id="c8a2e-139">Откроется страница " **Общие сведения о включенном содержимом** ", в результате чего система добавила параметры обработки формы и сайт центра контента.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-139">The **Content understanding activated** page will display, confirming that the system has added your form processing preferences and creating the Content Center site.</span></span> <span data-ttu-id="c8a2e-140">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-140">Select **Done**.</span></span>

8. <span data-ttu-id="c8a2e-141">Вы вернетесь на страницу **автоматизированного понимания контента** .</span><span class="sxs-lookup"><span data-stu-id="c8a2e-141">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="c8a2e-142">На этой странице можно выбрать пункт **Управление** , чтобы внести изменения в параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c8a2e-142">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="see-also"></a><span data-ttu-id="c8a2e-143">См. также</span><span class="sxs-lookup"><span data-stu-id="c8a2e-143">See also</span></span>



  






