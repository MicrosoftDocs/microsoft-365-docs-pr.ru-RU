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
description: Используйте центр администрирования Microsoft 365 или Windows PowerShell для удаления календарей Bookings.
ms.openlocfilehash: 7407298adb402de79a1010b51544deee4b94cf5a
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/10/2021
ms.locfileid: "50604024"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="f8a7a-103">Удаление календаря бронирования в Bookings</span><span class="sxs-lookup"><span data-stu-id="f8a7a-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="f8a7a-104">В этой статье рассказывается, как можно удалить нежелательный календарь бронирования.</span><span class="sxs-lookup"><span data-stu-id="f8a7a-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="f8a7a-105">Календарь бронирования можно удалить в центре администрирования Microsoft 365 или использовать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8a7a-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="f8a7a-106">Календарь бронирования — это почтовый ящик в Exchange Online, поэтому для удаления календаря бронирования необходимо удалить соответствующую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="f8a7a-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8a7a-107">Все календари бронирования, созданные в 2017 году или ранее, должны быть удалены с помощью инструкций PowerShell по этому вопросу.</span><span class="sxs-lookup"><span data-stu-id="f8a7a-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="f8a7a-108">Все календари бронирования, созданные в 2018 году или после, могут быть удалены в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f8a7a-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="f8a7a-109">В календаре бронирования хранятся все релевантные сведения о календаре и данных бронирования, в том числе:</span><span class="sxs-lookup"><span data-stu-id="f8a7a-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="f8a7a-110">Бизнес-сведения, логотип и рабочие часы, добавленные при создания календаря бронирования</span><span class="sxs-lookup"><span data-stu-id="f8a7a-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="f8a7a-111">Соответствующие сотрудники и службы, добавленные при создания календаря бронирования</span><span class="sxs-lookup"><span data-stu-id="f8a7a-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="f8a7a-112">Все заказы и отключаемые встречи добавляются в календарь бронирования после его создания.</span><span class="sxs-lookup"><span data-stu-id="f8a7a-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="f8a7a-113">После удаления календаря бронирования эта дополнительная информация также будет удалена и не может быть восстановлена.</span><span class="sxs-lookup"><span data-stu-id="f8a7a-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="f8a7a-114">Удаление календаря бронирования в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f8a7a-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="f8a7a-115">Перейдите в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f8a7a-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="f8a7a-116">В Центре администрирования выберите пункт **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="f8a7a-116">In the Admin center, select **Users**.</span></span>

   ![Изображение пользовательского интерфейса пользователей в центре администрирования Microsoft 365](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="f8a7a-118">На странице **Активные пользователи** выберите имена пользователей, которых хотите удалить, и нажмите кнопку **Удалить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="f8a7a-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Изображение пользовательского интерфейса Delete User в центре администрирования Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="f8a7a-120">Удаление календаря бронирования с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8a7a-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="f8a7a-121">Предварительные условия и рекомендации по подключению к [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) см. в обзоре Connect to Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8a7a-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="f8a7a-122">Для выполнения этих действий необходимо использовать активное командное окно Microsoft PowerShell, которое было выполнено, выбрав параметр "Запуск в качестве администратора".</span><span class="sxs-lookup"><span data-stu-id="f8a7a-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="f8a7a-123">В окне PowerShell загрузите модуль EXO V2, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f8a7a-123">In a PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > <span data-ttu-id="f8a7a-124">Если [модуль EXO v2 уже установлен](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module), предыдущая команда будет действовать как написанная.</span><span class="sxs-lookup"><span data-stu-id="f8a7a-124">If you've already [installed the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module), the previous command will work as written.</span></span>
   
2. <span data-ttu-id="f8a7a-125">В команде, которую вам нужно выполнить, используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f8a7a-125">The command that you need to run uses the following syntax:</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - <span data-ttu-id="f8a7a-126">_\<UPN\>_  — ваша учетная запись в формате имени субъекта-пользователя (например, `john@contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="f8a7a-126">_\<UPN\>_ is your account in user principal name format (for example, `john@contoso.com`).</span></span>

3. <span data-ttu-id="f8a7a-127">Когда вам будет предложено, войдите в систему с учетными данными администратора клиента Microsoft 365, в котором размещен календарь бронирования, который необходимо удалить навсегда.</span><span class="sxs-lookup"><span data-stu-id="f8a7a-127">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

4. <span data-ttu-id="f8a7a-128">Когда обработка этой команды завершится, введите следующую команду, чтобы получить список почтовых ящиков резервирования в вашем клиенте:</span><span class="sxs-lookup"><span data-stu-id="f8a7a-128">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails Scheduling
   ```

5. <span data-ttu-id="f8a7a-129">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f8a7a-129">Type the following command:</span></span>

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="f8a7a-130">Будьте осторожны, чтобы ввести точное имя псевдонима почтовых ящиков бронирования, которые необходимо удалить навсегда.</span><span class="sxs-lookup"><span data-stu-id="f8a7a-130">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

6. <span data-ttu-id="f8a7a-131">Чтобы убедиться, что календарь удален, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f8a7a-131">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   <span data-ttu-id="f8a7a-132">Удаленный календарь не будет отображаться в выходе.</span><span class="sxs-lookup"><span data-stu-id="f8a7a-132">The deleted calendar will not appear in the output.</span></span>
