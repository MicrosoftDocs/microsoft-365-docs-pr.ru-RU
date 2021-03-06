---
title: Использование управления версиями записей для обновления записей, хранящихся в SharePoint или OneDrive
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Узнайте о записях, которые помогут вам внедрить решение для управления записями в Microsoft 365.
ms.openlocfilehash: 86fbd84e03263ca5d99e1bfe6ab572589dc98bbd
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226135"
---
# <a name="use-record-versioning-to-update-records-stored-in-sharepoint-or-onedrive"></a>Использование управления версиями записей для обновления записей, хранящихся в SharePoint или OneDrive

>*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Так как нормативные записи блокируют редактирование, управление версиями записей для них недоступно.

Возможность пометить документ как [запись](records-management.md#records) и ограничить действия, которые можно выполнять с записью, является основной целью любого решения по управлению записями. Однако для создания последующих версий может также потребоваться совместная работа.

Например, контракт продажи можно пометить как запись, и затем, когда требуется этот контракт обновить и внести новые положение, пометить последнюю версию как новую запись, и при этом сохраняется и предыдущая версия записи. Для таких случаев в SharePoint и OneDrive поддерживается *управление версиями записей*. Папки записных книжек OneNote не поддерживают управление версиями записей.

Чтобы использовать управление версиями записей, сначала [отметьте документ и пометьте его как запись](declare-records.md). В этот момент рядом с меткой хранения отобразится свойство документа под названием *Состояние записи*, а изначальное состояние записи сменится на **Заблокировано**.

Доступны перечисленные ниже действия:

- **Периодическое редактирование и сохранение отдельных версий документа как записей с разблокировкой и блокировкой свойства "Состояние записи".** Только когда свойство **Состояние записи** имеет значение **Заблокировано**, новая версия записи сохраняется. Это переключение между заблокированными и разблокированными версиями уменьшает риск сохранения ненужных версий и копий документа.

- **Автоматическое сохранение записей в репозитории записей на месте, который размещается внутри семейства веб-сайтов.** Содержимое любого семейства веб-сайтов в SharePoint и OneDrive сохраняется в соответствующей архивной библиотеке. Место хранения версий записей в этой библиотеке —папка "Записи".

- **Сохранение всегда актуального документа, включающего в себя все версии.** В каждом документе SharePoint и OneDrive по умолчанию имеется журнал версий, который можно найти в меню элемента. Благодаря такому журналу версий можно легко определить, какие версии являются записями, и просмотреть эти документы.

> [!TIP]
> При управлении версиями записей с помощью метки хранения, предусматривающей удаление, рекомендуется также присвоить параметру хранения **Началом периода хранения считается:** значение **Дата создания меток хранения элементов**. При использовании этого параметра метки начало периода хранения сбрасывается для каждой новой версии записи, что гарантирует удаление более старых версий перед новыми версиями.

Управление версиями записей автоматически предлагается для любого документа с меткой хранения, помечающей его как запись. При просмотре пользователем свойств документа с использованием области сведений **Состояние записи** может переключиться с **Заблокировано** на **Разблокировано**. Одним действием в папке архивной библиотеки "Записи" создается запись, которая остается там в течение оставшегося периода хранения.

Пока документ разблокирован, редактировать файл может любой пользователь со стандартными разрешениями на редактирование. При этом, однако, удалить файл пользователи не могут, так как он все еще является записью. После завершения редактирования пользователь может переключить **Состояние записи** с **Разблокировано** на **Заблокировано**, что запрещает дальнейшие правки в этом состоянии.
<br/><br/>

![Свойство состояния записи в документе, обозначенном как запись](../media/recordversioning8.png)

## <a name="locking-and-unlocking-a-record"></a>Блокировка и разблокировка записи

После того, как метка, которая помечает содержимое как запись, применена к документу, любой пользователь с разрешениями Contribute или более узким уровнем разрешения может разблокировать запись или заблокировать разблокированную запись.
<br/><br/>

![Состояние записи демонстрирует, что документ, имеющий статус записи, разблокирован](../media/recordversioning9.png)

Разблокировка записи пользователем приводит к нижеуказанным результатам.

1. При отсутствии в текущем семействе веб-сайтов библиотеки хранения архивов такая библиотека создается.

2. При отсутствии в архивной библиотеке папки записи такая запись создается.

3. При использовании действия **Копировать в** самая последняя версия документа копируется в папку "Записи". Действие **Копировать в** относится только к последней версии документа и не затрагивает предыдущие версии. Скопированный документ теперь рассматривается как версия документа в виде записи, и файл приобретает следующий формат: \[Title GUID Version\#\]

4. Копия, созданная в папке «Записи», добавлена в журнал версий исходного документа, и в поле примечаний к этой версии отображается слово **Запись**.

5. Исходный документ — это новая версия, которую можно редактировать, но не удалять. В столбце библиотеки документов **Элемент является записью** по-прежнему содержится значение **Да**, так как документ все равно является записью, несмотря на то, что его теперь можно редактировать.

После того как пользователь заблокирует запись, внесение изменений в исходный документ снова станет невозможным. Однако именно благодаря действию по разблокировке записи ее версия появляется в папке "Записи", расположенной в архивной библиотеке.

## <a name="record-versions"></a>Версии записей

Каждый раз, когда пользователь производит разблокировку записи, копия последней версии этой записи появляется в архивной библиотеке со значением **Запись** в поле **Примечания** журнала версий.
<br/><br/>

![Отображение записи в архивной библиотеке](../media/recordversioning10.png)

Чтобы просмотреть журнал версий, выберите документ в библиотеке документов, а затем в меню элемента выберите **Журнал версий**.

## <a name="where-records-are-stored"></a>Место хранения записей

Записи хранятся в папке "Записи" архивной библиотеки на сайте верхнего уровня в семействе веб-сайтов. В левой панели навигации на сайте верхнего уровня выберите **Содержание сайта** \> **Архивная библиотека**.
<br/><br/>

![Архивная библиотека](../media/recordversioning11.png)

<br/><br/>

![Папка "Записи" в архивной библиотеке](../media/recordversioning12.png)

Подробнее о принципах работы архивной библиотеки см. в статье [Как работает хранение для SharePoint и OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).

## <a name="searching-the-audit-log-for-record-versioning-events"></a>Поиск событий управления версиями записей в журнале аудита

Действия по блокировке и разблокировке записей регистрируются в журнале аудита. В разделе **Действия с файлами и страницами** выберите **Для записи установлено новое состояние: "заблокирована"** и **Для записи установлено новое состояние: "разблокирована"**.

Дополнительные сведения о поиске таких событий см. в статье [Поиск в журнале аудита в Центре безопасности и соответствия требованиям](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).

## <a name="next-steps"></a>Дальнейшие действия

Другие сценарии, поддерживаемые службой управления записей, см. в разделе [Обычные сценарии для управления записями](get-started-with-records-management.md#common-scenarios-for-records-management).
