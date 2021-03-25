---
title: Запуск отчета группы ролей администратора в автономной службе EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как запустить отчет группы ролей администратора в автономных Exchange Online Protection (EOP). Этот отчет входит в журнал, когда администратор добавляет членов в группы ролей администратора или удаляет их из них.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0281dcb13f5cee0ba8db8c4faed5054f481337cf
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206588"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>Запуск отчета группы ролей администратора в автономной службе EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
-  [Автономный exchange Online Protection](exchange-online-protection-overview.md)

В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online администратор добавляет членов в группы административных ролей или удаляет их, служба регистрирует каждое событие. Дополнительные сведения о группах ролей в автономных EOP см. в рублях [Permissions in standalone EOP.](feature-permissions-in-eop.md)

При запуске отчета группы ролей администратора в центре администрирования Exchange (EAC) записи отображаются в качестве результатов поиска и включают затронутые группы ролей, которые изменили членство в группе ролей и когда и какие обновления членства были сделаны. Этот отчет можно использовать для отслеживания изменений в административных разрешениях, назначенных пользователям в организации.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Чтобы открыть центр администрирования Exchange, см. в [центре администрирования Exchange в режиме автономный EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Вам необходимо получить разрешения в Exchange Online Protection, прежде чем вы сможете сделать процедуры в этой статье. В частности, вам  потребуется роль  журналов аудита или журналов аудита только для просмотра,  которые по умолчанию назначены группам ролей "Управление **организацией",**"Управление соответствием требованиям" и "Администратор безопасности". Дополнительные сведения см. в рублях Разрешения в автономных [EOP](feature-permissions-in-eop.md) и Use the EAC изменить список участников [в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Сведения о ярлыках клавиатуры, которые могут применяться к процедурам в этой статье, см. в статье Клавишные ярлыки для центра администрирования Exchange в [Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Возникли проблемы? Обратитесь за помощью на форум по [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Запуск отчета о группе ролей администраторов с помощью Центра администрирования Exchange

Запустите отчет группы ролей администратора, чтобы найти изменения в группах ролей управления в определенный период времени.

1. В EAC перейдите **к** аудиту управления соответствием, а затем выберите Отчет группы ролей \>  **администратора.**

2. На **открываемой странице Поиск** изменений групп ролей администратора настройте следующие параметры:

   - **Дата начала** и **дата окончания.** Введите диапазон дат. По умолчанию отчет выполняет поиск изменений в группе ролей администраторов за последние две недели.

   - **Выберите группы ролей.** По умолчанию все группы ролей будут искаться. Чтобы фильтровать результаты определенными группами ролей, щелкните **Выберите группы ролей.** В диалоговом октаге, который отображается, выберите группу ролей и нажмите **кнопку добавить ->**. Повторите этот шаг столько раз, сколько необходимо, а затем нажмите **кнопку ОК,** когда вы закончите.

3. Когда вы закончите, нажмите кнопку **Поиск**.

Если будут найдены любые изменения, соответствующие заданным критериям, они появятся в области результатов. Чтобы в области сведений увидеть изменения, выберите группу ролей в результатах поиска.

## <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Если отчет о группе ролей администрирования запущен успешно, группы ролей, измененные в рамках диапазона дат, отображаются в области результатов поиска. Если результатов нет  в указанный диапазон дат группы ролей изменены не были. Если вы считаете, что результаты должны быть, измените диапазон дат и повторно запустите отчет.

## <a name="monitor-changes-to-role-group-membership"></a>Отслеживание изменений состава группы ролей

При добавлении или удалении участников группы ролей результаты поиска в области сведений указывают на изменение состава группы ролей с указанием ее текущих участников. В результатах не говорится явно, кто был добавлен или удален.

Чтобы определить, был ли добавлен или удален пользователь, следует сравнить две записи в отчете. Например, рассмотрим следующие записи журнала для группы ролей **HelpDesk**.

> 1/27/2018 16:43 <br> Администратор <br> Обновленные участники: Administrator;annb,florencef;pilarp <br> 02.06.2018 10:09 <br> Администратор <br> Обновленные участники: Administrator;annb;florencef;pilarp;tonip <br> 19.19.2018 14:12 <br> Администратор <br> Обновленные участники: Administrator;annb;florencef;tonip

В этом примере администратор внес следующие изменения:

- 2.06.2018 они добавили пользовательский tonip.
- 2/19/2018 они удалили pilarp пользователя.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>Для поиска записей журналов аудита используйте автономный Exchange Online PowerShell

Вы можете использовать Exchange Online PowerShell для поиска записей журналов аудита, которые соответствуют критериям, которые вы указываете. Список критериев поиска см. в списке критериев поиска [Search-AdminAuditLog.](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet) Эта процедура использует **кодлет Search-AdminAuditLog** и отображает результаты поиска в Exchange Online PowerShell. Этот комдлет можно использовать, когда необходимо вернуть набор результатов, превышает ограничения, определенные в комлете **New-AdminAuditLogSearch** или в отчетах аудита EAC.

Чтобы выполнить поиск по указанному критерию журнала аудита, используйте следующий синтаксис.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> Командлет **Search-AdminAuditLog** по умолчанию возвращает максимум 1000 записей журнала. Чтобы указать до 250 000 записей журнала, используйте параметр _ResultSize._ Или используйте значение для `Unlimited` возврата всех записей.

В этом примере выполняется поиск всех записей журнала аудита со следующими критериями:

- **Дата начала:** 08.04.2018
- **Дата окончания:** 10.03.2018
- **Пользовательские ID:** `davids` , `chrisd``kima`
- **Cmdlets:** **Set-Mailbox**
- **Параметры:** _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

В этом примере выполняется поиск изменений определенных почтовых ящиков. Это позволяет определить неполадку или предоставить сведения для диагностики. Используются следующие критерии:

- **Дата начала:** 05/01/2018
- **Дата окончания:** 10.03.2018
- **ID объекта:** contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

Если поиск возвращает множество записей журналов, рекомендуется использовать процедуру, предусмотренную в **Use Exchange Online PowerShell,** для поиска записей журналов аудита и отправки результатов получателю позже в этой статье. Действия в этом разделе позволяют отправить XML-файл в виде вложения сообщения электронной почты указанным отправителям, чтобы быстрее извлечь интересующие данные.

Дополнительные сведения о синтаксисе и параметрах см. в разделе [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Просмотр подробных сведений о записях журнала аудита

В **кодлете Search-AdminAuditLog** возвращаются поля, описанные в содержимом [журнала аудита.](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents) Поля **CmdletParameters** и **ModifiedProperties**, возвращаемые командлетом, содержат дополнительные сведения, которые невозможно просмотреть по умолчанию.

Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedProperties**, выполните указанные ниже действия. Или вы можете использовать процедуру в **Use Exchange Online PowerShell** для поиска записей журналов аудита и отправки результатов получателю позже в этой статье для создания XML-файла.

В этой процедуре используются следующие основные понятия:

- [about_Arrays](/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](/powershell/module/microsoft.powershell.core/about/about_variables)

1. Определите критерии поиска, запустите командлет **Search-AdminAuditLog** и сохраните результаты в переменной с помощью следующей команды.

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. Каждая запись журнала аудита хранится в качестве элемента массива в `$Results` переменной. Чтобы выбрать элемент массива, укажите его индекс. Индексы элементов массива начинаются с 0 для первого элемента массива. Например, чтобы получить пятый элемент массива с индексом 4, используйте следующую команду.

   ```PowerShell
   $Results[4]
   ```

3. Предыдущая команда возвращает запись журнала, хранящуюся в элементе массива 4. Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedProperties** для этой записи журнала, используйте следующие команды.

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedParameters** в другой записи журнала, измените индекс элемента массива.