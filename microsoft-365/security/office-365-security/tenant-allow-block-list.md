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
ms.openlocfilehash: 67c3badb86f1cfb9bf644cc202ed67e3163a6772
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933159"
---
# <a name="manage-the-tenant-allowblock-list"></a>Управление списком разрешенных и запрещенных клиентов

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> Функции, описанные в этой статье, находятся в предварительном просмотре, могут изменяться и недоступны во всех организациях.  Если в вашей организации нет функций подмены, как описано в этой статье, см. более старый опыт управления подменой в manage [spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).
>
> В данный момент нельзя **настроить** разрешенный URL-адрес или элементы файлов в списке разрешить или заблокировать клиента.

В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без Exchange Online почтовых ящиков, вы можете не согласиться с вердиктом по фильтрации EOP. Например, хорошее сообщение может быть помечено как плохое (ложное положительное) или плохое сообщение может быть разрешено (ложное отрицательное).

Список разрешить или заблокировать клиента на портале Microsoft 365 Defender позволяет вручную переопредировать Microsoft 365 фильтрации. Список разрешить/заблокировать клиента используется во время потока почты и во время щелчков пользователя. Можно указать следующие типы переопределей:

- URL-адреса для блокировки.
- Файлы для блокировки.
- Spoofed senders to allow or block. Если переопределять решение разрешить [](learn-about-spoof-intelligence.md)или заблокировать в анализе подмены сведений, подмена отправитель становится ручным разрешением или блокировкой записи, которая отображается только на вкладке **Spoof** в списке разрешить или заблокировать клиента. Вы также можете вручную создавать записи для подмены отправителей, прежде чем они будут обнаружены с помощью подмены.

В этой статье описывается настройка записей в списке разрешить или блокировать клиента на портале Microsoft 365 Defender или в PowerShell (Exchange Online PowerShell для Microsoft 365 организаций с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без Exchange Online почтовых ящиков).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com/>. Чтобы перейти непосредственно на страницу **Разрешить или блокировать списки клиента,** используйте <https://security.microsoft.com/tenantAllowBlockList> .

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

- Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Exchange Online:
  - **URL-адреса и файлы:**
    - Чтобы добавить и удалить значения из списка "Разрешить или заблокировать клиента", необходимо быть членом группы ролей администратора организации или **администратора** безопасности. 
    - Чтобы получить доступ только для чтения к списку разрешить или заблокировать клиента, необходимо быть членом групп ролей **Global Reader** или **Security Reader.**
  - **Spoofing**: Одна из следующих комбинаций:
    - **Управление организацией**
    - **Администратор безопасности** <u>и</u> **конфигурация** только для просмотра или управление организацией только **для просмотра.**

  Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365. Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).
  >
  > - Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.

## <a name="use-the-microsoft-365-defender-portal-to-create-block-url-entries-in-the-tenant-allowblock-list"></a>Используйте портал Microsoft 365 Defender для создания записей блокировки URL-адресов в списке разрешить или заблокировать клиента

1. На портале Microsoft 365 Defender **перейдите в** раздел Политики & правила правил политики угрозы Для клиента разрешить \>  \>  или \> **заблокировать списки**.

2. На странице **Разрешить или блокировать** список клиента убедитесь, что вкладка **URL-адресов** выбрана, а затем нажмите ![ кнопку Блок ](../../media/m365-cc-sc-create-icon.png) **значок Block**.

3. В **вылете** url-адресов блока, который отображается, настройте следующие параметры:
   - **Добавление URL-адресов с поддиальдами:** введите один URL-адрес на одну строку, не более 20. Подробные сведения о синтаксисе записей URL-адресов см. в разделе [Синтаксис](#url-syntax-for-the-tenant-allowblock-list) URL-адресов для раздела Разрешить или заблокировать список клиента в этой статье.
   - **Никогда не истекает** срок действия: Сделайте один из следующих действий:
     - Убедитесь, что параметр отключен (отключите) и используйте удаление в поле, чтобы указать дату истечения ![ ](../../media/scc-toggle-off.png) срока действия записей. 

       или

     - Переместите окантовку вправо, чтобы настроить записи, чтобы никогда не истекал срок действия: ![Включенный переключатель](../../media/scc-toggle-on.png).
   - **Необязательный** примечание. Введите описательный текст для записей.

4. Когда вы закончите, нажмите **Добавить**.

## <a name="use-the-microsoft-365-defender-portal-to-create-block-file-entries-in-the-tenant-allowblock-list"></a>Использование портала Microsoft 365 Defender для создания записей заблокированных файлов в списке разрешить или заблокировать клиента

1. На портале Microsoft 365 Defender **перейдите в** раздел Политики & правила правил политики угрозы Для клиента разрешить \>  \>  или \> **заблокировать списки**.

2. На странице **Разрешить или блокировать** список клиента выберите вкладку **Файлы** и нажмите блок ![ блок ](../../media/m365-cc-sc-create-icon.png) **значка Block**.

3. В **вылете блок-файлов,** который отображается, настройте следующие параметры:
   - **Добавление хеша файла:** введите одно хеш-значение SHA256 за строку, не более 20.
   - **Никогда не истекает** срок действия: Сделайте один из следующих действий:
     - Убедитесь, что параметр отключен (отключите) и используйте удаление в поле, чтобы указать дату истечения ![ ](../../media/scc-toggle-off.png) срока действия записей. 

     или

     - Переместите окантовку вправо, чтобы настроить записи, чтобы никогда не истекал срок действия: ![Включенный переключатель](../../media/scc-toggle-on.png).
   - **Необязательный** примечание. Введите описательный текст для записей.

4. Когда вы закончите, нажмите **Добавить**.

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Использование портала Microsoft 365 Defender для создания записей отправителя с подменой или блокировки в списке разрешить/заблокировать клиента

**Примечания**:

- Только сочетание _подмены_ пользователя  и инфраструктуры отправки, как определено в доменной паре, разрешено или заблокировано от подмены.
- При настройке разрешить или заблокировать запись для доменной пары сообщения из этой пары домена больше не отображаются в анализе подмены сведений.
- Срок действия записей для поддельных отправителей никогда не истекает.

1. На портале Microsoft 365 Defender **перейдите в** раздел Политики & правила правил политики угрозы Для клиента разрешить \>  \>  или \> **заблокировать списки**.

2. На странице **Разрешить или блокировать** список клиента выберите вкладку **Spoofing** и нажмите ![ кнопку Добавить значок ](../../media/m365-cc-sc-create-icon.png) **Block**.

3. В **вылете Добавить новые пары** домена, который появится, настройте следующие параметры:
   - **Добавление новых доменных пар с подкардами:** введите одну доменную пару в строку, не более 20. Подробные сведения о синтаксисе для записей подмены отправителя см. в разделе Синтаксис пары домена для записей подмены отправителя в разделе [Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) более поздней в этой статье.
   - **Тип Spoof:** Выберите одно из следующих значений:
     - **Внутренний:** подмена отправитель находится в домене, который принадлежит вашей организации [(принятый домен).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
     - **Внешний.** Поддельный отправитель находится во внешнем домене.
   - **Действие:** **Выберите разрешить или** **заблокировать**.

4. Когда вы закончите, нажмите **Добавить**.

## <a name="use-the-microsoft-365-defender-portal-to-view-entries-in-the-tenant-allowblock-list"></a>Используйте портал Microsoft 365 Defender для просмотра записей в списке разрешить или заблокировать клиента

1. На портале Microsoft 365 Defender **перейдите в** раздел Политики & правила правил политики угрозы Для клиента разрешить \>  \>  или \> **заблокировать списки**.

2. Выберите вкладку, которая вам нужна. Доступные столбцы зависят от выбранной вкладки:

   - **URL-адреса:**
     - **Значение:** URL-адрес.
     - **Действие**: Блок **значений**.
     - **Последнее обновление**
     - **Удаление на**
     - **Примечания**
   - **Files**
     - **Значение:** hash файла.
     - **Действие**: Блок **значений**.
     - **Последнее обновление**
     - **Удаление на**
     - **Примечания**
   - **Спуфинг**
     - **Подмена пользователя**
     - **Отправка инфраструктуры**
     - **Тип Spoof:** Значение **Внутреннее или** **Внешнее**.
     - **Действие:** блок **значения или** **разрешить**.

   Вы можете нажать на столбец заголовка для сортировки в порядке по возрастанию или убыванию.

   Вы можете нажать **группу,** чтобы сгруппить результаты. Доступные значения зависят от выбранной вкладки:

   - **URL-адреса.** Результаты можно сгруппить по **action.**
   - **Файлы.** Результаты можно сгруппить по **action.**
   - **Спуфинг:** Результаты можно сгруппить по **типу Action** или **Spoof.**

   Щелкните **Поиск,** введите все или часть значения, а затем нажмите КНОПКУ ВВОДА, чтобы найти определенное значение. По завершению щелкните ![ значок Clear search ](../../media/m365-cc-sc-close-icon.png) **Clear Search .**

   Щелкните **Фильтр,** чтобы отфильтровать результаты. Значения, доступные в **вылете Filter,** зависят от выбранной вкладки:

   - **URL-адреса**
     - **Действие**
     - **Не истекает срок действия**
     - **Последняя обновленная дата**
     - **Удаление на**
   - **Files**
     - **Действие**
     - **Не истекает срок действия**
     - **Последнее обновление**
     - **Удаление на**
   - **Спуфинг**
     - **Действие**
     - **Тип Spoof**

   По завершению нажмите кнопку **Применить**. Чтобы очистить существующие фильтры, **щелкните Фильтр,** а в вылете **Фильтр,** который появится, щелкните **Очистить фильтры**.

## <a name="use-the-microsoft-365-defender-portal-to-modify-entries-in-the-tenant-allowblock-list"></a>Использование портала Microsoft 365 Defender для изменения записей в списке разрешить или заблокировать клиента

1. На портале Microsoft 365 Defender **перейдите в** раздел Политики & правила правил политики угрозы Для клиента разрешить \>  \>  или \> **заблокировать списки**.

2. Выберите вкладку, которая содержит тип записи, которую необходимо изменить:
   - **URL-адреса**
   - **Files**
   - **Спуфинг**

3. Выберите запись, которую необходимо изменить, а затем нажмите ![ кнопку Изменить значок ](../../media/m365-cc-sc-edit-icon.png) **Изменить**. Значения, которые можно изменить в вылете, зависят от вкладки, выбранной на предыдущем шаге:
   - **URL-адреса**
     - **Не истекает** и/или не истекает срок действия.
     - **Необязательная заметка**
   - **Files**
     - **Не истекает** и/или не истекает срок действия.
     - **Необязательная заметка**
   - **Спуфинг**
     - **Действие.** Можно изменить значение **Разрешить или** **заблокировать**.
4. По завершении нажмите кнопку **Сохранить**.

## <a name="use-the-microsoft-365-defender-portal-to-remove-entries-from-the-tenant-allowblock-list"></a>Использование портала Microsoft 365 Defender для удаления записей из списка разрешить или заблокировать клиента

1. На портале Microsoft 365 Defender **перейдите в** раздел Политики & правила правил политики угрозы Для клиента разрешить \>  \>  или \> **заблокировать списки**.

2. Выберите вкладку, которая содержит тип записи, которую необходимо удалить:
   - **URL-адреса**
   - **Files**
   - **Спуфинг**

3. Выберите запись, которую необходимо удалить, а затем нажмите ![ кнопку Удалить значок ](../../media/m365-cc-sc-delete-icon.png) **Delete**.

4. В диалоговом октаге предупреждения нажмите кнопку **Удалить**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Используйте Exchange Online PowerShell или автономный EOP PowerShell для настройки списка разрешить или заблокировать клиента

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a>Использование PowerShell для добавления блок-файла или записей URL-адресов в список разрешить или заблокировать клиента

Чтобы добавить блок-файл или ЗАПИСИ URL-адресов в список Разрешить или Заблокировать клиента, используйте следующий синтаксис:

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

В этом примере добавляется запись заблокированного файла для указанных файлов, срок действия которых никогда не истекает.

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

В этом примере добавляется запись URL-адреса contoso.com всех поддоменов (например, contoso.com, www.contoso.com и xyz.abc.contoso.com). Поскольку мы не использовали параметры ExpireDate или NoExpiration, срок действия записи истекает через 30 дней.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

Подробные сведения о синтаксисе и параметрах см. в [обзоре New-TenantAllowBlockListItems.](/powershell/module/exchange/new-tenantallowblocklistitems)

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a>Используйте PowerShell, чтобы добавить в список разрешить или заблокировать поддельные записи отправителя в список разрешить или заблокировать клиента.

Чтобы добавить подменные записи отправителя в список разрешить или заблокировать клиента, используйте следующий синтаксис:

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

Подробные сведения о синтаксисе и параметрах см. в [обзоре New-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/new-tenantallowblocklistspoofitems)

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a>Использование PowerShell для просмотра записей блок-файла или URL-адресов в списке разрешить или заблокировать клиента

Чтобы просмотреть записи заблокированного файла или URL-адресов в списке разрешить или заблокировать клиента, используйте следующий синтаксис:

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

В этом примере возвращается информация для указанного значения hash файла.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

В этом примере возвращаются все заблокированные URL-адреса.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-TenantAllowBlockListItems.](/powershell/module/exchange/get-tenantallowblocklistitems)

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Использование PowerShell для просмотра записей подмены отправителя в списке разрешить или заблокировать подмену

Чтобы просмотреть поддельные записи отправителя в списке "Разрешить или заблокировать клиента", используйте следующий синтаксис:

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

В этом примере возвращаются все поддельные записи отправителя в списке разрешить или заблокировать клиента.

```powershell
Get-TenantAllowBlockListSpoofItems
```

В этом примере возвращаются все записи подмены отправитель, которые являются внутренними.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

В этом примере возвращаются все заблокированные поддельные записи отправитель, которые являются внешними.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/get-tenantallowblocklistspoofitems)

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a>Использование PowerShell для изменения записей блок-файла и URL-адресов в списке разрешить или заблокировать клиента

Чтобы изменить записи заблокированного файла и URL-адресов в списке разрешить или заблокировать клиента, используйте следующий синтаксис:

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

В этом примере изменяется срок действия указанной записи URL-адреса блока.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

Подробные сведения о синтаксисе и параметрах см. в [ссылке Set-TenantAllowBlockListItems.](/powershell/module/exchange/set-tenantallowblocklistitems)

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Использование PowerShell для изменения допуска или блокировки подмены записей отправителя в списке разрешить или заблокировать клиента

Чтобы изменить допустимые или заблокированные записи отправителя в списке разрешить или заблокировать клиента, используйте следующий синтаксис:

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

В этом примере изменяется подмена записи отправитель с разрешением на блокировку.

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

Подробные сведения о синтаксисе и параметрах см. в [инструкции Set-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/set-tenantallowblocklistspoofitems)

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a>Использование PowerShell для удаления URL-адресов или записей файлов из списка разрешить или заблокировать клиента

Чтобы удалить записи файлов и URL-адресов из списка разрешить или заблокировать клиента, используйте следующий синтаксис:

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

В этом примере удаляется указанная запись URL-адреса блокировки из списка разрешить или блокировать клиента.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Подробные сведения о синтаксисе и параметрах см. в [ссылке Remove-TenantAllowBlockListItems.](/powershell/module/exchange/remove-tenantallowblocklistitems)

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a>Использование PowerShell для удаления записей отправителя с подменой или блокировки из списка разрешить/заблокировать клиента

Чтобы удалить записи отправителя подмены из списка разрешить или заблокировать подмену, используйте следующий синтаксис:

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

Подробные сведения о синтаксисе и параметрах см. в [обзоре Remove-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)

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
  - \*.pdf

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

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Синтаксис пары домена для подмены записей отправителя в списке Разрешить или Заблокировать клиента

Доменная пара для подмены отправителя в Списке разрешить или заблокировать клиента использует следующий синтаксис: `<Spoofed user>, <Sending infrastructure>` .

- **Поддельный** пользователь. Это значение включает адрес электронной почты подмены пользователя, отображаемого в поле **From** в клиентах электронной почты. Этот адрес также известен как `5322.From` адрес. Допустимыми являются следующие значения:
  - Отдельный адрес электронной почты (например, chris@contoso.com).
  - Домен электронной почты (например, contoso.com).
  - Символ под диктовки (например, \* ).

- **Инфраструктура отправки.** Это значение указывает источник сообщений от подмены пользователя. Допустимыми являются следующие значения:
  - Домен, найденный в обратной DNS-записи IP-адреса сервера электронной почты источника (например, fabrikam.com).
  - Если исходный IP-адрес не имеет записи PTR, инфраструктура отправки определена как \<source IP\> /24 (например, 192.168.100.100/24).

Вот несколько примеров допустимой пары домена для определения поддельных отправителей:

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

Максимальное количество подмены записей отправитель 1000.

Добавление доменной пары позволяет или  блокирует только сочетание подмены пользователя и *инфраструктуры* отправки. Он не разрешает электронную почту от подмены пользователя из любого источника, а также не разрешает электронную почту из источника инфраструктуры отправки для любого подменного пользователя. 

Например, вы добавляете допустимую запись для следующей пары доменов:

- **Домен**: gmail.com
- **Инфраструктура**: tms.mx.com

Подмену допускаются только сообщения из этого *домена* и пара инфраструктуры отправки. Другие отправители, пытающиеся gmail.com, не допускаются. Сообщения от отправителей в других доменах, исходя из tms.mx.com, проверяются с помощью spoof intelligence.
