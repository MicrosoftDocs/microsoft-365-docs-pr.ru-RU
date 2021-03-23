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
ms.openlocfilehash: 21fc7b9994ffd7f76ed04000a50bd0ee8f7f167e
ms.sourcegitcommit: 8998f70d3f7bd673f93f8d1cf12ce981b1b771c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51034095"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Удаление календаря бронирования в Bookings

В этой статье рассказывается, как можно удалить нежелательный календарь бронирования. Календарь бронирования можно удалить в центре администрирования Microsoft 365 или использовать PowerShell. Календарь бронирования — это почтовый ящик в Exchange Online, поэтому для удаления календаря бронирования необходимо удалить соответствующую учетную запись пользователя.

> [!IMPORTANT]
> Все календари бронирования, созданные в 2017 году или ранее, должны быть удалены с помощью инструкций PowerShell по этому вопросу. Все календари бронирования, созданные в 2018 году или после, могут быть удалены в центре администрирования Microsoft 365.

В календаре бронирования хранятся все релевантные сведения о календаре и данных бронирования, в том числе:

- Бизнес-сведения, логотип и рабочие часы, добавленные при создания календаря бронирования
- Соответствующие сотрудники и службы, добавленные при создания календаря бронирования
- Все заказы и отключаемые встречи добавляются в календарь бронирования после его создания.

> [!WARNING]
> После удаления календаря бронирования эта дополнительная информация также будет удалена и не может быть восстановлена.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Удаление календаря бронирования в центре администрирования Microsoft 365

1. Перейдите в Центр администрирования Microsoft 365.

1. В Центре администрирования выберите пункт **Пользователи**.

   ![Изображение пользовательского интерфейса пользователей в центре администрирования Microsoft 365](../media/bookings-admin-center-users.png)

1. На странице **Активные пользователи** выберите имена пользователей, которых хотите удалить, и нажмите кнопку **Удалить пользователя**.

   ![Изображение пользовательского интерфейса Delete User в центре администрирования Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Удаление календаря бронирования с помощью Exchange Online PowerShell

Предварительные условия и рекомендации по подключению к [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) см. в обзоре Connect to Exchange Online PowerShell.

Для выполнения этих действий необходимо использовать активное командное окно Microsoft PowerShell, которое было выполнено, выбрав параметр "Запуск в качестве администратора".

1. В окне PowerShell загрузите модуль EXO V2, выполнив следующую команду:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > Если [модуль EXO v2 уже установлен](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module), предыдущая команда будет действовать как написанная.
   
2. В команде, которую вам нужно выполнить, используется следующий синтаксис:

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - _\<UPN\>_  — ваша учетная запись в формате имени субъекта-пользователя (например, `john@contoso.com`).

3. Когда вам будет предложено, войдите в систему с учетными данными администратора клиента Microsoft 365, в котором размещен календарь бронирования, который необходимо удалить навсегда.

4. Когда обработка этой команды завершится, введите следующую команду, чтобы получить список почтовых ящиков резервирования в вашем клиенте:

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

5. Введите следующую команду:

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > Будьте осторожны, чтобы ввести точное имя псевдонима почтовых ящиков бронирования, которые необходимо удалить навсегда.

6. Чтобы убедиться, что календарь удален, введите следующую команду:

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   Удаленный календарь не будет отображаться в выходе.
