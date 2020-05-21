---
title: Настройка и создание типа конфиденциальной информации
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: ''
description: Узнайте, как изменить или создать типы конфиденциальной информации в Office 365 для соблюдения Общего регламента по защите данных (GDPR).
ms.openlocfilehash: 70ce61f582cbc952811d01cccc7b958bf1b52dbb
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224636"
---
# <a name="customize-or-create-a-new-sensitive-information-type"></a>Настройка и создание типа конфиденциальной информации

В этой статье приведены три примера того, как изменить или создать типы конфиденциальной информации для соблюдения регламента GDPR.

- Изменение имеющегося типа конфиденциальной информации — номер банковской карты для ЕС

- Создание типа конфиденциальной информации — адрес электронной почты

- Создание типа конфиденциальной информации с примером XML-файла — номер клиента Contoso

См. также:

- [Создание пользовательского типа конфиденциальной информации с помощью PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)

- [Настройка встроенных типов конфиденциальных данных](customize-a-built-in-sensitive-information-type.md)

## <a name="modify-a-sensitive-information-type-to-improve-accuracy"></a>Изменение типа конфиденциальной информации для повышения точности данных

Если вы используете веб-часть "Поиск контента" для поиска персональных данных по типами конфиденциальной информации, но при этом не получаете ожидаемых результатов либо запрос возвращает слишком много ложноположительных результатов, вы можете изменить тип конфиденциальной информации в соответствии с особенностями своей среды.

Тип конфиденциальной информации рекомендуется создавать или настраивать на основе имеющегося типа, присвоив ему уникальное имя и идентификаторы. Например, если вы хотите настроить параметры типа конфиденциальной информации "Номер банковской карты для ЕС", копию соответствующего правила можно назвать "Номер банковской карты для ЕС (улучшенная версия)", чтобы отличать этот тип от исходного.

В новом типе конфиденциальной информации просто измените необходимые значения, чтобы повысить точность данных. После завершения отправьте новый тип конфиденциальной информации и создайте новое правило защиты от потери данных (или измените имеющееся), чтобы использовать новый тип конфиденциальной информации, который вы только что добавили. Изменение точности типов конфиденциальной информации выполняется методом проб и ошибок, поэтому рекомендуется сохранить копию исходного типа, к которому вы можете при необходимости вернуться в будущем.

Вот как настроить тип конфиденциальной информации:

1.  Экспортируйте имеющийся пакет правил Майкрософт со встроенными типами конфиденциальной информации в Office 365.

2.  Переименуйте этот XML-файл и откройте его в своем любимом редакторе XML.

3.  Изолируйте нужный тип конфиденциальной информации и удалите все остальные.

4.  С помощью PowerShell создайте два GUID для типа конфиденциальной информации, который вы изменяете.

5.  Измените идентификатор и другие основные элементы, чтобы сделать тип конфиденциальной информации уникальным (в том числе замените два GUID только что созданными).

6.  Настройте требования к соответствию для повышения точности.

    1.  Изменения в расположении слов и знаков: измените расположение слов и знаков, чтобы расширить или сжать окно, в котором тип конфиденциальной информации должны окружать ключевые слова.

    2.  Изменения в ключевых словах: добавьте ключевые слова в один из элементов \<Ключевые слова\>, чтобы предоставить более конкретные подкрепляющие доказательства для типа конфиденциальной информации с целью обнаружения соответствия этому правилу. Вы также можете удалить ключевые слова, которые приводят к ложным срабатываниям.

    3.  Изменения в доверии: измените доверие, при котором тип конфиденциальной информации должен соответствовать условиям, заданным в его определении, для нахождения совпадения и сообщения о нем.

7.  Передайте новый тип конфиденциальной информации.

8.  Выполните повторный обход контента, чтобы идентифицировать конфиденциальную информацию. См. статью [Ручной запрос обхода контента и переиндексации сайта](https://docs.microsoft.com/sharepoint/crawl-site-content).

## <a name="example-modify-the-eu-debit-card-number-sensitive-information-type"></a>Пример: изменение типа конфиденциальной информации "Номер банковской карты для ЕС"

Для повышения точности правил защиты от потери данных в любой системе их необходимо проверить, используя тестовый набор данных. Кроме того, может потребоваться точная настройка путем многократных изменений и проверок. В этом примере приведены изменения, внесенные в тип конфиденциальной информации "Номер банковской карты для ЕС" для повышения его точности.

При поиске номера банковской карты для ЕС в нашем примере определение соответствующего номера строго ограничено 16 знаками с использованием сложного шаблона. Кроме того, применяется проверка контрольной суммы. Мы не можем изменить этот шаблон из-за определения строки для этого типа конфиденциальной информации. Тем не менее мы можем внести перечисленные ниже изменения, чтобы повысить точность поиска этого типа конфиденциальной информации в среде Office 365 с помощью защиты от потери данных.

### <a name="proximity-modification"></a>Изменение расположения слов и знаков

Окно будет сжато путем изменения значения patternProximity в элементе \<Entity\> с 300 на 150 символов. Это значит, что подкрепляющие доказательства, или ключевые слова, должны в большей мере соответствовать нашему типу конфиденциальной информации для обнаружения соответствия этому правилу.

\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\>

### <a name="keyword-modifications"></a>Изменения ключевых слов

Некоторые ключевые слова могут приводить к ложным срабатываниям, поэтому их может потребоваться удалить. Вот ключевые слова в этом примере:

\<Keyword id="Keyword\_card\_terms\_dict"\>

\<Group\>

\<Term\>корпоративная карта\</Term\>

\<Term\>карта организации\</Term\>

\<Term\>acct nbr\</Term\>

\<Term\>acct num\</Term\>

\<Term\>acct no\</Term\>

...

\</Group\>

\</Keyword\>

### <a name="confidence-modifications"></a>Изменения в доверии

Удаляя ключевые слова из определения, вы, как правило, хотите настроить вероятность нахождения этого типа конфиденциальной информации путем сокращения этого значения. Стандартный уровень для типа "Номер банковской карты для ЕС" — 85.

\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\>

\<Pattern confidenceLevel="85"\>

...

\</Pattern\>

\</Entity\>

## <a name="create-a-new-custom-sensitive-information-type"></a>Создание пользовательского типа конфиденциальной информации

Чтобы создать пользовательский тип конфиденциальной информации, сначала воспользуйтесь веб-частью "Поиск контента" для:

-   оптимизации запроса KQL;

-   определения наиболее полезных ключевых слов.

Используйте эти результаты, чтобы создать тип конфиденциальной информации. Затем оптимизируйте новый тип конфиденциальной информации для своей среды.

Примечание. В ближайшее время будет представлен ряд новых типов конфиденциальной информации для персональных данных в странах ЕС. Если вам нужно создать типы конфиденциальной информации, сначала определите данные, характерные для вашей среды.

### <a name="step-1--use-kql-queries-and-key-words-to-find-additional-data-in-your-environment"></a>Шаг 1. Использование запросов KQL и ключевых слов для поиска дополнительных данных в среде

Возможно, вам потребуется создать дополнительные запросы для поиска персональных данных, на которые распространяется действие регламента GDPR. Для поиска данных в веб-части "Поиск контента" используется язык запросов Keyword Query Language (KQL). Точное обнаружение большинства конфиденциальных данных невозможно при использовании только языка KQL (без применения типов конфиденциальной информации). Поэтому наша цель — проверить и оптимизировать строки KQL с помощью веб-части "Поиск контента", а затем использовать их для создания и настройки новых типов конфиденциальной информации, чтобы повысить точность данных.

Для формулирования и оптимизации запросов с помощью KQL используйте эти ресурсы:

- [Руководство по синтаксису языка запросов по ключевым словам (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

- [Выполнение поиска контента](content-search.md)

Поиск контента предоставляет еще один ресурс, который помогает создавать запросы KQL и типы конфиденциальной информации, — ключевые слова. Зачем использовать список ключевых слов? Вы можете получить статистические данные о том, сколько элементов соответствуют каждому ключевому слову. Это поможет быстро определить наиболее (и наименее) эффективные ключевые слова. Дополнительные сведения о статистике поиска см. в статье [Просмотр статистики ключевых слов для результатов поиска контента](https://docs.microsoft.com/microsoft-365/compliance/view-keyword-statistics-for-content-search).

Ключевые слова в каждой строке соединяются с помощью оператора OR в созданном поисковом запросе. В строке также можно использовать ключевую фразу (которая заключается в скобки).

Подробнее см. в статье [Запросы ключевых слов и условия поиска контента](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions).

### <a name="exampleusing-content-search-to-identify-email-addresses"></a>Пример: использование веб-части "Поиск контента" для определения адресов электронной почты

Адреса электронной почты считаются конфиденциальной информацией, связанной с субъектами данных. В этом простом примере показано, как использовать Поиск контента.

Запросы KQL и ключевые слова невозможно использовать одновременно. Применяйте эти средства по отдельности, чтобы уточнить запрос и определить ключевые слова, которые могут понадобиться в типах конфиденциальной информации.

### <a name="kql-query"></a>Запрос KQL

(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)

Примечания.

-   Вы можете использовать Поблизости для поиска близости.

-   К сожалению, язык KQL не поддерживает запросы с классом Regex (например, IdRef="адрес\_электронной_почты\_Regex")

### <a name="keywords"></a>Ключевые слова

Введите каждое ключевое слово в отдельной строке. Примеры ключевых слов:

-   адрес электронной почты;

-   почта;

-   контакт;

-   отправитель;

-   получатель;

-   копия;

-   СК.

В этом примере вы можете узнать, что ключевые слова использовать необязательно, так как они приводят к большому количеству ложных срабатываний.

### <a name="step-2--create-a-new-custom-sensitive-information-type"></a>Шаг 2. Создание пользовательского типа конфиденциальной информации

После того как вы используете запросы KQL и ключевые слова для определения конфиденциальной информации, создайте с их помощью пользовательские типы конфиденциальной информации. Во многих случаях вам потребуется усложнить типы конфиденциальной информации, чтобы обеспечить нужный уровень точности. Затем эти пользовательские типы конфиденциальной информации можно использовать в веб-части "Поиск контента", в политиках защиты от потери данных и других инструментах, а также в других запросах KQL.

Тип конфиденциальной информации рекомендуется создавать на основе имеющегося типа. Выполните действия, описанные выше в этой статье.

### <a name="example--create-a-new-sensitive-information-for-email-addresses"></a>Пример: создание типа конфиденциальной информации для адресов электронной почты 

Мы продолжим использовать адрес электронной почты для примера ввиду его простоты. В приведенной ниже таблице описаны изменения, которые рекомендуется внести в новый тип конфиденциальной информации для электронной почты.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Этап</strong></th>
<th align="left"><strong>Изменение</strong></th>
<th align="left"><strong>Пример синтаксиса XML</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">Установка свойства IdRef
<p>В элементе &lt;Entity&gt; измените элемент &lt;IdMatch&gt; таким образом, чтобы его свойство idRef равнялось уникальному значению. Это значение будет указывать на элемент, определяющий наше регулярное выражение для адресов электронной почты.</p></td>
<td align="left">IdRef=&quot;Regex_email_address&quot;</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left"><p>Атрибут расстояния</p>
<p>Мы начнем со значения patternProximity в элементе &lt;Entity&gt;, равного 300.</p></td>
<td align="left">patternsProximity=&quot;300&quot;</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left"><p>Уровень вероятности</p>
<p>Установите для свойства recommendedConfidence значение, которое, по вашему мнению, соответствует вероятности нахождения точного совпадения. Скорее всего, для получения точного результата потребуется проверка с использованием репрезентативного набора данных. В качестве начального параметра задайте значение 75.</p></td>
<td align="left"><p>recommendedConfidence=&quot;75&quot;&gt;</p>
<p>Полученный в результате код XML для первых трех элементов выглядит примерно так:</p>
<p>&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</p>
<p>&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</p>
<p>&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</p>
<p>&lt;Any minMatches=&quot;1&quot;&gt;</p>
<p>&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</p>
<p>&lt;/Any&gt;</p>
<p>&lt;/Pattern&gt;</p>
<p>&lt;/Entity&gt;</p></td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left"><p>Элемент Regex</p>
<p>Сразу после элементов &lt;Entity&gt; добавьте новый элемент &lt;Regex&gt;, определяющий регулярное выражение, которое используется для определения адресов электронной почты.</p></td>
<td align="left">&lt;Regex id=&quot;Regex_email_address&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left"><p>Ключевые слова</p>
<p>После элемента &lt;Regex&gt; добавьте новый элемент &lt;Keyword&gt;, который определяет список ключевых слов, связанных с адресами электронной почты. Убедитесь, что значение идентификатора для элемента &lt;Keyword&gt; соответствует значению &lt;Match idRef&gt; в элементе &lt;Entity&gt;&lt;Pattern&gt;. При необходимости вы можете добавить собственные ключевые слова.</p>
<p>Ключевые слова необязательно включать в тип конфиденциальной информации, связанный с электронной почтой. Эти ключевые слова приведены для примера.</p></td>
<td align="left"><p>&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</p>
<p>&lt;Group&gt;</p>
<p>&lt;Term&gt;электронная почта&lt;/Term&gt;</p>
<p>&lt;Term&gt;адрес электронной почты&lt;/Term&gt;</p>
<p>&lt;Term&gt;контакт&lt;/Term&gt;</p>
<p>&lt;/Group&gt;</p>
<p>&lt;/Keyword&gt;</p></td>
</tr>
<tr class="even">
<td align="left">6</td>
<td align="left"><p>Элемент LocalizedStrings</p>
<p>Убедитесь, что элемент &lt;LocalizedStrings&gt;&lt;Resource&gt; включает уникальное имя, определяющее ваш тип конфиденциальной информации.</p></td>
<td align="left"><p>&lt;LocalizedStrings&gt;</p>
<p>&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</p>
<p>&lt;Name default=&quot;true&quot; langcode=&quot;ru-ru&quot;&gt;Адрес электронной почты&lt;/Name&gt;</p>
<p>&lt;Description default=&quot;true&quot; langcode=&quot;ru-ru&quot;&gt;Обнаружение адресов электронной почты.&lt;/Description&gt;</p>
<p>&lt;/Resource&gt;</p>
<p>&lt;/LocalizedStrings&gt;</p></td>
</tr>
</tbody>
</table>

## <a name="create-a-new-sensitive-information-type-with-example-powershell-and-xml-file--contoso-customer-number"></a>Создание типа конфиденциальной информации с примером XML-файла с помощью PowerShell — номер клиента Contoso

Организация Contoso использует номер клиента Contoso (CCN — Contoso Customer Number) для идентификации каждого клиента в базе данных. Вот из каких компонентов состоит номер CCN.

-   Две цифры представляют собой год создания записи. Организацию Contoso основали в 2002 году, поэтому самое раннее возможное значение составляет 02.

-   Три цифры представляют собой партнерское агентство, создавшее запись. Возможные значения — от 000 до 999.

-   Символ "альфа" представляет собой сферу деятельности. Возможные значения: a–z без учета регистра.

-   Четырехзначный серийный номер. Возможные значения — от 0000 до 9999.

Примеры номеров CCN:

> 15080P9562;
>
> 14040O1119;
>
> 15020J8317;
>
> 14050E2330;
>
> 16050E2166;
>
> 17040O1118.

Организация Contoso всегда ссылается на клиентов, используя номер CCN во внутренних и внешних сообщениях, документах и т. д. Ей требуется создать тип конфиденциальной информации для обнаружения использования номеров CCN, чтобы получить возможность применить защиту к использованию этой разновидности персональных данных.

### <a name="create-a-new-sensitive-information-type-for-contoso-customer-number"></a>Создание типа конфиденциальной информации для номера клиента Contoso

<table>
<thead>
<tr class="header">
<th align="left"><strong>Шаг</strong></th>
<th align="left"><strong>Действие </strong></th>
<th align="left"><strong>Результат</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">Contoso использует PowerShell и Поиск контента для поиска документов, которые соответствуют примеру набора номеров CCN.</td>
<td align="left">

<p>#Подключитесь к Центру безопасности и соответствия требованиям</p>
<p>$adminUser = &quot;alland@contoso.com&quot;</p>
<p>Connect-IPPSSession -UserPrincipalName $adminUser</p>
<p>#Create &amp; start search for sample data</p>
<p>$searchName = &quot;Sample Customer Information Search&quot;</p>
<p>$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</p>
<p>New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</p>
<p>Start-ComplianceSearch -Identity $searchName</p>
</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left">Организация Contoso анализирует результаты. При каждом применении номера CCN использовалась дата в формате, принятом в ЕС, а также одно из приведенных справа ключевых слов с параметром близости в 300 символов.</td>
<td align="left">номер клиента, н-р клиента, № клиента, №клиента, клиент Contoso</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left">Организация Contoso разработала приведенный справа шаблон регулярного выражения (RegEx) для определения своих номеров CCN.</td>
<td align="left">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left">Организация Contoso разработала приведенный справа шаблон регулярного выражения (RegEx) для определения дат в форматах, которые приняты в ЕС и используются в ее различных дочерних подразделениях.</td>
<td align="left">
````xml
(0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?|‌ feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|‌ apr(ile|il)?|abr(il)?|avril|may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|‌ oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?|nov(ember|iembre|embre|embro)?|dec(ember)?|‌ dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}
````
</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left">Организация Contoso создала три уникальных GUID с помощью PowerShell.</td>
<td align="left"><p>#Generate a unique GUID for RulePack Id, Publisher Id, and Entity Id</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p></td>
</tr>
<tr class="even">
<td align="left">6</td>
<td align="left">Организация Contoso определяет приведенные справа параметры для соответствующего правила в отношении типа конфиденциальных данных.</td>
<td align="left"><p>Имя: номер клиента Contoso (CCN)</p>
<p>Описание: номер клиента Contoso (CCN), который используется для поиска дополнительных ключевых слов и даты в формате, принятом в ЕС</p></td>
</tr>
<tr class="odd">
<td align="left">7</td>
<td align="left">Организация Contoso создает XML-файл для нового типа конфиденциальной информации с целью обнаружения номера клиента Contoso (CCN) и сохраняет его в локальной файловой системе как C:\Scripts\ContosoCCN.xml в кодировке UTF-8.</td>
<td align="left">См. XML-файл под этой таблицей.</td>
</tr>
<tr class="even">
<td align="left">8</td>
<td align="left">Организация Contoso создает пользовательский тип конфиденциальной информации с помощью PowerShell, как показано справа.</td>
<td align="left"><p>#Подключитесь к Центру безопасности и соответствия требованиям</p>
<p>$adminUser = &quot;alland@contoso.com&quot;</p>
<p>Connect-IPPSSession -UserPrincipalName $adminUser</p>
<p>#Create new Sensitive Information Type</p>
<p>New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</p></td>
</tr>
</tbody>
</table>

### <a name="example-xml-file-for-the-new-sensitive-information-type-step-7"></a>Пример XML-файла для нового типа конфиденциальной информации (шаг 7)
```xml
\<?xml version="1.0" encoding="utf-8"?\>

\<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce"\>

\<RulePack id="130ae63b-a91e-4a12-9e02-a90e36a83d7f"\>

\<Version major="1" minor="0" build="0" revision="0" /\>

\<Publisher id="47148982-defd-42a1-890a-7b9472099f1f" /\>

\<Details defaultLangCode="en"\>

\<LocalizedDetails langcode="en"\>

\<PublisherName\>Contoso Ltd.\</PublisherName\>

\<Name\>Contoso Rule Package\</Name\>

\<Description\>Defines Contoso's custom set of classification rules\</Description\>

\</LocalizedDetails\>

\</Details\>

\</RulePack\>

\<Rules\>

\<!-- Contoso Customer Number (CCN) --\>

\<Entity id="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b" patternsProximity="300" recommendedConfidence="85"\>

\<Pattern confidenceLevel="85"\>

\<IdMatch idRef="Regex\_contoso\_ccn" /\>

\<Match idRef="Keyword\_contoso\_ccn" /\>

\<Match idRef="Regex\_eu\_date" /\>

\</Pattern\>

\</Entity\>

\<Regex id="Regex\_contoso\_ccn"\>[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}\</Regex\>

\<Keyword id="Keyword\_contoso\_ccn"\>

\<Group matchStyle="word"\>

\<Term caseSensitive="false"\>customer number\</Term\>

\<Term caseSensitive="false"\>customer no\</Term\>

\<Term caseSensitive="false"\>customer \#\</Term\>

\<Term caseSensitive="false"\>customer\#\</Term\>

\<Term caseSensitive="false"\>Contoso customer\</Term\>

\</Group\>

\</Keyword\>

\<Regex id="Regex\_eu\_date"\> (0?[1-9]|[12][0-9]|3[0-1])[\\/-](0?[1-9]|1[0-2]|j\\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?‌ |feb(ruary|ruari|rero|braio|ruar|br)?|f\\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\\x00e4rz|maart‌|apr(ile|il)?|abr(il)?|avril‌ |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?‌ |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\\x00e9c(embre)?)[ \\/-](19|20)?[0-9]{2}\</Regex\>

\<LocalizedStrings\>

\<Resource idRef="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b"\>

\<Name default="true" langcode="en-us"\>Contoso Customer Number (CCN)\</Name\>

\<Description default="true" langcode="en-us"\>Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date\</Description\>

\</Resource\>

\</LocalizedStrings\>

\</Rules\>

\</RulePackage\>
```
