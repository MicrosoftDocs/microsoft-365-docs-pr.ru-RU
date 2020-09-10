---
title: Добавление настраиваемых и обязательных вопросов на страницу "резервирование"
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: fd6b7587-5055-4bcd-83a4-13bd4929bfff
description: Если вам нужно задать вопросы для пользователей, почтовые встречи с вами в сети, можно добавить настраиваемые вопросы и необходимые вопросы на страницу "резервирование".
ms.openlocfilehash: ebbb07857fd8bb196f769dfb7e71ad25a85dfd54
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "47420086"
---
# <a name="add-custom-and-required-questions-to-the-booking-page"></a><span data-ttu-id="92e83-103">Добавление настраиваемых и обязательных вопросов на страницу "резервирование"</span><span class="sxs-lookup"><span data-stu-id="92e83-103">Add custom and required questions to the booking page</span></span>

<span data-ttu-id="92e83-104">При резервировании вы можете создавать вопросы, чтобы запрашивать клиентов при резервировании встреч.</span><span class="sxs-lookup"><span data-stu-id="92e83-104">Bookings lets you create questions to ask your customers when they are booking appointments.</span></span> <span data-ttu-id="92e83-105">Кроме того, вы можете выбрать вопросы, которые требуются.</span><span class="sxs-lookup"><span data-stu-id="92e83-105">It also lets you choose which questions are required.</span></span>

<span data-ttu-id="92e83-106">Вы связываете вопросы со службой, поэтому каждая служба может иметь разный набор вопросов.</span><span class="sxs-lookup"><span data-stu-id="92e83-106">You associate the questions with a service, so each service can have a different set of questions.</span></span> <span data-ttu-id="92e83-107">Например, волосы стилист может попросить пользователей, которые заменяют встречу с цветовыми волосыми, если у них есть известные аллергиес, блеачес или оттенки.</span><span class="sxs-lookup"><span data-stu-id="92e83-107">For example, a hair stylist may ask customers who are booking a hair coloring appointment if they have any known allergies to bleaches or tints.</span></span> <span data-ttu-id="92e83-108">Это позволит вам и вашим клиентам сэкономить время, когда они приходят на встречу.</span><span class="sxs-lookup"><span data-stu-id="92e83-108">This allows you and your customers to save time when they arrive for their appointment.</span></span>

<span data-ttu-id="92e83-109">Пользователи увидят настраиваемые вопросы при создании встречи на странице "резервирование".</span><span class="sxs-lookup"><span data-stu-id="92e83-109">The customers will see the custom questions when they are creating their appointment on the booking page.</span></span> <span data-ttu-id="92e83-110">Сотрудники увидят настраиваемые вопросы при создании нового резервирования из календаря резервирования или при просмотре существующей встречи.</span><span class="sxs-lookup"><span data-stu-id="92e83-110">Staff will see the custom questions when they create a new booking from the Bookings calendar or when viewing an existing appointment.</span></span> <span data-ttu-id="92e83-111">При резервировании все вопросы сохраняются в основном списке, поэтому не нужно повторно создавать одни и те же вопросы для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="92e83-111">Bookings saves all of your questions to a master list so that you don't have to re-create the same questions for every service.</span></span> <span data-ttu-id="92e83-112">Вы также можете указать, какие вопросы являются обязательными или необязательными.</span><span class="sxs-lookup"><span data-stu-id="92e83-112">You can also choose whether questions are required or optional.</span></span>

> [!NOTE]
> <span data-ttu-id="92e83-113">Ответы клиента на вопросы могут отображаться при просмотре встречи в календаре резервирования.</span><span class="sxs-lookup"><span data-stu-id="92e83-113">The customer's answers to the questions can be seen when you look at their appointment in the booking calendar.</span></span>

<span data-ttu-id="92e83-114">Дополнительные сведения о персонализации и настройке страницы резервирования приведены в разделе [Настройка страницы резервирования](customize-booking-page.md).</span><span class="sxs-lookup"><span data-stu-id="92e83-114">For more information about how to personalize and customize your booking page, see [Customize your booking page](customize-booking-page.md).</span></span>

## <a name="add-custom-questions-to-your-services"></a><span data-ttu-id="92e83-115">Добавление настраиваемых вопросов в службы</span><span class="sxs-lookup"><span data-stu-id="92e83-115">Add custom questions to your services</span></span>

1. <span data-ttu-id="92e83-116">Войдите в Microsoft 365 и перейдите к разделу **резервирования**.</span><span class="sxs-lookup"><span data-stu-id="92e83-116">Sign in to Microsoft 365 and go to **Bookings**.</span></span>

1. <span data-ttu-id="92e83-117">Перейдите в раздел **службы** и либо измените существующую службу, либо **добавьте службу**.</span><span class="sxs-lookup"><span data-stu-id="92e83-117">Go to **Services** and either edit an existing service or **Add a service**.</span></span>

1. <span data-ttu-id="92e83-118">Прокрутите окно вниз до раздела **Настраиваемые поля** , а затем выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="92e83-118">Scroll down to the **Custom fields** section, and then select **Modify**.</span></span>

   <span data-ttu-id="92e83-119">Мы уже добавили некоторые основные вопросы о клиенте: адрес электронной почты, номер телефона, адрес клиента и заметки клиента.</span><span class="sxs-lookup"><span data-stu-id="92e83-119">We already added some basic customer information questions: Customer email, phone number, customer address, and customer notes.</span></span> <span data-ttu-id="92e83-120">При первом выполнении этого вопроса сведения о клиентах будут выделены серым цветом.</span><span class="sxs-lookup"><span data-stu-id="92e83-120">The first time you do this, the customer information questions are highlighted in gray.</span></span> <span data-ttu-id="92e83-121">Это означает, что пользователь увидит этот вопрос.</span><span class="sxs-lookup"><span data-stu-id="92e83-121">That means that the user will see this question.</span></span> <span data-ttu-id="92e83-122">Если вы выберете вопрос, рамка вокруг него исчезнет, а клиент не задаст этот вопрос.</span><span class="sxs-lookup"><span data-stu-id="92e83-122">If you select the question, the highlight box around it will disappear and your customer won't be asked that question.</span></span>

   <span data-ttu-id="92e83-123">В этом примере телефонный номер и заметки клиента были отключены, и мы создали два новых настраиваемых вопроса.</span><span class="sxs-lookup"><span data-stu-id="92e83-123">In this example, phone number and customer notes have been turned off and we created two new custom questions to ask.</span></span>

   ![Изображение экрана настраиваемых вопросов](../media/bookings-questions-custom-fields.png)

1. <span data-ttu-id="92e83-125">Чтобы сделать запрос необходимым, установите флажок **обязательно** .</span><span class="sxs-lookup"><span data-stu-id="92e83-125">To make the question required, select the **Required** checkbox.</span></span> <span data-ttu-id="92e83-126">Ваш клиент не сможет выполнять резервирование до тех пор, пока не ответит на необходимые вопросы.</span><span class="sxs-lookup"><span data-stu-id="92e83-126">Your customer won't be able to complete the booking until they've answered the required questions.</span></span>

1. <span data-ttu-id="92e83-127">Чтобы создать настраиваемый вопрос, выберите **Добавить вопрос** в верхней части панели.</span><span class="sxs-lookup"><span data-stu-id="92e83-127">To create a custom question, select **Add a question** from the top of the panel.</span></span> <span data-ttu-id="92e83-128">Напишите свой вопрос, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="92e83-128">Write your question, and then select **Save**.</span></span>

1. <span data-ttu-id="92e83-129">Щелкните вопрос, чтобы включить его.</span><span class="sxs-lookup"><span data-stu-id="92e83-129">Click on the question to enable it.</span></span> <span data-ttu-id="92e83-130">Рядом с ним отображается выделенное поле, и вопрос включается.</span><span class="sxs-lookup"><span data-stu-id="92e83-130">A highlighted box appears around it and the question is enabled.</span></span>

1. <span data-ttu-id="92e83-131">В верхней части страницы нажмите кнопку **ОК** , а затем **Сохраните службу**.</span><span class="sxs-lookup"><span data-stu-id="92e83-131">Click **Ok** at the top of the page, and then **Save the service**.</span></span>

<span data-ttu-id="92e83-132">При резервировании все пользовательские вопросы будут сохранены в основном списке, чтобы можно было легко добавлять вопросы в каждую службу, не требуя повторного ввода одних и тех же вопросов.</span><span class="sxs-lookup"><span data-stu-id="92e83-132">Bookings will save all of your custom questions in a master list so that you can easily add questions to each service without needing to repeatedly type the same questions.</span></span> <span data-ttu-id="92e83-133">Например, если вы откроете другую службу, вопрос, созданный для первой службы, будет отображаться в разделе Настраиваемые поля, но он вил будет отключен.</span><span class="sxs-lookup"><span data-stu-id="92e83-133">For example, if you open a different service, the question you created for the first service will show in the Custom fields section, but it wil be disabled.</span></span> <span data-ttu-id="92e83-134">Щелкните вопрос, чтобы отображался Выделенный прямоугольник, а вопрос включен.</span><span class="sxs-lookup"><span data-stu-id="92e83-134">Click the question so that a highlighted rectangle displays and the question is enabled.</span></span>

<span data-ttu-id="92e83-135">В этом примере показано, что для этой службы доступны вопросы, добавленные для первой службы.</span><span class="sxs-lookup"><span data-stu-id="92e83-135">In this example, you can see that the questions that were added for the first service are available for this service.</span></span> <span data-ttu-id="92e83-136">Все вопросы, которые вы создаете для этой службы, будут доступны для всех служб.</span><span class="sxs-lookup"><span data-stu-id="92e83-136">Any questions you create for this service will be available for all services.</span></span>

   ![Изображение вопросов, которые отображаются для нескольких служб](../media/bookings-questions-services.png)

<span data-ttu-id="92e83-138">Если страница резервирования уже опубликована, никаких других действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="92e83-138">If your booking page is already published, you don't need to do anything else.</span></span> <span data-ttu-id="92e83-139">Пользователи увидят вопросы, которые будут в следующий раз поступить к работе.</span><span class="sxs-lookup"><span data-stu-id="92e83-139">Customers will see the questions the next time they book with you.</span></span> <span data-ttu-id="92e83-140">Если страница резервирования еще не опубликована, перейдите на **страницу "резервирование** " из Outlook в Интернете, а затем нажмите **сохранить и опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="92e83-140">If your booking page isn't published yet, go to the **booking page** from Outlook on the web, and then select **Save and publish**.</span></span>

> [!WARNING]
> <span data-ttu-id="92e83-141">Вы также можете удалять вопросы из основного списка.</span><span class="sxs-lookup"><span data-stu-id="92e83-141">You can also delete questions from the master list.</span></span> <span data-ttu-id="92e83-142">Тем не менее, если вы удалите вопрос, он будет удален из каждой службы.</span><span class="sxs-lookup"><span data-stu-id="92e83-142">However, if you delete a question it will be deleted from every service.</span></span> <span data-ttu-id="92e83-143">Мы рекомендуем отключить вопрос, выбрав его, чтобы не повлиять на другие службы.</span><span class="sxs-lookup"><span data-stu-id="92e83-143">We recommend that you disable the question by selecting it to ensure you do not impact any other services.</span></span> <span data-ttu-id="92e83-144">Вы видите, что вопрос отключен, если он не заключен в выделенный прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="92e83-144">You can see that a question is disabled if it is not surrounded by a highlighted rectangle.</span></span>

## <a name="customer-experience"></a><span data-ttu-id="92e83-145">Взаимодействие с клиентами</span><span class="sxs-lookup"><span data-stu-id="92e83-145">Customer experience</span></span>

<span data-ttu-id="92e83-146">Когда ваши клиенты запланируют встречу с вами, в разделе **добавить сведения** будут отображаться основные вопросы о клиенте.</span><span class="sxs-lookup"><span data-stu-id="92e83-146">When your customers book an appointment with you, the basic customer information questions will show in the **Add your details** section.</span></span> <span data-ttu-id="92e83-147">Любые дополнительные вопросы, которые вы добавляете, будут находиться в разделе **предоставление дополнительных сведений** .</span><span class="sxs-lookup"><span data-stu-id="92e83-147">Any customized questions you add will be in the **Provide additional information** section.</span></span>

![Изображение, которое видят клиенты при включении вопросов](../media/bookings-questions-customer.png)

## <a name="staff-experience"></a><span data-ttu-id="92e83-149">Опыт работы сотрудников</span><span class="sxs-lookup"><span data-stu-id="92e83-149">Staff experience</span></span>

<span data-ttu-id="92e83-150">Когда ваши клиенты запланируют встречу с вами, сотрудники увидят вопросы и ответы клиентов в календаре резервирования.</span><span class="sxs-lookup"><span data-stu-id="92e83-150">When your customers book an appointment with you, your staff will see the questions and the customer's answers on the booking calendar.</span></span> <span data-ttu-id="92e83-151">Чтобы просмотреть его, перейдите в **Bookings** раздел \> **Календарь** книги и откройте встречу.</span><span class="sxs-lookup"><span data-stu-id="92e83-151">To see it, go to **Bookings** \> **Calendar** and then open an appointment.</span></span>

![Изображение того, что сотрудники видят при включении вопросов](../media/bookings-questions-staff.png)
