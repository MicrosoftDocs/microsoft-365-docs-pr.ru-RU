---
title: Прекращение поддержки устаревших средств обнаружения электронных данных
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: In-Place eDiscovery и In-Place удержания (и соответствующие cmdlets PowerShell) в Exchange Online будут отменены в первой половине 2020 г. Кроме Search-Mailbox и Advanced eDiscovery 1.0, в течение того же периода времени также неактуален.
ms.openlocfilehash: a40cc67b29e33d61d6750792f6a773622a73f678
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750882"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Прекращение поддержки устаревших средств обнаружения электронных данных

> [!IMPORTANT]
> Корпорация Майкрософт оценивает состояние системы здравоохранения, и мы понимаем, как это влияет на наших клиентов. Мы хотим быть партнерами и ответственными глобальными гражданами. Чтобы облегчить одну из многих проблем, с которыми вы столкнулись, мы собираемся отложить запланированное уволение устаревших средств eDiscovery, описанных в этой статье, на три месяца. **Обновленные даты выхода из системы приведены ниже.**

На протяжении многих лет корпорация Майкрософт предоставляла средства eDiscovery, которые обеспечивают поиск, предварительный просмотр и экспорт содержимого электронной почты из Exchange Online. Однако эти средства больше не предоставляют эффективный способ поиска контента, не относящемся к Exchange, в других службах Microsoft 365, таких как SharePoint Online и группы Microsoft 365. Для решения этой проблемы корпорация Майкрософт предлагает другие средства eDiscovery, которые помогают искать широкий спектр контента Microsoft 365. Мы работаем над тем, чтобы включить самые современные и мощные функции eDiscovery в Центр соответствия требованиям [Microsoft 365.](https://compliance.microsoft.com) Это позволяет организациям отвечать на юридические, внутренние и другие запросы документов на содержимое во многих службах Microsoft 365, включая Exchange Online.

В результате этой новой и улучшенной функции eDiscovery в Центре соответствия требованиям Microsoft 365 мы удаляем следующие функции и функции, связанные с eDiscovery, связанные с поиском содержимого электронной почты в Exchange Online и Microsoft 365:

- [EDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) и [in-Place Holds](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) в Центре администрирования Exchange.

- The Exchange Online PowerShell cmdlets that support In-Place eDiscovery and In-Place Holds (these cmdlets are collectively identified as **-MailboxSearch* cmdlets). К ним относятся следующие cmdlets:

  - [New-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > The [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch) and [Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch) cmdlets will be available after the other **-MailboxSearch***_ cmdlets are retired so that you can use them to help in your transition to other eDiscovery and hold tools. Однако после определенной даты (приведенной ниже) служба поддержки Майкрософт больше не будет поддерживать эти два cmdlet.

- The [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox) cmdlet in Exchange Online PowerShell.

- Следующие операции в API веб-служб Exchange:

   - [GetSearchableMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced eDiscovery 1.0](office-365-advanced-ediscovery.md)— первая версия Advanced eDiscovery, доступ к которой можно получить с помощью основного дела eDiscovery в Центре безопасности & соответствия требованиям Office 365. Отставку Advanced eDiscovery 1.0 не влияет на возможность создания основных дел eDiscovery и управления ими.

> [!NOTE]
> Функции eDiscovery, которые больше не применяются, применимы только к облачным версиям Microsoft 365 и Office 365. Функции eDiscovery в локальной версии Exchange и SharePoint будут по-прежнему поддерживаться до дальнейшего уведомления.

В следующих разделах этой статьи представлены рекомендации по каждой удаляемой функции. Эти сведения, включая временные шкалы и альтернативные средства, которые можно использовать вместо средства для выхода из использования.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place eDiscovery и In-Place в Центре администрирования Exchange 

По первоначальному сообщению от 1 июля 2017 г. функция In-Place eDiscovery & Hold в Центре администрирования Exchange (EAC) больше не используется. Страница In-Place с удержанием электронных & в EAC позволяет искать, удерживать и экспортировать контент из Exchange Online. In-Place eDiscovery также позволит вам копировать результаты поиска в почтовый ящик обнаружения, чтобы вы или другие менеджеры по обнаружению электронных данных могли просмотреть контент и сделать его доступным для юридических, нормативных и общедоступных запросов.

Так как все эти возможности (кроме копирования результатов поиска в почтовый ящик обнаружения) теперь доступны в средствах поиска контента, обнаружения электронных данных и Advanced eDiscovery в Центре соответствия требованиям [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) (с улучшенными функциональными возможностями, надежностью и поддержкой широкого спектра служб Microsoft 365), рекомендуется начать использовать эти средства как можно скорее. В таблице ниже перечислены средства, которые можно использовать вместо In-Place eDiscovery и In-Place удержания.

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Организации Office 365 и Microsoft 365 корпоративный

- Организации Office 365 и Microsoft 365 для образования

- Организации Office 365 и Microsoft 365 для государственных организаций; это относится к GCC, GCC High и DoD

- Office 365 Germany

### <a name="timeline-for-retirement"></a>Временная шкала для выхода из нее

- 1 июля 2020 г. Вы не сможете создавать новые поисковые запросы и запросы на удерживаемую среду, но вы по-прежнему можете запускать, редактировать и удалять существующие поисковые запросы на свой риск. Служба поддержки Майкрософт больше не In-Place eDiscovery & в EAC.

- 1 октября 2020 г. функция In-Place eDiscovery & в EAC будет помещена в режим только для чтения. Это означает, что вы сможете удалять только существующие запросы на поиск и удерживая их.

### <a name="alternative-tools"></a>Альтернативные средства

В следующей таблице описываются другие средства, которые можно использовать для замены существующих функций, которые больше не используются.

<table>
<thead>
<tr class="header">
<th>функциональность.</th>
<th>Альтернативное средство</th>
<th>Примечания</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Поиск, экспорт и удержание для юридических целей</td>
<td>Основные дела eDiscovery в Центре соответствия требованиям Microsoft 365 </td>
<td><p>Использование возможностей основных дел eDiscovery обеспечивает функциональный четность для In-Place eDiscovery и In-Place. Эта кнопка предоставляет доступ ко следующим командам:</p>
<ul>
<li>
<p>Масштабы поиска до миллионов местоположений</p>
</li>
<li>
<p>Высокая надежность поиска, экспорта и помещения контента на удержание</p>
</li>
<li>
<p>Поиск контента в Exchange Online, SharePoint Online, OneDrive для бизнеса, Skype для бизнеса, Microsoft Teams, групп Yammer, групп Microsoft 365 и другого контента, хранящемся в приложениях Office 365</p></li></ul>
</td>
</tr>
<tr class="even">
<td>Удержание для целей хранения</td>
<td>Политики хранения в Центре соответствия требованиям Microsoft 365</td>
<td><p>Политики хранения можно использовать для хранения контента и при желании удаления его по истечении срока хранения. Другие возможности:</p>
<ul>
<li>
<p>Применение политик для всей организации </p>
</li><li>
<p>Применение политик к определенным расположениям контента, таким как Exchange Online, SharePoint Online, OneDrive для бизнеса, Skype для бизнеса, Microsoft Teams и группы Office 365</p></li>
<li>
<p>Применение политик к определенным пользователям</p></li></ul>
<p>Дополнительные сведения <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies">см. в сведениях о политиках хранения и метах хранения.</a></td>
</tr>
<tr class="odd">
<td>Копирование результатов поиска электронной почты в почтовый ящик обнаружения для проверки</td><td>Наборы для проверки в Advanced eDiscovery 2.0</td>
<td><p>Просмотр контента в Microsoft 365 никогда не был проще. Наборы для проверки имеют множество отличных возможностей, которые помогают сократить время и данные, необходимые для проверки, в том числе:</p>
<ul>
<li><p>Выполнение запросов быстрого поиска и фильтрация содержимого в наборе для проверки</p></li>
<li><p>Анализ контента в наборе для проверки; это включает потоки электронной почты, обнаружение практически дублирующихся сообщений, анализ тем и прогнозирование кодирования</p></li>
<li><p>Добавление тегов к документам в наборе для проверки</p></li>
<li><p>Предложения по тегированию для определения содержимого адвокатской привилегии клиента</p></li></ul>
<p>Дополнительные сведения см. в статье <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Обзор решения Advanced eDiscovery в Microsoft 365</a>.</p>
<p>
<p>Кроме того, вы можете экспортировать результаты поиска в PST-файлы, а затем импортировать PST-файлы в почтовый ящик обнаружения с помощью службы импорта Microsoft 365. Пошаговая инструкция по импорту PST-файлов в <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">Office 365:</a>с помощью отправки по сети.
</tr>
<tr class=even>
  <td>Копирование сообщений из одного почтового ящика в другой</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Назначение разрешений почтовому ящику</a></td>
  <td>Чтобы предоставить пользователю доступ к электронной почте другого пользователя (например, когда сотрудник покидает вашу организацию и вам необходимо предоставить другому пользователю доступ к электронной почте бывшего сотрудника), рекомендуется назначить ему разрешения на доступ к почтовому ящику бывшего сотрудника. Поэтому вместо копирования элементов почтового ящика в другой почтовый ящик пользователя или общий почтовый ящик просто назначьте пользователю разрешения на доступ к исходным почтовым ящикам.</td>
  
  </tr>
<tr class="odd">
<td>Восстановление элементов из папки "Элементы с функцией восстановления"</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>Вы можете восстановить окончательно удаленные элементы <i></i> (также известные как элементы с возможностью восстановления) в почтовых ящиках, если срок хранения удаленных элементов для элемента не истек. Дополнительные сведения см. в папке "Элементы с <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">восстановления" в Exchange Online.</a></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>FAQs about In-Place eDiscovery and In-Place Holds

_ Я использую функцию копирования результатов поиска In-Place обнаружения электронных & в EAC для копирования результатов поиска в почтовый ящик обнаружения для проверки *адвокатами. Какие параметры у меня есть?**

Репликацию этой функции можно реплицировать двумя способами. Во-первых, необходимо использовать [наборы для проверки в Advanced eDiscovery 2.0.](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set) Наборы для проверки имеют многие из тех же возможностей, которые вы видите в традиционном средстве проверки, например быстрый поиск документов, добавление тегов, потоки электронной почты, почти дублирование групп, анализ тем и прогнозирование кодирования. Если вы все еще хотите использовать почтовые ящики обнаружения для проверки, второй вариант — экспортировать результаты поиска в PST-файлы, а затем импортировать PST-файлы в почтовый ящик обнаружения с помощью функции импорта [PST-файлов](use-network-upload-to-import-pst-files.md) в Центре соответствия требованиям Майкрософт.

**Как управлять расположениями контента (например, почтовыми ящиками или сайтами), которые менеджер по обнаружению электронных сообщений может искать с помощью новых средств?**

Центр соответствия требованиям Microsoft 365 также использует границы соответствия требованиям для контроля того, какие расположения контента может искать менеджер по обнаружению электронных данных. [](set-up-compliance-boundaries.md) Границы соответствия требованиям полезны в правительственных организациях, которые должны оставаться в границах агентства, или в нескольких национальных корпорациях, которые должны соблюдать географические доски.

**Как переместить текущие поисковые запросы и запросы в Центр соответствия требованиям Microsoft 365?**

С помощью PowerShell можно In-Place поиск и удерживаемую eDiscovery из EAC. Инструкции см. в инструкциях по переносу поисковых запросов и удерживаний из EAC в Центр соответствия требованиям [Microsoft 365.](https://go.microsoft.com/fwlink/?linkid=2114224)

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch cmdlets

По первоначальному уведомлению, объявленному 1 июля 2017 г. в Центре администрирования Exchange, функции удержания In-Place eDiscovery & и соответствующие cmdlets **\* -MailboxSearch** отошедали. Эти cmdlets предоставляют пользователям возможность поиска, удержания и экспорта содержимого почтовых ящиков для юридических, нормативных и общедоступных запросов.

Так как эти возможности теперь доступны в Центре соответствия требованиям [<span class="underline">Microsoft 365</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) и PowerShell Центра безопасности и соответствия требованиям Office 36 & 5 с улучшенной производительностью и масштабируемостью, следует использовать эти улучшенные команды. These cmdlets include [<span class="underline"> \* -ComplianceCase</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase), [<span class="underline"> \* -ComplianceSearch</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch), [<span class="underline"> \* -CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy), [<span class="underline"> \* -CaseHoldRule</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule), and [<span class="underline"> \* -ComplianceSearchAction</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction).

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Организации Office 365 и Microsoft 365 корпоративный

- Организации Office 365 и Microsoft 365 для образования

- Организации Office 365 и Microsoft 365 для государственных организаций; это относится к GCC, GCC High и DoD

- Office 365 Germany

### <a name="timeline"></a>Временная шкала

- 1 июля 2020 г.: вы не сможете использовать **New-MailboxSearch** для создания новых поисковых запросов In-Place eDiscovery и In-Place Holds, но вы по-прежнему можете использовать их для запуска, изменения и удаления существующих поисковых запросов и справок на свой риск. Служба поддержки Майкрософт больше не будет предоставлять помощь по таким типам поиска и оказания услуг.

- 1 октября 2020 г. Как было сказано ранее, функции In-Place eDiscovery & Holds в EAC будут размещены в режиме только для чтения. Это также означает, что вы не сможете использовать **new-MailboxSearch,** **Start-MailboxSearch** или **Set-MailboxSearch.** Вы сможете получать и удалять только существующие поисковые запросы и запросы.

### <a name="alternative-tools"></a>Альтернативные средства

В следующей таблице описываются другие средства, которые можно использовать для замены существующих функций, которые больше не используются.

<table>
<thead>
<tr class="header">
<th>функциональность.</th>
<th>Альтернативные средства</th>
<th>Примечания</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Поиск и экспорт</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Для поиска и экспорта контента можно совместно работать с помощью cmdlets ComplianceSearch и ComplianceSearchAction. Вы можете создать новый поиск и просмотреть оценку поиска с помощью <strong>новых,</strong> <strong>Get-</strong>и <strong>Start-ComplianceSearch-cmdlets.</strong> Затем вы можете экспортировать результаты поиска с помощью cmdlet <strong>New-ComplianceSearchAction.</strong> Вам по-прежнему придется использовать основное средство eDiscovery в Центре соответствия требованиям Microsoft 365, чтобы скачать эти результаты поиска на локальный компьютер.</p>
<p>
<p><strong>Примечание.</strong> Если вы используете эти cmdlets для создания поисковых запросов, которые не связаны с основным <strong></strong> делом eDiscovery, эти поисковые запросы будут расположены на странице "Поиск контента" в Центре соответствия требованиям Microsoft 365.</p></td>
</tr>
<tr class="even">
<td>Удержание содержимого в почтовом ящике</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>В Центре соответствия требованиям Microsoft 365 необходимо связывать с регистром соответствия требованиям. Сначала создайте дело соответствия требованиям, а затем создайте CaseHoldPolicy и CaseHoldRule.</p>
<p><strong>Примечание.</strong> Создание CaseHoldPolicy без создания CaseHoldRule сделает удержание неоперабельным, пока Не будет создан CaseHoldRule и не связан с CaseHoldPolicy. Дополнительные сведения см. в документации по cmdlet.</p></td>
</tr>
<tr class="odd">
<td>Копирование результатов поиска в почтовый ящик обнаружения</td>
<td>Нет</td>
<td>Прямой замены этой функции нет, так как она не предоставляет доступ ко всем службам Microsoft 365. Альтернативные решения см. в следующих вопросы и вопросы.</td>
</tr>
  <tr class=even>
  <td>Копирование сообщений из одного почтового ящика в другой</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Назначение разрешений почтовому ящику</a></td>
  <td>Чтобы предоставить пользователю доступ к электронной почте другого пользователя (например, когда сотрудник покидает вашу организацию и вам необходимо предоставить другому пользователю доступ к электронной почте бывшего сотрудника), рекомендуется назначить ему разрешения на доступ к почтовому ящику бывшего сотрудника. Поэтому вместо копирования элементов почтового ящика в другой почтовый ящик пользователя или общий почтовый ящик просто назначьте пользователю разрешения на доступ к исходным почтовым ящикам.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>FaQs about ***-MailboxSearch** cmdlets

**Мы используем поиск по копированию для экспорта сообщений электронной почты или мгновенных сообщений для других расследований eDiscovery и юридических расследований. Какие другие параметры у нас есть после с выхода из них?**

API [<span class="underline">Microsoft Graph</span>](https://developer.microsoft.com/en-us/graph) предоставляют ряд методов для извлечения данных для анализа и других целей, которые гораздо более устойчивы и масштабируемы, чем при использовании с помощью cmdlets **\* -MailboxSearch.**

**Как перенести поиск и удерживание в Центр соответствия требованиям Microsoft 365?**

С помощью скрипта PowerShell можно In-Place поиск и удерживаемую возможность eDiscovery из Центра администрирования Exchange. Дополнительные сведения см. в записях миграции старых поисковых запросов и запросов на поиск при обнаружении электронных данных в Центре соответствия требованиям [Microsoft 365.](migrate-legacy-eDiscovery-searches-and-holds.md)

**После удаления из них я по-прежнему могу удалить или получить поиск?**

Да, хотя мы удаляем возможность создания и изменения поиска, вы по-прежнему сможете использовать **Get-MailboxSearch** и **Remove-MailboxSearch** до дальнейшего уведомления. Тем не менее, после даты выхода из службы поддержки Майкрософт вы будете сами себе на риск, и служба поддержки Майкрософт больше не сможет предоставить помощь.

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox

The **Search-Mailbox** cmdlet in Exchange Online PowerShell is being retired as originally announced in a warning in the cmdlet output starting back in 2018. Изначально **для поиска** в почтовом ящике пользователя и очистки вредоносного содержимого использовался его почтовый ящик. Для поиска и очистки контента рекомендуется использовать в PowerShell Центра безопасности и соответствия требованиям Office 36 & 5 с помощью cmdlets **New-ComplianceSearch** и **New-ComplianceSearchAction.** Встроенные функции безопасности [<span class="underline">Microsoft 365</span>](https://docs.microsoft.com/microsoft-365/security/) обеспечивают надежную защиту от угроз для электронной почты и многих других служб Майкрософт.

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Организации Office 365 и Microsoft 365 корпоративный

- Организации Office 365 и Microsoft 365 для образования

- Организации Office 365 и Microsoft 365 для государственных организаций; это относится к GCC, GCC High и DoD

- Office 365 Germany

### <a name="timeline"></a>Временная шкала

-  1 июля 2020  г.: больше не будет доступен и служба поддержки Майкрософт больше не будет предоставлять помощь.

### <a name="alternative-tools"></a>Альтернативные средства

В следующей таблице описываются другие средства, которые можно использовать для замены существующих функций, которые больше не используются.

<table>
<thead>
<tr class="header">
<th>функциональность.</th>
<th>Альтернативные средства</th>
<th>Примечания</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Поиск в почтовом ящике</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>Для поиска и экспорта контента можно совместно работать с помощью cmdlets ComplianceSearch и ComplianceSearchAction. Вы можете создать новый поиск и просмотреть оценку поиска с помощью <strong>новых,</strong> <strong>Get-</strong>и <strong>Start-ComplianceSearch-cmdlets.</strong> Затем можно использовать команду <strong>New-ComplianceSearchAction -Export</strong> для экспорта результатов поиска. Вам по-прежнему придется использовать основное средство eDiscovery в Центре соответствия требованиям Microsoft 365, чтобы скачать эти результаты поиска на локальный компьютер.</p></p>
</td>
</tr>
<tr class="even">
<td>Удаление массовых рассылок электронной почты из почтового ящика</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Настройка политики архивации и удаления для почтовых ящиков</span></a></p>
<p></p></td>
<td><p>Администраторы могут создать политику архивации и удаления, которая автоматически перемещает элементы в архивный почтовый ящик пользователя и автоматически удаляет элементы из почтового ящика.</p>
</td>
</tr>
<tr class="even">
<td>Копирование результатов поиска в почтовый ящик обнаружения</td>
<td> </td>
<td>Прямой замены этой функции нет, так как она не предоставляет доступ ко всем службам Microsoft 365. Альтернативные решения см. в разделе "FaQs in the <strong>*-MailboxSearch cmdlets".</strong> </td>
</tr>
<tr class=odd>
  <td>Копирование сообщений из одного почтового ящика в другой</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Назначение разрешений почтовому ящику</a></td>
  <td>Чтобы предоставить пользователю доступ к электронной почте другого пользователя (например, когда сотрудник покидает вашу организацию и вам необходимо предоставить другому пользователю доступ к электронной почте бывшего сотрудника), рекомендуется назначить ему разрешения на доступ к почтовому ящику бывшего сотрудника. Поэтому вместо копирования элементов почтового ящика в другой почтовый ящик пользователя или общий почтовый ящик просто назначьте пользователю разрешения на доступ к исходным почтовым ящикам.</td>
</tr>
<tr class=even>
  <td>Очистка сообщений из почтового ящика</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>Для поиска и очистки контента совместно работают с помощью cmdlets ComplianceSearch и ComplianceSearchAction. Вы можете создать и запустить поиск с помощью командлетов <strong>New-ComplianceSearch</strong> и <strong>New-ComplianceSearch,</strong> а затем очистить контент с помощью команды <strong>New-ComplianceSearchAction -Purge -PurgeType.</strong> Дополнительные сведения <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">см. в поиске и удалении сообщений.</span></a></p>
</td>
</tr>
<tr class="odd"> 
<td>Очистка сообщений из почтового ящика</td>
<td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Назначение разрешений почтовому ящику</a></td>
<td>Чтобы очистить сообщения из почтового ящика, назначьте администратору разрешения на доступ к почтовому ящику сотрудника. Сообщения можно удалять и перезасылать при необходимости, пользуясь встроенными возможностями поиска и просмотра в Outlook.</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Операции API веб-служб Exchange

Эти операции в API веб-служб Exchange используются функцией In-Place eDiscovery & Holds в Центре администрирования Exchange и соответствующими cmdlets **\* -MailboxSearch** в Exchange Online PowerShell. Кроме того, они будут отменены в рамках выхода других устаревших средств eDiscovery.

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Организации Office 365 и Microsoft 365 корпоративный

- Организации Office 365 и Microsoft 365 для образования

- Организации Office 365 и Microsoft 365 для государственных организаций; это относится к GCC, GCC High и DoD

- Office 365 Germany

### <a name="timeline"></a>Временная шкала

- 1 июля 2020 г.: операции GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes и GetHoldOnMailboxes будут недоступны, и служба поддержки Майкрософт больше не будет предоставлять помощь.

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery 1.0

Advanced eDiscovery версии 1.0, которая является версией Advanced eDiscovery, доступной в случае основного eDiscovery, нажав кнопку "Переключиться на **Advanced eDiscovery",** больше не будет. Его функциональность заменена новым [решением Advanced eDiscovery](https://aka.ms/edisco) в Центре соответствия требованиям Microsoft 365.

Чтобы определить, использует ли ваша организация Advanced eDiscovery 1.0:

1. Перейдите в [Центр безопасности и соответствия & Office 365.](https://protection.office.com)

2. В левой области навигации Центра безопасности & соответствия требованиям щелкните **eDiscovery > eDiscovery** и откройте дело основного eDiscovery.

3. Если вы видите кнопку "Переключиться на **Advanced eDiscovery",** нажмите ее, чтобы перейти к версии 1.0 Advanced eDiscovery, которая больше не существует. Возможность создания дел и управления ими в Core eDiscovery не затрагивается. Больше не будет возможности добавлять и анализировать данные дела в Advanced eDiscovery 1.0 (щелкнув "Переключиться на **advanced eDiscovery").**

Новое решение Advanced eDiscovery в Microsoft 365 (также известное как *Advanced eDiscovery 2.0)* предоставляет все возможности исходного решения, но теперь включает основанный на хранителях подход к идентификации контента в других службах Microsoft 365, сбору этого контента и его добавлению в набор для проверки, в котором проверяющие могут использовать быстрые поисковые запросы, теги и функции аналитики для сбора релевантного документа. Advanced eDiscovery теперь включает улучшенную обработку и просмотр файлов как от Майкрософт, так [](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) и для других типов файлов. Здесь вы можете найти полный список типов файлов, а также поддерживаемые поля [метаданных.](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery) Кроме того, новое решение Advanced eDiscovery предоставляет мощную функцию управления хранением данных, которая позволяет применять хранение к контенту в различных службах, уведомлять пользователей об этом и отслеживать ответы хранителя в рамках дела Advanced eDiscovery.

Чтобы получить доступ к Advanced eDiscovery 2.0:

1. Перейдите в [Центр соответствия требованиям Microsoft 365.](https://compliance.microsoft.com)

2. В левой области навигации Центра соответствия требованиям Microsoft 365 щелкните "Показать **все"** и выберите "> **Advanced".**

В настоящее время рекомендуется приступить к переходу рабочего процесса eDiscovery на новые функции Advanced eDiscovery. При необходимости вы можете архивировать дела Advanced eDiscovery 1.0, экспортировать содержимое и хранить его в автономном режиме. Хотя вы по-прежнему сможете получить доступ к Advanced eDiscovery 1.0 в существующих случаях до 31 декабря 2020 г., служба поддержки Майкрософт не будет предоставлять поддержку после 1 октября 2020 г. Дополнительные сведения см. на следующей временной шкале.

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Организации Office 365 и Microsoft 365 корпоративный

- Организации Office 365 и Microsoft 365 для образования

- Организации Office 365 и Microsoft 365 для государственных организаций; это относится к GCC, GCC High и DoD

- Office 365 Germany

### <a name="timeline"></a>Временная шкала

- 1 июля 2020 г.: вы не сможете создать новые дела Advanced eDiscovery 1.0.

- 1 октября 2020 г.: вы не сможете добавлять новые данные (подготовка результатов поиска для Advanced eDiscovery) в любые дела. Вы сможете продолжать работать с данными в существующих случаях на свой собственный риск. Служба поддержки Майкрософт больше не будет предоставлять помощь. 

- 31 декабря 2020 г. Вы не сможете получить доступ к делам Advanced eDiscovery 1.0.

### <a name="alternative-tools"></a>Альтернативные средства

Решение [Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) в Центре соответствия требованиям Microsoft 365.
