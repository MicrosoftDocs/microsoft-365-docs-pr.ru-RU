---
title: Изоляция и управление доступом в Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: Сводка. Описание изоляции и управления доступом в различных приложениях Microsoft 365.
ms.openlocfilehash: 40a1f1d93fe34333366e456cc006ab2d1c700a83
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693286"
---
# <a name="isolation-and-access-control-in-microsoft-365"></a>Изоляция и управление доступом в Microsoft 365

Azure Active Directory (Azure AD) и Microsoft 365 используют очень сложную модель данных, включающую десятки служб, сотни сущностей, тысячи отношений и десятки тысяч атрибутов. На высоком уровне Azure AD и каталоги служб — это контейнеры клиентов и получателей, которые синхронизируются с помощью протоколов репликации на основе состояния. Помимо сведений о каталоге, хранящихся в Azure AD, у каждой рабочей нагрузки службы есть своя инфраструктура служб каталогов.
 
![Синхронизация данных клиента Microsoft 365](../media/office-365-isolation-tenant-data-sync.png)

В этой модели нет единого источника данных каталога. Конкретные системы принадлежат отдельным частям данных, но ни одна система не содержит все данные. Службы Microsoft 365 взаимодействуют с Azure AD в этой модели данных. Azure AD — это «система истинности» для общих данных, которая обычно представляет собой небольшие и статические данные, используемые каждой службой. Федеративная модель, используемая в Microsoft 365 и Azure AD, предоставляет общее представление данных.

Microsoft 365 использует как физическое хранилище, так и облачное хранилище Azure. Exchange Online (включая Exchange Online Protection) и Skype для бизнеса используют собственное хранилище для данных клиентов. SharePoint Online использует как хранилище данных SQL Server, так и хранилище Azure, поэтому потребность в дополнительной изоляции данных клиентов на уровне хранения.

## <a name="exchange-online"></a>Exchange Online

Exchange Online хранит данные клиентов в почтовых ящиках. Почтовые ящики размещаются в базах данных расширенного обработчика хранилищ (ESE) под названием databases. Сюда входят почтовые ящики пользователей, связанные почтовые ящики, общие почтовые ящики и почтовые Почтовые ящики пользователей включают сохраненный контент Skype для бизнеса, например историю бесед.

Содержимое почтового ящика пользователя включает:

- Сообщения электронной почты и вложения электронной почты
- Сведения о календаре и занятости
- Контакты
- Задачи
- Примечания
- Группы
- Данные вывода

Каждая база данных почтовых ящиков в Exchange Online содержит почтовые ящики нескольких клиентов. Код авторизации обеспечивает защиту каждого почтового ящика, в том числе в рамках клиента. По умолчанию доступ к почтовому ящику имеют только назначенный пользователь. Список управления доступом (ACL), защищающий почтовый ящик, содержит удостоверение, прошедшее проверкой подлинности с помощью Azure AD на уровне клиента. Почтовые ящики для каждого клиента ограничены удостоверениями, проверенными в поставщике проверки подлинности клиента, который включает в себя только пользователей этого клиента. Контент в клиенте а не может быть получен пользователями в клиенте б, если только он явно не утвержден клиентом A.

## <a name="skype-for-business"></a>Skype для бизнеса

Skype для бизнеса хранит данные в различных местах:

- Сведения о пользователях и учетных записях, включая конечные точки подключений, идентификаторы клиентов, абонентские группы, параметры роуминга, состояние присутствия, списки контактов и т. д., хранятся на серверах Active Directory Skype для бизнеса и на различных серверах баз данных Skype для бизнеса. Списки контактов хранятся в почтовом ящике Exchange Online пользователя, если пользователь включен для обеих продуктов, или на серверах Skype для бизнеса, если пользователь не работает. Серверы баз данных Skype для бизнеса не разбиты на несколько клиентов, но изоляция данных с несколькими клиентами обеспечивается с помощью управления доступом на основе ролей (RBAC).
- Содержимое собраний и отправленные данные хранятся в общих папках распределенной файловой системы (DFS). Этот контент также можно архивировать в Exchange Online, если он включен. Общие ресурсы DFS не разбиты на разделы для каждого клиента. содержимое защищено с помощью списков управления доступом (ACL) и с поддержкой нескольких клиентов с помощью RBAC.
- Записи о вызовах, являющиеся журналом активности, например журнал вызовов, сеансы обмена мгновенными сообщениями, общий доступ к приложениям, журнал мгновенных сообщений и т. д., также могут храниться в Exchange Online, но большинство записей сведений о вызовах временно хранятся на серверах записи сведений о вызовах (CDR). Содержимое не секционировано для каждого клиента, но с помощью RBAC применяется мультитенантность.

## <a name="sharepoint-online"></a>SharePoint Online

В SharePoint Online есть несколько независимых механизмов, обеспечивающих изоляцию данных. В базах данных приложений хранятся объекты в виде абстрактного кода. Например, когда пользователь отправляет файл в SharePoint Online, файл разбивается, преобразуется в код приложения и хранится в нескольких таблицах нескольких баз данных.

Если пользователь может получить прямой доступ к хранилищу, содержащему данные, содержимое не будет интерпретировано для человека или любой другой системы, отличной от SharePoint Online. Эти механизмы включают управление доступом и свойства. Все ресурсы SharePoint Online защищаются с помощью кода авторизации и политики RBAC, в том числе в рамках клиента. Список управления доступом (ACL), защищающий ресурс, содержит удостоверение, прошедшее проверку подлинности на уровне клиента. Данные SharePoint Online для клиента ограничены удостоверениями, прошедших проверку с помощью поставщика проверки подлинности для клиента.

В дополнение к ACL, свойство уровня клиента, которое определяет поставщика проверки подлинности (то есть Azure AD), записывается один раз и не может быть изменен после установки. После настройки свойства клиента поставщика проверки подлинности для клиента его нельзя изменить с помощью интерфейсов API, предоставленных клиенту.

Для каждого клиента используется уникальный идентификатор *подписки* . Всем сайтам клиентов владеет клиент и ему назначен идентификатор *подписки* , уникальный для клиента. Свойство *SubscriptionId* на сайте записывается один раз и является постоянным. После назначения клиенту сайт невозможно переместить в другой клиент. Значение *SubscriptionId* — это ключ, используемый для создания области безопасности для поставщика проверки подлинности и привязанного к клиенту.

SharePoint Online использует SQL Server и хранилище Azure для хранения метаданных контента. Ключ раздела для хранилища контента — код *сайта* в SQL. При выполнении запроса SQL SharePoint Online использует идентификатор *сайта* , проверенный как часть проверки на уровне клиента *SubscriptionId* .

SharePoint Online хранит зашифрованное содержимое файлов в больших двоичных объектов Microsoft Azure. Каждая ферма SharePoint Online обладает собственной учетной записью Microsoft Azure, а все большие двоичные объекты, сохраненные в Azure, шифруются по отдельности с помощью ключа, хранящегося в хранилище контента SQL. Ключ шифрования, защищенный в коде уровнем авторизации и не предоставленный непосредственно конечному пользователю. В SharePoint Online есть мониторинг в режиме реального времени, чтобы определить, когда HTTP-запрос считывает или записывает данные для нескольких клиентов. Идентификатор запроса *SubscriptionId* отслеживается на основании *идентификатора подписки* доступного ресурса. Запросы на доступ к ресурсам нескольких клиентов никогда не должны выполняться конечными пользователями. Запросы службы в среде с несколькими клиентами являются единственным исключением. Например, программа-обходчик собирает все изменения контента для всей базы данных одновременно. Обычно это включает запросы сайтов нескольких клиентов в одном запросе службы, которые выполняются в целях повышения эффективности.

## <a name="teams"></a>Teams

Данные Teams хранятся по-разному в зависимости от типа контента. 

Ознакомьтесь с разделом "Ignite" в [архитектуре Microsoft Teams](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) для подробного обсуждения.

### <a name="core-teams-customer-data"></a>Основные данные клиента Teams

Если ваш клиент подготавливается к работе в Австралии, Канаде, Европейской профсоюзной, Франции, Германии, Индии, Японии, Южная Африка, Южной Корея, Швейцарии (то есть Лихтенштейн), Соединенных арабскими арабскими (Лихтенштейн), Великобритании или США, корпорация Майкрософт сохраняет следующие данные клиента только в этом расположении:

- Разговоры в Teams, беседы в группах и каналах, изображения, сообщения голосовой почты и контакты.
- контент сайта SharePoint Online и файлы, которые хранятся на этом сайте;
- Файлы, отправленные в OneDrive для работы или учебного заведения.

#### <a name="chat-channel-messages-team-structure"></a>Чат, сообщения канала, структура группы

Каждая команда в Teams выполняется с помощью группы Microsoft 365 и ее сайта SharePoint и почтового ящика Exchange. Частные беседы (включая сеансы групп) сообщения, отправляемые в составе беседы по каналу, а структура команд и каналов хранятся в службе Chat, работающей в Azure. Данные также хранятся в скрытой папке в почтовых ящиках пользователей и групп, чтобы включить функции защиты информации.

#### <a name="voicemail-and-contacts"></a>Голосовая почта и контакты

Голосовые сообщения хранятся в Exchange. Контакты хранятся в облачном хранилище данных на основе Exchange. Exchange и облачное хранилище на основе Exchange уже предоставляют данные размещению в каждом из мировых центров обработки данных жеос. Для всех команд Голосовая почта и контакты хранятся внутри страны для Австралии, Канады, Франции, Германии, Индии, Японии, Соединенных арабских арабских, Соединенных Королевствов, Южно-Африканского Республика, Южная Корея, Швейцарии (то есть Лихтенштейн) и США. Для всех других стран файлы хранятся в США, Европе или Азиатско Страном регионе, основанном на сходстве клиентов.

#### <a name="images-and-media"></a>Изображения и мультимедиа

Носитель, используемый в беседах (за исключением GIF-файлов Giphy, которые не сохранены, но ссылка на исходный URL-адрес службы Giphy, Giphy не является службой), хранится в службе мультимедиа на основе Azure, которая разворачивается в тех же местах, что и служба Chat.

#### <a name="files"></a>Файлы

Файлы (включая OneNote и вики), которые кто-то использует в канале, хранятся на сайте SharePoint группы. Файлы, общие для частного чата или чата во время собрания или звонка, отправляются и хранятся в OneDrive для работы или учебной учетной записи пользователя, имеющего общий доступ к файлу. Exchange, SharePoint и OneDrive уже предоставляют размещению данных в каждом из мировых центров обработки данных жеос. Таким образом, для существующих клиентов все файлы, записные книжки OneNote, вики-сайт Teams и почтовые ящики, которые входят в работу Teams, уже хранятся в расположении на основе сходства клиента. Файлы хранятся внутри страны для Австралии, Канады, Франции, Германии, Индии, Японии, Соединенных арабских арабских, Соединенных Королевствов, Южно-Африканского Республика, Южная Корея и Швейцарии (включая Лихтенштейн). Во всех остальных странах файлы хранятся в странах США, Европы или Азиатско стран для странного региона, основанных на сходстве клиентов.