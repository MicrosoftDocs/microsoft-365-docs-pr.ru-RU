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
description: Узнайте, как получить доступ к microsoft Bookings в Microsoft 365.
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913770"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Включение и отключение Microsoft Bookings

Бронирование может быть включено или отключено для всей организации или для определенных пользователей. При включании резервирования для пользователей они могут создать страницу Bookings, создать календарь и разрешить другим пользователям бронировать время с ними.

> [!NOTE]
> Элементы управления администратора, описанные в этих разделах, недоступны для клиентов Office 365, управляемых 21Vianet (Китай).

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Включить или отключить бронирование для организации с помощью центра администрирования Microsoft 365

1. Вопишитесь в центр администрирования Microsoft 365 в качестве глобального администратора.

2. В центре администрирования перейдите в  **параметры**   \> **параметров org и** выберите **Bookings**.

3. Выберите почтовый ящик для разрешить вашей организации **использовать Bookings,** чтобы включить или отключить Бронирование для вашей организации.

   > [!NOTE]
   > Отключение bookings отключит весь доступ к службе, включая создание и управление страницами Bookings.

4. Выберите **Сохранить изменения.**

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Включить или отключить бронирование для организации с помощью PowerShell

Чтобы включить или отключить бронирование для вашей организации с помощью командлета [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) [PowerShell PowerShell PowerShell,](/powershell/exchange/connect-to-exchange-online-powershell) подключись к Exchange Online PowerShell и запустите следующую команду:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Включить или отключить бронирование для отдельных пользователей

Вы можете отключить бронирование для отдельных пользователей.

1. Перейдите в центр администрирования Microsoft 365, а затем выберите **пользователей Users** \> **Active.**

1. Выберите нужного пользователя, а затем выберите **лицензии и приложения.**

1. Расширение **приложений** и очистка почтового ящика для Microsoft Bookings.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Требуются утверждения сотрудников перед обменом бесплатными и занятыми сведениями

Администраторы могут требовать от сотрудников в их организации сделать выбор до того, как их сведения о доступности будут делиться через Bookings и прежде чем их можно будет забронировать на странице бронирования. Этот параметр доступен в центре администрирования Microsoft 365 в соответствии с **настройками** \>  \> **параметров.**

Когда этот параметр включен, сотрудники, добавленные в качестве сотрудников в календарях бронирования, найдут ссылку Утверждение или Отклонение в получаемом уведомлении электронной почты.

Эта функция постепенно развертывается по всему миру для клиентов Microsoft 365. Если вы не видите этот параметр в центре администрирования Microsoft 365, проверьте это в ближайшее время.

## <a name="block-social-sharing-options"></a>Блокировка параметров социального обмена

Администраторы могут управлять общим доступом к страницам бронирования в социальных сетях. Этот параметр доступен в центре администрирования Microsoft 365 в соответствии с **настройками** \>  \> **параметров.**

Эта функция постепенно развертывается по всему миру для клиентов Microsoft 365. Если вы не видите этот параметр в центре администрирования Microsoft 365, проверьте это в ближайшее время.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Разрешить создавать календари Bookings только выбранным пользователям

С помощью ограничений политики можно запретить лицензированным пользователям создавать календари бронирований. Сначала необходимо включить бронирование для всей организации. Все пользователи в вашей организации будут иметь лицензии Bookings, но только те, которые включены в политику, могут создавать календари bookings и иметь полный контроль над тем, кто может получить доступ к создамым календарям.

Пользователи, включенные в эту политику, могут создавать новые календари резервирования и добавляться в качестве персонала в любом качестве (включая роль администратора) в существующие календари bookings. Пользователи, не включенные в эту политику, не смогут создавать новые календари резервирования и получат сообщение об ошибке, если они попытаются это сделать.

Вам потребуется выполнить следующие команды с помощью Exchange Online PowerShell. Дополнительные сведения о запуске комлетов Exchange Online см. в рублях [Connect to Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

> [!IMPORTANT]
> Ниже приведены действия, которые предполагают, что Outlook Web App почтовых ящиков в вашей организации не были созданы никакие другие политики почтовых ящиков Outlook Web App OWA.

1. Создайте новую политику почтовых ящиков для пользователей, которые должны иметь право создавать календари бронирований. (Создание календаря резервирования по умолчанию разрешено новыми политиками почтовых ящиков.)

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Дополнительные сведения см. [в сообщении New-OwaMailboxPolicy.](/powershell/module/exchange/new-owamailboxpolicy)

2. Назначьте эту политику соответствующим пользователям, запуская эту команду для каждого пользователя, который должен предоставить разрешение на создание календарей bookings.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Дополнительные сведения см. в статье [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).

3. Необязательный вариант: запустите эту команду, если вы хотите отключить Bookings для всех остальных пользователей в вашей организации.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Дополнительные сведения см. в статье [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).

Дополнительные сведения о политиках почтовых ящиков OWA можно узнать по следующим темам:

- [Создание Outlook для политики веб-почтовых ящиков в Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Применить или удалить Outlook в политике веб-почтовых ящиков на почтовом ящике в Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)