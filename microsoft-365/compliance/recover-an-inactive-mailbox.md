---
title: Возврат неактивного почтового ящика
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
ms.custom: seo-marvel-apr2020
description: Узнайте, как восстановить содержимое неактивного почтового ящика в Office 365 путем преобразования его в новый почтовый ящик, содержащий содержимое неактивного почтового ящика.
ms.openlocfilehash: e7f5ea9e3d47bf6b7ee6de495d2f5f47984cdf8f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926177"
---
# <a name="recover-an-inactive-mailbox"></a>Возврат неактивного почтового ящика

Неактивный почтовый ящик (тип обратимо удаленного почтового ящика) используется для сохранения электронной почты бывшего сотрудника после ухода из организации. Если этот сотрудник возвращается в организацию или другой сотрудник берет на себя обязанности бывшего сотрудника, существует два способа сделать содержимое неактивного почтового ящика доступным пользователю:

- **Восстановление неактивного почтового ящика.** Если бывший сотрудник возвращается в организацию или если новый сотрудник нанят для того, чтобы взять на себя обязанности бывшего сотрудника, вы можете восстановить содержимое неактивного почтового ящика. Этот метод преобразует неактивный почтовый ящик в новый активный почтовый ящик, содержащий содержимое неактивного почтового ящика. После восстановления неактивный почтовый ящик больше не существует. В этом разделе описывается этот метод.

- **Восстановление неактивного почтового ящика.** Если другой сотрудник берет на себя обязанности бывшего сотрудника или если другому пользователю необходим доступ к содержимому неактивного почтового ящика, можно восстановить (или объединить) содержимое неактивного почтового ящика в существующий почтовый ящик. Можно также восстановить архив из неактивного почтового ящика. Процедуры для этого метода см. в примере Восстановление неактивного почтового [ящика в Office 365.](restore-an-inactive-mailbox.md)

В разделе [Дополнительные сведения](#more-information) представлены дополнительные сведения о различиях между восстановлением и возвратом неактивного почтового ящика, а также описание того, что происходит при возврате неактивного почтового ящика.

> [!NOTE]
> Восстановить или восстановить неактивный почтовый ящик, настроенный с помощью архива автоматического расширения, не удалось. Если необходимо восстановить данные из неактивного почтового ящика с автоматически расширяющийся архив, используйте поиск контента для экспорта данных из почтового ящика и импорта в другой почтовый ящик. Инструкции см. в следующих разделах:
>
> - [Поиск контента](content-search.md)
> - [Экспорт результатов поиска контента](export-search-results.md)

## <a name="requirements-to-recover-an-inactive-mailbox"></a>Требования по восстановлению неактивного почтового ящика

- Для восстановления неактивного почтового ящика Exchange Online PowerShell. Вы не можете сделать этого в Центре администрирования Exchange (EAC). Пошаговые инструкции см. в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Выполните следующую команду, чтобы отобразить сведения о неактивных почтовых ящиках в организации.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  Используйте полученную информацию для возврата определенного неактивного почтового ящика.

## <a name="recover-inactive-mailboxes"></a>Восстановление неактивных почтовых ящиков

Чтобы **восстановить неактивный** почтовый ящик, используйте комлет New-Mailbox с параметром *InactiveMailbox.*

1. Создайте переменную, содержащую свойства неактивного почтового ящика.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > В предыдущей команде используйте значение свойства **DistinguishedName** или **ExchangeGUID** для определения неактивного почтового ящика. Эти свойства уникальны для каждого почтового ящика в организации, тогда как у активного и неактивного почтового ящика может быть один и тот же основной SMTP-адрес.

2. В этом примере используются свойства, полученные в предыдущей команде, а неактивный почтовый ящик восстанавливается в активный почтовый ящик пользователя Ann Beebe. Убедитесь, что значения, указанные для параметров  *Name*  и  *MicrosoftOnlineServicesID,*  уникальны в организации.

   ```powershell
   New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
   ```

   Основной адрес SMTP для восстановленного неактивного почтового ящика будет иметь такое же значение, как и тот, который указан *параметром MicrosoftOnlineServicesID.*

После восстановления неактивного почтового ящика также создается новая учетная запись пользователя. Необходимо активировать эту учетную запись пользователя, назначив лицензию. Чтобы назначить лицензию в центре администрирования Microsoft 365, см. в руб. Добавить пользователей и одновременно назначить [лицензии.](../admin/add-users/add-users.md)

## <a name="more-information"></a>Дополнительные сведения

- **В чем основное различие между возвратом и восстановление неактивного почтового ящика?** При восстановлении неактивного почтового ящика почтовый ящик преобразуется в новый почтовый ящик, содержимое и структура папок неактивного почтового ящика сохраняются, а почтовый ящик связан с новой учетной записью пользователя. После возврата неактивный почтовый ящик больше не существует, и любые изменения, внесенные в его содержимое, влияют на содержимое, который изначально удерживался в неактивном почтовом ящике. При восстановлении неактивного почтового ящика его содержимое просто копируется в другой почтовый ящик. Неактивный почтовый ящик сохраняется и остается неактивным. Любые изменения, внесенные в содержимое целевого почтового ящика, не повлияет на исходное содержимое в неактивном почтовом ящике. В неактивном почтовом ящике по-прежнему можно осуществлять поиск с помощью обнаружения электронных данных на месте, его можно восстановить в другой почтовый ящик, можно восстановить сам ящик или удалить его.

- **Что происходит при возврате неактивного почтового ящика?** При возврате неактивного почтового ящика, происходит следующее.

  - Удержание, которое было применено к неактивному почтовому ящику, меняется или удаляется в зависимости от типа удержания, примененного к неактивному почтовому ящику до его восстановления.

    - **Удержание судебного разбирательства.** Если для неактивного почтового ящика включено удержание судебного разбирательства, он удаляется из восстановленного почтового ящика.

    - **Удержание на** In-Place удаляется из восстановленного почтового ящика. Это означает, что восстановленный почтовый ящик удаляется как исходный почтовый ящик из любого In-Place или In-Place поиска об обнаружении электронных сообщений.

    - **Microsoft 365 хранения с помощью блокировки сохранения.** Если неактивному почтовому ящику назначена политика хранения с помощью блокировки сохранения (называемой политикой хранения *заблокированных),* восстановленный почтовый ящик назначен той же политике хранения с блокировкой. Дополнительные сведения о заблокированных политиках хранения см. в см. в руб. [ Используйте блокировку сохранения, чтобы ограничить изменения политик хранения и политик меток[хранения.](retention-preservation-lock.md)

    - **Microsoft 365 хранения без блокировки сохранения.** Неактивный почтовый ящик удаляется из Microsoft 365 политики хранения, применяемой к ней. Однако в восстановленных почтовых ящиках включено удержание судебного разбирательства, чтобы предотвратить удаление контента почтовых ящиков на основе любых политик хранения для всей организации, удаляемой контентом старше определенного возраста. Вы можете сохранить удержание судебного разбирательства или удалить его. Дополнительные сведения см. в [дополнительных сведениях о создании судебного удержания.](create-a-litigation-hold.md)

  - Период восстановления одного элемента (который определяется свойством почтового ящика **RetainDeletedItemsFor** )  30 дней. Как правило, при создании почтового ящика в Exchange Online период хранения задан как 14 дней. Если установить максимальное значение (30 дней), вы получите больше времени для восстановления окончательно удаленных (или очищенных) данных из неактивного почтового ящика. Можно также отключить восстановление одного элемента или вернуть период восстановления элемента по умолчанию (14 дней). Дополнительные сведения см. в разделе [Enable or disable single item recovery for a mailbox](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-single-item-recovery).

  - Приостановка хранения включена с длительностью 30 дней. Это означает, что политика хранения Exchange по умолчанию и все Exchange или Microsoft 365, которые назначены новому почтовому ящику, не будут обрабатываться в течение 30 дней. Это дает возвращаемого сотрудника или нового владельца восстановленного неактивного почтового ящика время для управления старыми сообщениями. В противном случае политика хранения Exchange или Microsoft 365 может удалять старые элементы почтовых ящиков (или переместить элементы в архивный почтовый ящик, если он включен), срок действия которых истек в зависимости от параметров, настроенных для политик хранения Exchange или Microsoft 365. По истечении 30 дней срок хранения истекает, свойство хранения почтовых ящиков **RetentionHoldEnabled** задалось **false,** и помощник по управляемым папкам начинает обработку политик, назначенных почтовому ящику. Если вам не нужно это дополнительное время, можно просто удалить удержание хранения. Кроме того, можно увеличить продолжительность приостановки хранения, используя команду **Set-Mailbox -EndDateForRetentionHold**. Дополнительные сведения см. в разделе [Place a mailbox on retention hold](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).

- **Включите удержание для восстановленного почтового ящика, если вам необходимо сохранить его исходное состояние.** Чтобы новый владелец или политика хранения почтовых ящиков не удаляли все сообщения из восстановленного неактивного почтового ящика, можно разместить почтовый ящик в удержании судебного разбирательства. Дополнительные сведения см. в [дополнительных сведениях о создании судебного удержания.](./create-a-litigation-hold.md)

- **Какой идентификатор пользователя можно применять при восстановлении неактивного почтового ящика?** При восстановлении неактивного почтового ящика значение, которое указывается для параметра  *MicrosoftOnlineServicesID,*  может быть иным, чем исходное, связанное с неактивным почтовым ящиком. Также можно применять исходный идентификатор пользователя. Но, как уже говорилось ранее, при восстановлении неактивного почтового ящика убедитесь, что  *значения,*  используемые для Name и  *MicrosoftOnlineServicesID,*  уникальны в организации.

- **Что делать, если срок хранения неактивного почтового ящика еще не истек?** Если неактивный почтовый ящик был обратимо удален менее 30 дней назад, вы не сможете восстановить его с помощью командлета **New-Mailbox -InactiveMailbox**. Его необходимо восстановить, восстановив соответствующую учетную запись пользователя. Дополнительные сведения см. в [публикации Delete a user from your organization.](../admin/add-users/delete-a-user.md)

- **Как узнать, истек ли срок хранения обратимо удаленного неактивного почтового ящика?** Выполните следующую команду.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | Format-List ExternalDirectoryObjectId
  ```

  Если значение свойства **ExternalDirectoryObjectId** отсутствует, срок хранения неактивного почтового ящика истек, и его можно восстановить с помощью команды **New-Mailbox -InactiveMailbox**. Если для свойства **ExternalDirectoryObjectId** имеется значение, срок хранения удаленных почтовых ящиков не истек, и необходимо восстановить почтовый ящик, восстановив учетную запись пользователя. См. статью [Удаление пользователя из организации](../admin/add-users/delete-a-user.md).

- **Возможно, вам потребуется включить архивный почтовый ящик после восстановления неактивного почтового ящика.** Это позволяет вернувшемуся пользователю или новому сотруднику переместить старые сообщения в архивный почтовый ящик. По истечении срока хранения политика архива, которая является частью политики хранения Exchange по умолчанию, назначенной Exchange Online почтовых ящиков, перемещает в архивные почтовые ящики элементы старше двух лет. Если не включить архивный почтовый ящик, элементы старше двух лет останутся в основном почтовом ящике пользователя. Дополнительные сведения см. в [фотоальбоме Включить архивные почтовые ящики.](enable-archive-mailboxes.md)