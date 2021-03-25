---
title: Просмотр событий уменьшения поверхности атаки
description: Импорт пользовательских представлений для просмотра событий уменьшения поверхности атаки.
keywords: представление событий, использование охраны, аудита, проверки, событий
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: de605a667284c1218a3efe6e388d99b26b42e333
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076614"
---
# <a name="view-attack-surface-reduction-events"></a>Просмотр событий уменьшения поверхности атаки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Просмотрите события уменьшения поверхности атаки в обозревателе событий, чтобы отслеживать, какие правила или параметры работают. Вы также можете определить, слишком ли "шумно" или влияет на рабочий процесс.

Просмотр событий удобен при оценке функций. Вы можете включить режим аудита для функций или параметров, а затем просмотреть, что произошло бы, если бы они были полностью включены.

В этой статье перечислены все события, связанные с ними функции или параметры, а также описано, как создавать настраиваемые представления для фильтрации определенных событий.

Подробные отчеты о событиях и блоках в рамках Службы безопасности Windows, если у вас есть подписка на E5, и используйте [Microsoft Defender для конечной точки.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)

## <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>Использование пользовательских представлений для проверки возможностей уменьшения поверхности атаки

Создайте настраиваемые представления в windows Event Viewer, чтобы просмотреть события только для определенных возможностей и параметров. Самый простой способ — импорт настраиваемого представления в качестве XML-файла. XML можно скопировать непосредственно на этой странице.

Вы также можете вручную перейти к области событий, соответствующей этой функции.

### <a name="import-an-existing-xml-custom-view"></a>Импорт существующего пользовательского представления XML

1. Создайте пустой файл .txt и скопируйте XML для пользовательского представления, который необходимо использовать в файле .txt. Сделайте это для каждого из пользовательских представлений, которые вы хотите использовать. Переименуйте файлы следующим образом (убедитесь, что вы измените тип с .txt на .xml):
    - Настраиваемый просмотр событий доступа к управляемым папкам: *cfa-events.xml*
    - Использование настраиваемой точки зрения событий *защиты:ep-events.xml*
    - Настраиваемый просмотр событий уменьшения *поверхности* атаки:asr-events.xml
    - Настраиваемые представления событий сети и защиты: *np-events.xml*

2. Введите **просмотр событий в** меню Пуск и откройте **viewer событий**.

3. Выберите   >  **настраиваемый просмотр импорта действий...**

    ![Анимация с выделением настраиваемого представления Import слева от окна даже просмотра](/windows/security/threat-protection/images/events-import)

4. Перейдите к месту извлечения XML-файла для нужного пользовательского представления и выберите его.

5. Выберите **Открыть**.

6. Это создаст настраиваемую точку зрения, которая фильтрует только для показа событий, связанных с этой функцией.

### <a name="copy-the-xml-directly"></a>Скопируйте XML напрямую

1. Введите **просмотра событий в** меню Пуск и откройте для просмотра событий Windows . 

2. На левой панели в статье **Действия** выберите **Создание настраиваемого представления...**

    ![Анимация, выделяемая для создания настраиваемого параметра представления в окне просмотра событий](/windows/security/threat-protection/images/events-create)

3. Перейдите на вкладку XML и выберите **изменение запроса вручную.** Вы увидите предупреждение о том, что вы не можете изменить запрос с помощью вкладки **Filter,** если вы используете XML-параметр. Выберите **Да**.

4. Вклеить XML-код для функции, необходимой для фильтрации событий из раздела XML.

5. Нажмите кнопку **ОК**. Укажите имя фильтра.

6. Это создаст настраиваемую точку зрения, которая фильтрует только для показа событий, связанных с этой функцией.

### <a name="xml-for-attack-surface-reduction-rule-events"></a>XML для событий правила уменьшения поверхности атаки

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-controlled-folder-access-events"></a>XML для событий управляемого доступа к папкам

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-exploit-protection-events"></a>XML для событий защиты от эксплойтов

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Security-Mitigations/KernelMode">
   <Select Path="Microsoft-Windows-Security-Mitigations/KernelMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Concurrency">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Contention">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Messages">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Operational">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Power">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Render">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Tracing">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/UIPI">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="System">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Security-Mitigations/UserMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-network-protection-events"></a>XML для событий защиты сети

```xml
<QueryList>
 <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
  <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
  <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
 </Query>
</QueryList>
```

## <a name="list-of-attack-surface-reduction-events"></a>Список событий уменьшения поверхности атаки

Все события уменьшения поверхности атаки находятся в журналах приложений и служб > **Microsoft > Windows,** а затем в папке или поставщике, как указано в следующей таблице.

Вы можете получить доступ к этим событиям в windows Event viewer:

1. Откройте меню **Пуск** и введите просмотра **событий,** а затем выберите результат **просмотра** событий.
2. Расширь журналы приложений и **служб > Microsoft > Windows,** а затем перейдите в папку, указанную в статье **Provider/source** в таблице ниже.
3. Дважды щелкните элемент sub, чтобы увидеть события. Прокрутите события, чтобы найти то, что вы ищете.

   ![Анимация с использованием просмотра событий](/windows/security/threat-protection/images/event-viewer)

Функция | Поставщик/источник | Идентификатор события | Описание
:-|:-|:-:|:-
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 1 | Аудит ACG
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 2 | Соблюдение ACG
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 3 | Не разрешайте аудит детских процессов
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 4  | Не разрешайте блокировку детских процессов
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 5  | Блок аудита изображений с низкой целостностью
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 6  | Блок блок изображений с низкой целостностью
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 7  | Блокировка аудита удаленных изображений
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 8  | Блок удаленных изображений
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 9  | Отключение аудита вызовов системы win32k
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 10  | Отключение блокировки системных вызовов win32k
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 11 | Аудит охраны целостности кода
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 12  | Блок защиты целостности кода
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 13 | Аудит EAF
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 14  | Соблюдение EAF
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 15  | Аудит EAF+
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 16  | Соблюдение EAF+
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 17  | Аудит IAF
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 18  | Соблюдение IAF
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 19 | Аудит ROP StackPivot
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 20 | ROP StackPivot enforce
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 21 | Аудит ROP CallerCheck
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 22 | Принудительное выполнение ROP CallerCheck
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 23 | Аудит ROP SimExec
Защита от эксплойтов | Security-Mitigations (Режим ядра/режим пользователя) | 24 | Принудительное выполнение ROP SimExec
Защита от эксплойтов | WER-Diagnostics | 5  | Блок CFG
Защита от эксплойтов | Win32K (операционная) | 260 | Ненарушимый шрифт
Защита сети | Защитник Windows (операционная) | 5007 | Событие при смене параметров
Защита сети | Защитник Windows (операционная) | 1125 | Событие, когда защита сети загорелась в режиме аудита
Защита сети | Защитник Windows (операционная) | 1126 | Событие, когда защита сети загорелась в блок-режиме
Управляемый доступ к папкам | Защитник Windows (операционная) | 5007 | Событие при смене параметров
Управляемый доступ к папкам | Защитник Windows (операционная) | 1124 | Событие доступа к управляемой папке с аудитом
Управляемый доступ к папкам | Защитник Windows (операционная) | 1123 | Событие доступа к заблокированной управляемой папке
Управляемый доступ к папкам | Защитник Windows (операционная) | 1127 | Заблокированный сектор доступа к контролируемым папкам записи события блокировки
Управляемый доступ к папкам | Защитник Windows (операционная) | 1128 | Событие блока записи сектора записи контролируемых папок с аудитом
Сокращение направлений атак | Защитник Windows (операционная) | 5007 | Событие при смене параметров
Сокращение направлений атак | Защитник Windows (операционная) | 1122 | Событие при пожаре правила в режиме аудита
Сокращение направлений атак | Защитник Windows (операционная) | 1121 | Событие при пожаре правила в block-mode
