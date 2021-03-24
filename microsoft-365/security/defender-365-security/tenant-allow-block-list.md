---
title: Управление вашими допусками и блоками в списке разрешить или блокировать клиента
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Администраторы могут научиться настраивать разрешит и блокирует в списке разрешить или заблокировать клиента на портале безопасности.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 55116ddac8fa25b63e50b7fba73f668855e2858d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071110"
---
# <a name="manage-the-tenant-allowblock-list"></a>Управление списком разрешенных и запрещенных клиентов

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> Функции, описанные в этой статье, находятся в предварительном просмотре, могут изменяться и недоступны во всех организациях.
>
> В настоящее время нельзя **настроить разрешенные** элементы в списке разрешить или заблокировать клиента.

В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online вы можете не согласиться с вердиктом по фильтрации EOP. Например, хорошее сообщение может быть помечено как плохое (ложное положительное) или плохое сообщение может быть разрешено (ложное отрицательное).

Список разрешить или заблокировать клиента в Центре & безопасности позволяет вручную переопредировать решения по фильтрации Microsoft 365. Список разрешить/заблокировать клиента используется во время потока почты и во время щелчков пользователя. Вы можете указать URL-адреса или файлы, чтобы всегда блокировать.

В этой статье описывается настройка записей в Списке разрешения клиента или блока в Центре обеспечения безопасности & или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>. Чтобы перейти непосредственно на **страницу Разрешить или заблокировать** список клиента, используйте <https://protection.office.com/tenantAllowBlockList> .

- Вы указываете файлы, используя значение hash SHA256 для файла. Чтобы найти значение hash SHA256 для файла в Windows, запустите следующую команду в командной подсказке:

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Например, значение `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` . Перцептивные значения hash (pHash) не поддерживаются.

- Доступные значения URL-адресов описаны в синтаксисе [URL-адресов](#url-syntax-for-the-tenant-allowblock-list) для раздела "Разрешить или заблокировать список клиента" в этой статье.

- Список разрешить или блокировать клиента позволяет не более 500 записей для URL-адресов и 500 записей для хеш-файлов.

- Максимальное количество символов для каждой записи:
  - Хеши файла = 64
  - URL-адрес = 250

- Запись должна быть активна в течение 30 минут.

- По умолчанию срок действия записей в списке разрешить или блокировать клиента истекает через 30 дней. Вы можете указать дату или установить, чтобы срок их действия никогда не истек.

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:
  - Чтобы добавить и удалить значения из списка "Разрешить или заблокировать клиента", необходимо быть членом группы ролей администратора организации или **администратора** безопасности. 
  - Чтобы получить доступ только для чтения к списку разрешить или заблокировать клиента, необходимо быть членом групп ролей **Global Reader** или **Security Reader.**

  Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > 
  > - Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365. Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).
  > - Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Используйте Центр & безопасности для создания записей URL-адресов в списке разрешить или блокировать клиента

Подробные сведения о синтаксисе записей URL-адресов см. в разделе [Синтаксис](#url-syntax-for-the-tenant-allowblock-list) URL-адресов для раздела Разрешить или заблокировать список клиента в этой статье.

1. В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**

2. На странице **Разрешить или заблокировать** список клиента убедитесь, что выбрана вкладка URL-адресов, а затем нажмите **кнопку Блок** 

3. В **вылете** url-адресов блока, который отображается, настройте следующие параметры:

   - **Добавление URL-адресов для блокировки:** введите один URL-адрес на строку, не более 20.

   - **Никогда не истекает** срок действия: Сделайте один из следующих действий:

     - Проверьте отключение параметра (Отключение) и используйте истекает в поле, чтобы указать дату истечения ![ ](../../media/scc-toggle-off.png) срока действия записей. 

       или

     - Переместите окантовку вправо, чтобы настроить записи, чтобы никогда не истекал срок действия: ![Включенный переключатель](../../media/scc-toggle-on.png).

   - **Необязательный** примечание. Введите описательный текст для записей.

4. Когда вы закончите, нажмите **Добавить**.

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a>Используйте Центр & безопасности для создания записей файлов в списке разрешить или заблокировать клиента

1. В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**

2. На странице **Разрешить или блокировать** список клиента выберите вкладку **Файлы** и нажмите **кнопку Блок**.

3. В **добавлении файлов для блокировки** вылетов, которые появляются, настройте следующие параметры:

   - **Добавление хеша файла:** введите одно хеш-значение SHA256 за строку, не более 20.

   - **Никогда не истекает** срок действия: Сделайте один из следующих действий:

     - Проверьте отключение параметра (Отключение) и используйте истекает в поле, чтобы указать дату истечения ![ ](../../media/scc-toggle-off.png) срока действия записей. 

     или

     - Переместите окантовку вправо, чтобы настроить записи, чтобы никогда не истекал срок действия: ![Включенный переключатель](../../media/scc-toggle-on.png).

   - **Необязательный** примечание. Введите описательный текст для записей.

4. Когда вы закончите, нажмите **Добавить**.

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Используйте Центр & безопасности для просмотра записей в списке разрешить или заблокировать клиента

1. В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**

2. Выберите **вкладку URL-адреса** или **вкладку Files.**

Нажмите на следующие заголовки столбца, чтобы отсортироваться в порядке по возрастанию или убыванию:

- **Значение:** URL-адрес или hash файла.
- **Последняя обновленная дата**
- **Срок действия**
- **Примечание**

Щелкните **Поиск,** введите все или часть значения, а затем нажмите КНОПКУ ВВОДА, чтобы найти определенное значение. По завершению щелкните **значок Clear Search** Clear search ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .

Щелкните **Фильтр**. В **вылете Filter,** который отображается, настройте любой из следующих параметров:

- **Никогда не истекает:** Выберите отключение: ![ отключите или ](../../media/scc-toggle-off.png) включите. ![ ](../../media/scc-toggle-on.png)

- **Последнее обновление:** Выберите дату начала **(Из**), даты окончания **(To)** или обоих.

- **Срок действия:** Выберите дату начала **(От),** даты окончания **(к)** или и то, и другое.

По завершению нажмите кнопку **Применить**.

Чтобы очистить существующие фильтры, **щелкните Фильтр,** а в вылете **Фильтр,** который появится, щелкните **Очистить фильтры**.

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a>Используйте Центр & безопасности для изменения записей блоков в списке разрешить или заблокировать клиента

Вы не можете изменить существующие заблокированные URL-адрес или значения файлов в записи. Чтобы изменить эти значения, необходимо удалить и воссоздать запись.

1. В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**

2. Выберите **вкладку URL-адреса** или **вкладку Files.**

3. Выберите блок-запись, которую необходимо изменить, а затем нажмите **кнопку Изменить значок Редактирование** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .

4. В вылете, который отображается, настройте следующие параметры:

   - **Никогда не истекает** срок действия: Сделайте один из следующих действий:

     - Убедитесь, что параметр отключен (отключается) и используйте истекает в поле, чтобы указать дату истечения ![ ](../../media/scc-toggle-off.png) срока действия записи. 

       или

     - Перемещение точки вправо, чтобы настроить запись, чтобы не истек срок действия: ![Включенный переключатель](../../media/scc-toggle-on.png).

   - **Необязательный примечание.** Введите описательный текст для записи.

5. Когда закончите, нажмите кнопку **Сохранить**.

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a>Используйте Центр & безопасности для удаления блоковых записей из списка разрешить или заблокировать клиента

1. В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**

2. Выберите **вкладку URL-адреса** или **вкладку Files.**

3. Выберите блок-запись, которую необходимо удалить, а затем нажмите **кнопку Удалить значок Удалить** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .

4. В диалоговом октаге предупреждения нажмите кнопку **Удалить**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Используйте Exchange Online PowerShell или автономный EOP PowerShell для настройки списка разрешить/заблокировать клиента

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a>Использование PowerShell для добавления записей блоков в список разрешить или заблокировать клиента

Чтобы добавить блоковые записи в список разрешить или блокировать клиента, используйте следующий синтаксис:

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

В этом примере добавляется запись URL-адреса contoso.com всех поддоменов (например, contoso.com, www.contoso.com и xyz.abc.contoso.com). Поскольку мы не использовали параметры ExpireDate или NoExpiration, срок действия записи истекает через 30 дней.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

В этом примере добавляется запись заблокированного файла для указанных файлов, срок действия которых никогда не истекает.

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

Подробные сведения о синтаксисе и параметрах см. в [обзоре New-TenantAllowBlockListItems.](/powershell/module/exchange/new-tenantallowblocklistitems)

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>Использование PowerShell для просмотра записей в списке разрешить или заблокировать клиента

Чтобы просмотреть записи в списке разрешить или блокировать клиента, используйте следующий синтаксис:

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

В этом примере возвращаются все заблокированные URL-адреса.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

В этом примере возвращается информация для указанного значения hash файла.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-TenantAllowBlockListItems.](/powershell/module/exchange/get-tenantallowblocklistitems)

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a>Использование PowerShell для изменения записей блоков в списке разрешить или заблокировать клиента

Вы не можете изменить существующие значения URL-адресов или файлов в блок-записи. Чтобы изменить эти значения, необходимо удалить и воссоздать запись.

Чтобы изменить записи блокировки в списке разрешить или блокировать клиента, используйте следующий синтаксис:

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

В этом примере изменяется срок действия указанной блок-записи.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Подробные сведения о синтаксисе и параметрах см. в [ссылке Set-TenantAllowBlockListItems.](/powershell/module/exchange/set-tenantallowblocklistitems)

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a>Использование PowerShell для удаления записей блокировки из списка разрешить или заблокировать клиента

Чтобы удалить блоковые записи из списка "Разрешить или блокировать клиента", используйте следующий синтаксис:

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

В этом примере удаляется указанная запись URL-адреса блокировки из списка разрешить или блокировать клиента.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Подробные сведения о синтаксисе и параметрах см. в [ссылке Remove-TenantAllowBlockListItems.](/powershell/module/exchange/remove-tenantallowblocklistitems)

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>Синтаксис URL-адреса для списка разрешить или блокировать клиента

- Ip4v и IPv6-адреса разрешены, но порты TCP/UDP — нет.

- Расширения filename не разрешены (например, test.pdf).

- Юникод не поддерживается, но Punycode есть.

- Имена хост-кодов разрешены, если все следующие утверждения верны:
  - Имя хост-пользователя содержит период.
  - Существует по крайней мере один символ слева от периода.
  - Справа от периода имеется по крайней мере два символа.

  Например, `t.co` разрешено или `.com` `contoso.` запрещено.

- Subpaths не подразумеваются.

  Например, `contoso.com` не включает `contoso.com/a` .

- Поддиальды (*) разрешены в следующих сценариях:

  - За левой подгруппой должен следовать период, чтобы указать поддомен.

    Например, `*.contoso.com` разрешено; `*contoso.com` запрещено.

  - Правая подмайка должна следовать за полосой вперед (/), чтобы указать путь.

    Например, `contoso.com/*` разрешено или `contoso.com*` `contoso.com/ab*` запрещено.

  - Все подпаты не подразумеваются правой подгруппой.

    Например, `contoso.com/*` не включает `contoso.com/a` .

  - `*.com*` является недействительным (не разрешимый домен, а правая подкратная карточка не следует передовую черту).

  - В IP-адресах запрещено использовать поддиальдные знаки.

- Символ tilde (~) доступен в следующих сценариях:

  - Левая тильда подразумевает домен и все поддомены.

    Например, `~contoso.com` включает `contoso.com` и `*.contoso.com` .

- Записи URL-адресов, содержащие протоколы (например, или ) не будут работать, так как URL-записи применяются `http://` `https://` к всем `ftp://` протоколам.

- Имя пользователя или пароль не поддерживаются или не требуются.

- Кавычка (' или ") являются недействительными символами.

- URL-адрес должен включать все перенаправления, где это возможно.

### <a name="url-entry-scenarios"></a>Сценарии ввода URL-адресов

Допустимые записи URL-адресов и их результаты описаны в следующих разделах.

#### <a name="scenario-no-wildcards"></a>Сценарий: нет поддиальдов

**Запись:**`contoso.com`

- **Разрешить совпадение:** contoso.com

- **Разрешить не совпадать:**

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Совпадение блоков:**

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Блок не соответствует**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Сценарий: левая подгруппа (subdomain)

**Запись:**`*.contoso.com`

- **Разрешить совпадение** **и блокировку:**

  - www.contoso.com
  - xyz.abc.contoso.com

- **Разрешить не совпадать и** **блок не совпадает:**

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Сценарий: правая под диктовка в верхней части пути

**Запись:**`contoso.com/a/*`

- **Разрешить совпадение** **и блокировку:**

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Разрешить не совпадать и** **блок не совпадает:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Сценарий: левая тильда

**Запись:**`~contoso.com`

- **Разрешить совпадение** **и блокировку:**

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Разрешить не совпадать и** **блок не совпадает:**

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Сценарий: суффикс правой подстановки

**Запись:**`contoso.com/*`

- **Разрешить совпадение** **и блокировку:**

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Разрешить не совпадать** и **блок не совпадает**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Сценарий. Поддомайн левой подстановки и суффикс правой подстановки

**Запись:**`*.contoso.com/*`

- **Разрешить совпадение** **и блокировку:**

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Разрешить не совпадать** и **блок не соответствует**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Сценарий: левая и правая тильда

**Запись:**`~contoso.com~`

- **Разрешить совпадение** **и блокировку:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Разрешить не совпадать и** **блок не совпадает:**

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Сценарий: IP-адрес

**Запись:**`1.2.3.4`

- **Разрешить совпадение** **и блокировку:** 1.2.3.4

- **Разрешить не совпадать и** **блок не совпадает:**

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>IP-адрес с правой подголой карточкой

**Запись:**`1.2.3.4/*`

- **Разрешить совпадение** **и блокировку:**

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Примеры недействительных записей

Следующие записи являются недействительными:

- **Отсутствующие или недействительные значения домена:**

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*PDF

- **Под диктовка текста или без интервалов символов:**

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **IP-адреса с портами:**

  - contoso.com:443
  - abc.contoso.com:25

- **Неописуемые подражательные знаки:**

  - \*
  - \*.\*

- **Средние подкарды:**

  - conto \* so.com
  - conto~so.com

- **Двойные подкарды**

  - contoso.com/\*\*
  - contoso.com/\*/\*