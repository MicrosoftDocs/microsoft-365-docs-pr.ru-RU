---
title: Управление разрешенными и заблокированными URL-адресами в списке разрешенных и заблокированных клиентов
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как настроить url-адреса в списке "Разрешить или заблокировать клиента" в Центре безопасности & соответствия требованиям.
ms.openlocfilehash: f60e2f29bf9b880e9d2247fa59554300ae348a03
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683215"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a>Управление URL-адресами в списке разрешенных и заблокированных клиентов

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Функции, описанные в этой статье, доступны в предварительной версии, могут изменяться и доступны не во всех организациях.

В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online вы можете не согласиться с решением о фильтрации EOP. Например, хорошее сообщение может быть помечено как плохое (ложное срабатыващение), или может быть разрешено сообщение с ложным отрицательным результатом.

Список "Разрешить или заблокировать клиента" в Центре безопасности & соответствия требованиям позволяет вручную переопределять решения фильтров Microsoft 365. Список "Разрешить/заблокировать" клиента используется во время потока почты и во время нажатия пользователем. Вы можете указать URL-адреса, которые необходимо разрешить или заблокировать, в списке "Разрешить или заблокировать клиента".

В этом разделе описывается настройка записей в списке разрешения и блокировки клиентов в Центре безопасности и соответствия требованиям & или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>. Чтобы перейти непосредственно на **страницу "Список заблокированных** и разрешаний клиентов", используйте <https://protection.office.com/tenantAllowBlockList> .

- Доступные значения URL-адресов описаны в синтаксисах [URL-адресов](#url-syntax-for-the-tenant-allowblock-list) для раздела "Список допустимого и заблокированного клиента" далее в этой статье.

- Список "Разрешить/заблокировать" клиента позволяет использовать не более 500 записей для URL-адресов.

- Запись должна быть активна в течение 15 минут.

- Блок-записи имеют приоритет над допустимой записью.

- По умолчанию срок действия записей в списке "Разрешить или заблокировать клиента" истекает через 30 дней. Вы можете указать дату или установить для них срок действия без срока действия.

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:
  - Чтобы добавить и удалить значения из списка "Разрешить или заблокировать клиента",  необходимо быть членом группы ролей "Управление организацией" или "Администратор безопасности". 
  - Для доступа только для чтения к списку разрешаний и блокировок  клиентов необходимо быть членом группы ролей **"Глобальное** читатель" или "Читатель безопасности".

  Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).

  **Примечания**.

  - Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365. Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Использование Центра безопасности & соответствия требованиям для создания записей URL-адресов в списке "Разрешить или заблокировать клиента"

Подробные сведения о синтаксисах для [](#url-syntax-for-the-tenant-allowblock-list) записей URL-адресов см. в разделе "Синтаксис URL-адресов для списка допустимого и заблокированного клиента" далее в этой статье.

1. В Центре безопасности & соответствия требованиям  перейдите в список "Политики управления угрозами" в списке \>  \> **"Разрешить/заблокировать клиента".**

2. **Убедитесь,** что вкладка "URL-адреса" выбрана на странице "Разрешить или заблокировать список клиентов" и нажмите кнопку  **"Добавить".**

3. В **окне "Добавление новых** URL-адресов" настройте следующие параметры:

   - **Добавление URL-адресов с поддиаными** знаками: введите один URL-адрес в строку не более 20.

   - **Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.

   - **Срок действия не истекает:** сделайте одно из следующих действий:

     - Убедитесь, что параметр отключен (выключен) и используйте поле "Срок действия" для указания даты окончания срока ![ ](../../media/scc-toggle-off.png) действия записей. 

     или

     - Чтобы настроить срок действия записей, переместите его вправо: ![Включенный переключатель](../../media/scc-toggle-on.png).

   - **Необязательное примечание.** Введите описательное текст для записей.

4. По завершению нажмите кнопку **"Добавить".**

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Просмотр запис & ей в списке "Разрешить или заблокировать" с помощью Центра безопасности и соответствия требованиям

1. В Центре безопасности & соответствия требованиям  перейдите в список "Политики управления угрозами" в списке \>  \> **"Разрешить/заблокировать клиента".**

2. Выберите вкладку **"URL-адреса".**

Щелкните следующие заголовки столбцов, чтобы отсортировать их по возрастанию или убыванию:

- **Значение**
- **Action**: **Block** or **Allow**.
- **Дата последнего обновления**
- **Дата окончания срока действия**
- **Примечание**

Щелкните **"Группа"** для группировки записей по **действию** **(блокировка** или **разрешение)** или **"Нет".**

Нажмите **кнопку**"Поиск", введите все или часть значения, а затем нажмите ввод, чтобы найти определенное значение. По завершению нажмите кнопку **"Очистить поиск"** ![ и нажмите значок "Очистить поиск". ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif)

Щелкните **"Фильтр"**. Во появляется **во** flyout фильтра, настройте любой из следующих параметров:

- **Действие:** выберите **"Разрешить",** **"Заблокировать"** или "И то, и другое".

- **Никогда не истекает:** выключите: ![ отключите ](../../media/scc-toggle-off.png) или включите: ![ включите. ](../../media/scc-toggle-on.png)

- **Last updated**: Select a start date (**From),** an end date (**To**) or both.

- **Дата окончания** срока действия: выберите даты начала **(от),** даты окончания (**To)** или и того, и другого.

По завершению нажмите кнопку **"Применить".**

Чтобы очистить существующие фильтры, щелкните **"Фильтр",** а затем в окле "Фильтр" щелкните **"Очистить фильтры".** 

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>Использование Центра безопасности & соответствия требованиям для изменения записей в списке "Разрешить или заблокировать клиента"

Вы не можете изменить значение URL-адреса. Вместо этого необходимо удалить запись и повторно создать ее.

1. В Центре безопасности & соответствия требованиям  перейдите в список "Политики управления угрозами" в списке \>  \> **"Разрешить/заблокировать клиента".**

2. Выберите вкладку **"URL-адреса".**

3. Выберите запись, которую нужно изменить,  и нажмите значок ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) редактирования.

4. Во появляется во flyout настройте следующие параметры:

   - **Block/Allow**: Select **Allow** or **Block**.

   - **Срок действия не истекает:** сделайте одно из следующих действий:

     - Убедитесь, что параметр отключен (выключен) и используйте поле "Срок действия" для указания даты окончания ![ ](../../media/scc-toggle-off.png) срока действия записи. 

     или

     - Переместите его вправо, чтобы настроить срок действия записи: ![Включенный переключатель](../../media/scc-toggle-on.png).

   - **Необязательное примечание.** Введите описательный текст для записи.

5. По завершении нажмите кнопку **Сохранить**.

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>Использование Центра безопасности & соответствия требованиям для удаления записей из списка "Разрешить или заблокировать клиента"

1. В Центре безопасности & соответствия требованиям  перейдите в список "Политики управления угрозами" в списке \>  \> **"Разрешить/заблокировать клиента".**

2. Выберите вкладку **"URL-адреса".**

3. Выберите запись, которую нужно удалить, и нажмите кнопку **"Удалить** ![ значок удаления". ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)

4. В появится диалоговое окно предупреждения, нажмите кнопку **"Удалить".**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Использование Exchange Online PowerShell или автономный EOP PowerShell для настройки списка "Разрешить/заблокировать" клиента

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a>Добавление записей в список "Разрешить или заблокировать" с помощью PowerShell

Чтобы добавить записи в список допустимой и заблокированной записей клиента, используйте следующий синтаксис:

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

В этом примере добавляется запись блокировки URL-contoso.com всех поддоменов (например, contoso.com, www.contoso.com и xyz.abc.contoso.com). Так как мы не использовали параметры ExpirationDate или NoExpiration, срок действия записи истекает через 30 дней.

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

Подробные сведения о синтаксисе и параметрах см. в описании [New-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>Использование PowerShell для просмотра записей в списке "Разрешить или заблокировать клиента"

Чтобы просмотреть записи в списке "Разрешить или заблокировать клиента", используйте следующий синтаксис:

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

В этом примере возвращаются все заблокированные URL-адреса.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

Подробные сведения о синтаксисе и параметрах см. в описании [Get-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a>Использование PowerShell для изменения записей в списке "Разрешить или заблокировать клиента"

Вы не можете изменить значение URL-адреса. Вместо этого необходимо удалить запись и повторно создать ее.

Чтобы изменить записи в списке допустимой и заблокированной записей клиента, используйте следующий синтаксис:

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

В этом примере изменяется дата окончания срока действия указанной записи.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Подробные сведения о синтаксисе и параметрах см. в описании [Set-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a>Использование PowerShell для удаления записей из списка "Разрешить или заблокировать клиента"

Чтобы удалить записи из списка "Клиенты: разрешить или заблокировать", используйте следующий синтаксис:

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

В этом примере из списка допустимого и заблокированного клиента удаляется указанная запись URL-адреса.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Подробные сведения о синтаксисе и параметрах см. в описании [remove-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>Синтаксис URL-адресов для списка допустимого и заблокированного клиента

- Ip4v- и IPv6-адреса разрешены, а порты TCP/UDP — нет.

- Расширения имен файлов запрещены (например, test.pdf).

- Юникод не поддерживается, но это punycode.

- Имена хостов разрешены, если истинны все следующие утверждения:

  - Имя хоста содержит период.
  - Слева от периода находится по крайней мере один символ.
  - Справа от периода есть по крайней мере два символа.

  Например, `t.co` разрешено или `.com` `contoso.` запрещено.

- Подпазки не подразумеваются.

  Например, `contoso.com` не включает `contoso.com/a` .

- В следующих сценариях допускается использовать поддиамографию (*):

  - Чтобы указать поддомен, необходимо следовать за левый поддиакон.

    Например, `*.contoso.com` разрешено; `*contoso.com` запрещено.

  - Для указания пути правый поддиаптер должен следовать косой черты (/).

    Например, `contoso.com/*` разрешено или `contoso.com*` `contoso.com/ab*` запрещено.

  - Поддиапатический знак не подразумевает все подпазки.

    Например, `contoso.com/*` не включает `contoso.com/a` .

  - `*.com*` является недопустимым (не является разрешаемым доменом, а правый поддиапный знак не следует косой черте).

  - Поддиапные знаки не разрешены в IP-адресах.

- Символ тильды (~) доступен в следующих сценариях:

  - Левая тильда подразумевает домен и все поддомены.

    Например, `~contoso.com` включает `contoso.com` и `*.contoso.com` .

- Url-адреса, содержащие протоколы (например, , или ) не удастся, так как записи URL применяются `http://` `https://` к всем `ftp://` протоколам.

- Имя пользователя или пароль не поддерживаются и не требуются.

- Кавычка (' или ") являются недопустимыми символами.

- URL-адрес должен включать все перенаправления по возможности.

### <a name="url-entry-scenarios"></a>Сценарии ввода URL-адреса

Допустимые URL-адреса и их результаты описаны в следующих разделах.

#### <a name="scenario-no-wildcards"></a>Сценарий: поддиаными знаками не является

**Запись:**`contoso.com`

- **Разрешить соответствие**: contoso.com

- **Allow not matched**:

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Блокировка совпадений:**

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Block not matched**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Сценарий: левый поддомен (поддомен)

**Запись:**`*.contoso.com`

- **Разрешить соответствие и** **блокировку совпадений:**

  - www.contoso.com
  - xyz.abc.contoso.com

- **Allow not matched** and **Block not matched**:

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Сценарий: правый под wildcard в верхней части пути

**Запись:**`contoso.com/a/*`

- **Разрешить соответствие и** **блокировку совпадений:**

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Allow not matched** and **Block not matched**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Сценарий: левая тильда

**Запись:**`~contoso.com`

- **Разрешить соответствие и** **блокировку совпадений:**

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Allow not matched** and **Block not matched**:

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Сценарий: правый суффикс с подстановными знаками

**Запись:**`contoso.com/*`

- **Разрешить соответствие и** **блокировку совпадений:**

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Allow not matched** and **Block not matched**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Сценарий: левый поддомен и правый суффикс подстановки

**Запись:**`*.contoso.com/*`

- **Разрешить соответствие и** **блокировку совпадений:**

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Allow not matched** and **Block not matched**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Сценарий: левая и правая тильда

**Запись:**`~contoso.com~`

- **Разрешить соответствие и** **блокировку совпадений:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Allow not matched** and **Block not matched**:

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Сценарий: IP-адрес

**Запись:**`1.2.3.4`

- **Разрешить соответствие** и **блокировку**: 1.2.3.4

- **Allow not matched** and **Block not matched**:

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>IP-адрес с правильным поддиапным знаком

**Запись:**`1.2.3.4/*`

- **Разрешить соответствие и** **блокировку совпадений:**

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Примеры недопустимых записей

Недопустимы следующие записи:

- **Отсутствуют или недопустимые значения домена:**

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*PDF

- **Поддиапные знаки для текста или без знаков интервала:**

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **IP-адреса с портами:**

  - contoso.com:443
  - abc.contoso.com:25

- **Неописательные поддиапники:**

  - \*
  - \*.\*

- **Средние подикаки:**

  - conto \* so.com
  - conto~so.com

- **Double wildcards**

  - contoso.com/\*\*
  - contoso.com/\*/\*
