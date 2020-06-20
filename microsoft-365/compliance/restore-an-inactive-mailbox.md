---
title: Восстановление неактивного почтового ящика
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
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: Узнайте, как восстановить (или объединить) содержимое неактивного почтового ящика в существующий почтовый ящик в Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8ae3927aaaba64711cdcc3362399b109f228cb12
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818939"
---
# <a name="restore-an-inactive-mailbox"></a>Восстановление неактивного почтового ящика

Неактивный почтовый ящик (который представляет собой тип обратимо удаленного почтового ящика) используется для хранения электронной почты бывшего сотрудника после того, как он покидает организацию. Если другой сотрудник берет на себя обязанности бывшего сотрудника или этот сотрудник возвращается в организацию, вы можете предоставить содержимое неактивного почтового ящика пользователю двумя способами.
  
- **Restore an inactive mailbox** If another employee takes on the job responsibilities of the departed employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. You can also restore the archive from an inactive mailbox. After it's restored, the inactive mailbox is preserved and is retained as an inactive mailbox. This topic describes the procedures for restoring an inactive mailbox.

- **Восстановление неактивного почтового ящика** Если отработка, возвращенная в организацию, или сотрудник, нанятый сотрудником, должен принять должностные обязанности отчасти сотрудника, можно восстановить содержимое неактивного почтового ящика. При этом неактивный почтовый ящик преобразуется в новый ящик, который содержит элементы неактивного почтового ящика. После восстановления неактивный почтовый ящик больше не существует. Пошаговые процедуры приведены [в статье восстановление неактивного почтового ящика в Office 365](recover-an-inactive-mailbox.md).

В разделе **Дополнительные сведения** этой статьи представлены дополнительные сведения о различиях между восстановлением и восстановлением неактивного почтового ящика.
  
## <a name="requirements-to-restore-an-inactive-mailbox"></a>Требования для восстановления неактивного почтового ящика

- Для восстановления неактивного почтового ящика необходимо использовать Exchange Online PowerShell. Вы не можете сделать этого в Центре администрирования Exchange (EAC). Пошаговые инструкции приведены [в статье подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).

- Выполните следующую команду в Exchange Online PowerShell, чтобы получить сведения об удостоверении неактивных почтовых ящиков в Организации.

    ```powershell
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     Используйте полученную информацию для восстановления определенного неактивного почтового ящика.

- Дополнительные сведения о неактивных почтовых ящиках приведены [в статье Неактивные почтовые ящики в Office 365](inactive-mailboxes-in-office-365.md)

## <a name="restore-an-inactive-mailbox"></a>Восстановление неактивного почтового ящика

Use the **New-MailboxRestoreRequest** cmdlet with the  _SourceMailbox_ and  _TargetMailbox_ parameters to restore the contents of an inactive mailbox to an existing mailbox. For more information about using this cmdlet, see [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298).
  
1. Создайте переменную, содержащую свойства неактивного почтового ящика.

    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.
  
2. Restore the contents of the inactive mailbox to an existing mailbox. The contents of the inactive mailbox (source mailbox) will be merged into the corresponding folders in the existing mailbox (target mailbox).

    ```powershell
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```

   Alternatively, you can specify a top-level folder in the target mailbox in which to restore the contents from the inactive mailbox. If the specified target folder or target folder structure doesn't already exist in the target mailbox, it is created during the restore process. 

    Этот пример копирует элементы и вложенные папки из неактивного почтового ящика в папку "Inactive Mailbox" в структуре папок верхнего уровня в целевом почтовом ящике.

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a>Восстановление архива из неактивного почтового ящика

If an inactive mailbox has an archive mailbox, you can also restore it to the archive mailbox of an existing mailbox. To restore the archive from an inactive mailbox, you have to add the  _SourceIsArchive_ and  _TargetIsAchive_ switches to the command used to restore an inactive mailbox.
  
1. Создайте переменную, содержащую свойства неактивного почтового ящика.

    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!NOTE]
    > In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address. 
  
2. Restore the contents of the archive from the inactive mailbox (source archive) to the archive of an existing mailbox (target archive). In this example, the contents from the source archive are copied to a folder named "Inactive Mailbox Archive" in the archive of the target mailbox.

    ```powershell
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

## <a name="more-information"></a>Дополнительные сведения

- **В чем основное различие между возвратом и восстановление неактивного почтового ящика?** После возврата неактивного почтового ящика он, по сути, преобразуется в новый почтовый ящик, содержимое и структура папок неактивного почтового ящика сохраняются, и он связывается с новой учетной записью пользователя. После возврата неактивный почтовый ящик больше не существует, и любые изменения, внесенные в его содержимое, влияют на содержимое, который изначально удерживался в неактивном почтовом ящике. При восстановлении неактивного почтового ящика его содержимое просто копируется в другой почтовый ящик. Неактивный почтовый ящик сохраняется и остается неактивным. Любые изменения, внесенные в содержимое целевого почтового ящика, не повлияет на исходное содержимое в неактивном почтовом ящике. Для неактивного почтового ящика можно выполнить поиск с помощью [средства поиска контента](content-search.md), его содержимое можно восстановить в другом почтовом ящике, либо его можно восстановить или удалить позже.

- **How do you find inactive mailboxes?** To get a list of the inactive mailboxes in your organization and display information that is useful for restoring an inactive mailbox, you can run this command.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **Используйте политику хранения для судебного разбирательства или Microsoft 365 для хранения неактивного содержимого почтового ящика.** Если вы хотите сохранить состояние неактивного почтового ящика после его восстановления, вы можете поместить целевой почтовый ящик на [хранение для судебного разбирательства](https://go.microsoft.com/fwlink/?linkid=856286) или применить [политику хранения Microsoft 365](retention-policies.md) перед восстановлением неактивного почтового ящика. Это предотвратит удаление элементов из неактивного почтового ящика после их восстановления в целевом ящике.

- **Включите удержание хранения в целевом почтовом ящике перед восстановлением неактивного почтового ящика.** Так как элементы почтовых ящиков неактивного почтового ящика могут быть устаревшими, можно включить удержание хранения в целевом почтовом ящике перед восстановлением неактивного почтового ящика Когда вы помещаете почтовый ящик на хранение хранения, назначенная ему политика хранения не будет обработана до тех пор, пока не будет удалено удержание хранения или пока не истечет срок хранения. Это дает владельцу целевого времени почтового ящика Управление старыми сообщениями из неактивного почтового ящика. В противном случае политика хранения может удалять старые элементы (или перемещать элементы в архивный почтовый ящик, если он включен), использующий параметры хранения, настроенные для целевого почтового ящика. Дополнительные сведения см. [в статье помещение почтового ящика на хранение в Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300).

- **Что делает параметр AllowLegacyDNMismatch?** В предыдущих примерах для восстановления неактивного почтового ящика параметр **AllowLegacyDNMismatch** использовался, чтобы разрешить восстановление неактивного почтового ящика в другой целевой почтовый ящик. В обычном сценарии восстановления цель заключается в восстановлении содержимого, при этом исходный и целевой почтовые ящики совпадают. Поэтому командлет **New-MailboxRestoreRequest** по умолчанию проверяет, что значение свойства **legacyExchangeDN** в исходном и целевом почтовых ящиках одинаково. Эта позволяет предотвратить случайное восстановление исходного почтового ящика в неправильном целевом почтовом ящике. Если попытаться восстановить неактивный почтовый ящик без параметра **AllowLegacyDNMismatch**, команда может завершиться с ошибкой, если значения свойства **LegacyExchangeDN** исходного и целевого почтового ящика различаются.

- **You can use other parameters with the New-MailboxRestoreRequest cmdlet to implement different restore scenarios for inactive mailboxes.** For example, you can run this command to restore the archive from the inactive mailbox into the primary mailbox of the target mailbox. 

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  Можно также восстановить неактивный основной почтовый ящик в архиве в целевом почтовом ящике, выполнив эту команду.

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **What does the TargetRootFolder parameter do?** As previously explained, you can use the **TargetRootFolder** parameter to specify a folder in the top of the folder structure (also called the root) in the target mailbox in which to restore the contents of the inactive mailbox. If you don't use this parameter, mailbox items from the inactive mailbox are merged into the corresponding default folders of the target mailbox, and custom folders are re-created in the root of the target mailbox. The following illustrations highlight these differences between not using and using the **TargetRootFolder** parameter.

    **Иерархия папок в целевом почтовом ящике, если параметр TargetRootFolder не используется**

    ![Снимок экрана: не используется параметр TargetRootFolder.](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    **Иерархия папок в целевом почтовом ящике, если параметр TargetRootFolder используется**

    ![Снимок экрана: используется параметр TargetRootFolder.](../media/300da592-7323-48db-b8a4-07012259d113.png)
