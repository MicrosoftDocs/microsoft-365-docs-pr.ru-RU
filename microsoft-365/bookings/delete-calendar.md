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
# <a name="delete-a-booking-calendar-in-bookings"></a>Удаление календаря резервирования в Bookings

В этой статье объясняется, как удалить календарь нежелательного резервирования. Вы можете удалить календарь резервирования в Центре администрирования Microsoft 365 или использовать PowerShell. Календарь Bookings — это почтовый ящик в Exchange Online, поэтому необходимо удалить соответствующую учетную запись пользователя, чтобы удалить календарь резервирования.

> [!IMPORTANT]
> Все календари резервирования, созданные в 2017 г. или до этого, необходимо удалить с помощью инструкций PowerShell по этой теме. Все календари резервирования, созданные в 2018 г. или после этого, можно удалить в Центре администрирования Microsoft 365.

В календаре резервирования хранятся все релевантные сведения о календаре и данных резервирования, в том числе:

- Бизнес-информация, логотип и рабочие часы, добавленные при создания календаря резервирования
- Соответствующие сотрудники и службы, добавленные при создания календаря резервирования
- Все резервирования и встречи, добавленные в календарь резервирования после его создания.

> [!WARNING]
> После удаления календаря резервирования эти дополнительные сведения также окончательно удаляются и не могут быть восстановлены.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Удаление календаря резервирования в Центре администрирования Microsoft 365

1. Перейдите в Центр администрирования Microsoft 365.

1. В Центре администрирования выберите пункт **Пользователи**.

   ![Изображение пользовательского интерфейса пользователей в Центре администрирования Microsoft 365](../media/bookings-admin-center-users.png)

1. На странице **Активные пользователи** выберите имена пользователей, которых хотите удалить, и нажмите кнопку **Удалить пользователя**.

   ![Изображение удаления пользовательского интерфейса пользователя в Центре администрирования Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Удаление календаря резервирования с помощью Exchange Online PowerShell

Необходимые условия и рекомендации по подключению к [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) см. в подключении к Exchange Online PowerShell.

Для выполнения этих действий необходимо использовать активное командное окно Microsoft PowerShell, которое вы запустили, выбрав параметр "Запуск от администратора".

1. Введите следующую команду:

   ```PowerShell
    $user = get-credential
   ```

1. Когда вам будет предложено войти с помощью учетных данных администратора клиента, войдите в клиент Microsoft 365, в котором размещен календарь резервирования, который вы хотите окончательно удалить.

1. В командной командной области PowerShell введите команду:

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. Введите следующую команду:

   ```PowerShell
    Import-PSSession $s
   ```

1. Когда обработка этой команды завершится, введите следующую команду, чтобы получить список почтовых ящиков резервирования в вашем клиенте:

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. Введите следующую команду:

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > Будьте осторожны, чтобы ввести точное имя псевдонима почтового ящика резервирования, который вы хотите окончательно удалить.

1. Чтобы убедиться, что календарь удален, введите следующую команду:

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   Удаленный календарь не будет отображаться в выходных данных.
