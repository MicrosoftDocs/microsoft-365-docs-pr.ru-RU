---
title: Удаление пользователя из организации
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Узнайте, как удалить учетную запись пользователя и что делать с электронной почтой и OneDrive контентом, а также о том, следует ли сохранять лицензию на продукт.
ms.openlocfilehash: 81dc71c6734340146e1dd13bcd59696eed5be202
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394355"
---
# <a name="delete-a-user-from-your-organization"></a>Удаление пользователя из организации
  
**Ищете, как удалить собственную *учетную* запись Microsoft 365, которую вы используете на работе или в школе? Чтобы сделать эти действия, обратитесь в техническую службу в вашей работе или университете.**

## <a name="before-you-begin"></a>Прежде чем начать

- Удалить учетные [записи пользователей могут только Microsoft 365,](about-admin-roles.md) которые имеют разрешения глобального администратора или управления пользователями для бизнеса или школы.
- Вы можете [восстановить](restore-user.md) ее в течение 30 дней, пока данные не удалены окончательно.
- Если вы хотите сохранить данные пользователя OneDrive, переместим их в другое расположение. Вы даже можете переместить данные до 30 дней после удаления учетной записи. См. сведения о том, как получить [доступ к данным бывшего пользователя](get-access-to-and-back-up-a-former-user-s-data.md)и получить их обратно. Вам не нужно перемещать SharePoint файлы; вы все еще будете иметь доступ к ним.
- Если вы хотите сохранить электронную почту пользователя, перенесите ее в другое место **ПЕРЕД** удалением учетной записи. Если вы уже удалили учетную запись, в течение 30 дней ее можно восстановить, перенести данные электронной почты, а затем снова удалить. См. статью [Получение доступа к данным бывшего пользователя и создание их резервной копии](get-access-to-and-back-up-a-former-user-s-data.md).
- Если у вас есть подписка Enterprise типа Office 365 корпоративный E3, можно сохранить данные почтового ящика удаленной учетной записи пользователя, превратив ее в неактивный почтовый *ящик.* Дополнительные дополнительные сообщения см. в [сообщении Управление неактивными почтовыми](../../compliance/inactive-mailboxes-in-office-365.md)ящиками в Exchange Online.

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>Глобальный администратор. Удалите пользователя, прекратите платить за лицензию и выберите, что делать с его электронной почтой и OneDrive контентом

Если вы глобальный администратор, при удалении пользователя вы также можете предоставить другому пользователю доступ к электронной почте и выбрать, что делать с OneDrive контентом.

### <a name="things-to-consider"></a>Важные факторы

Перед началом подумайте, что нужно сделать с электронной почтой и контентом пользователя OneDrive, а также о том, хотите ли вы сохранить лицензию или перестать платить за нее.
  
|Элемент | Описание |
|:-----|:-----|
|Лицензии на продукт  <br/> |Вы можете удалить лицензию у пользователя и удалить ее из подписки, чтобы перестать платить за эту лицензию. Если вы выберете этот параметр, лицензия будет автоматически удалена из подписки.  <br/><br/> **Вы не можете удалить лицензию,** если вы приобрели ее через партнер или лицензирование тома. Если вы платите за годовой план или в середине цикла вы выставления счета, вы не сможете удалить лицензию из подписки до тех пор, пока ваше обязательство не будет выполнено.  <br/> |
|OneDrive контента  <br/> |Если пользователь сохранил файлы для OneDrive, вы можете предоставить другому пользователю доступ к этим файлам.  <br/><br/> Вам потребуется переместить файлы, которые необходимо сохранить в течение установленного для OneDrive файлов. **По умолчанию период хранения составляет 30 дней.** Если вы не перемещайте файлы в течение периода хранения после удаления пользователя, OneDrive контент будет окончательно удален. Чтобы увеличить количество дней, в течение OneDrive для удаленных учетных записей, см. в OneDrive хранения для [удаленных пользователей.](/onedrive/set-retention)  <br/><br/> **Важно!** Если удаленный пользователь использовал персональный компьютер для загрузки файлов из SharePoint и OneDrive, вы не сможете удалить файлы, хранимые на компьютере. Они будут по-прежнему иметь доступ к любым файлам, синхронизированным с OneDrive.           |
|Электронная почта  <br/> | Предоставление другому пользователю доступа к электронной почте удаленного пользователя преобразует удаленный почтовый ящик пользователя в общий почтовый ящик. Затем новый владелец почтового ящика может получить доступ к почтовому ящику и отслеживать новые сообщения электронной почты. У вас также будут следующие параметры:  <br/>  <br/>Измените имя дисплея . Рекомендуется изменить имя дисплея, чтобы было легко определить общий почтовый ящик в списке **активных** пользователей.  <br/>  Включите автоматические ответы . Мы уже написали для вас вежливый автоматический ответ. Вы можете отправлять различные автоматические ответы людям в вашей организации и людям из-за пределов организации.  <br/> <br/> Очистка псевдонимов . Псевдонимы являются дополнительными адресами электронной почты для пользователей. Некоторые организации не используют их, поэтому если у вас нет таких организаций, вам не нужно ничего делать здесь. Если у пользователя есть псевдонимы, рекомендуется удалить их, чтобы можно было повторно использовать эти адреса электронной почты. В противном случае нельзя повторно использовать эти адреса электронной почты до тех пор, пока не пройдет период хранения удаленных почтовых ящиков. По умолчанию удаленный почтовый ящик восстанавливается в течение 30 дней. Дополнительные сведения см. в [публикации Delete or restore user mailboxes in Exchange Online.](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox) <br/> |
|Active Directory  <br/> |Если в вашем бизнесе используется **Active Directory,** синхронизируются с Azure AD, необходимо удалить учетную запись пользователя из Active Directory. В Office 365 сделать это нельзя. Инструкции см. в [публикации Delete a User Account.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))  <br/> |

### <a name="get-started"></a>Начало работы

Так как руководство по работе проходит по шагам по удалите пользователя, вот как начать работу.

::: moniker range="o365-worldwide"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.

::: moniker-end

2. Выберите пользователя, который необходимо удалить, а затем выберите **удалить пользователя**.

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>Администратор управления пользователями: удалите одного или несколько пользователей из Office 365

> [!IMPORTANT]
> Не удаляйте учетную запись пользователя, [](../email/convert-user-mailbox-to-shared-mailbox.md) если она была преобразована в общий почтовый ящик или настроена переададка электронной почты в учетную запись. Эти функции по-прежнему нуждаются в учетной записи. Общий почтовый ящик не требует лицензии. Если учетная запись преобразована в общий почтовый ящик, вы можете [перестать платить за лицензию.](#stop-paying-for-the-license) Если вы настроили переададку электронной почты в учетную запись, вы не можете удалить лицензию. При этом переадекция электронной почты остановится и отключит почтовый ящик.
  
::: moniker range="o365-worldwide"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.  

::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.

::: moniker-end

2. Выберите имена пользователей, которые необходимо удалить, выберите три точки (больше действий), а затем выберите  **удалить пользователя**.

   Несмотря на удаление учетной записи пользователя, вы по-прежнему платите **за лицензию.** См. следующую процедуру, чтобы перестать платить за лицензию.  Или можно назначить лицензию другому пользователю. Он не будет назначен кому-то автоматически.

### <a name="stop-paying-for-the-license"></a>Прекращение оплаты лицензии

Уменьшение количества лицензий — это отдельный шаг, который может выполнять только глобальный администратор или администратор биллинга.
  
::: moniker range="o365-worldwide"

1. В Центре администрирования перейдите на страницу **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.
::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования перейдите на страницу **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Ваши продукты</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования перейдите на страницу **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Ваши продукты</a>.
::: moniker-end

2. На **вкладке Продукты** выберите подписку, для которую необходимо удалить лицензии.

3. На странице сведений о подписке выберите **Удалить лицензии**.

4. В области **Удаление лицензий** в поле **"Новое** количество" в поле **Total licenses** введите общее количество лицензий, которые необходимо получить для этой подписки. Например, если у вас есть 100 лицензий и вы хотите удалить пять из них, введите 95.

5. Нажмите кнопку **Сохранить**.

Позже, когда вы пройдете шаги, чтобы добавить другого человека в свой бизнес, вам будет предложено купить лицензию в то же время, с одним шагом!

## <a name="delete-many-users-at-the-same-time"></a>Удаление одновременно многих пользователей

См. [в см. в рубке "Удалить-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell".

## <a name="fix-issues-with-deleting-a-user"></a>Устранение проблем с удалением пользователя

Вот наиболее распространенные проблемы, с которыми сталкиваются пользователи при удалении пользователя:
  
- **Вы получаете сообщение об ошибке в строке "Пользователь не может быть удален. Попробуйте еще раз позже."** Дважды проверьте, настроена ли учетная запись для пересылания электронной почты или она преобразована в общий почтовый ящик. Оба этих фактора приводят к этой ошибке. Не удаляйте учетную запись, если она переададации электронной почты или преобразована в общий почтовый ящик.

- **Нет соответствующих разрешений для удаления пользователя**. Удалять пользователей [могут только Microsoft 365](about-admin-roles.md) глобальные администраторы или администраторы управления пользователями. Обычно это специалисты службы технической поддержки в организации или учебном заведении.

- **Пользователь удаляется, но его имя продолжает отображаться в глобальной адресной книге.** Это происходит, когда бизнес использует Active Directory. Необходимо удалить учетную запись пользователей из Active Directory. Инструкции см. в [публикации Delete a User Account.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))

**Хотите удалить Microsoft 365 с компьютера? Перейдите к [отмене подписки.](../../commerce/subscriptions/cancel-your-subscription.md)**

## <a name="related-content"></a>См. также:

[Восстановление пользователя](restore-user.md) (статья)\
[Постоянное удаление почтового ящика](/exchange/permanently-delete-a-mailbox-exchange-2013-help) (статьи)\
[Удаление бывшего](remove-former-employee.md) сотрудника из Office 365 (статья)\
[Добавление нового сотрудника в Office 365](add-new-employee.md) (статья)\
[Удаление учетной записи](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))пользователя. Используйте эти инструкции, если в вашем бизнесе используется **Active Directory,** синхронизируются с Azure AD. В Office 365 сделать это нельзя. (статья)