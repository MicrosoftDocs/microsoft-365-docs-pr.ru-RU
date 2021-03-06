---
title: Назначение удержания на месте для обратимо удаленного почтового ящика в Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как создать запрос удержания на месте для обратимо удаленного почтового ящика, чтобы сделать последний неактивным и сохранить его содержимое.
ms.openlocfilehash: d72a5407bfafabed30466447e404cdd4196678ae
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226099"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Назначение удержания на месте для обратимо удаленного почтового ящика в Exchange Online

Узнайте, как создать запрос удержания на месте для обратимо удаленного почтового ящика, чтобы сделать последний неактивным и сохранить его содержимое. После этого вы сможете использовать средства обнаружения электронных данных для поиска в неактивном почтовом ящике.

> [!IMPORTANT]
> По мере того как мы продолжаем вкладывать средства в различные способы сохранения контента почтовых ящиков, мы объявляем о завершении In-Place держит в центре администрирования Exchange (EAC). С 1 июля 2020 г. вы не сможете создавать новые In-Place в Exchange Online. Но вы все равно сможете управлять In-Place в EAC или с помощью **cmdlet Set-MailboxSearch** в Exchange Online PowerShell. Однако с 1 октября 2020 г. вы не сможете управлять In-Place holds. Удалить их можно будет только в EAC или с помощью **cmdlet Remove-MailboxSearch.** Дополнительные сведения об уходе из In-Place содержится в см. в In-Place устаревших средств [eDiscovery.](legacy-ediscovery-retirement.md)

You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted. Afterwards, you realize there's information in the mailbox that needs to be preserved. What can you do? Если срок хранения удаленных почтовых ящиков не истек, можно поместить In-Place удержание на удаленный почтовый ящик (называемый мягким удаленным почтовым ящиком) и сделать его неактивным. An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization. The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive. После неактивности почтового ящика можно искать почтовый ящик с помощью In-Place eDiscovery в Exchange Online, поиске контента в Центре соответствия требованиям & безопасности или центре поиска электронных данных в SharePoint Online.

> [!NOTE]
> В Exchange Online обратимо удаленный почтовый ящик  почтовый ящик, который был удален, но может быть восстановлен в течение определенного срока хранения (в Exchange Online он составляет 30 дней). Это значит, что такой почтовый ящик можно восстановить или сделать неактивным в течение 30 дней после удаления. По истечении этого периода обратимо удаленный почтовый ящик помечается для окончательного удаления, и в этом случае его уже невозможно восстановить или сделать неактивным.

## <a name="requirements-for-in-place-holds"></a>Требования к In-Place удерживает

- Примените командлет **New-MailboxSearch** в Оболочка Windows PowerShell, чтобы назначить удержание на месте для обратимо удаленного почтового ящика. В SharePoint Online вы не можете использовать Центр администрирования Exchange (EAC) или центр обнаружения электронных данных.

- Сведения о том, как с помощью Оболочка Windows PowerShell подключаться к Exchange Online, см. в статье [Подключение к PowerShell для Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Выполните указанную ниже команду, чтобы отобразить удостоверения обратимо удаленных почтовых ящиков в организации.

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- Дополнительные сведения о неактивных почтовых ящиках см. в обзоре неактивных почтовых ящиков [в Office 365.](inactive-mailboxes-in-office-365.md)

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>Назначение удержания на месте для обратимо удаленного почтового ящика, чтобы сделать последний неактивным

С помощью командлета **New-MailboxSearch** сделайте обратимо удаленный почтовый ящик неактивным. Дополнительные сведения см. в статье [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch).

1. Создайте переменную, содержащую свойства обратимо удаленного почтового ящика.

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > В указанной выше команде используйте значение свойства **DistinguishedName** или **ExchangeGuid** для определения обратимо удаленного почтового ящика. Эти свойства уникальны для каждого почтового ящика в организации, тогда как у активного и обратимо удаленного почтовых ящиков может быть один и тот же основной SMTP-адрес.

2. Создайте запрос удержания на месте и назначьте его для обратимо удаленного почтового ящика. В этом примере не указан период удержания. Это означает, что элементы будут храниться в течение неограниченного срока или до тех пор, пока для неактивного почтового ящика не будет отменено удержание.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   Кроме того, вы можете указать длительность удержания при создании запроса удержания на месте. В этом примере элементы в неактивном почтовом ящике удерживаются около 7 лет.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. Через пару минут запустите одну из указанных ниже команд, чтобы убедиться в неактивности этого обратимо удаленного почтового ящика.

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    Еще вариант:

   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>Дополнительные сведения

Сделав обратимо удаленный почтовый ящик неактивным, вы сможете управлять им несколькими способами. Дополнительные сведения см. в таких статьях:

- [Изменение срока хранения неактивного почтового ящика](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Возврат неактивного почтового ящика](recover-an-inactive-mailbox.md)

- [Восстановление неактивного почтового ящика](restore-an-inactive-mailbox.md)

- [Удаление неактивного почтового ящика](delete-an-inactive-mailbox.md) (путем удаления удержания)