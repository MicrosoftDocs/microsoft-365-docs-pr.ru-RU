---
title: Удаление календаря резервирования
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Используйте центр администрирования Microsoft 365 или Windows PowerShell, чтобы удалить календари резервирования.
ms.openlocfilehash: 3a1cb1c54f60247ab72056b3e39b56b0981228b7
ms.sourcegitcommit: eb3c30d53a5434d8bad7c8f48a5612f3e2675945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422446"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="064ff-103">Удаление календаря резервирования в резервированиях</span><span class="sxs-lookup"><span data-stu-id="064ff-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="064ff-104">В этой статье объясняется, как можно удалить нежелательный календарь резервирования.</span><span class="sxs-lookup"><span data-stu-id="064ff-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="064ff-105">Вы можете удалить календарь резервирования в центре администрирования Microsoft 365 или использовать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="064ff-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="064ff-106">Книга "книги" является почтовым ящиком в Exchange Online, поэтому удалите соответствующую учетную запись пользователя, чтобы удалить календарь резервирования.</span><span class="sxs-lookup"><span data-stu-id="064ff-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="064ff-107">Все календари резервирования, созданные в 2017 или до, необходимо удалить с помощью инструкций PowerShell, приведенных в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="064ff-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="064ff-108">Все календари резервирования, созданные в 2018 или After, можно удалить в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="064ff-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="064ff-109">Календарь резервирования содержит все релевантные сведения об этом календаре резервирования и данных, в том числе:</span><span class="sxs-lookup"><span data-stu-id="064ff-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="064ff-110">Деловые сведения, логотип и рабочие часы, добавленные при создании календаря резервирования</span><span class="sxs-lookup"><span data-stu-id="064ff-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="064ff-111">Подходящие сотрудники и службы, добавленные при создании календаря резервирования</span><span class="sxs-lookup"><span data-stu-id="064ff-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="064ff-112">Все резервирования и временные встречи, добавленные в календарь резервирования после его создания.</span><span class="sxs-lookup"><span data-stu-id="064ff-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="064ff-113">После удаления календаря резервирования эти дополнительные сведения также безвозвратно удаляются и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="064ff-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="064ff-114">Удаление календаря резервирования в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="064ff-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="064ff-115">Перейдите в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="064ff-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="064ff-116">В Центре администрирования выберите пункт **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="064ff-116">In the Admin center, select **Users**.</span></span>

   ![Изображение пользовательского интерфейса "Пользователи" в центре администрирования Microsoft 365](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="064ff-118">На странице **Активные пользователи** выберите имена пользователей, которых хотите удалить, и нажмите кнопку **Удалить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="064ff-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Изображение элемента пользовательского интерфейса "Удаление пользователя" в центре администрирования Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="064ff-120">Удаление календаря резервирования с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="064ff-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="064ff-121">Необходимые условия и рекомендации по подключению к Exchange Online PowerShell приведены [в статье подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) .</span><span class="sxs-lookup"><span data-stu-id="064ff-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="064ff-122">Для выполнения этих действий необходимо использовать активное командное окно Microsoft PowerShell, которое было запущено, выбрав параметр "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="064ff-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="064ff-123">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="064ff-123">Enter the following command:</span></span>

   ```PowerShell
    $user = get-credential
   ```

1. <span data-ttu-id="064ff-124">При появлении соответствующего запроса войдите в систему, используя учетные данные администратора клиента для клиента Microsoft 365, на котором размещается календарь резервирования, который требуется окончательно удалить.</span><span class="sxs-lookup"><span data-stu-id="064ff-124">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

1. <span data-ttu-id="064ff-125">В командной строки PowerShell введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="064ff-125">At the PowerShell command prompt, enter this command:</span></span>

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. <span data-ttu-id="064ff-126">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="064ff-126">Enter the following command:</span></span>

   ```PowerShell
    Import-PSSession $s
   ```

1. <span data-ttu-id="064ff-127">Когда обработка этой команды завершится, введите следующую команду, чтобы получить список почтовых ящиков резервирования в вашем клиенте:</span><span class="sxs-lookup"><span data-stu-id="064ff-127">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. <span data-ttu-id="064ff-128">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="064ff-128">Type the following command:</span></span>

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="064ff-129">Будьте осторожны, чтобы ввести точное имя псевдонима почтового ящика, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="064ff-129">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

1. <span data-ttu-id="064ff-130">Чтобы убедиться, что календарь удален, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="064ff-130">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   <span data-ttu-id="064ff-131">Удаленный календарь не будет отображаться в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="064ff-131">The deleted calendar will not appear in the output.</span></span>
