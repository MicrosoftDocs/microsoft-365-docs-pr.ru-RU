---
title: Управление разрешенным и заблокированными URL-адресами в списке разрешений или блокировок клиента
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
description: Администраторы могут узнать, как настраивать URL-адреса в списке разрешений или блокировок клиента в Центре безопасности & требованиям.
ms.openlocfilehash: 888a96f23daf2cf47847466ad4080f310be7f9b4
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845946"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a>Управление URL-адресами в списке разрешенных и заблокированных клиентов

> [!NOTE]
> Возможности, описанные в этой статье, являются предварительными версиями, могут изменяться и доступны не во всех организациях.

В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в организациях с автономной службой Exchange Online Protection (EOP) без почтовых ящиков Exchange Online можно обособить среду, которая не используется для фильтрации EOP. Например, хорошее сообщение может быть помечено как плохое (ложное срабатывание) или сообщение с плохим (ложное отрицательное).

Список разрешений или блокировок клиента в Центре безопасности & требованиям позволяет вручную переопределить заявления фильтров Microsoft 365. Список разрешений или блокировок клиента используется в потоке почты и во время нажатий пользователем. Вы можете указать URL-адреса, которые следует разрешить или заблокировать в списке разрешенных или заблокированных клиентов.

В этом разделе описывается настройка записей в списке разрешений или блокировок клиента в Центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономная оболочка PowerShell EOP для организаций без почтовых ящиков Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>. Чтобы перейти непосредственно на страницу **"Список разрешений или блокировок** клиента", используйте <https://protection.office.com/tenantAllowBlockList> этот параметр.

- Доступные значения URL-адресов описаны в [синтаксисе URL-адресов для раздела "Список разрешенных или заблокированных клиентов"](#url-syntax-for-the-tenant-allowblock-list) далее в этой статье.

- Список разрешений или блокировок клиента разрешает не более 500 записей для URL-адресов.

- Запись должна быть активной в течение 15 минут.

- Блокирование записей имеет приоритет над разрешает.

- По умолчанию срок действия записей в списках разрешений или блокировок клиента истекает через 30 дней. Можно указать дату или задать для них никогда неограниченный срок действия.

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Чтобы вы могли выполнить процедуры, упомянутые в этой теме, вам должны быть назначены соответствующие разрешения.

  - Чтобы добавить значения в черный список или черный список клиентов и удалить их из него, вы должны быть членом одной из следующих групп ролей:

    - **Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).
    - **Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Чтобы получить доступ к белому или запрещающему списку клиентов только для чтения, вы должны быть членом одной из следующих групп ролей:

    - **Средство считывания сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).
    - **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Создание записей URL-& адресов в списке разрешений или блокировок клиента с помощью Центра безопасности

Дополнительные сведения о синтаксисе URL-адресов см. в [синтаксисе URL-адреса для раздела списка разрешенных и заблокированных](#url-syntax-for-the-tenant-allowblock-list) клиентов далее в этой статье.

1. В Центре безопасности & выберите списки разрешенных или блокирующих **Threat management** \> **Policy** \> **клиентов политики управления угрозами.**

2. На странице **"Список разрешений или блокировок** клиента" убедитесь, **что выбрана вкладка** URL-адресов, и нажмите кнопку **"Добавить"**

3. В **появившемся** окне "Добавление новых URL-адресов" настройте следующие параметры:

   - **Добавьте URL-адреса с подстановочными**знаками: введите по одному URL-адресу на строке до 20.

   - **Блокировать/разрешить:** выберите, следует ли **разрешить** или **заблокировать** указанные URL-адреса.

   - **Срок действия никогда не**истекает: выполните одно из указанных ниже действий.

     - Убедитесь, что параметр выключен (выключен) и используйте поле "Срок действия элемента" для указания ![ ](../../media/scc-toggle-off.png) срока действия записей. **Expires on**

     или

     - Чтобы настроить такой переключатель вправо, переместите переключатель вправо, чтобы настроить неограниченный срок действия записей: ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Необязательное примечание:** введите текст с описательным текстом записей.

4. По завершении нажмите кнопку **"Добавить".**

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Использование Центра безопасности & соответствия требованиям для просмотра записей в списке разрешенных или заблокированных клиентов

1. В Центре безопасности & выберите списки разрешенных или блокирующих **Threat management** \> **Policy** \> **клиентов политики управления угрозами.**

2. Перейдите на **вкладку "URL-адреса".**

Чтобы отсортировать по возрастанию или убыванию, щелкните следующие заголовки столбцов:

- **Значение**
- **Действие:** **заблокировать или** **разрешить.**
- **Дата последнего обновления**
- **Дата окончания срок**
- **Примечание**

Выберите **"Групповая",** чтобы сгруппировать **записи** по действиям **(запретить** **или**разрешить) **или "Нет".**

Нажмите **"Поиск"**(или введите значение целиком) или часть значения и нажмите клавишу ВВОД, чтобы найти нужное значение. Когда все будет готово, щелкните значок **очистить** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) поиск.

Щелкните **"Фильтр".** В **появившемся** окне "Фильтр" настройте любые из следующих параметров:

- **Действие:** выберите **"Разрешить",** **"Блокировать" или** "оба".

- **Срок действия не истекает:** выбирайте ![ (переключатель) ](../../media/scc-toggle-off.png) или включите ( ![ установите переключатель). ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

- **Last updated**: Select a start date (**From),** an end date (**To)** or both.

- **Дата окончания**срока действия: выберите дату начала (**"Из")** и /оба**варианта.**

Закончив, нажмите кнопку **"Применить".**

Чтобы очистить существующие фильтры, щелкните **"Фильтр"** и в появившемся окне **"Фильтр"** нажмите кнопку **"Очистить фильтры".**

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>Использование Центра безопасности & безопасности для изменения записей в списке разрешенных или заблокированных клиентов

Нельзя изменить само значение URL-адреса. Необходимо удалить запись, а затем воссоздать ее.

1. В Центре безопасности & выберите списки разрешенных или блокирующих **Threat management** \> **Policy** \> **клиентов политики управления угрозами.**

2. Перейдите на **вкладку "URL-адреса".**

3. Выберите запись, которую вы хотите изменить, и нажмите значок **"Изменить** ![ изменить". ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)

4. В отображенной всплывающем элементе настройте следующие параметры:

   - **Блокировать/разрешить:** выберите **"Разрешить или** **заблокировать".**

   - **Срок действия никогда не**истекает: выполните одно из указанных ниже действий.

     - Убедитесь, что параметр выключен (выключен) и используйте поле "Срок действия элемента" для указания ![ ](../../media/scc-toggle-off.png) даты срока действия записи. **Expires on**

     или

     - Чтобы настроить срок действия записи, переместите вправо перемещаемый переключатель: ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Необязательное примечание:** введите текст с текстом, который появляется для записи.

5. Выполнив необходимые действия, нажмите кнопку **Сохранить**.

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>Удаление записей из списка & разрешений или блокировок клиента с помощью Центра безопасности для доступа

1. В Центре безопасности & выберите списки разрешенных или блокирующих **Threat management** \> **Policy** \> **клиентов политики управления угрозами.**

2. Перейдите на **вкладку "URL-адреса".**

3. Выберите удаляемую запись и нажмите значок **Delete** ![ "Удалить". ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)

4. В появившемся диалоговом окне предупреждения нажмите кнопку **"Удалить".**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Использование Exchange Online PowerShell или автономной службы EOP PowerShell для настройки списка разрешенных или заблокированных клиентов

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a>Добавление записей в черный или черный список клиентов с помощью PowerShell

Чтобы добавить записи в черный список или блокировок клиента, используйте следующий синтаксис:

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

В этом примере добавляется запись блокировки URL-адресов для contoso.com всех дочерних доменов (например, contoso.com, www.contoso.com и xyz.abc.contoso.com). Так как мы не использули параметры ExpirationDate или NoExpiration, срок действия записи истекает через 30 дней.

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

Дополнительные сведения о синтаксисе и параметрах [см. в разделе New-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>Просмотр записей в черных или блокируемых списках клиентов с помощью PowerShell

Чтобы просмотреть записи в черных или заблокированных списках клиентов, используйте следующий синтаксис:

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

В этом примере возвращаются все заблокированные URL-адреса.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

Дополнительные сведения о синтаксисе и параметрах см. в [статье Get-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a>Использование PowerShell для изменения записей в списке разрешений или блокировок клиента

Нельзя изменить само значение URL-адреса. Необходимо удалить запись, а затем воссоздать ее.

Чтобы изменить записи в черных или заблокированных списках клиентов, используйте следующий синтаксис:

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

В этом примере изменяется срок действия указанной записи.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Дополнительные сведения о синтаксисе и параметрах см. в [разделе Set-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a>Использование PowerShell для удаления записей из черного списка или разрешений клиентов

Чтобы удалить записи из черного или черного списка клиентов, используйте следующий синтаксис:

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

Этот пример удаляет запись URL-адреса из списка разрешенных или заблокированных доменов для клиента.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Дополнительные сведения о синтаксисе и параметрах [см. в статье Remove-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>Синтаксис URL-адреса для списка разрешенных или заблокированных адресов клиента

- Адреса IP4v и IPv6 разрешены, а TCP/UDP-порты не поддерживаются.

- Расширения файлов не допускаются (например, test.pdf).

- Юникод не поддерживается, а Punycode — код.

- Имена узлов допускаются, если собираются все следующие операторы:

  - Имя узла содержит точку.
  - Слева от точки назначается хотя бы один знак.
  - Точка содержит по крайней мере два символа.

  Например, `t.co` это допускается или `.com` `contoso.` запрещено.

- Вложенные пути не подходят.

  Например, без `contoso.com` включения. `contoso.com/a`

- Подстановочные знаки (*) разрешены в следующих сценариях.

  - Следует за простым подстановочным знаком задать поддомен точку.

    Например, `*.contoso.com` разрешено; `*contoso.com` не разрешено.

  - Чтобы указать путь, необходимо следовать указаниям правого подстановочного знака косой черты (/).

    Например, `contoso.com/*` это допускается или `contoso.com*` `contoso.com/ab*` запрещено.

  - Все дочерние пути не подразумевается соответствующим подстановочным знаком.

    Например, без `contoso.com/*` включения. `contoso.com/a`

  - `*.com*` является недопустимым (не допустимым доменом, для которых реакция в качестве подходящего подстановочного знака не следует символу косой черты).

  - В IP-адресах нельзя использовать подстановочные знаки.

- Символ тильда (~) доступен в следующих сценариях:

  - Левая тильда подразумевает домен и все дочерние домены.

    Например, `~contoso.com` включает `contoso.com` `*.contoso.com` и.

- URL-адреса, содержащие протоколы (например, , или) не будут `http://` `https://` `ftp://` работать, потому что URL-записи применяются ко всем протоколам.

- Имя пользователя и пароль не поддерживаются и не обязательны.

- Кавычки (' или ") предусмайствует недопустимые символы.

- URL-адрес должен по возможности включать все перенаправления.

### <a name="url-entry-scenarios"></a>Сценарии ввода URL-адресов

Допустимые записи URL-адресов и их результаты описаны в следующих разделах.

#### <a name="scenario-no-wildcards"></a>Сценарий: подстановочные знаки отсутствуют

**Entry**: `contoso.com`

- **Разрешить совпадение:** contoso.com

- **Разрешить не совпадение:**

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com
  
- **Block match**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Блокировать не совпадений:** abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Сценарий: левый подстановочный знак (дочерний домен)

**Entry**: `*.contoso.com`

- **Разрешить совпадение** **и блокировку:**

  - www.contoso.com
  - xyz.abc.contoso.com

- **Разрешить несовпадение** и блокировку не **совпадает:**

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a>Сценарий: прямой подстановочный знак вверху пути

**Entry**: `contoso.com/a/*`

- **Разрешить совпадение** **и блокировку:**

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Разрешить несовпадение** и блокировку не **совпадает:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com
  
#### <a name="scenario-left-tilde"></a>Сценарий: левая тильда

**Entry**: `~contoso.com`

- **Разрешить совпадение** **и блокировку:**

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Разрешить несовпадение** и блокировку не **совпадает:**

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Сценарий: подходящий суффикс подстановочных знаков

**Entry**: `contoso.com/*`

- **Разрешить совпадение** **и блокировку:**

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Разрешить несовпадение** **и блокировку:** contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Сценарий: левый поддомен с подстановочными знаками и правой суффикс подстановочных знаков

**Entry**: `*.contoso.com/*`

- **Разрешить совпадение** **и блокировку:**

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Разрешить несовпадение** **и блокировку:** contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Сценарий: левая и правая тильда

**Entry**: `~contoso.com~`

- **Разрешить совпадение** **и блокировку:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Разрешить несовпадение** и блокировку не **совпадает:**

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Сценарий: IP-адрес

**Entry**: `1.2.3.4`

- **Разрешить** **совпадение и блокировку:** 1.2.3.4

- **Разрешить несовпадение** и блокировку не **совпадает:**

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>IP-адрес с правильным подстановочным знаком

**Entry**: `1.2.3.4/*`

- **Разрешить совпадение** **и блокировку:**

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Примеры недопустимых записей

Следующие записи являются недопустимыми:

- **Отсутствуют или недопустимые значения доменов:**

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*PDF

- **Подстановочный знак для текста или без пробелов:**

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **IP-адреса с портами:**

  - contoso.com:443
  - abc.contoso.com:25

- **Недействующие подстановочные знаки:**

  - \*
  - \*.\*

- **Средние подстановочные знаки:**

  - отклонник \* so.com
  - conto~so.com

- **Двойной подстановочные**

  - contoso.com/\*\*
  - contoso.com/\*/\*
