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
description: Используйте Центр администрирования Microsoft 365 или Windows PowerShell для удаления календарей Bookings.
ms.openlocfilehash: 2fcb92cee18d709ef0e1fa3faa0246e622a9f9db
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126653"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="f6ee9-103">Удаление календаря резервирования в Bookings</span><span class="sxs-lookup"><span data-stu-id="f6ee9-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="f6ee9-104">В этой статье объясняется, как удалить календарь нежелательного резервирования.</span><span class="sxs-lookup"><span data-stu-id="f6ee9-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="f6ee9-105">Вы можете удалить календарь резервирования в Центре администрирования Microsoft 365 или использовать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6ee9-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="f6ee9-106">Календарь Bookings — это почтовый ящик в Exchange Online, поэтому необходимо удалить соответствующую учетную запись пользователя, чтобы удалить календарь резервирования.</span><span class="sxs-lookup"><span data-stu-id="f6ee9-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6ee9-107">Все календари резервирования, созданные в 2017 г. или до этого, необходимо удалить с помощью инструкций PowerShell по этой теме.</span><span class="sxs-lookup"><span data-stu-id="f6ee9-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="f6ee9-108">Все календари резервирования, созданные в 2018 г. или после этого, можно удалить в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f6ee9-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="f6ee9-109">В календаре резервирования хранятся все релевантные сведения о календаре и данных резервирования, в том числе:</span><span class="sxs-lookup"><span data-stu-id="f6ee9-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="f6ee9-110">Бизнес-информация, логотип и рабочие часы, добавленные при создания календаря резервирования</span><span class="sxs-lookup"><span data-stu-id="f6ee9-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="f6ee9-111">Соответствующие сотрудники и службы, добавленные при создания календаря резервирования</span><span class="sxs-lookup"><span data-stu-id="f6ee9-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="f6ee9-112">Все резервирования и встречи, добавленные в календарь резервирования после его создания.</span><span class="sxs-lookup"><span data-stu-id="f6ee9-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="f6ee9-113">После удаления календаря резервирования эти дополнительные сведения также окончательно удаляются и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="f6ee9-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="f6ee9-114">Удаление календаря резервирования в Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f6ee9-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="f6ee9-115">Перейдите в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f6ee9-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="f6ee9-116">В Центре администрирования выберите пункт **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="f6ee9-116">In the Admin center, select **Users**.</span></span>

   ![Изображение пользовательского интерфейса пользователей в Центре администрирования Microsoft 365](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="f6ee9-118">На странице **Активные пользователи** выберите имена пользователей, которых хотите удалить, и нажмите кнопку **Удалить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="f6ee9-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Изображение удаления пользовательского интерфейса пользователя в Центре администрирования Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="f6ee9-120">Удаление календаря резервирования с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6ee9-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="f6ee9-121">Необходимые условия и рекомендации по подключению к [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) см. в подключении к Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6ee9-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="f6ee9-122">Для выполнения этих действий необходимо использовать активное командное окно Microsoft PowerShell, которое вы запустили, выбрав параметр "Запуск от администратора".</span><span class="sxs-lookup"><span data-stu-id="f6ee9-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="f6ee9-123">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f6ee9-123">Enter the following command:</span></span>

   ```PowerShell
    $user = get-credential
   ```

1. <span data-ttu-id="f6ee9-124">Когда вам будет предложено войти с помощью учетных данных администратора клиента, войдите в клиент Microsoft 365, в котором размещен календарь резервирования, который вы хотите окончательно удалить.</span><span class="sxs-lookup"><span data-stu-id="f6ee9-124">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

1. <span data-ttu-id="f6ee9-125">В командной командной области PowerShell введите команду:</span><span class="sxs-lookup"><span data-stu-id="f6ee9-125">At the PowerShell command prompt, enter this command:</span></span>

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. <span data-ttu-id="f6ee9-126">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f6ee9-126">Enter the following command:</span></span>

   ```PowerShell
    Import-PSSession $s
   ```

1. <span data-ttu-id="f6ee9-127">Когда обработка этой команды завершится, введите следующую команду, чтобы получить список почтовых ящиков резервирования в вашем клиенте:</span><span class="sxs-lookup"><span data-stu-id="f6ee9-127">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. <span data-ttu-id="f6ee9-128">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f6ee9-128">Type the following command:</span></span>

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="f6ee9-129">Будьте осторожны, чтобы ввести точное имя псевдонима почтового ящика резервирования, который вы хотите окончательно удалить.</span><span class="sxs-lookup"><span data-stu-id="f6ee9-129">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

1. <span data-ttu-id="f6ee9-130">Чтобы убедиться, что календарь удален, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f6ee9-130">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   <span data-ttu-id="f6ee9-131">Удаленный календарь не будет отображаться в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f6ee9-131">The deleted calendar will not appear in the output.</span></span>
