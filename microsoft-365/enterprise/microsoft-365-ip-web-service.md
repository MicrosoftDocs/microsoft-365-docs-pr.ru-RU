---
title: Веб-служба IP-адресов и URL-адресов в Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/6/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: pandrew
search.appverid:
- MET150
- MOE150
- BCS160
description: Узнайте, как использовать веб-службу IP-адресов и URL-адресов в Office 365, чтобы лучше выявлять и разграничивать сетевой трафик Office 365.
ms.openlocfilehash: 0469070ed6d46b7695526697c255e23c0dc009ec
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286421"
---
# <a name="office-365-ip-address-and-url-web-service"></a>Веб-служба IP-адресов и URL-адресов в Office 365

Веб-служба IP- и URL-адресов в Office 365 позволяет лучше выявлять и разграничивать сетевой трафик Office 365, упрощая оценку, настройку и обновление. Эта веб-служба на основе REST заменяет собой ранее доступные скачиваемые XML-файлы, поддержка которых была прекращена 2 октября 2018 г.

Будучи клиентом или поставщиком устройств сети периметра, вы можете создавать решения с использованием веб-службы для записей FQDN и IP-адресов в Office 365. Доступ к данным можно получить непосредственно в браузере с помощью этих URL-адресов:

- Для получения последней версии диапазонов IP-адресов и URL-адресов Office 365 перейдите на веб-страницу [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).
- Для получения данных на странице диапазонов IP-адресов и URL-адресов Office 365 для брандмауэров и прокси-серверов перейдите на веб-страницу [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).
- Для получения всех последних изменений с июля 2018 года (тогда стала доступной веб-служба) перейдите на веб-страницу [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).

Как клиент вы можете использовать эту веб-службу, чтобы:

- обновлять скрипты PowerShell для получения данных конечной точки Office 365 и изменять форматирование для сетевых устройств;
- применять эту информацию для обновления PAC-файлов, развернутых на клиентских компьютерах.

Как поставщик устройств сети периметра вы можете использовать эту веб-службу, чтобы:

- создавать и тестировать программное обеспечение устройств для скачивания списка с целью автоматической настройки;
- проверять текущую версию;
- получать текущие изменения.

> [!NOTE]
> Если вы используете Azure ExpressRoute для подключения к Office 365, см. статью [Azure ExpressRoute для Office 365](azure-expressroute.md), чтобы ознакомиться со службами Office 365, поддерживаемыми в Azure ExpressRoute. Чтобы понимать, какие сетевые запросы для приложений Office 365 требуют подключения в Интернету, см. статью [URL-адреса и диапазоны IP-адресов Office 365](urls-and-ip-address-ranges.md). Это поможет вам лучше настроить устройства периметра безопасности.

Подробнее:

- [Объявление в записи блога на форуме Tech Community Office 365.](https://techcommunity.microsoft.com/t5/Office-365-Blog/Announcing-Office-365-endpoint-categories-and-Office-365-IP/ba-p/177638)
- [Форум Tech Community Office 365, содержащий сведения об использовании веб-служб.](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)

## <a name="common-parameters"></a>Общие параметры

Эти параметры являются общими для всех методов веб-службы:

- **format=<JSON | CSV>**. По умолчанию данные возвращаются в формате JSON. Используйте этот необязательный параметр для возврата данных в формате данных с разделителями-запятыми (CSV).
- **ClientRequestId=\<guid>**. Обязательный GUID, создаваемый для сопоставления клиента. Создайте уникальный GUID для каждого компьютера, который вызывает веб-службу (скрипты, указанные на этой странице, позволяют создать GUID). Не используйте GUID, показанные в примерах ниже, так как они могут быть заблокированы веб-службой в будущем. Формат GUID: _xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_. Здесь "x" означает шестнадцатеричное число.

  Чтобы создать GUID, можно использовать команду PowerShell [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) или веб-службу, например [Online GUID Generator](https://www.guidgenerator.com/).

## <a name="version-web-method"></a>Веб-метод версии

Корпорация Майкрософт обновляет записи IP-адресов и FQDN Office 365 в конце каждого месяца. Иногда обновления публикуются вне цикла для устранения инцидентов, поддержки обновлений для системы безопасности или выполнения других операционных требований.

Данным для каждого опубликованного экземпляра назначается номер версии, а веб-метод версии позволяет проверить наличие последней версии каждого экземпляра службы Office 365. Рекомендуется проверять версию не чаще, чем раз в час.

Параметры для веб-метода версии:

- **AllVersions=<true | false>**. По умолчанию возвращается последний номер версии. Включите этот необязательный параметр для запрашивания всех версий, опубликованных с момента первого выпуска веб-службы.
- **Format=<JSON | CSV | RSS>**. Кроме форматов JSON и CSV, веб-метод версии поддерживает RSS. Вы можете использовать этот необязательный параметр вместе с параметром _AllVersions=true_ для запрашивания RSS-канала, который можно применять в Outlook или других средствах чтения RSS.
- **Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>**. Этот необязательный параметр указывает экземпляр, для которого возвращается версия. Если его опустить, будут возвращены все экземпляры. Допустимые экземпляры: Worldwide, China, Germany, USGovDoD, USGovGCCHigh.

Веб-метод версии не имеет ограничения по частоте и не возвращает HTTP-код отклика 429. Отклик для веб-метода версии включает заголовок с контролем кэша, рекомендующий кэширование данных в течение 1 часа. Результатом веб-метода версии может быть отдельная запись или массив записей. Ниже перечислены элементы каждой записи.

- instance — короткое имя экземпляра службы Office 365.
- latest — последняя версия для конечных точек указанного экземпляра.
- versions — список всех предыдущих версий для указанного экземпляра. Этот элемент включен, только если параметр _AllVersions_ имеет значение true.

### <a name="examples"></a>Примеры:

Пример 1. Запрос URI: [https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Этот URI возвращает последнюю версию каждого экземпляра службы Office 365. Пример результата:

```json
[
 {
  "instance": "Worldwide",
  "latest": "2018063000"
 },
 {
  "instance": "USGovDoD",
  "latest": "2018063000"
 },
 {
  "instance": "USGovGCCHigh",
  "latest": "2018063000"
 },
 {
  "instance": "China",
  "latest": "2018063000"
 },
 {
  "instance": "Germany",
  "latest": "2018063000"
 }
]
```

> [!IMPORTANT]
> GUID для параметра ClientRequestID в этих URI приведен только в качестве примера. Чтобы попробовать применить URI веб-службы, создайте собственный GUID. GUID, показанные в этих примерах, могут быть заблокированы веб-службой в будущем.

Пример 2. Запрос URI: [https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Этот URI возвращает последнюю версию указанного экземпляра службы Office 365. Пример результата:

```json
{
 "instance": "Worldwide",
 "latest": "2018063000"
}
```

Пример 3. Запрос URI: [https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Этот URI показывает выходные данные в формате CSV. Пример результата:

```csv
instance,latest
Worldwide,2018063000
```

Пример 4. Запрос URI: [https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Этот URI показывает все более ранние версии, которые были опубликованы для экземпляра службы Office 365 Worldwide. Пример результата:

```json
{
  "instance": "Worldwide",
  "latest": "2018063000",
  "versions": [
    "2018063000",
    "2018062000"
  ]
}
```

Пример 5. URI RSS-канала: [https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS](https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS)

Этот URI показывает RSS-канал опубликованных версий, которые содержат ссылки на список изменений для каждой версии. Пример результата:

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<rss version="2.0" xmlns:a10="https://www.w3.org/2005/Atom">
<channel>
<link>https://aka.ms/o365ip</link>
<description/>
<language>en-us</language>
<lastBuildDate>Thu, 02 Aug 2018 00:00:00 Z</lastBuildDate>
<item>
<guid isPermaLink="false">2018080200</guid>
<link>https://endpoints.office.com/changes/Worldwide/2018080200?singleVersion&clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7</link> <description>Version 2018080200 includes 2 changes. IPs: 2 added and 0 removed.</description>
<pubDate>Thu, 02 Aug 2018 00:00:00 Z</pubDate>
</item>
```

## <a name="endpoints-web-method"></a>Веб-метод конечных точек

Веб-метод конечных точек возвращает все записи для диапазонов IP-адресов и URL-адресов, входящих в службу Office 365. Для настройки сетевого устройства всегда следует использовать новейшие данные от веб-метода конечных точек. Корпорация Майкрософт отправляет уведомление за 30 дней до публикации новых дополнений, чтобы вы успели обновить списки управления доступом и списки обхода прокси-сервера. Рекомендуем вызывать веб-метод конечных точек еще раз, только когда веб-метод версии указывает на доступность новой версии данных.

Параметры веб-метода конечных точек представлены ниже.

- **ServiceAreas=<Common | Exchange | SharePoint | Skype>**. Список областей обслуживания, разделенных запятыми. Допустимые элементы: _Common_, _Exchange_, _SharePoint_ и _Skype_. Так как элементы области обслуживания _Common_ обязательны для всех других областей обслуживания, веб-служба всегда включает их. Если не включить этот параметр, будут возвращены все области обслуживания.
- **TenantName=<имя_клиента>**. Имя клиента Office 365. Веб-служба получает предоставленное вами имя и вставляет его в части URL-адресов, которые включают имя клиента. Если вы не предоставляете имя клиента, эти части URL-адресов будут содержать подстановочный знак (\*).
- **NoIPv6=<true | false>**. Установите для него значение _true_, чтобы исключить адреса IPv6 из выходных данных, если в вашей сети не используется IPv6.
- **Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>**. Этот обязательный параметр указывает экземпляр, из которого должны быть возвращены конечные точки. Допустимые экземпляры: _Worldwide_, _China_, _Germany_, _USGovDoD_ и _USGovGCCHigh_.

Если вы вызываете веб-метод конечных точек слишком часто с одного клиентского IP-адреса, то можете получить код HTTP-отклика _429 (слишком большое количество запросов)_. Если вы получили этот код отклика, подождите 1 час перед повтором своего запроса или сгенерируйте новый GUID для запроса. Рекомендуется запланировать вызов веб-метода конечных точек, только если веб-метод версии указывает, что доступна новая версия.

Результат веб-метода конечных точек — массив записей, в котором каждая запись представляет собой определенный набор конечных точек. Элементы каждой записи:

- id — неизменяемый идентификатор набора конечных точек.
- serviceArea — область обслуживания, которая является частью _Common_, _Exchange_, _SharePoint_ или _Skype_.
- urls — URL-адреса для набора конечных точек. Массив JSON записей DNS. Если значение не указано, опускается.
- tcpPorts — TCP-порты для набора конечных точек. Все элементы портов отформатированы в виде списка портов с разделителями-запятыми или диапазонов портов, разделенных символами дефиса (-). Порты применяются ко всем IP- и URL-адресам в наборе конечных точек для данной категории. Если значение не указано, опускается.
- udpPorts — порты UDP для диапазонов IP-адресов в этом наборе конечных точек. Если значение не указано, опускается.
- ips — диапазоны IP-адресов, связанные с этим набором конечных точек (с перечисленными портами TCP или UDP). Массив JSON диапазонов IP-адресов. Если значение не указано, опускается.
- category — категория возможности подключения к набору конечных точек. Допустимые значения: _Optimize_, _Allow_ и _Default_. Если выходные данные веб-метода конечных точек используются для поиска определенного IP- или URL-адреса, запрос может возвращать несколько категорий. В таком случае необходимо следовать рекомендациям для категории с наивысшим приоритетом. Например, если для конечной точки выводятся значения _Optimize_ и _Allow_, следует выполнять требования для значения _Optimize_. Обязательный элемент.
- expressRoute имеет значение _True_, если для этого набора конечных точек выполняется маршрутизация через ExpressRoute. В противном случае он получает значение _False_.
- required — имеет значение _True_, если этот набор конечных точек требуется для подключения к Office 365. _False_, если этот набор конечных точек необязателен.
- notes — текст, который в случае необязательных конечных точек описывает функциональность Office 365, которая будет недоступна, если IP- или URL-адреса в этом наборе конечных точек недоступны на сетевом уровне. Если значение не указано, опускается.

### <a name="examples"></a>Примеры:

Пример 1. Запрос URI: [https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Этот URI получает все конечные точки для экземпляра Office 365 Worldwide для всех рабочих нагрузок. В примере результата показан фрагмент выходных данных:

```json
[
 {
  "id": 1,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.protection.outlook.com"
   ],
  "ips":
   [
    "2a01:111:f403::/48", "23.103.132.0/22", "23.103.136.0/21", "23.103.198.0/23", "23.103.212.0/22", "40.92.0.0/14", "40.107.0.0/17", "40.107.128.0/18", "52.100.0.0/14", "213.199.154.0/24", "213.199.180.128/26", "94.245.120.64/26", "207.46.163.0/24", "65.55.88.0/24", "216.32.180.0/23", "23.103.144.0/20", "65.55.169.0/24", "207.46.100.0/24", "2a01:111:f400:7c00::/54", "157.56.110.0/23", "23.103.200.0/22", "104.47.0.0/17", "2a01:111:f400:fc00::/54", "157.55.234.0/24", "157.56.112.0/24", "52.238.78.88/32"
   ],
  "tcpPorts": "443",
  "expressRoute": true,
  "category": "Allow"
 },
 {
  "id": 2,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.mail.protection.outlook.com"
   ],
```

Обратите внимание, что полные выходные данные запроса в этом примере будут содержать другие наборы конечных точек.

Пример 2. Запрос URI: [https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

В этом примере получены конечные точки для экземпляра Office 365 Worldwide в отношении Exchange Online и зависимостей.

Выходные данные в примере 2 аналогичны таковым в примере 1, но результаты не будут включать конечные точки для SharePoint Online или Skype бизнеса в Интернете.

## <a name="changes-web-method"></a>Веб-метод изменений

Веб-метод изменений возвращает самые последние опубликованные обновления. Как правило, это изменения диапазонов IP- и URL-адресов за предыдущий месяц.

Наиболее критические изменения в данных конечных точек — это новые URL- и IP-адреса. Неудачная попытка добавить IP-адрес в список управления доступом брандмауэра или добавить URL-адрес в список обхода прокси-сервера может привести к простою пользователей Office 365 за этим сетевым устройством. Несмотря на операционные требования, новые конечные точки публикуются в веб-службе за 30 дней до даты подготовки конечных точек к использованию, чтобы вы успели обновить списки управления доступом и списки обхода прокси-сервера.

Обязательный параметр веб-метода изменений:

- **Version=\<YYYYMMDDNN>** — обязательный параметр маршрутизации URL-адресов. Этим значением является используемая в настоящий момент версия. Веб-служба возвращает изменения, внесенные с момента этой версии. Формат: _ГГГГММДДЧЧ_, где _ЧЧ_ — натуральное число, увеличивающееся, если в один день нужно опубликовать больше одной версии, при этом значение _00_ представляет первое обновление дня. Веб-служба требует, чтобы параметр _version_ содержал ровно 10 цифр.

Веб-метод изменений ограничен по частоте аналогично веб-методу конечных точек. Если вы получили код отклика HTTP 429, подождите 1 час перед повтором своего запроса или сгенерируйте новый GUID для запроса.

Результат веб-метода изменений — массив записей, в котором каждая запись представляет собой изменение в определенной версии конечных точек. Элементы каждой записи:

- id: неизменяемый идентификатор записи изменения.
- endpointSetId: идентификатор записи набора конечных точек, который был изменен.
- disposition: описание того, как именно изменена запись набора конечных точек. Значения: _change_, _add_ или _remove_.
- impact: не все изменения будут одинаково важны для каждой среды. Данный элемент описывает ожидаемое влияние на среду периметра корпоративной сети в результате этого изменения. Этот элемент включается только в записи изменений версии **2018112800** и более поздних. Доступны указанные далее варианты для элемента impact. AddedIp: IP-адрес был добавлен в Office 365 и будет доступен в службе в ближайшее время. Этот элемент представляет изменения, которые вам необходимо внести для брандмауэра или другого устройства периметра 3 уровня сети. Если вы не добавили этот элемент перед началом его использования, могут возникать сбои.
  AddedUrl: URL-адрес был добавлен в Office 365 и будет доступен в службе в ближайшее время. Этот элемент представляет изменения, которые вам необходимо внести для прокси-сервера или устройства периметра сети, анализирующего URL-адреса. Если вы не добавили этот URL-адрес перед началом его использования, могут возникать сбои.
  AddedIpAndUrl: IP-адрес и URL-адрес были добавлены. Этот элемент представляет изменение, которое вам необходимо внести на устройстве 3 уровня брандмауэра, прокси-сервере или устройстве анализа URL-адреса. Если вы не добавили эту пару IP- и URL-адресов перед началом ее использования, могут возникать сбои.
  RemovedIpOrUrl: минимум один IP- или URL-адрес удален из Office 365. Удалите конечные точки сети со своих устройств периметра, но четкого срока, когда вы должны это сделать, не установлено.
  ChangedIsExpressRoute: изменен атрибут поддержки ExpressRoute. Если вы используете ExpressRoute, может потребоваться выполнить определенные действия в зависимости от вашей конфигурации.
  MovedIpOrUrl: мы перенесли IP-адрес или URL-адрес в другой набор конечных точек. Как правило, никаких дополнительных действий не требуется.
  RemovedDuplicateIpOrUrl: мы удалили повторяющийся IP- или URL-адрес, но он по-прежнему опубликован для Office 365. Как правило, никаких дополнительных действий не требуется.
  OtherNonPriorityChanges: мы изменили что-то менее критическое, чем все прочие параметры (например, содержимое поля заметки).
- version — версия опубликованного набора конечных точек, в который внесено изменение. Формат номеров версий: _ГГГГММДДЧЧ_, где _ЧЧ_ — натуральное число, увеличивающееся, если в один день нужно опубликовать больше одной версии.
- previous — подструктура с подробным указанием предыдущих значений измененных элементов в наборе конечных точек. Не будет включена для новых добавляемых наборов конечных точек. Включает _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ и _notes_.
- current — подструктура с подробным указанием обновленных значений измененных элементов в наборе конечных точек. Включает _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ и _notes_.
- add — подструктура с подробным указанием элементов, добавляемых в коллекции наборов конечных точек. Опускается, если добавлений нет.
  effectiveDate определяет дату начала использования добавлений в службе.
  ips — элементы, добавляемые в массив _ips_.
  urls — элементы, добавляемые в массив _urls_.
- remove — подструктура с подробным указанием элементов, удаляемых из набора конечных точек. Опускается, если удаленных элементов нет.
  ips — элементы, удаляемые из массива _ips_.
  urls — элементы, удаляемые из массива _urls_.

### <a name="examples"></a>Примеры:

Пример 1. Запрос URI: [https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Запрашивает все предыдущие изменения в экземпляре службы Office 365 Worldwide. Пример результата:

```json
[
 {
  "id": 424,
  "endpointSetId": 32,
  "disposition": "Change",
  "version": "2018062700",
  "remove":
   {
    "urls":
     [
      "*.api.skype.com", "skypegraph.skype.com"
     ]
   }
 },
 {
  "id": 426,
  "endpointSetId": 31,
  "disposition": "Change",
  "version": "2018062700",
  "add":
   {
    "effectiveDate": "20180609",
    "ips":
     [
      "51.140.203.190/32"
     ]
   },
  "remove":
   {
    "ips":
     [
```

Пример 2. Запрос URI: [https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Запрашивает изменения, внесенные в экземпляр Office 365 Worldwide после выхода указанной версии. В этом случае указанная версия является последней. Пример результата:

```json
[
  {
    "id":3,
    "endpointSetId":33,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["65.55.127.0/24","66.119.157.192/26","66.119.158.0/25",
      "111.221.76.128/25","111.221.77.0/26","207.46.5.0/24"]
    }
  },
  {
    "id":4,
    "endpointSetId":45,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["13.78.93.8/32","40.113.87.220/32","40.114.149.220/32",
      "40.117.100.83/32","40.118.214.164/32","104.208.31.113/32"]
    }
  }
]
```

## <a name="example-powershell-script"></a>Пример скрипта PowerShell

Этот скрипт PowerShell позволяет узнать, нужно ли выполнить действия для обновленных данных. Этот скрипт можно запустить в качестве запланированной задачи, чтобы проверить наличие обновления версии. Чтобы избежать чрезмерной нагрузки на веб-службу, не запускайте этот скрипт чаще одного раза в час.

Этот скрипт выполняет следующее:

- Проверяет номер версии текущих конечных точек экземпляра Office 365 Worldwide, вызывая API REST веб-службы.
- Проверяет наличие текущего файла версии по адресу _$Env:TEMP\O365_endpoints_latestversion.txt_. Как правило, путь для глобальной переменной **$Env:TEMP** — _C:\Users\\<username\>\AppData\Local\Temp_.
- Если этот скрипт выполняется впервые, он возвращает текущую версию и все текущие IP- и URL-адреса, записывает версию конечных точек в файл _$Env:TEMP\O365_endpoints_latestversion.txt_, а выходные данные конечных точек — в файл _$Env:TEMP\O365_endpoints_data.txt_. Вы можете изменить путь и/или имя выходного файла, изменив следующие строки:

    ``` powershell
    $versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
    $datapath = $Env:TEMP + "\O365_endpoints_data.txt"
    ```

- Если при каждом последующем выполнении скрипта последняя версия веб-службы идентична версии в файле _O365_endpoints_latestversion.txt_, скрипт завершает работу, не внося каких-либо изменений.
- Если последняя версия веб-службы новее версии в файле _O365_endpoints_latestversion.txt_, скрипт возвращает конечные точки и фильтры для конечных точек категорий **Allow** и **Optimize**, обновляет версию в файле _O365_endpoints_latestversion.txt_ и записывает обновленные данные в файл _O365_endpoints_data.txt_.

Скрипт создает уникальный _ClientRequestId_ для компьютера, на котором выполняется, и повторно использует этот идентификатор для нескольких вызовов. Этот идентификатор хранится в файле _O365_endpoints_latestversion.txt_.

### <a name="to-run-the-powershell-script"></a>Запуск скрипта PowerShell

1. Скопируйте скрипт и сохраните его на локальном жестком диске или в папке со скриптами под именем _Get-O365WebServiceUpdates.ps1_.
1. Выполните скрипт в предпочитаемом редакторе скриптов, например VS Code или интегрированной среде сценариев PowerShell, или из консоли PowerShell с помощью следующей команды:

    ``` powershell
   powershell.exe -file <path>\Get-O365WebServiceUpdates.ps1
    ```

    Отсутствуют параметры для передачи в скрипт.

```powershell
<# Get-O365WebServiceUpdates.ps1
From https://aka.ms/ipurlws
v1.1 8/6/2019

DESCRIPTION
This script calls the REST API of the Office 365 IP and URL Web Service (Worldwide instance)
and checks to see if there has been a new update since the version stored in an existing
$Env:TEMP\O365_endpoints_latestversion.txt file in your user directory's temp folder
(usually C:\Users\<username>\AppData\Local\Temp).
If the file doesn't exist, or the latest version is newer than the current version in the
file, the script returns IPs and/or URLs that have been changed, added or removed in the latest
update and writes the new version and data to the output file $Env:TEMP\O365_endpoints_data.txt.

USAGE
Run as a scheduled task every 60 minutes.

PARAMETERS
n/a

PREREQUISITES
PS script execution policy: Bypass
PowerShell 3.0 or later
Does not require elevation
#>

#Requires -Version 3.0

# web service root URL
$ws = "https://endpoints.office.com"
# path where output files will be stored
$versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
$datapath = $Env:TEMP + "\O365_endpoints_data.txt"

# fetch client ID and version if version file exists; otherwise create new file and client ID
if (Test-Path $versionpath) {
    $content = Get-Content $versionpath
    $clientRequestId = $content[0]
    $lastVersion = $content[1]
    Write-Output ("Version file exists! Current version: " + $lastVersion)
}
else {
    Write-Output ("First run! Creating version file at " + $versionpath + ".")
    $clientRequestId = [GUID]::NewGuid().Guid
    $lastVersion = "0000000000"
    @($clientRequestId, $lastVersion) | Out-File $versionpath
}

# call version method to check the latest version, and pull new data if version number is different
$version = Invoke-RestMethod -Uri ($ws + "/version/Worldwide?clientRequestId=" + $clientRequestId)
if ($version.latest -gt $lastVersion) {
    Write-Host "New version of Office 365 worldwide commercial service instance endpoints detected"
    # write the new version number to the version file
    @($clientRequestId, $version.latest) | Out-File $versionpath
    # invoke endpoints method to get the new data
    $endpointSets = Invoke-RestMethod -Uri ($ws + "/endpoints/Worldwide?clientRequestId=" + $clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into custom objects with port and category
    # URL results
    $flatUrls = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $urls = $(if ($endpointSet.urls.Count -gt 0) { $endpointSet.urls } else { @() })
        $urlCustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $urlCustomObjects = $urls | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    url      = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $urlCustomObjects
    }
    # IPv4 results
    $flatIp4s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv4 strings contain dots
        $ip4s = $ips | Where-Object { $_ -like '*.*' }
        $ip4CustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $ip4CustomObjects = $ip4s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip4CustomObjects
    }
    # IPv6 results
    $flatIp6s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv6 strings contain colons
        $ip6s = $ips | Where-Object { $_ -like '*:*' }
        $ip6CustomObjects = @()
        if ($endpointSet.category -in ("Optimize")) {
            $ip6CustomObjects = $ip6s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip6CustomObjects
    }

    # write output to screen
    Write-Output ("Client Request ID: " + $clientRequestId)
    Write-Output ("Last Version: " + $lastVersion)
    Write-Output ("New Version: " + $version.latest)
    Write-Output ""
    Write-Output "IPv4 Firewall IP Address Ranges"
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "IPv6 Firewall IP Address Ranges"
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "URLs for Proxy Server"
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-String
    Write-Output ("IP and URL data written to " + $datapath)

    # write output to data file
    Write-Output "Office 365 IP and UL Web Service data" | Out-File $datapath
    Write-Output "Worldwide instance" | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output ("Version: " + $version.latest) | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv4 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv6 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "URLs for Proxy Server" | Out-File $datapath -Append
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-File $datapath -Append
}
else {
    Write-Host "Office 365 worldwide commercial service instance endpoints are up-to-date."
}
```

## <a name="example-python-script"></a>Пример скрипта на Python

Ниже показан скрипт на Python, протестированный с использованием Python 3.6.3 на Windows 10. Он позволяет узнать, нужно ли выполнить действия для обновленных данных, проверяя номер версии для конечных точек экземпляра Office 365 Worldwide. Если изменение есть, скрипт скачивает конечные точки и фильтрует результаты для категорий _Allow_ и _Optimize_. Он также использует уникальный ClientRequestId для нескольких вызовов и сохраняет последнюю версию, обнаруженную во временном файле. Вам нужно вызывать этот скрипт раз в час для проверки наличия обновления версии.

```python
import json
import tempfile
from pathlib import Path
import urllib.request
import uuid
# helper to call the webservice and parse the response
def webApiGet(methodName, instanceName, clientRequestId):
    ws = "https://endpoints.office.com"
    requestPath = ws + '/' + methodName + '/' + instanceName + '?clientRequestId=' + clientRequestId
    request = urllib.request.Request(requestPath)
    with urllib.request.urlopen(request) as response:
        return json.loads(response.read().decode())
# path where client ID and latest version number will be stored
datapath = Path(tempfile.gettempdir() + '/endpoints_clientid_latestversion.txt')
# fetch client ID and version if data exists; otherwise create new file
if datapath.exists():
    with open(datapath, 'r') as fin:
        clientRequestId = fin.readline().strip()
        latestVersion = fin.readline().strip()
else:
    clientRequestId = str(uuid.uuid4())
    latestVersion = '0000000000'
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + latestVersion)
# call version method to check the latest version, and pull new data if version number is different
version = webApiGet('version', 'Worldwide', clientRequestId)
if version['latest'] > latestVersion:
    print('New version of Office 365 worldwide commercial service instance endpoints detected')
    # write the new version number to the data file
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + version['latest'])
    # invoke endpoints method to get the new data
    endpointSets = webApiGet('endpoints', 'Worldwide', clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into tuples with port and category
    flatUrls = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            category = endpointSet['category']
            urls = endpointSet['urls'] if 'urls' in endpointSet else []
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatUrls.extend([(category, url, tcpPorts, udpPorts) for url in urls])
    flatIps = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            ips = endpointSet['ips'] if 'ips' in endpointSet else []
            category = endpointSet['category']
            # IPv4 strings have dots while IPv6 strings have colons
            ip4s = [ip for ip in ips if '.' in ip]
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatIps.extend([(category, ip, tcpPorts, udpPorts) for ip in ip4s])
    print('IPv4 Firewall IP Address Ranges')
    print(','.join(sorted(set([ip for (category, ip, tcpPorts, udpPorts) in flatIps]))))
    print('URLs for Proxy Server')
    print(','.join(sorted(set([url for (category, url, tcpPorts, udpPorts) in flatUrls]))))

    # TODO send mail (e.g. with smtplib/email modules) with new endpoints data
else:
    print('Office 365 worldwide commercial service instance endpoints are up-to-date')
```

## <a name="web-service-interface-versioning"></a>Управление версиями интерфейса веб-службы

В будущем могут понадобиться обновления параметров или результатов для этих методов веб-служб. После публикации общедоступной версии веб-служб корпорация Майкрософт примет разумные меры для заблаговременного уведомления о существенных обновлениях веб-службы. Если корпорация Майкрософт сочтет, что обновление потребует изменений клиентов, использующих веб-службы, она сохранит доступ к предыдущей версии веб-службы в течение как минимум 12 месяцев после выпуска новой версии. Пользователи, которые не выполнят обновление в течение этого времени, могут лишиться доступа к веб-службе и ее методам. Пользователи должны убедиться, что клиенты веб-службы продолжат работать без ошибок, если такие изменения будут внесены в подпись интерфейса веб-службы:

- Добавление нового необязательного параметра к существующему веб-методу, который необязательно должны предоставлять старые клиенты и который не влияет на результат, получаемый старым клиентом.
- Добавление нового именованного атрибута в один из элементов REST отклика или дополнительных столбцов в файл CSV отклика.
- Добавление нового веб-метода с новым именем, который не вызывается старыми клиентами.

## <a name="update-notifications"></a>Уведомления об обновлениях

Вы можете использовать несколько различных методов, чтобы получать по электронной почте уведомления о публикации изменений IP- и URL-адресов в веб-службе.

- Сведения о решении Microsoft Flow см. в статье [Использование Microsoft Flow для получения электронных сообщений об изменениях URL-адресов и IP-адресов Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651).
- Сведения о развертывании Azure Logic App с помощью шаблона ARM см. на странице [Уведомление об обновлении Office 365 (версия 1.1)](https://aka.ms/ipurlws-updates-template).
- Сведения о записи собственного скрипта уведомлений с помощью PowerShell см. в статье [Send-MailMessage](/powershell/module/microsoft.powershell.utility/send-mailmessage).

## <a name="exporting-a-proxy-pac-file"></a>Экспорт PAC-файла прокси-сервера

[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) — это скрипт PowerShell, который считывает последние конечные точки сети из IP-адреса и веб-службы URL-адресов Office 365 и создает пример PAC-файла. Сведения об использовании этого скрипта см. в статье [Использование PAC-файла для прямой маршрутизации обязательного трафика Office 365](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).

## <a name="related-topics"></a>Статьи по теме
  
[URL-адреса и диапазоны IP-адресов для Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Управление конечными точками Office 365](managing-office-365-endpoints.md)
  
[Вопросы и ответы о конечных точках Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)

[Принципы сетевого подключения к Office 365](microsoft-365-network-connectivity-principles.md)

[Сеть Office 365 и настройка производительности](network-planning-and-performance.md)

[Оценка сетевого подключения к Office 365](assessing-network-connectivity.md)
  
[Качество мультимедиа и характеристики сетевого подключения в случае Skype для бизнеса Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Оптимизация сети для Skype для бизнеса Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)

[Настройка производительности Office 365 с помощью базовых показателей и журнала производительности](performance-tuning-using-baselines-and-history.md)
  
[План устранения проблем с производительностью Office 365](performance-troubleshooting-plan.md)