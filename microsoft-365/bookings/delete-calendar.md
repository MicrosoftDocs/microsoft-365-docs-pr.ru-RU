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
ms.openlocfilehash: 1ef67ce4dbf67da6f081106815f76ff85f11ef92
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288447"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="0c549-103">Удаление календаря бронирования в Bookings</span><span class="sxs-lookup"><span data-stu-id="0c549-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="0c549-104">В этой статье рассказывается, как можно удалить нежелательный календарь бронирования.</span><span class="sxs-lookup"><span data-stu-id="0c549-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="0c549-105">Календарь бронирования можно удалить в Центр администрирования Microsoft 365 или использовать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c549-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="0c549-106">Календарь Bookings — это почтовый ящик в Exchange Online поэтому для удаления календаря бронирования необходимо удалить соответствующую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="0c549-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c549-107">Все календари бронирования, созданные в 2017 году или ранее, должны быть удалены с помощью инструкций PowerShell по этому вопросу.</span><span class="sxs-lookup"><span data-stu-id="0c549-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="0c549-108">Все календари бронирования, созданные в 2018 г. или после этого, можно удалить в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c549-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="0c549-109">В календаре бронирования хранятся все релевантные сведения о календаре и данных бронирования, в том числе:</span><span class="sxs-lookup"><span data-stu-id="0c549-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="0c549-110">Бизнес-сведения, логотип и рабочие часы, добавленные при создания календаря бронирования</span><span class="sxs-lookup"><span data-stu-id="0c549-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="0c549-111">Соответствующие сотрудники и службы, добавленные при создания календаря бронирования</span><span class="sxs-lookup"><span data-stu-id="0c549-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="0c549-112">Все заказы и отключаемые встречи добавляются в календарь бронирования после его создания.</span><span class="sxs-lookup"><span data-stu-id="0c549-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="0c549-113">После удаления календаря бронирования эта дополнительная информация также будет удалена и не может быть восстановлена.</span><span class="sxs-lookup"><span data-stu-id="0c549-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="0c549-114">Удаление календаря бронирования в Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c549-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="0c549-115">Перейдите в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c549-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="0c549-116">В Центре администрирования выберите пункт **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="0c549-116">In the Admin center, select **Users**.</span></span>

   ![Изображение пользовательского интерфейса пользователей в Центр администрирования Microsoft 365](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="0c549-118">На странице **Активные пользователи** выберите имена пользователей, которых хотите удалить, и нажмите кнопку **Удалить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="0c549-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Изображение пользовательского интерфейса delete user in Центр администрирования Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="0c549-120">Удаление календаря бронирования с Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c549-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="0c549-121">См. [Подключение в Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell-v2) для необходимых условий и рекомендаций по подключению к Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c549-121">See [Connect to Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell-v2) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="0c549-122">Для выполнения этих действий необходимо использовать активное командное окно Microsoft PowerShell, которое было выполнено, выбрав параметр "Запуск в качестве администратора".</span><span class="sxs-lookup"><span data-stu-id="0c549-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="0c549-123">В окне PowerShell загрузите модуль EXO V2, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0c549-123">In a PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > <span data-ttu-id="0c549-124">Если [модуль EXO v2 уже установлен](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module), предыдущая команда будет действовать как написанная.</span><span class="sxs-lookup"><span data-stu-id="0c549-124">If you've already [installed the EXO V2 module](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module), the previous command will work as written.</span></span>
   
2. <span data-ttu-id="0c549-125">В команде, которую вам нужно выполнить, используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="0c549-125">The command that you need to run uses the following syntax:</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - <span data-ttu-id="0c549-126">_\<UPN\>_  — ваша учетная запись в формате имени субъекта-пользователя (например, `john@contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="0c549-126">_\<UPN\>_ is your account in user principal name format (for example, `john@contoso.com`).</span></span>

3. <span data-ttu-id="0c549-127">При запросе войдите в систему с учетными данными администратора клиента Microsoft 365, в котором размещен календарь бронирования, который необходимо удалить навсегда.</span><span class="sxs-lookup"><span data-stu-id="0c549-127">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

4. <span data-ttu-id="0c549-128">Когда обработка этой команды завершится, введите следующую команду, чтобы получить список почтовых ящиков резервирования в вашем клиенте:</span><span class="sxs-lookup"><span data-stu-id="0c549-128">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

5. <span data-ttu-id="0c549-129">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0c549-129">Type the following command:</span></span>

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="0c549-130">Будьте осторожны, чтобы ввести точное имя псевдонима почтовых ящиков бронирования, которые необходимо удалить навсегда.</span><span class="sxs-lookup"><span data-stu-id="0c549-130">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

6. <span data-ttu-id="0c549-131">Чтобы убедиться, что календарь удален, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0c549-131">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   <span data-ttu-id="0c549-132">Удаленный календарь не будет отображаться в выходе.</span><span class="sxs-lookup"><span data-stu-id="0c549-132">The deleted calendar will not appear in the output.</span></span>
