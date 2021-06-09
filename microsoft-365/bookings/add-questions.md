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
description: Если вам нужно задать клиентам вопросы, когда они бронировать встречу с вами в Интернете, вы можете добавить настраиваемые вопросы и необходимые вопросы на страницу бронирования.
ms.openlocfilehash: ebbb07857fd8bb196f769dfb7e71ad25a85dfd54
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "47420086"
---
# <a name="add-custom-and-required-questions-to-the-booking-page"></a><span data-ttu-id="db132-103">Добавление обязательных и пользовательских вопросов на страницу резервирования</span><span class="sxs-lookup"><span data-stu-id="db132-103">Add custom and required questions to the booking page</span></span>

<span data-ttu-id="db132-104">Бронирование позволяет создавать вопросы, чтобы задать своим клиентам при бронировании встреч.</span><span class="sxs-lookup"><span data-stu-id="db132-104">Bookings lets you create questions to ask your customers when they are booking appointments.</span></span> <span data-ttu-id="db132-105">Он также позволяет выбрать, какие вопросы необходимы.</span><span class="sxs-lookup"><span data-stu-id="db132-105">It also lets you choose which questions are required.</span></span>

<span data-ttu-id="db132-106">Вы связываете вопросы со службой, поэтому у каждой службы может быть другой набор вопросов.</span><span class="sxs-lookup"><span data-stu-id="db132-106">You associate the questions with a service, so each service can have a different set of questions.</span></span> <span data-ttu-id="db132-107">Например, стилист может спросить клиентов, которые бронирует встречу по раскраске волос, если у них есть какие-либо известные аллергии на отбеливатели или оттенки.</span><span class="sxs-lookup"><span data-stu-id="db132-107">For example, a hair stylist may ask customers who are booking a hair coloring appointment if they have any known allergies to bleaches or tints.</span></span> <span data-ttu-id="db132-108">Это позволяет вам и вашим клиентам сэкономить время при прибытии на встречу.</span><span class="sxs-lookup"><span data-stu-id="db132-108">This allows you and your customers to save time when they arrive for their appointment.</span></span>

<span data-ttu-id="db132-109">Клиенты увидят настраиваемые вопросы при создании встречи на странице бронирования.</span><span class="sxs-lookup"><span data-stu-id="db132-109">The customers will see the custom questions when they are creating their appointment on the booking page.</span></span> <span data-ttu-id="db132-110">Сотрудники увидят настраиваемые вопросы при создании нового бронирования из календаря Бронирования или при просмотре существующей встречи.</span><span class="sxs-lookup"><span data-stu-id="db132-110">Staff will see the custom questions when they create a new booking from the Bookings calendar or when viewing an existing appointment.</span></span> <span data-ttu-id="db132-111">Резервирование сохраняет все ваши вопросы в мастер-список, чтобы вам не нужно было повторно создавать те же вопросы для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="db132-111">Bookings saves all of your questions to a master list so that you don't have to re-create the same questions for every service.</span></span> <span data-ttu-id="db132-112">Вы также можете выбрать, являются ли вопросы обязательными или необязательными.</span><span class="sxs-lookup"><span data-stu-id="db132-112">You can also choose whether questions are required or optional.</span></span>

> [!NOTE]
> <span data-ttu-id="db132-113">Ответы клиента на вопросы можно увидеть при взгляде на их встречу в календаре бронирования.</span><span class="sxs-lookup"><span data-stu-id="db132-113">The customer's answers to the questions can be seen when you look at their appointment in the booking calendar.</span></span>

<span data-ttu-id="db132-114">Дополнительные сведения о персонализации и настройке страницы бронирования см. в странице [Настройка страницы бронирования.](customize-booking-page.md)</span><span class="sxs-lookup"><span data-stu-id="db132-114">For more information about how to personalize and customize your booking page, see [Customize your booking page](customize-booking-page.md).</span></span>

## <a name="add-custom-questions-to-your-services"></a><span data-ttu-id="db132-115">Добавление пользовательских вопросов в службы</span><span class="sxs-lookup"><span data-stu-id="db132-115">Add custom questions to your services</span></span>

1. <span data-ttu-id="db132-116">Войдите в Microsoft 365 и перейдите в **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="db132-116">Sign in to Microsoft 365 and go to **Bookings**.</span></span>

1. <span data-ttu-id="db132-117">Перейдите **к службам** и отредактировать существующую службу или **добавить службу.**</span><span class="sxs-lookup"><span data-stu-id="db132-117">Go to **Services** and either edit an existing service or **Add a service**.</span></span>

1. <span data-ttu-id="db132-118">Прокрутите вниз в **раздел Настраиваемые поля,** а затем выберите **Изменение**.</span><span class="sxs-lookup"><span data-stu-id="db132-118">Scroll down to the **Custom fields** section, and then select **Modify**.</span></span>

   <span data-ttu-id="db132-119">Мы уже добавили некоторые основные вопросы к сведениям о клиентах: электронную почту клиента, номер телефона, адрес клиента и заметки о клиентах.</span><span class="sxs-lookup"><span data-stu-id="db132-119">We already added some basic customer information questions: Customer email, phone number, customer address, and customer notes.</span></span> <span data-ttu-id="db132-120">При первом этом случае вопросы информации о клиентах выделены серым цветом.</span><span class="sxs-lookup"><span data-stu-id="db132-120">The first time you do this, the customer information questions are highlighted in gray.</span></span> <span data-ttu-id="db132-121">Это означает, что пользователь увидит этот вопрос.</span><span class="sxs-lookup"><span data-stu-id="db132-121">That means that the user will see this question.</span></span> <span data-ttu-id="db132-122">Если выбрать вопрос, поле выделения вокруг него исчезнет, и клиенту не будет задан этот вопрос.</span><span class="sxs-lookup"><span data-stu-id="db132-122">If you select the question, the highlight box around it will disappear and your customer won't be asked that question.</span></span>

   <span data-ttu-id="db132-123">В этом примере отключили номер телефона и заметки клиентов, и мы создали два новых настраиваемого вопроса.</span><span class="sxs-lookup"><span data-stu-id="db132-123">In this example, phone number and customer notes have been turned off and we created two new custom questions to ask.</span></span>

   ![Изображение экрана пользовательских вопросов](../media/bookings-questions-custom-fields.png)

1. <span data-ttu-id="db132-125">Чтобы сделать этот вопрос нужным, выберите **необходимый почтовый** ящик.</span><span class="sxs-lookup"><span data-stu-id="db132-125">To make the question required, select the **Required** checkbox.</span></span> <span data-ttu-id="db132-126">Клиент не сможет завершить бронирование, пока не ответит на необходимые вопросы.</span><span class="sxs-lookup"><span data-stu-id="db132-126">Your customer won't be able to complete the booking until they've answered the required questions.</span></span>

1. <span data-ttu-id="db132-127">Чтобы создать настраиваемый вопрос, **выберите Добавить вопрос** из верхней части панели.</span><span class="sxs-lookup"><span data-stu-id="db132-127">To create a custom question, select **Add a question** from the top of the panel.</span></span> <span data-ttu-id="db132-128">Напишите вопрос, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="db132-128">Write your question, and then select **Save**.</span></span>

1. <span data-ttu-id="db132-129">Нажмите на вопрос, чтобы включить его.</span><span class="sxs-lookup"><span data-stu-id="db132-129">Click on the question to enable it.</span></span> <span data-ttu-id="db132-130">Вокруг него появляется выделенная поле, и вопрос включен.</span><span class="sxs-lookup"><span data-stu-id="db132-130">A highlighted box appears around it and the question is enabled.</span></span>

1. <span data-ttu-id="db132-131">Щелкните **Ок** в верхней части страницы и **сохраните службу.**</span><span class="sxs-lookup"><span data-stu-id="db132-131">Click **Ok** at the top of the page, and then **Save the service**.</span></span>

<span data-ttu-id="db132-132">Заказы сэкономят все настраиваемые вопросы в основном списке, чтобы вы могли легко добавлять вопросы в каждую службу без необходимости повторно введите те же вопросы.</span><span class="sxs-lookup"><span data-stu-id="db132-132">Bookings will save all of your custom questions in a master list so that you can easily add questions to each service without needing to repeatedly type the same questions.</span></span> <span data-ttu-id="db132-133">Например, если вы откроете другую службу, вопрос, созданный для первой службы, будет показываться в разделе Настраиваемые поля, но он будет отключен.</span><span class="sxs-lookup"><span data-stu-id="db132-133">For example, if you open a different service, the question you created for the first service will show in the Custom fields section, but it wil be disabled.</span></span> <span data-ttu-id="db132-134">Щелкните вопрос, чтобы выделенный прямоугольник отображался и вопрос включен.</span><span class="sxs-lookup"><span data-stu-id="db132-134">Click the question so that a highlighted rectangle displays and the question is enabled.</span></span>

<span data-ttu-id="db132-135">В этом примере можно увидеть, что вопросы, добавленные для первой службы, доступны для этой службы.</span><span class="sxs-lookup"><span data-stu-id="db132-135">In this example, you can see that the questions that were added for the first service are available for this service.</span></span> <span data-ttu-id="db132-136">Все вопросы, которые вы создаете для этой службы, будут доступны для всех служб.</span><span class="sxs-lookup"><span data-stu-id="db132-136">Any questions you create for this service will be available for all services.</span></span>

   ![Изображение вопросов, которые отображаются для нескольких служб](../media/bookings-questions-services.png)

<span data-ttu-id="db132-138">Если страница бронирования уже опубликована, больше ничего не нужно делать.</span><span class="sxs-lookup"><span data-stu-id="db132-138">If your booking page is already published, you don't need to do anything else.</span></span> <span data-ttu-id="db132-139">Клиенты увидят вопросы при следующей книге с вами.</span><span class="sxs-lookup"><span data-stu-id="db132-139">Customers will see the questions the next time they book with you.</span></span> <span data-ttu-id="db132-140">Если страница бронирования еще не опубликована,  перейдите на страницу бронирования из Outlook в Интернете, а затем выберите **Сохранить и опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="db132-140">If your booking page isn't published yet, go to the **booking page** from Outlook on the web, and then select **Save and publish**.</span></span>

> [!WARNING]
> <span data-ttu-id="db132-141">Вы также можете удалить вопросы из списка.</span><span class="sxs-lookup"><span data-stu-id="db132-141">You can also delete questions from the master list.</span></span> <span data-ttu-id="db132-142">Однако если удалить вопрос, он будет удален из каждой службы.</span><span class="sxs-lookup"><span data-stu-id="db132-142">However, if you delete a question it will be deleted from every service.</span></span> <span data-ttu-id="db132-143">Мы рекомендуем отключить этот вопрос, выбрав его, чтобы не влиять на другие службы.</span><span class="sxs-lookup"><span data-stu-id="db132-143">We recommend that you disable the question by selecting it to ensure you do not impact any other services.</span></span> <span data-ttu-id="db132-144">Можно увидеть, что вопрос отключен, если он не окружен выделенным прямоугольником.</span><span class="sxs-lookup"><span data-stu-id="db132-144">You can see that a question is disabled if it is not surrounded by a highlighted rectangle.</span></span>

## <a name="customer-experience"></a><span data-ttu-id="db132-145">Взаимодействие с клиентами</span><span class="sxs-lookup"><span data-stu-id="db132-145">Customer experience</span></span>

<span data-ttu-id="db132-146">Когда ваши клиенты бронировать встречу с вами, основные вопросы о клиентах будут показываться в разделе **Добавить сведения.**</span><span class="sxs-lookup"><span data-stu-id="db132-146">When your customers book an appointment with you, the basic customer information questions will show in the **Add your details** section.</span></span> <span data-ttu-id="db132-147">Все настраиваемые вопросы, которые вы добавляете, будут в разделе **Предоставление дополнительных сведений.**</span><span class="sxs-lookup"><span data-stu-id="db132-147">Any customized questions you add will be in the **Provide additional information** section.</span></span>

![Изображение того, что видят клиенты при включении вопросов](../media/bookings-questions-customer.png)

## <a name="staff-experience"></a><span data-ttu-id="db132-149">Опыт работы с персоналом</span><span class="sxs-lookup"><span data-stu-id="db132-149">Staff experience</span></span>

<span data-ttu-id="db132-150">Когда ваши клиенты бронировать встречу с вами, ваши сотрудники будут видеть вопросы и ответы клиента в календаре бронирования.</span><span class="sxs-lookup"><span data-stu-id="db132-150">When your customers book an appointment with you, your staff will see the questions and the customer's answers on the booking calendar.</span></span> <span data-ttu-id="db132-151">Чтобы увидеть его, перейдите **в календарь** \> **бронирований** и откройте встречу.</span><span class="sxs-lookup"><span data-stu-id="db132-151">To see it, go to **Bookings** \> **Calendar** and then open an appointment.</span></span>

![Изображение того, что видят сотрудники при включении вопросов](../media/bookings-questions-staff.png)
