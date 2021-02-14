---
title: Добавление обязательных и пользовательских вопросов на страницу резервирования
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: fd6b7587-5055-4bcd-83a4-13bd4929bfff
description: Если вам нужно задать клиентам вопросы при заказе встречи с вами в Интернете, вы можете добавить настраиваемые вопросы и необходимые вопросы на страницу резервирования.
ms.openlocfilehash: ebbb07857fd8bb196f769dfb7e71ad25a85dfd54
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "47420086"
---
# <a name="add-custom-and-required-questions-to-the-booking-page"></a><span data-ttu-id="82d5d-103">Добавление обязательных и пользовательских вопросов на страницу резервирования</span><span class="sxs-lookup"><span data-stu-id="82d5d-103">Add custom and required questions to the booking page</span></span>

<span data-ttu-id="82d5d-104">С помощью Bookings вы можете задавать вопросы клиентам при резервированиях.</span><span class="sxs-lookup"><span data-stu-id="82d5d-104">Bookings lets you create questions to ask your customers when they are booking appointments.</span></span> <span data-ttu-id="82d5d-105">Он также позволяет выбрать, какие вопросы являются требуемой.</span><span class="sxs-lookup"><span data-stu-id="82d5d-105">It also lets you choose which questions are required.</span></span>

<span data-ttu-id="82d5d-106">Вы связываете вопросы со службой, поэтому у каждой службы может быть разный набор вопросов.</span><span class="sxs-lookup"><span data-stu-id="82d5d-106">You associate the questions with a service, so each service can have a different set of questions.</span></span> <span data-ttu-id="82d5d-107">Например, дизайнер может спросить у клиентов, которые резервирует встречу по цветам, если у них есть известные оттенки или оттенки.</span><span class="sxs-lookup"><span data-stu-id="82d5d-107">For example, a hair stylist may ask customers who are booking a hair coloring appointment if they have any known allergies to bleaches or tints.</span></span> <span data-ttu-id="82d5d-108">Это позволяет вам и вашим клиентам сэкономить время, когда они приедут на встречу.</span><span class="sxs-lookup"><span data-stu-id="82d5d-108">This allows you and your customers to save time when they arrive for their appointment.</span></span>

<span data-ttu-id="82d5d-109">Пользователи увидят настраиваемые вопросы при создании встречи на странице резервирования.</span><span class="sxs-lookup"><span data-stu-id="82d5d-109">The customers will see the custom questions when they are creating their appointment on the booking page.</span></span> <span data-ttu-id="82d5d-110">Сотрудники будут видеть настраиваемые вопросы при создании нового резервирования из календаря Bookings или при просмотре существующей встречи.</span><span class="sxs-lookup"><span data-stu-id="82d5d-110">Staff will see the custom questions when they create a new booking from the Bookings calendar or when viewing an existing appointment.</span></span> <span data-ttu-id="82d5d-111">Bookings сохраняет все ваши вопросы в эталмовом списке, чтобы вам не нужно было повторно создавать одинаковые вопросы для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="82d5d-111">Bookings saves all of your questions to a master list so that you don't have to re-create the same questions for every service.</span></span> <span data-ttu-id="82d5d-112">Вы также можете выбрать, являются ли вопросы обязательными или необязательными.</span><span class="sxs-lookup"><span data-stu-id="82d5d-112">You can also choose whether questions are required or optional.</span></span>

> [!NOTE]
> <span data-ttu-id="82d5d-113">Ответы клиента на вопросы можно увидеть при взгляде на его встречу в календаре резервирования.</span><span class="sxs-lookup"><span data-stu-id="82d5d-113">The customer's answers to the questions can be seen when you look at their appointment in the booking calendar.</span></span>

<span data-ttu-id="82d5d-114">Дополнительные сведения о персонализации и настройке страницы резервирования см. в [подстройке страницы резервирования.](customize-booking-page.md)</span><span class="sxs-lookup"><span data-stu-id="82d5d-114">For more information about how to personalize and customize your booking page, see [Customize your booking page](customize-booking-page.md).</span></span>

## <a name="add-custom-questions-to-your-services"></a><span data-ttu-id="82d5d-115">Добавление настраиваемой информации в службы</span><span class="sxs-lookup"><span data-stu-id="82d5d-115">Add custom questions to your services</span></span>

1. <span data-ttu-id="82d5d-116">Войдите в Microsoft 365 и перейдите в **Bookings.**</span><span class="sxs-lookup"><span data-stu-id="82d5d-116">Sign in to Microsoft 365 and go to **Bookings**.</span></span>

1. <span data-ttu-id="82d5d-117">Перейдите **в "Службы"** и либо отредактируете существующую службу, либо **добавьте службу.**</span><span class="sxs-lookup"><span data-stu-id="82d5d-117">Go to **Services** and either edit an existing service or **Add a service**.</span></span>

1. <span data-ttu-id="82d5d-118">Прокрутите вниз до раздела **"Настраиваемые поля"** и выберите **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="82d5d-118">Scroll down to the **Custom fields** section, and then select **Modify**.</span></span>

   <span data-ttu-id="82d5d-119">Мы уже добавили некоторые основные вопросы о клиенте: электронная почта клиента, номер телефона, адрес клиента и заметки клиента.</span><span class="sxs-lookup"><span data-stu-id="82d5d-119">We already added some basic customer information questions: Customer email, phone number, customer address, and customer notes.</span></span> <span data-ttu-id="82d5d-120">При первом этом вопросы о клиенте выделены серым цветом.</span><span class="sxs-lookup"><span data-stu-id="82d5d-120">The first time you do this, the customer information questions are highlighted in gray.</span></span> <span data-ttu-id="82d5d-121">Это означает, что пользователь увидит этот вопрос.</span><span class="sxs-lookup"><span data-stu-id="82d5d-121">That means that the user will see this question.</span></span> <span data-ttu-id="82d5d-122">Если вы выберете вопрос, поле выделения вокруг него исчезнет, и вашему клиенту не будет задан этот вопрос.</span><span class="sxs-lookup"><span data-stu-id="82d5d-122">If you select the question, the highlight box around it will disappear and your customer won't be asked that question.</span></span>

   <span data-ttu-id="82d5d-123">В этом примере номер телефона и заметки клиента были отключены, и мы создали два новых настраиваемого вопроса.</span><span class="sxs-lookup"><span data-stu-id="82d5d-123">In this example, phone number and customer notes have been turned off and we created two new custom questions to ask.</span></span>

   ![Изображение экрана настраиваемого вопроса](../media/bookings-questions-custom-fields.png)

1. <span data-ttu-id="82d5d-125">Чтобы сделать вопрос нужным, выберите **необходимый контрольный** ящик.</span><span class="sxs-lookup"><span data-stu-id="82d5d-125">To make the question required, select the **Required** checkbox.</span></span> <span data-ttu-id="82d5d-126">Ваш клиент не сможет завершить резервирование, пока не ответит на необходимые вопросы.</span><span class="sxs-lookup"><span data-stu-id="82d5d-126">Your customer won't be able to complete the booking until they've answered the required questions.</span></span>

1. <span data-ttu-id="82d5d-127">Чтобы создать настраиваемый вопрос, выберите **"Добавить вопрос"** в верхней части панели.</span><span class="sxs-lookup"><span data-stu-id="82d5d-127">To create a custom question, select **Add a question** from the top of the panel.</span></span> <span data-ttu-id="82d5d-128">Запишите свой вопрос и выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="82d5d-128">Write your question, and then select **Save**.</span></span>

1. <span data-ttu-id="82d5d-129">Щелкните вопрос, чтобы включить его.</span><span class="sxs-lookup"><span data-stu-id="82d5d-129">Click on the question to enable it.</span></span> <span data-ttu-id="82d5d-130">Вокруг него появляется выделенная поле, и вопрос включен.</span><span class="sxs-lookup"><span data-stu-id="82d5d-130">A highlighted box appears around it and the question is enabled.</span></span>

1. <span data-ttu-id="82d5d-131">Нажмите **кнопку** "ОК" в верхней части страницы и **сохраните службу.**</span><span class="sxs-lookup"><span data-stu-id="82d5d-131">Click **Ok** at the top of the page, and then **Save the service**.</span></span>

<span data-ttu-id="82d5d-132">Bookings сохранит все ваши настраиваемые вопросы в основном списке, чтобы вы могли легко добавлять вопросы в каждую службу, не внося одинаковые вопросы.</span><span class="sxs-lookup"><span data-stu-id="82d5d-132">Bookings will save all of your custom questions in a master list so that you can easily add questions to each service without needing to repeatedly type the same questions.</span></span> <span data-ttu-id="82d5d-133">Например, если вы откроете другую службу, вопрос, созданный для первой службы, будет отключен в разделе "Настраиваемые поля".</span><span class="sxs-lookup"><span data-stu-id="82d5d-133">For example, if you open a different service, the question you created for the first service will show in the Custom fields section, but it wil be disabled.</span></span> <span data-ttu-id="82d5d-134">Щелкните вопрос, чтобы отобразить выделенный прямоугольник и включить вопрос.</span><span class="sxs-lookup"><span data-stu-id="82d5d-134">Click the question so that a highlighted rectangle displays and the question is enabled.</span></span>

<span data-ttu-id="82d5d-135">В этом примере можно увидеть, что вопросы, добавленные для первой службы, доступны для этой службы.</span><span class="sxs-lookup"><span data-stu-id="82d5d-135">In this example, you can see that the questions that were added for the first service are available for this service.</span></span> <span data-ttu-id="82d5d-136">Все вопросы, которые вы создаете для этой службы, будут доступны для всех служб.</span><span class="sxs-lookup"><span data-stu-id="82d5d-136">Any questions you create for this service will be available for all services.</span></span>

   ![Изображение вопросов, которые отображаются для нескольких служб](../media/bookings-questions-services.png)

<span data-ttu-id="82d5d-138">Если страница резервирования уже опубликована, больше ничего делать не нужно.</span><span class="sxs-lookup"><span data-stu-id="82d5d-138">If your booking page is already published, you don't need to do anything else.</span></span> <span data-ttu-id="82d5d-139">Клиенты увидят вопросы при следующей книге.</span><span class="sxs-lookup"><span data-stu-id="82d5d-139">Customers will see the questions the next time they book with you.</span></span> <span data-ttu-id="82d5d-140">Если страница резервирования еще не опубликована,  перейдите на страницу резервирования в Outlook в Интернете и выберите "Сохранить **и опубликовать".**</span><span class="sxs-lookup"><span data-stu-id="82d5d-140">If your booking page isn't published yet, go to the **booking page** from Outlook on the web, and then select **Save and publish**.</span></span>

> [!WARNING]
> <span data-ttu-id="82d5d-141">Вы также можете удалить вопросы из этого списка.</span><span class="sxs-lookup"><span data-stu-id="82d5d-141">You can also delete questions from the master list.</span></span> <span data-ttu-id="82d5d-142">Однако при удалении вопроса он будет удален из каждой службы.</span><span class="sxs-lookup"><span data-stu-id="82d5d-142">However, if you delete a question it will be deleted from every service.</span></span> <span data-ttu-id="82d5d-143">Мы рекомендуем отключить вопрос, выбрав его, чтобы не влиять на другие службы.</span><span class="sxs-lookup"><span data-stu-id="82d5d-143">We recommend that you disable the question by selecting it to ensure you do not impact any other services.</span></span> <span data-ttu-id="82d5d-144">Вы можете увидеть, что вопрос отключен, если он не находится в выделенной прямоугольнике.</span><span class="sxs-lookup"><span data-stu-id="82d5d-144">You can see that a question is disabled if it is not surrounded by a highlighted rectangle.</span></span>

## <a name="customer-experience"></a><span data-ttu-id="82d5d-145">Взаимодействие с клиентами</span><span class="sxs-lookup"><span data-stu-id="82d5d-145">Customer experience</span></span>

<span data-ttu-id="82d5d-146">Когда ваши клиенты будут бронировать встречу с вами, в разделе "Добавление сведений" покажутся основные вопросы о **клиенте.**</span><span class="sxs-lookup"><span data-stu-id="82d5d-146">When your customers book an appointment with you, the basic customer information questions will show in the **Add your details** section.</span></span> <span data-ttu-id="82d5d-147">Все добавляемые вами настраиваемые вопросы будут в разделе **"Предоставление дополнительных** сведений".</span><span class="sxs-lookup"><span data-stu-id="82d5d-147">Any customized questions you add will be in the **Provide additional information** section.</span></span>

![Изображение того, что видят клиенты, когда включены вопросы](../media/bookings-questions-customer.png)

## <a name="staff-experience"></a><span data-ttu-id="82d5d-149">Опыт работы сотрудников</span><span class="sxs-lookup"><span data-stu-id="82d5d-149">Staff experience</span></span>

<span data-ttu-id="82d5d-150">Когда ваши клиенты бронят встречу с вами, ваши сотрудники будут видеть вопросы и ответы клиента в календаре резервирования.</span><span class="sxs-lookup"><span data-stu-id="82d5d-150">When your customers book an appointment with you, your staff will see the questions and the customer's answers on the booking calendar.</span></span> <span data-ttu-id="82d5d-151">Чтобы увидеть его, перейдите в **календарь Bookings** \>  и откройте встречу.</span><span class="sxs-lookup"><span data-stu-id="82d5d-151">To see it, go to **Bookings** \> **Calendar** and then open an appointment.</span></span>

![Изображение того, что видят сотрудники, когда включены вопросы](../media/bookings-questions-staff.png)
