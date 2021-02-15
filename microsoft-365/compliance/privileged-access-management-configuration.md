---
title: Начало работы с управлением привилегированным доступом
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: В этой статье вы узнаете, как активировать и настроить управление привилегированным доступом в Office 365.
ms.openlocfilehash: 0b8d79c3012ecd321d7b00c1566aa557077d55f1
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126536"
---
# <a name="get-started-with-privileged-access-management"></a>Начало работы с управлением привилегированным доступом

В этом разделе вы можете включить и настроить управление привилегированным доступом в организации. Для управления привилегированным доступом и использования его можно использовать Центр администрирования Microsoft 365 или Exchange Management PowerShell.

## <a name="before-you-begin"></a>Перед началом работы

Перед началом работы с управлением привилегированным доступом необходимо подтвердить подписку [на Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) и все надстройки. Чтобы получить доступ к управлению привилегированным доступом и использовать его, в организации должна быть одна из следующих подписок или надстройки:

- Подписка Microsoft 365 E5 (платная или пробная версия)
- Подписка на Microsoft 365 E3 (или подписка на Office 365 E3 + enterprise Mobility and Security E3) + надстройка соответствия требованиям Microsoft 365 E5
- Любая подписка на Microsoft 365, Office 365, Exchange, SharePoint или OneDrive для бизнеса + надстройка Microsoft 365 E5 Insider Risk Management  
- Подписка на Microsoft 365 A5 (платная или пробная версия)
- Подписка на Microsoft 365 A3 (или подписка на Office 365 A3 + Enterprise Mobility and Security A3) + надстройка соответствия Требованиям Microsoft A5
- Любая подписка на Microsoft 365, Office 365, Exchange, SharePoint или OneDrive для образования + надстройка Microsoft 365 A5 Insider Risk Management
- Подписка на Office 365 корпоративный E5 (платная или пробная версия)
- Подписка на Office 365 корпоративный E3 + надстройка Office 365 Advanced Compliance (больше недоступна для новых подписок, см. примечание)

Пользователям, которые отправили запросы на управление привилегированным доступом и отвечали на них, должна быть назначена одна из вышеуказанных лицензий.

>[!IMPORTANT]
>Office 365 Advanced Compliance больше не продается в качестве автономных подписок. По истечении срока действия текущих подписок клиенты должны перейти на одну из вышеперечисленной подписки, которая содержит те же или дополнительные функции соответствия требованиям.

Если у вас нет плана Office 365 корпоративный E5 и вы хотите попробовать управление привилегированным доступом, вы можете [](https://www.microsoft.com/microsoft-365/enterprise) добавить [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) к существующей подписке на Office 365 или зарегистрироваться для получения пробной подписки на Microsoft 365 корпоративный E5.

## <a name="enable-and-configure-privileged-access-management"></a>Включить и настроить управление привилегированным доступом

Чтобы настроить и использовать привилегированный доступ в организации, выполните следующие действия.

- [Шаг 1. Создание группы утвержденного](privileged-access-management-configuration.md#step1)

    Прежде чем приступить к использованию привилегированного доступа, определите, кому необходимы полномочия по утверждению входящих запросов на доступ к задачам с повышенными привилегиями. Любой пользователь, в который входит группа "Утверждение", может утверждать запросы на доступ. Эта группа включена путем создания группы безопасности с включенной поддержкой почты в Office 365.

- [Шаг 2. Включить привилегированный доступ](privileged-access-management-configuration.md#step2)

    Привилегированный доступ должен быть явно включен в Office 365 с группой утвержденных по умолчанию, включая набор системных учетных записей, которые необходимо исключить из управления привилегированным доступом управления доступом.

- [Шаг 3. Создание политики доступа](privileged-access-management-configuration.md#step3)

    Создание политики утверждения позволяет определить конкретные требования утверждения, определенные для отдельных задач. Возможные типы утверждения: **Auto** или **Manual**.

- [Шаг 4. Отправка и утверждение запросов на привилегированный доступ](privileged-access-management-configuration.md#step4)

    После включения привилегированный доступ требует утверждения для любой задачи, для задачи с определенной политикой утверждения. Для задач, включенных в политику утверждения, пользователи должны запрашивать и получать разрешение на доступ, чтобы иметь разрешения, необходимые для выполнения задачи.

После утверждения запрашивающий пользователь может выполнить предполагаемую задачу, а привилегированный доступ разрешит и выполнит задачу от имени пользователя. Утверждение остается действительным в течение запрашиваемой длительности (по умолчанию — 4 часа), в течение которого запрашивающая может выполнить предполагаемую задачу несколько раз. Все такие исполняемые данные регистрируются в журнале и доступны для аудита безопасности и соответствия требованиям. 

>[!NOTE]
>Если вы хотите включить и настроить привилегированный доступ с помощью Exchange Management PowerShell, выполните действия, которые необходимо предпринять при подключении к [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) с помощью многофакторной проверки подлинности, чтобы подключиться к Exchange Online PowerShell с помощью учетных данных Office 365. Чтобы включить привилегированный доступ при подключении к Exchange Online PowerShell, не требуется включить многофакторную проверку подлинности для организации. При подключении с многофакторной проверкой подлинности создается маркер OAuth, используемый привилегированным доступом для подписи запросов.

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>Шаг 1. Создание группы утвержденного

1. Во sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.

2. В Центре администрирования перейдите в **группу**  >  **"Добавить группу".**

3. Выберите **группу безопасности** с включенной поддержкой почты  и заполнив поля **"Имя",** **"Адрес** электронной почты группы" и "Описание" для новой группы.

4. Сохраните группу. Для полной настройки группы и ее появления в Центре администрирования Microsoft 365 может потребоваться несколько минут.

5. Выберите группу нового утвержденного и выберите **"Изменить",** чтобы добавить пользователей в группу.

6. Сохраните группу.

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>Шаг 2. Включить привилегированный доступ

### <a name="in-the-microsoft-365-admin-center"></a>В Центре администрирования Microsoft 365

1. Во sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.

2. В Центре администрирования перейдите **к** параметрам безопасности  >  **параметров** организации &  >    >  **конфиденциальности привилегированного доступа.**

3. Включить утверждение **"Требовать" для управления привилегированными задачами.**

4. Назначьте группу утвержденного, созданную на шаге 1, в качестве группы "По **умолчанию".**

5. **Сохранить** и **закрыть**.

### <a name="in-exchange-management-powershell"></a>В Exchange Management PowerShell

Чтобы включить привилегированный доступ и назначить группу утвержденного, в Exchange Online PowerShell запустите следующую команду:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

Пример.

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
>Функция системных учетных записей обеспечивает работу определенных автоматизаций в организациях без зависимости от привилегированного доступа, однако рекомендуется, чтобы такие исключения были исключительными и их следует утверждать и регулярно проверять.

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>Шаг 3. Создание политики доступа

В организации можно создать и настроить до 30 политик привилегированного доступа.

### <a name="in-the-microsoft-365-admin-center"></a>В Центре администрирования Microsoft 365

1. Во sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.

2. В Центре администрирования перейдите **к** параметрам безопасности  >  **параметров** организации &  >    >  **конфиденциальности привилегированного доступа.**

3. Выберите **"Управление политиками и запросами доступа".**

4. Выберите **"Настроить политики" и** **"Добавить политику".**

5. В полях в выпадаемом поле выберите соответствующие значения для вашей организации:
    
    **Тип политики:** задача, роль или группа ролей

    **Область политики**: Exchange

    **Имя политики:** Выберите из доступных политик

    **Тип утверждения:** ручной или автоматический

    **Группа утверждения:** выберите группу утвержденных, созданную на шаге 1

6. Выберите **"Создать",** а затем **закройте.** Для полной настройки и включения политики может потребоваться несколько минут.

### <a name="in-exchange-management-powershell"></a>В Exchange Management PowerShell

Чтобы создать и определить политику утверждения, в Exchange Online PowerShell запустите следующую команду:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

Пример.

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>Шаг 4. Отправка и утверждение запросов на привилегированный доступ

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>Запрос авторизации повышения прав для выполнения привилегированных задач

Запросы на привилегированный доступ действительны в течение 24 часов после отправки запроса. Если запросы не утверждены или отклонены, срок действия запросов истекает, а доступ не утверждается.

#### <a name="in-the-microsoft-365-admin-center"></a>В Центре администрирования Microsoft 365

1. Во sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.

2. В Центре администрирования перейдите **к** параметрам безопасности  >  **параметров** организации &  >    >  **конфиденциальности привилегированного доступа.**

3. Выберите **"Управление политиками и запросами доступа".**

4. Выберите **новый запрос.** В полях в выпадаемом поле выберите соответствующие значения для вашей организации:

    **Тип запроса:** задача, роль или группа ролей

    **Область запроса**: Exchange

    **Запрос :** выберите из доступных политик

    **Продолжительность (часы)**: количество часов запрашиваемого доступа. Количество часов, которое можно запросить, не ограничивается.

    **Комментарии:** текстовое поле для комментариев, связанных с вашим запросом на доступ

5. Выберите **"Сохранить"** и **"Закрыть"** Ваш запрос будет отправлен группе утвержденного по электронной почте.

#### <a name="in-exchange-management-powershell"></a>В Exchange Management PowerShell

Запустите следующую команду в Exchange Online PowerShell, чтобы создать и отправить запрос на утверждение группе утверждаю стороны:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

Пример.

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>Просмотр состояния запросов на повышение прав

После создания запроса на утверждение состояние запроса на повышение прав можно просмотреть в Центре администрирования или в PowerShell управления Exchange с помощью связанного с ИД запроса.

#### <a name="in-the-microsoft-365-admin-center"></a>В Центре администрирования Microsoft 365

1. Во sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.

2. В Центре администрирования перейдите к параметрам безопасности  >  **параметров**  >  **организации &**  >  **конфиденциальности привилегированного доступа.**

3. Выберите **"Управление политиками и запросами доступа".**

4. Выберите **"Представление",** чтобы отфильтровать отправленные запросы по состояниям "Ожидание", **"Утверждено",**"Отклонено" или "Блокировка **клиента".**  

#### <a name="in-exchange-management-powershell"></a>В Exchange Management PowerShell

Чтобы просмотреть состояние запроса на утверждение для определенного ИД запроса, запустите следующую команду в Exchange Online PowerShell:

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

Пример.

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>Утверждение запроса на повышение прав авторизации

После создания запроса на утверждение члены соответствующей группы утверждения получают уведомление по электронной почте и могут утвердить запрос, связанный с ИД запроса. Запросиватель уведомлен об утверждении или отказе в запросе по электронной почте.

#### <a name="in-the-microsoft-365-admin-center"></a>В Центре администрирования Microsoft 365

1. Во sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.

2. В Центре администрирования перейдите к параметрам безопасности параметров организации  >    >  **&**  >  **конфиденциальности привилегированного доступа.**

3. Выберите **"Управление политиками и запросами доступа".**

4. Выберите указанный запрос, чтобы просмотреть сведения и принять меры по запросу.

5. Выберите **"Утвердить",** чтобы утвердить запрос, или выберите **"Запретить"** для отказа в запросе. Ранее утвержденные запросы могут иметь доступ отозван, выбрав **"Отзыв".**

#### <a name="in-exchange-management-powershell"></a>В Exchange Management PowerShell

Чтобы утвердить запрос на повышение прав, запустите следующую команду в Exchange Online PowerShell:

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

Пример.

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

Чтобы запретить запрос на повышение прав, запустите следующую команду в Exchange Online PowerShell:

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

Пример.

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Удаление политики привилегированного доступа в Office 365

Если она больше не требуется в вашей организации, вы можете удалить политику привилегированного доступа.

### <a name="in-the-microsoft-365-admin-center"></a>В Центре администрирования Microsoft 365

1. Во sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.

2. В Центре администрирования перейдите к параметрам безопасности  >  **параметров**  >  **организации &**  >  **конфиденциальности привилегированного доступа.**

3. Выберите **"Управление политиками и запросами доступа".**

4. Выберите **"Настроить политики".**

5. Выберите политику, которая нужно удалить, а затем выберите **"Удалить политику".**

6. Нажмите **Закрыть**.

### <a name="in-exchange-management-powershell"></a>В Exchange Management PowerShell

Чтобы удалить политику привилегированного доступа, запустите следующую команду в Exchange Online Powershell:

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Отключение привилегированного доступа в Office 365

При необходимости вы можете отключить управление привилегированным доступом в организации. Отключение привилегированного доступа не удаляет связанные политики утверждения или группы утвержденных лиц.

### <a name="in-the-microsoft-365-admin-center"></a>В Центре администрирования Microsoft 365

1. Во sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.

2. В Центре администрирования перейдите **к** параметрам безопасности  >  **параметров** организации &  >    >  **конфиденциальности привилегированного доступа.**

3. Включить утверждение **"Требовать" для управления привилегированным доступом.**

### <a name="in-exchange-management-powershell"></a>В Exchange Management PowerShell

Чтобы отключить привилегированный доступ, запустите следующую команду в Exchange Online Powershell:

```PowerShell
Disable-ElevatedAccessControl
```
