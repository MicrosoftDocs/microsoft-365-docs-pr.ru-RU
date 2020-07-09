---
title: Обновление списков рассылки до Microsoft 365 группы в Outlook
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Узнайте, как обновить один или несколько списков рассылки до Microsoft 365 группы в Outlook, а также как использовать PowerShell для одновременного обновления нескольких списков рассылки.
ms.openlocfilehash: a1fb974be4838ebe98c2c55fe8694e89e27d636e
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083578"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Обновление списков рассылки до Microsoft 365 группы в Outlook

Вы можете обновить списки рассылки до Microsoft 365 группы с Outlook. Это отличный способ предоставить всем организациям, перечисленным в Организации, все функции и функции групп Microsoft 365. [Причины для перехода со списков рассылки на группы в Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

Вы можете обновить один или сразу несколько списков рассылки.

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Обновление одного или нескольких списков рассылки до Microsoft 365 группы в Outlook

Для обновления списка рассылки необходимо быть глобальным администратором или администратором Exchange. Чтобы выполнить обновление до группы Microsoft 365, группа рассылки должна иметь владельца почтового ящика. 

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.

2. В центре администрирования Exchange перейдите в раздел группы **получателей** \> **Groups**.<br/>Вы увидите уведомление о том, что списки рассылки (также называемые **группами рассылки** ), которые можно обновить до групп Microsoft 365.<br/> ![Нажмите кнопку "получить начало"](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. Выберите один или несколько списков рассылки ( **групп рассылки** ) на странице **групп**.<br/>![Выбор группы рассылки](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. Выберите значок обновление.<br/>![Значок обновления до Microsoft 365 групп](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. В диалоговом окне сведения нажмите **кнопку Да** , чтобы подтвердить обновление. Процесс начинается немедленно. В зависимости от размера и количества обновляемых списков документов процесс может занять несколько минут или часов.<br/>Если список рассылки не может быть обновлен, появится диалоговое окно с сообщением. Сведения о [том, какие списки рассылки невозможно обновить?](#which-distribution-lists-cannot-be-upgraded).

6. Если вы обновляете несколько списков рассылки, используйте раскрывающийся список, чтобы отфильтровать, какие списки рассылки были обновлены. Если список не заполнен, подождите некоторое время, а затем нажмите кнопку **Обновить** , чтобы увидеть, что Обновлено успешно.<br/>There's no notice that tells you when the upgrade process has completed for all DLs you selected. You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.

7. If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade. See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).

> [!NOTE]
> If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of. See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>Что делать, если возникает ошибка обновления

Списки рассылки, которые не удалось обновить, остаются без изменений.

If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md). The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.

It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely. If you want, wait a while and then try to upgrade the DL again.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>Обновление нескольких списков рассылки одновременно с помощью PowerShell

Если вы хорошо знакомы с PowerShell, можно воспользоваться этим средством вместо пользовательского интерфейса. У нас есть набор командлетов, которые помогут вам обновить списки рассылки. См. ниже.

### <a name="upgrade-a-single-dl"></a>Обновление одного списка рассылки

Чтобы обновить один DL, выполните следующую команду:

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

Например, если вы хотите обновить списки рассылки с помощью SMTP-адреса dl1@contoso.com, выполните следующую команду:

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> Вы также можете обновить один список рассылки до группы Microsoft 365 с помощью командлета PowerShell [New – UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) .

### <a name="upgrade-multiple-dls-in-a-batch"></a>Обновление нескольких списков рассылки в пакете

Вы также можете передать несколько списков рассылки в виде пакета и обновить их вместе:

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

Например, если вы хотите обновить пять списков рассылки с SMTP-адресом `dl1@contoso.com` и `dl2@contoso.com` , `dl3@contoso.com` , `dl4@contoso.com` и, `dl5@contoso.com` выполните следующую команду:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>Обновление всех подходящих списков рассылки

Существует два способа обновления всех подходящих списков рассылки.

> [!NOTE]
> Командлет Upgrade – DistributionGroup не получает данные из конвейера по этой причине, поэтому для успешного выполнения необходимо использовать оператор ForEach — Object {} .

1. Получите подходящие списки рассылки в клиенте и обновите их с помощью команды Upgrade:

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. Получение списка всех списков рассылки и обновление только соответствующих списков рассылки:

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Вопросы и ответы об обновлении списков рассылки до Microsoft 365 группы в Outlook

### <a name="which-distribution-lists-cannot-be-upgraded"></a>Какие списки рассылки невозможно обновить?

Обновлять можно только простые облачные списки рассылки, не являющиеся вложенными. В приведенной ниже таблице перечислены списки рассылки, которые **не могут** быть обновлены.

|**Описание**|**Поддерживается?**|
|:-----|:-----|
|Список рассылки с локальным управлением.  <br/> |Нет  <br/> |
|Nested distribution lists. Distribution list either has child groups or is a member of another group.  <br/> |Нет  <br/> |
|Списки рассылки с членами **RecipientTypeDetails** , отличными от **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**  <br/> |Нет  <br/> |
|Список рассылки с более чем 100 владельцами  <br/> |Нет  <br/> |
|Список рассылки, у которого нет владельцев.  <br/> |Нет  <br/> |
|Список рассылки, в псевдониме которого есть специальные знаки.  <br/> |Нет  <br/> |
|Список рассылки, настроенный в качестве адреса перенаправления для общего почтового ящика.  <br/> |Нет  <br/> |
|Если DL является частью **ограничения отправителя** в другом списке рассылки.  <br/> |Нет  <br/> |
|Группы безопасности  <br/> |Нет  <br/> |
|Динамические списки рассылки.  <br/> |Нет  <br/> |
|Списки рассылки, которые были преобразованы в **румлистс**  <br/> |Нет  <br/> |
|Списки рассылки, в которых **мембержоинрестриктион** и/или **мембердепартрестриктион** **закрыт**  <br/> |Нет  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a>Как проверить, какие списки рассылки подходят для обновления?

Если вы хотите проверить, подходит ли DL, выполните следующую команду:

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

Чтобы проверить, какие списки рассылки могут быть обновлены, выполните следующую команду:

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>Кто может выполнять сценарии обновления?

Пользователи с правами глобального администратора или администратора Exchange.

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>Почему карточка контакта по-прежнему отображается в списке рассылки? Что сделать, чтобы обновленный список рассылки не отображался в списке автозаполнения?

- Для Outlook: когда кто-то пытается отправить сообщение в Outlook, введя имя группы Microsoft 365 после миграции, получатель будет разрешаться как список рассылки, а не как группа. Карточка контакта этого получателя останется в списке рассылки. Это связано с кэшем получателей или кэшем псевдонимов в Outlook. Сообщение электронной почты будет успешно отправлено в группу, но может привести к путанице отправителя.<br/>Для решения этой проблемы вам нужно сбросить кэш, выполнив действия, описанные в статье [Сведения о списке автозаполнения в Outlook](https://go.microsoft.com/fwlink/?LinkID=798736).

- Для Outlook в Интернете: в случае Outlook в Интернете получатель списка рассылки останется в кэше. Вы можете выполнить действия, описанные в статье [Удаление предлагаемого имени или адреса электронной почты из списка автозавершения](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) , чтобы обновить кэш, чтобы увидеть карточку контакта группы.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>Получат ли участники группы приветственные сообщения?

No. The setting to enable welcome messages is set to false by default. This setting affects both existing and new group members who may join after the migration is complete. If the group owner later allows guest users, guest users won't receive a welcome email in their inbox. Guest members can continue working with the group.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>Что делать, если один или несколько списков рассылки не обновляются?

Существует несколько случаев, когда DL является допустимым, но его не удалось обновить. Список рассылки не обновляется и остается в виде списка рассылки.

- Если администратор применил **политику адресов электронной почты** групп для групп в Организации и пытается обновить списки рассылки, которые не удовлетворяют этим условиям, список рассылки не обновляется.

- Списки рассылки с **мембержоинрестриктион** или **мембердепартрестриктион** , для которых задано значение **Closed**, не удалось обновить

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>Что происходит со списком рассылки при сбое обновления, запущенного через EAC?

The upgrade will happen only when the call is submitted to the server. If the upgrade fails, your DLs will be intact. They will work like they used to.


