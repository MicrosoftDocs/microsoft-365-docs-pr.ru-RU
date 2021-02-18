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
description: Администраторы могут узнать, как запускать отчет о группе ролей администраторов в автономных службах Exchange Online Protection (EOP). Этот отчет занося в журнал, когда администратор добавляет участников в группы ролей администраторов или удаляет их из них.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d778e807a087a5e29b31645457d4a81bd05c5649
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288023"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>Запуск отчета группы ролей администратора в автономной службе EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
-  [Автономный exchange Online Protection](exchange-online-protection-overview.md)

В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online, когда администратор добавляет участников в группы административных ролей или удаляет их из них, служба регистрирует каждое событие. Дополнительные сведения о группах ролей в автономных EOP см. в [подгоне "Разрешения" в автономных EOP.](feature-permissions-in-eop.md)

При запуске отчета о группе ролей администраторов в Центре администрирования Exchange записи отображаются в качестве результатов поиска и включают затронутые группы ролей, кто изменил членство в группе ролей и когда, а также какие обновления членства были сделаны. Этот отчет можно использовать для отслеживания изменений в административных разрешениях, назначенных пользователям в организации.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Чтобы открыть Центр администрирования Exchange, см. центр [администрирования Exchange в режиме автономных EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Для работы с процедурами, которые данная статья, вам должны быть назначены разрешения в Exchange Online Protection. В частности, вам  потребуется роль  "Журналы аудита" или "Только просмотр журналов аудита", которые по умолчанию назначены группам ролей "Управление организацией", "Управление соответствием требованиям" и "Администратор безопасности".    Дополнительные сведения см. в сведениях о разрешениях в автономных [EOP](feature-permissions-in-eop.md) и использовании EAC для изменения списка участников [в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Сведения о сочетаниях клавиш, которые могут применяться к процедурам в этой статье, см. в статье "Сочетания клавиш" для Центра администрирования [Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Возникли проблемы? Обратитесь за помощью на форум по [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Запуск отчета о группе ролей администраторов с помощью Центра администрирования Exchange

Запустите отчет о группе ролей администраторов, чтобы найти изменения в группах ролей управления за определенный период времени.

1. В EAC перейдите **к** аудиту управления соответствием и выберите "Запуск отчета о группе ролей \>  **администраторов".**

2. На **открываемой странице "Поиск** изменений в группах ролей администраторов" настройте следующие параметры:

   - **Дата начала** и **дата окончания:** введите диапазон дат. По умолчанию отчет выполняет поиск изменений в группе ролей администраторов за последние две недели.

   - **Выберите группы ролей:** по умолчанию поиск ведется во всех группах ролей. Чтобы отфильтровать результаты по определенным группам ролей, щелкните **"Выбрать группы ролей".** В отображемом диалоговом окте выберите группу ролей и нажмите **кнопку add ->.** Повторите этот шаг столько раз,  сколько необходимо, а затем нажмите кнопку "ОК", когда закончите.

3. По завершению нажмите кнопку **"Поиск".**

Если будут найдены любые изменения, соответствующие заданным критериям, они появятся в области результатов. Чтобы в области сведений увидеть изменения, выберите группу ролей в результатах поиска.

## <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Если отчет о группе ролей администрирования запущен успешно, группы ролей, измененные в рамках диапазона дат, отображаются в области результатов поиска. Если результатов нет  в указанный диапазон дат группы ролей изменены не были. Если вы считаете, что результаты должны быть, измените диапазон дат и повторно запустите отчет.

## <a name="monitor-changes-to-role-group-membership"></a>Отслеживание изменений состава группы ролей

При добавлении или удалении участников группы ролей результаты поиска в области сведений указывают на изменение состава группы ролей с указанием ее текущих участников. В результатах не говорится явно, кто был добавлен или удален.

Чтобы определить, был ли добавлен или удален пользователь, следует сравнить две записи в отчете. Например, рассмотрим следующие записи журнала для группы ролей **HelpDesk**.

> 27.01.2018 16:43 <br> Администратор <br> Обновленные участники: Administrator;annb,florencef;pilarp <br> 06.02.2018 10:09 <br> Администратор <br> Обновленные участники: Administrator;annb;florencef;pilarp;tonip <br> 19.02.2018 14:12 <br> Администратор <br> Обновленные участники: Administrator;annb;florencef;tonip

В этом примере администратор внес следующие изменения:

- 06.02.2018 добавлен пользователь для фрагмента.
- 19.02.2018 пользователь pilarp удален.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>Использование автономных Exchange Online PowerShell для поиска записей журнала аудита

Вы можете использовать Exchange Online PowerShell для поиска записей журнала аудита, которые соответствуют заявляемой вами критерии. Список критериев поиска см. в поиске [Search-AdminAuditLog.](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet) В этой процедуре используется **cmdlet Search-AdminAuditLog** и отображаются результаты поиска в Exchange Online PowerShell. Его можно использовать, если вам нужно вернуть набор результатов, превыша который превышает ограничения, определенные в данных о новом **администратореAuditLogSearch** или в отчетах отчетов аудита EAC.

Чтобы выполнить поиск по указанному критерию журнала аудита, используйте следующий синтаксис.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> Командлет **Search-AdminAuditLog** по умолчанию возвращает максимум 1000 записей журнала. Используйте параметр _ResultSize,_ чтобы указать до 250 000 записей журнала. Или используйте значение для `Unlimited` возврата всех записей.

В этом примере выполняется поиск всех записей журнала аудита со следующими критериями:

- **Дата начала:** 04.08.2018
- **Дата окончания:** 03.01.2018
- **ИД пользователей:** `davids` , `chrisd` , `kima`
- **Cmdlets**: **Set-Mailbox**
- **Параметры:** _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

В этом примере выполняется поиск изменений определенных почтовых ящиков. Это позволяет определить неполадку или предоставить сведения для диагностики. Используются следующие критерии:

- **Дата начала:** 01.05.2018
- **Дата окончания:** 03.01.2018
- **ИД объекта**: contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

Если поиск возвращает много записей журнала, рекомендуется использовать процедуру, представленную в **Exchange Online PowerShell,** для поиска записей журнала аудита и отправки результатов получателю далее в этой статье. Действия в этом разделе позволяют отправить XML-файл в виде вложения сообщения электронной почты указанным отправителям, чтобы быстрее извлечь интересующие данные.

Дополнительные сведения о синтаксисе и параметрах см. в разделе [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Просмотр подробных сведений о записях журнала аудита

The **Search-AdminAuditLog cmdlet** returns the fields described in [Audit log contents](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents). Поля **CmdletParameters** и **ModifiedProperties**, возвращаемые командлетом, содержат дополнительные сведения, которые невозможно просмотреть по умолчанию.

Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedProperties**, выполните указанные ниже действия. Кроме того, вы можете использовать процедуру в **Exchange Online PowerShell** для поиска записей журнала аудита и отправки результатов получателю далее в этой статье для создания XML-файла.

В этой процедуре используются следующие основные понятия:

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. Определите критерии поиска, запустите командлет **Search-AdminAuditLog** и сохраните результаты в переменной с помощью следующей команды.

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. Каждая запись журнала аудита хранится в переменной как элемент `$Results` массива. Чтобы выбрать элемент массива, укажите его индекс. Индексы элементов массива начинаются с 0 для первого элемента массива. Например, чтобы получить пятый элемент массива с индексом 4, используйте следующую команду.

   ```PowerShell
   $Results[4]
   ```

3. Предыдущая команда возвращает запись журнала, хранящуюся в элементе массива 4. Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedProperties** для этой записи журнала, используйте следующие команды.

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedParameters** в другой записи журнала, измените индекс элемента массива.
