---
title: Включение и отключение Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Узнайте, как получить доступ к Microsoft Bookings в Microsoft 365.
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126603"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Включение и отключение Microsoft Bookings

Bookings можно отключить или отключить для всей организации или для определенных пользователей. Если вы включите Bookings для пользователей, они смогут создать страницу Bookings, создать календарь и разрешить другим пользователям резервировать время.

> [!NOTE]
> Средства администрирования, описанные в этих разделах, недоступны для клиентов Office 365 под управлением 21Vianet (Китай).

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Включите или отключите Bookings для своей организации с помощью Центра администрирования Microsoft 365

1. Во sign in to the Microsoft 365 admin center as a global admin.

2. В Центре администрирования перейдите в  **"Параметры**   \> **организации"** и выберите **Bookings.**

3. Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.

   > [!NOTE]
   > Отключение Bookings отключит весь доступ к службе, включая создание страниц Bookings и управление ими.

4. Выберите **"Сохранить изменения"**.

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Включите или отключите Bookings для своей организации с помощью PowerShell

Чтобы включить или отключить Bookings для вашей организации с помощью командлета [PowerShell Set-OrganizationConfig,](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)подключите к [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) и запустите следующую команду:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Включить или отключить Bookings для отдельных пользователей

Вы можете отключить Bookings для отдельных пользователей.

1. Перейдите в Центр администрирования Microsoft 365 и выберите **"Активные** \> **пользователи".**

1. Выберите нужного пользователя, а затем выберите **"Лицензии и приложения".**

1. Раз **развернуть приложения** и очистить этот контрольный список для Microsoft Bookings.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Требовать утверждения персонала перед обменом сведениями о занятости

Администраторы могут требовать от сотрудников своей организации получения доступа до того, как их сведения о доступности будут делиться через Bookings, и прежде чем их можно будет бронировать на странице резервирования. Этот параметр доступен в Центре администрирования Microsoft 365 **в** параметрах \>  \> **Bookings.**

Если этот параметр включен, сотрудники, добавленные в качестве сотрудников в календарях резервирования, будут находить ссылку "Утвердить или отклонить" в уведомлении по электронной почте, которое они получают.

Эта функция постепенно развертывается по всему миру для пользователей Microsoft 365. Если вы не видите этот параметр в Центре администрирования Microsoft 365, проверьте это в ближайшее время.

## <a name="block-social-sharing-options"></a>Блокировка параметров социального общего доступа

Администраторы могут управлять общим доступом к страницам резервирования в социальных сетях. Этот параметр доступен в Центре администрирования Microsoft 365 **в** параметрах \>  \> **Bookings.**

Эта функция постепенно развертывается по всему миру для пользователей Microsoft 365. Если вы не видите этот параметр в Центре администрирования Microsoft 365, проверьте это в ближайшее время.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Разрешить только выбранным пользователям создавать календари Bookings

С помощью ограничений политики вы можете запретить лицензированным пользователям создавать календари Bookings. Сначала необходимо включить Bookings для всей организации. Все пользователи в вашей организации будут иметь лицензии Bookings, но только пользователи, включенные в политику, могут создавать календари Bookings и иметь полный контроль над доступом к календарям, которые они создают.

Пользователи, включенные в эту политику, могут создавать новые календари Bookings и добавляться в качестве персонала в любой емкости (включая роль администратора) в существующие календари Bookings. Пользователи, не включенные в эту политику, не смогут создавать новые календари Bookings и получат сообщение об ошибке при попытке сделать это.

Вам потребуется выполнить следующие команды с помощью Exchange Online PowerShell. Дополнительные сведения о запуске exchange Online см. в подключении [к Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

> [!IMPORTANT]
> В шагах ниже предполагается, что в Outlook Web App почтовых ящиков (OWA) не были созданы другие политики почтовых ящиков OWA.

1. Создайте новую политику почтовых ящиков для пользователей, которые должны иметь возможность создавать календари Bookings. (Создание календаря Bookings по умолчанию разрешено новыми политиками почтовых ящиков.)

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Дополнительные сведения см. в [записи New-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)

2. Назначьте эту политику соответствующим пользователям, выировав эту команду для каждого пользователя, который должен предоставить разрешение на создание календарей Bookings.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Дополнительные сведения см. в статье [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).

3. Необязательно: если вы хотите отключить Bookings для всех остальных пользователей в вашей организации, запустите эту команду.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Дополнительные сведения см. в статье [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).

Дополнительные сведения о политиках почтовых ящиков OWA можно узнать в следующих темах:

- [Создание политики почтовых ящиков Outlook в Интернете в Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Применение или удаление политики почтовых ящиков Outlook в Интернете для почтового ящика в Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
